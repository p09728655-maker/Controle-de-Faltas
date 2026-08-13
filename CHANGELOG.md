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

## v2.2.1 — 13/08/2026

- Corrige a impressão do dia: o modal "Faltas do dia" aparecia na folha impressa por cima do relatório A4 — agora só o relatório sai na impressão
- Corrige a navegação por seções (Resumo, Quando, Onde…): a rolagem agora usa a âncora nativa do navegador, resolvendo o salto errado para o fim da página em alguns navegadores
- Departamento sem o prefixo numérico no relatório do dia ("2-PRODUÇÃO" → "Produção")

## v2.2.0 — 13/08/2026

Correção do absenteísmo + impressão do dia.

**Correção importante:** as horas de **afastados e férias** entravam no cálculo de horas de falta e de absenteísmo. Um afastado o ano inteiro "gerava" 8,8h de falta por dia, e setores pequenos estouravam 100% de absenteísmo (ex.: Transporte com 161%). Agora:

- Horas de falta e absenteísmo contam apenas faltas, atestados e atrasos — férias e afastamentos ficam nos seus próprios indicadores (em dias)
- Vale para os KPIs, gráficos, tabelas, leitura, relatórios e resumo do dia
- Se mesmo assim um setor passar de 100%, o painel avisa para conferir a carga na aba HORAS CARGA
- A tabela de lançamentos e o CSV continuam mostrando o valor bruto da planilha

- Novo botão **🖨 Imprimir dia** dentro do modal "Faltas do dia": relatório A4 em fundo claro só daquele dia, com as ocorrências agrupadas por tipo (faltas primeiro, férias por último), departamento e motivo — bom para imprimir ou salvar em PDF
- Respeita a opção "Mostrar nomes completos" do modal (LGPD)
- O absenteísmo do mês aparece no cabeçalho do relatório

## v2.1.0 — 13/08/2026

Novo layout do resumo **📤 Faltas do dia** para WhatsApp.

- Agrupado por tipo de ocorrência com contagem em cada bloco — faltas primeiro, férias por último (antes era por departamento, com tudo misturado)
- Nomes e setores em maiúsculas/minúsculas em vez de CAIXA ALTA
- Setor sem o prefixo numérico ("14-ALMOXARIFADO" → "Almoxarifado")
- Emoji por tipo de ocorrência (❌ falta, 🏥 atestado, ⏰ atraso, 🚑 afastado, 🏖️ férias) e motivo em itálico
- Removido o emoji do título que aparecia como "�" em alguns aparelhos

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
