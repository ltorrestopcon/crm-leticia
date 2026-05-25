# CRM Letícia — Cockpit Comercial

Sistema de CRM pessoal de **Letícia Torres**, Executiva de Contas Jr II na Topcon Suite.

Atende às 6 frentes simultâneas: vendas, upsell/cross-sell, retenção & churn, demandas administrativas, melhoria de processos e atendimento WhatsApp.

**Regiões de atuação:** Centro-Oeste, Norte, Nordeste, São Paulo e Espírito Santo.
**Base de análise:** desde 01/01/2026.

---

## Arquivos neste repositório

### 1. `CRM_Leticia.xlsx`
Planilha Excel com 5 abas:

- **Dashboard** — KPIs e gráficos
- **Tarefas** — Lista única com filtros, listas suspensas e formatação condicional (cores por status, prioridade e prazo)
- **Clientes** — Cadastro de referência
- **Histórico** — Arquivo de tarefas concluídas
- **Configurações** — Módulos, status, prioridades e responsáveis

Funciona offline em Excel ou LibreOffice. Edite normalmente e salve.

### 2. `CRM_Dashboard.html`
Dashboard estilo HubSpot, totalmente standalone.

- Abre em qualquer navegador (Chrome, Firefox, Edge)
- Funciona **sem internet**
- Salva tarefas no `localStorage` do navegador
- Inclui dados de exemplo (não dados reais do SF)
- Visualizações: Kanban por status, tabela, filtros, gráficos

**Como abrir:** clique 2x no arquivo, ou no Chrome use `Ctrl+O` e selecione.

### 3. `CRM_Live_Dashboard.html`
**Versão ao vivo, exclusiva do Cowork.**

- 10 abas profissionais: Cockpit, Atividades SF, Service Desk, Inbox Unificada, Operações de Conta, Retenção & Churn, Sales Ops & Processos, Funil & Receita YTD, Hunting List, Analytics Comercial
- Puxa dados em tempo real do Salesforce (tarefas, oportunidades, vendas, contas) e Zendesk (tickets)
- Foco do Dia automático (top 5 prioridades)
- Análises YTD desde 01/01/2026

**⚠️ Importante:** este arquivo **só funciona dentro do Cowork** (desktop app da Anthropic) porque depende de `window.cowork.callMcpTool` para acessar os conectores Salesforce e Zendesk autenticados. Se aberto fora do Cowork, mostrará mensagens de erro nos painéis live (SF, Zendesk, Vendas, Pipeline, Hunting). As abas manuais (Inbox, Operações de Conta, Churn, Sales Ops) e o localStorage continuam funcionando.

---

## Stack

- Excel (openpyxl, fórmulas dinâmicas)
- HTML/CSS/JS standalone
- Chart.js v4 para visualizações
- localStorage para persistência cliente-side
- Integração MCP: Salesforce + Zendesk (apenas no Cowork)

## Modelo de dados

- **Módulos:** TopconFleet, TopconBatch, Topcon, Zendesk, Administrativo, Assistente Comercial, Vendas
- **Status (variados por aba):** Aberto, Em Andamento, Aguardando, Concluído, Em Risco, Cancelado, Retido, etc.
- **Regiões:** Centro-Oeste, Norte, Nordeste, São Paulo, Espírito Santo, Outras

---

_Repositório privado. Construído com Claude (Anthropic) em sessões de Cowork mode._
