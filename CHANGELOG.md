# Histórico de versões — Controle de Faltas e Ausências

A versão atual aparece no rodapé do painel (ex.: `v2.0.0`).
Quem já usa o painel recebe o aviso **"🔄 Nova versão disponível"** automaticamente na visita seguinte à publicação.

## Como publicar uma atualização

1. Fazer a alteração no `index.html`
2. Subir a versão na constante `VERSAO` do `index.html` (ex.: `2.0.0` → `2.1.0`)
3. Subir a mesma versão no nome do cache no `sw.js` (`faltas-patrimar-v2.1.0`)
4. Registrar a mudança neste arquivo (mais recente em cima)
5. Commit + push — o Vercel publica sozinho

Regra prática para o número: **corrigiu algo** → muda o último dígito (2.0.1) · **função nova** → muda o do meio (2.1.0) · **mudou a cara do painel** → muda o primeiro (3.0.0).

---

## v2.0.0 — 13/08/2026

Refatoração completa no padrão do dashboard de atestados.

- Tema escuro com a identidade visual do painel de atestados (Barlow, cards, KPIs coloridos)
- Caixa **"O que este painel está dizendo"**: resumo do período em linguagem simples, com fatos clicáveis que aplicam filtros
- Navegação fixa por seções: Resumo · Quando · Onde · Quem · Por quê · Rotatividade · Detalhe
- Filtros com chips de período, busca livre, tags removíveis e contador de registros
- **📤 Faltas do dia**: resumo gerencial do dia para enviar por WhatsApp, e-mail ou copiar
- Exportação CSV dos registros filtrados
- Tabela de lançamentos completa, ordenável por qualquer coluna
- Relatório de impressão A4 em fundo claro (KPIs, resumo por setor, top faltas, afastados)
- Gráficos clicáveis (mês, setor, motivo) que aplicam o filtro correspondente
- Nomes ocultos por padrão (LGPD)
- Número de versão no rodapé + aviso automático de nova versão

## v1.0.0 — 2026

Versão original.

- Painel claro com KPIs, absenteísmo mensal, horas por setor, motivos, dia da semana, turnover, top faltas, afastados e resumo por setor
- Leitura local da planilha `CONTROLE_FALTAS_2026.xlsx` (abas BASE, HORAS CARGA e TURNOVER)
- PWA com funcionamento offline
