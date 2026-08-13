# Controle de Faltas e Ausências — Patrimar Móveis

Painel do Departamento Pessoal para faltas, férias, afastamentos e turnover.
Lê a planilha `CONTROLE_FALTAS_2026.xlsx` direto no navegador — **nenhum dado é enviado para a internet** (LGPD).

## Arquivos

| Arquivo | Função |
|---|---|
| `index.html` | O painel completo (autocontido) |
| `manifest.json` | Configuração do PWA (instalar como app) |
| `sw.js` | Cache offline (app + bibliotecas) |
| `CHANGELOG.md` | Histórico de versões e como publicar atualizações |
| `icone-192.png` / `icone-512.png` | Ícones do app |
| `vercel.json` | Configuração do deploy |

## Como usar

1. Abrir o painel
2. Clicar ou arrastar o `CONTROLE_FALTAS_2026.xlsx`
3. A caixa **"O que este painel está dizendo"** resume o período em uma frase
4. Navegar pelas seções fixas no topo: **Resumo · Quando · Onde · Quem · Por quê · Rotatividade · Detalhe**
5. Filtrar por período (chips), mês, departamento, setor, ocorrência ou busca livre — os filtros ativos viram tags removíveis

Botões do topo:

- **📤 Faltas do dia** — resumo gerencial do dia pronto para enviar por WhatsApp ou e-mail (ou copiar)
- **Nomes ocultos** — nomes mascarados por padrão (LGPD); clique para mostrar
- **Imprimir relatório** — relatório A4 em fundo claro com KPIs e tabelas
- **Exportar CSV** — registros filtrados em CSV (abre no Excel)
- **Trocar arquivo** — carregar outra versão da planilha

Abas lidas da planilha: `BASE`, `HORAS CARGA`, `TURNOVER`.

## Publicar (GitHub + Vercel)

```bash
git init
git add .
git commit -m "Painel de faltas e ausências — Departamento Pessoal"
git branch -M main
git remote add origin https://github.com/p09728655-maker/controle-faltas.git
git push -u origin main
```

Depois, no Vercel: **Add New → Project → importar o repositório `controle-faltas` → Deploy** (sem build, é site estático).

## Atualização mensal

Não precisa mexer no site: o DP abre o painel e carrega a planilha atualizada. Só é preciso novo deploy se o **layout** mudar.

## Versões e atualizações do painel

A versão atual aparece no rodapé (ex.: `v2.0.0`). Quando uma nova versão é publicada, quem já usa o painel vê o aviso **"🔄 Nova versão disponível — Atualizar agora"** na visita seguinte — sem perder a planilha aberta.

Para publicar uma atualização, siga o passo a passo do [`CHANGELOG.md`](CHANGELOG.md) (mudar `VERSAO` no `index.html`, o cache no `sw.js` e registrar a mudança).
