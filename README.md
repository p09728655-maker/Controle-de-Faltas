# Controle de Faltas e Ausências — Patrimar Móveis

Painel do Departamento Pessoal para faltas, férias, afastamentos e turnover.
Lê a planilha `CONTROLE_FALTAS_2026.xlsx` direto no navegador — **nenhum dado é enviado para a internet** (LGPD).

## Arquivos

| Arquivo | Função |
|---|---|
| `index.html` | O painel completo (autocontido) |
| `manifest.json` | Configuração do PWA (instalar como app) |
| `sw.js` | Cache offline (app + bibliotecas) |
| `icone-192.png` / `icone-512.png` | Ícones do app |
| `vercel.json` | Configuração do deploy |

## Como usar

1. Abrir o painel
2. Clicar ou arrastar o `CONTROLE_FALTAS_2026.xlsx`
3. Filtrar por mês, departamento, setor e status
4. Botão **🔒 Ocultar nomes** antes de projetar (LGPD) · **🖨 Imprimir relatório** para o A4

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
