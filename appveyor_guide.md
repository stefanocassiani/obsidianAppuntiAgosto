# Guida AppVeyor per Sviluppatori

## Setup Iniziale

### 1. Collegare il Repository
1. Vai su [AppVeyor.com](https://www.appveyor.com)
2. Accedi con GitHub/BitBucket
3. Clicca "New Project" e seleziona il tuo repository
4. AppVeyor rileverà automaticamente il tipo di progetto

### 2. File di Configurazione: `appveyor.yml`

Crea questo file nella root del tuo progetto:

```yaml
# Versione di AppVeyor
version: 1.0.{build}

# Ambiente di build
image: Visual Studio 2022

# Configurazioni da testare
configuration:
  - Debug
  - Release

# Piattaforme da testare
platform:
  - x64
  - x86

# Clonare solo l'ultimo commit per velocità
clone_depth: 1

# Script prima del build
before_build:
  - nuget restore

# Comandi di build
build:
  project: MyApp.sln
  verbosity: minimal

# Test automatici
test_script:
  - dotnet test

# Cosa fare dopo il build di successo
after_build:
  - 7z a MyApp-v%APPVEYOR_BUILD_VERSION%.zip %APPVEYOR_BUILD_FOLDER%\bin\Release\*

# Artefatti da conservare
artifacts:
  - path: '*.zip'
    name: MyApp

# Deploy su GitHub Releases (opzionale)
deploy:
  - provider: GitHub
    auth_token:
      secure: YOUR_ENCRYPTED_TOKEN
    artifact: MyApp
    on:
      branch: master
      appveyor_repo_tag: true
```

## Esempi per Diversi Tipi di Progetto

### Progetto C# .NET

```yaml
version: 1.0.{build}
image: Visual Studio 2022

before_build:
  - dotnet restore

build_script:
  - dotnet build --configuration Release

test_script:
  - dotnet test --configuration Release --no-build

artifacts:
  - path: 'src\MyApp\bin\Release\net6.0\*'
    name: MyApp-Binaries
```

### Progetto Node.js

```yaml
version: 1.0.{build}
image: Visual Studio 2022

install:
  - node --version
  - npm --version
  - npm install

build_script:
  - npm run build

test_script:
  - npm test

artifacts:
  - path: 'dist\*'
    name: MyApp-Web
```

### Progetto Python

```yaml
version: 1.0.{build}
image: Visual Studio 2022

install:
  - python --version
  - pip install -r requirements.txt

build_script:
  - python setup.py build

test_script:
  - python -m pytest tests/

artifacts:
  - path: 'dist\*'
    name: MyApp-Python
```

## Funzionalità Avanzate

### 1. Build Matrix (Test su Multiple Configurazioni)

```yaml
environment:
  matrix:
    - PYTHON_VERSION: "3.8"
      PYTHON_ARCH: "64"
    - PYTHON_VERSION: "3.9"
      PYTHON_ARCH: "64"
    - PYTHON_VERSION: "3.10"
      PYTHON_ARCH: "64"

install:
  - "SET PATH=C:\\Python%PYTHON_VERSION%-x%PYTHON_ARCH%\\;%PATH%"
  - pip install -r requirements.txt
```

### 2. Notifiche

```yaml
notifications:
  - provider: Email
    to:
      - developer@example.com
    on_build_success: false
    on_build_failure: true

  - provider: Slack
    incoming_webhook: https://hooks.slack.com/services/YOUR/SLACK/WEBHOOK
```

### 3. Deploy Condizionale

```yaml
deploy:
  - provider: GitHub
    auth_token:
      secure: YOUR_TOKEN
    artifact: MyApp
    on:
      branch: master
      configuration: Release
```

## Script Personalizzati

### Build Script Complesso

```yaml
build_script:
  - echo "Starting custom build..."
  - msbuild MyApp.sln /p:Configuration=Release /p:Platform="Any CPU"
  - echo "Build completed!"

after_build:
  - echo "Creating installer..."
  - makensis installer.nsi
  - echo "Installer created!"
```

### Test con Coverage

```yaml
test_script:
  - packages\OpenCover.4.6.519\tools\OpenCover.Console.exe -target:"packages\NUnit.ConsoleRunner.3.7.0\tools\nunit3-console.exe" -targetargs:"MyApp.Tests\bin\Release\MyApp.Tests.dll" -register:user -output:"coverage.xml"

after_test:
  - packages\coveralls.net.0.7.0\tools\csmacnz.Coveralls.exe --opencover -i coverage.xml --repoToken %COVERALLS_REPO_TOKEN%
```

## Badge per README

Aggiungi questo badge al tuo README.md:

```markdown
[![Build status](https://ci.appveyor.com/api/projects/status/YOUR_PROJECT_ID?svg=true)](https://ci.appveyor.com/project/YOUR_USERNAME/YOUR_PROJECT)
```

## Variabili d'Ambiente Utili

```yaml
environment:
  # Token per deploy
  GITHUB_TOKEN:
    secure: YOUR_ENCRYPTED_TOKEN
  
  # Versione custom
  VERSION: 1.2.3

# Uso nelle build
build_script:
  - echo "Building version %VERSION%"
  - echo "Commit: %APPVEYOR_REPO_COMMIT%"
  - echo "Branch: %APPVEYOR_REPO_BRANCH%"
```

## Best Practices

1. **Cache Dependencies**: Velocizza i build
```yaml
cache:
  - packages -> **\packages.config
  - node_modules -> package.json
```

2. **Build solo quando necessario**:
```yaml
skip_commits:
  files:
    - docs/*
    - '**/*.md'
```

3. **Parallel Jobs**: Per progetti grandi
```yaml
parallel: true
```

4. **Artifact Cleanup**:
```yaml
artifacts:
  - path: MyApp.exe
    name: MyApp
    type: File
```

## Esempio Completo per App Windows

```yaml
version: 1.0.{build}
image: Visual Studio 2022

configuration: Release
platform: Any CPU

assembly_info:
  patch: true
  file: AssemblyInfo.*
  assembly_version: "1.0.{build}"
  assembly_file_version: "1.0.{build}"

before_build:
  - nuget restore MyWindowsApp.sln

build:
  project: MyWindowsApp.sln
  verbosity: minimal

after_build:
  - 7z a MyWindowsApp-v%APPVEYOR_BUILD_VERSION%.zip %APPVEYOR_BUILD_FOLDER%\MyWindowsApp\bin\Release\*

artifacts:
  - path: MyWindowsApp-v$(appveyor_build_version).zip
    name: MyWindowsApp

deploy:
  provider: GitHub
  auth_token:
    secure: YOUR_GITHUB_TOKEN
  artifact: MyWindowsApp
  on:
    appveyor_repo_tag: true
```

## Vantaggi per i tuoi Progetti

✅ **Build automatiche** ad ogni commit  
✅ **Test automatici** su multiple configurazioni  
✅ **Deploy automatico** delle release  
✅ **Badge di stato** per il README  
✅ **Notifiche** in caso di problemi  
✅ **Artifacts** conservati automaticamente  
✅ **Integrazione** con GitHub/BitBucket  
✅ **Gratuito** per progetti open source