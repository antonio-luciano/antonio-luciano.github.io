---
title: "Primeiros Passos com o Microsoft Graph no PowerShell"
date: 2025-05-06 19:00:00 +0000
categories: [PowerShell, Microsoft Graph]
tags: [powershell, microsoft365, graph, exchange, teams, entra, sharepoint]
author: Antonio Luciano
---
<br>  <!-- Quebra de linha -->

O **Microsoft Graph PowerShell** é um módulo moderno e poderoso que permite também **interagir com dados do Microsoft 365** de forma centralizada, segura e escalável. Através de cmdlets baseados em REST API, você pode consultar, gerenciar e automatizar tarefas envolvendo:

- Microsoft Entra ID
- Microsoft Teams
- Exchange Online
- SharePoint Online
- OneDrive Business
- Intune e muito mais.

## 🧰 Pré-requisitos

Antes de utilizar o módulo, certifique-se de ter:

1. **PowerShell 5.1 ou superior (Windows)** ou **PowerShell 7+ (cross-platform)**
2. Sistema operacional: **Windows 10/11, Windows Server, ou macOS/Linux com PowerShell 7**
3. Permissões adequadas para acessar os recursos do Microsoft 365

## 📦 Instalando o Módulo

Execute o seguinte comando no PowerShell com permissões de administrador:

```powershell
Install-Module Microsoft.Graph -Scope CurrentUser
```

💡 Se quiser instalar módulos específicos (como Microsoft.Graph.Users), você pode especificá-los:

```powershell
Install-Module Microsoft.Graph.Users -Scope CurrentUser
```

## 🔐 Autenticando no Microsoft Graph

Para iniciar uma sessão:

```powershell
Connect-MgGraph
```
Você será redirecionado para uma janela de login. Após autenticação, poderá começar a executar os cmdlets.

Verifique os escopos e permissões com:

```powershell
Get-MgContext
```

## 🌐 Exemplos de Comandos Úteis

Abaixo estão alguns exemplos práticos do dia a dia:

👤 Listar os usuários do Microsoft Entra ID
```powershell
Get-MgUser | Select-Object DisplayName, UserPrincipalName, AccountEnabled
```
🔍 Obter detalhes de um usuário específico
```powershell
Get-MgUser -UserId "usuario@dominio.com"
```
🏢 Listar todos os grupos do Microsoft 365
```powershell
Get-MgGroup | Select DisplayName, MailEnabled, SecurityEnabled
```
📧 Obter caixas de correio (Exchange Online)
```powershell
Get-MgUser | Where-Object { $_.Mail -like "*@dominio.com" } | Select DisplayName, Mail
```
📝 Obter os membros de um grupo
```powershell
Get-MgGroupMember -GroupId "id-do-grupo"
```
Para obter o ID de um grupo:
```powershell
Get-MgGroup | Format-Table DisplayName, Id
```

## 📘 Dicas úteis

Você pode carregar apenas os módulos necessários para sua tarefa:
```powershell
Import-Module Microsoft.Graph.Users
```
Use Disconnect-MgGraph para encerrar a sessão com segurança.
Para atualizar o módulo:
```powershell
Update-Module Microsoft.Graph
```

## 📚 Documentação oficial

<a href="https://learn.microsoft.com/en-us/powershell/microsoftgraph/overview?view=graph-powershell-1.0" target="_blank" rel="noopener noreferrer">Microsoft Graph PowerShell Docs</a><br>
<a href="https://learn.microsoft.com/en-us/graph/permissions-reference" target="_blank" rel="noopener noreferrer">Permissões e escopos da API</a>


## 🚀 Conclusão

O módulo Microsoft Graph para PowerShell permite agilidade, centralização e automação no gerenciamento de soluções Microsoft 365. Dominar esse recurso transforma sua rotina de administração em algo muito mais eficiente e escalável.

Experimente, explore a documentação oficial e integre o Graph ao seu dia a dia e seus scripts!