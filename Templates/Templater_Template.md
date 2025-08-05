---
tags: [template, dynamic]
---

# 🧠 Templater Example

- Current date: <% tp.date.now("YYYY-MM-DD") %>
- Current time: <% tp.date.now("HH:mm") %>
- Vault name: <% tp.user.vaultName() %>

## 🔁 Reusable Block
<%* 
const name = await tp.system.prompt("What's your name?");
tR += `Hello, ${name}!`
%>
