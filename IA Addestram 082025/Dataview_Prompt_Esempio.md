# 📊 Esempio Dataview Query

## Lista task da completare oggi

```dataview
table file.link as "Nota", text as "Attività"
from "Daily"
where !completed
sort file.name desc
```

## Note col tag #AI

```dataview
list from #AI
```

## Riepilogo settimanale

```dataview
table file.name as "Nota", length(text) as "Lunghezza"
from "Daily"
where date(today) - file.day <= dur(7 days)
sort file.day desc
```
