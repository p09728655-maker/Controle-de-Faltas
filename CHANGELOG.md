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

## v2.8.0 — 13/08/2026

Envio direto pelo WhatsApp na aba **Hoje**, com o texto redesenhado.

- O botão **"📤 Enviar este dia"** virou **"💬 Enviar no WhatsApp"**: um clique e o WhatsApp abre já com o resumo do dia escrito — no celular abre o app, no computador o WhatsApp Web. Antes era preciso passar pela janela do resumo antes de enviar
- O envio segue os **nomes como estão na tela**: com o topo em "Nomes ocultos", o texto sai abreviado e avisa "_Nomes abreviados (LGPD)._" no rodapé da mensagem
- **Texto do dia redesenhado** para leitura no celular: cabeçalho com dia da semana por extenso, panorama em três linhas (quantas pessoas e setores, quantas exigem ação, quantas são programadas, e a contagem por tipo de ocorrência), separadores entre os blocos, e as listas divididas em **"⚠️ EXIGEM AÇÃO"** e **"🗓️ PROGRAMADO"** — férias e banco de horas não competem mais com o que precisa de providência no dia
- Fecha com **"🏭 POR SETOR"** (o peso de cada setor no dia, do maior para o menor), o absenteísmo do mês e a marcação de confidencialidade
- A prévia no modal "📤 Faltas do dia" agora mostra a mensagem **como ela chega no WhatsApp** — balão verde, negrito e itálico já aplicados, em vez do texto cru com asteriscos

## v2.7.0 — 13/08/2026

Impressão por setor **sem nomes** — o papel que pode circular fora do DP.

- Novo relatório A4 **"Ausências do Dia por Setor"**: só quantidades — setor × tipo de ocorrência, total e % do dia, com a linha "Total do dia" fechando cada coluna. Nenhum nome de colaborador aparece, e o rodapé deixa isso escrito ("Sem identificação de colaboradores — apenas quantidades por setor")
- Fecha com **"Motivos informados no dia"** (ex.: Assuntos Pessoais (3) · Médico (3) · INSS (2)) — também sem ligar motivo a pessoa
- Dois caminhos para chegar nele: botão **"🖨 Por setor (sem nomes)"** no quadro de resumo da aba Hoje (imprime o dia que está na tela) e no modal "📤 Faltas do dia", onde dá para escolher qualquer data
- Corrigido: os números da linha "Total do dia" no resumo da tela apareciam desalinhados das colunas

## v2.6.0 — 13/08/2026

Aba **Hoje** reorganizada — acabou o espaço vazio no meio e chegou o resumo por setor.

- **Novo quadro "Resumo do dia por setor"**: quatro números do dia (ausentes, exigem ação, programado e setores afetados) e uma tabela com o setor, quanto deu de cada tipo de ocorrência, o total e uma barra de composição colorida. A linha "Total do dia" fecha a conta de cada coluna
- Os blocos de "quem está ausente" agora se **encaixam pela altura, em cascata** — antes o setor mais cheio esticava a linha inteira e sobrava um buraco embaixo dos setores pequenos
- Blocos com nome do colaborador quebrando em duas linhas quando preciso, em vez de esticar a coluna
- Cabeçalho de cada coluna do resumo na cor da ocorrência (falta em vermelho, atestado em azul, afastado em laranja, atraso em violeta, férias em verde) — mesma cor das etiquetas do painel

## v2.5.2 — 13/08/2026

- Removido o quadro "Quem faltou hoje" do Resumo — ficou obsoleto com a aba **Hoje**, que mostra o dia completo por setor. O botão "📤 Enviar este dia" segue na aba Hoje

## v2.5.1 — 13/08/2026

- O aviso **"🔄 Nova versão disponível"** agora chega mesmo com o painel aberto direto: o app confere se saiu atualização a cada 30 minutos e também quando a aba volta a ficar visível (minimizou e voltou). Antes, só ao abrir/recarregar ou na checagem automática do navegador (~24h)

## v2.5.0 — 13/08/2026

Nova aba **Hoje** — o dia inteiro na tela, setor por setor.

- Nova aba **Hoje** na navegação: mostra todas as ausências do dia agrupadas por setor, em blocos lado a lado — sem rolagem interna, dá para ver o dia completo de uma vez. Setores com mais ocorrências aparecem primeiro, e cada bloco traz colaborador, ocorrência e motivo
- O botão "📤 Enviar este dia" também está na aba Hoje
- O quadro "Quem faltou hoje" do Resumo continua compacto; quando a lista não cabe, aparece um aviso com atalho para a aba Hoje
- Respeita o botão "Nomes ocultos" como o resto do painel

## v2.4.1 — 13/08/2026

Marcação de confidencialidade em tudo que sai do painel.

- Faixa do topo dos relatórios impressos agora diz **"🔒 Confidencial — Uso interno · Departamento Pessoal"** (relatório do período e do dia)
- Novo rodapé **"Confidencial — uso interno · Patrimar Móveis"** repetido em **todas as páginas** da impressão, não só na primeira
- Rodapé dos relatórios ganhou o aviso **"Documento confidencial — uso interno. Não divulgar."**
- Resumo do dia enviado por **WhatsApp, e-mail ou copiado** agora abre com "🔒 Confidencial — uso interno" e fecha com a mesma marcação; o assunto do e-mail sai como **[CONFIDENCIAL — uso interno]**
- Aviso "Confidencial — uso interno" também nos rodapés das telas do painel e da tela de abertura

## v2.4.0 — 13/08/2026

Absenteísmo batendo com a planilha + quadro "Quem faltou hoje".

- **Absenteísmo agora bate com o % AUSÊNCIA da planilha por padrão** (inclui as horas dos afastados, ex.: Julho 7,41%). No card Absenteísmo dá para alternar para **"Sem afastados"** — a visão gerenciável, só faltas, atestados e atrasos (Julho 4,63%). O modo escolhido vale para todos os KPIs, gráficos, tabelas, relatórios e resumo do dia
- Novo quadro **"Quem faltou hoje"** no topo do painel: lista de quem está ausente hoje com setor, ocorrência e motivo — sem precisar abrir nada. Se hoje ainda não tem lançamentos, mostra o último dia com registros. Botão "📤 Enviar este dia" abre direto o resumo para WhatsApp/e-mail/impressão
- Correção de data: lançamento cuja célula de DATA carrega horário após meio-dia caía no dia seguinte — agora a data é lida corretamente

## v2.3.0 — 13/08/2026

Excel lincado — sem buscar o arquivo toda vez.

- Ao escolher a planilha (clique ou arrastar), o app guarda a referência do arquivo no navegador (Chrome/Edge de computador)
- Na próxima visita aparece o botão **🔄 Reabrir CONTROLE_FALTAS_2026.xlsx** — 1 clique e o painel monta com a versão atual do arquivo, sem navegar pelas pastas
- Com o app instalado (PWA), a permissão persiste e o painel **abre sozinho** com os dados
- Novo botão **🔄 Recarregar** no topo: relê o arquivo do disco na hora — bom para depois de salvar uma alteração no Excel
- Tudo continua 100% local: o arquivo não sai do computador (LGPD)
- Em navegadores sem suporte (Firefox, celular), o fluxo continua como era
- Resumo e impressão do dia agora ordenados pelo nome visível: setor (sem o prefixo numérico) e depois colaborador, em ordem alfabética

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
