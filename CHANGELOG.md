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

## v2.13.2 — 21/08/2026

O bloco preto depois das barras de composição sumiu, na tela.

- A coluna **Composição** agora fica exatamente do tamanho da barra. Antes, por ter o conteúdo mais largo da linha, era ela quem absorvia a sobra de um monitor grande — e como a barra tem faixa fixa, a sobra virava um vazio preto à direita das barras
- A sobra da largura passou a se **espalhar entre as colunas de setor e de números**, que respiram por igual — o quadro continua ocupando a linha inteira, sem buraco concentrado
- Vale para o quadro do dia (aba **Hoje**) e o do período (aba **Onde**); a impressão não muda, já tinha esse ajuste

## v2.13.1 — 21/08/2026

O quadro por setor agora explica o que os números significam.

- Abaixo da tabela **"Resumo do dia por setor"** (aba Hoje) e do quadro da aba **Onde**, uma linha explica: **os números contam pessoas; a hora menor ao lado é o tempo somado de ausência**
- Quando o dia/período tem falta de **meio período**, a explicação completa: quem faltou ½ dia **conta como 1 pessoa, mas entra só com as horas que perdeu** — é por isso que um setor pode mostrar 5 pessoas e menos horas do que 5 × 8,8h
- A mesma observação sai nos **relatórios impressos** que usam esse quadro ("Ausências do Dia por Setor" e "Ausências por Setor e Tipo") e nas mensagens de **WhatsApp** do dia (com e sem nomes)
- A nota do meio período só aparece quando há registro de ½ dia no recorte — sem parcial, sai só a explicação curta

## v2.13.0 — 21/08/2026

A falta de meio período agora aparece identificada no painel.

- O painel passou a ler a **coluna P** da aba BASE: **I** = dia inteiro, **M** = meio período
- Registros de meio período ganham a etiqueta **"½ dia"** ao lado do tipo de ocorrência na aba **Hoje** e na tabela **Detalhe**
- O card **Ausentes no dia** mostra quantos lançamentos do dia são de meio período
- Na mensagem de WhatsApp **"Faltas do dia"** (com nomes), a linha da pessoa sai com _meio período_
- No relatório impresso **"Faltas do Dia"**, o **½ dia** aparece ao lado das horas
- **Nada muda nas contas**: as somas já usavam FALTAS UNIT. (0,5) e HORAS FALTA (3:59) da planilha — a novidade é só a identificação visual de quem faltou meio período

## v2.12.3 — 20/08/2026

A largura que sobrou virou número maior — o ajuste que faltava na v2.12.2.

- **O corpo da tabela acompanha a largura disponível.** Na tela vai de 13px num notebook a 20px num monitor grande; no papel, de 9pt na folha em pé a 11,5pt na deitada. A folha deitada era o pior caso: os números saíam do mesmo tamanho da folha em pé e a sobra toda virava barra
- **A tabela volta a ocupar a linha inteira.** Na v2.12.2 ela encolheu até o fim do conteúdo e deixou um vazio preto ao lado, na tela
- A **barra de composição** fica numa faixa proporcional à folha (22mm em pé, 34mm deitada) em vez de herdar a sobra
- Com 7 tipos de ocorrência ou mais a tabela segue em modo compacto, mas agora também ganha corpo na folha deitada (7,5pt → 8,1pt)

## v2.12.2 — 20/08/2026

A barra de composição deixou de tomar a largura da folha e da tela.

- A barra agora tem **faixa fixa** (190px na tela, 34mm no papel) em vez de herdar toda a sobra da largura. Antes, na folha deitada, ela sozinha ocupava mais da metade da área útil — e na tela, mais de dois terços da tabela
- **A tabela para onde o conteúdo termina**: cada coluna fica do tamanho do que carrega e o quadro não se estica só para preencher a linha. Os números continuam juntos do nome do setor, sem vão no meio
- No **celular** a barra cai para 110px, para a tabela rolar menos de lado
- Vale para a tela (abas Hoje e Onde) e para os três relatórios com essa tabela: "Imprimir relatório", "Imprimir este quadro" e o do dia por setor

## v2.12.1 — 14/08/2026

Ajuste das colunas da tabela impressa, que ficou igual à da tela.

- O **nome do setor não quebra mais em duas linhas**: a coluna ocupa o nome inteiro e os números ficam com o resto. Antes, "Almoxarifado / Estoque" e "Departamento Pessoal" saíam empilhados no papel enquanto sobrava espaço nas colunas de número
- A **barra de composição entrou no papel**, como na tela: além de mostrar o peso de cada tipo de ocorrência no setor, é ela que fica com a sobra da largura da folha, em vez de espalhar as colunas de número
- De 7 tipos de ocorrência para cima a barra sai de cena — ali o espaço é dos números, e a tabela já entra em modo compacto
- Vale para os três relatórios com essa tabela: "Imprimir relatório", "Imprimir este quadro" e o do dia por setor

## v2.12.0 — 14/08/2026

Impressão só do quadro por setor, coluna de setor ajustada e a tabela larga cabendo no A4.

### Botão "Imprimir este quadro"

- O quadro **"Por setor e tipo de ocorrência"** da aba Onde ganhou botão próprio: sai um A4 só com ele — cabeçalho, filtros, o resumo do período (lançamentos, o que exigiu ação, o que foi programado, horas e absenteísmo), a tabela e os motivos informados
- Como não sai nome de ninguém, **pode circular fora do DP**, igual ao "Por setor (sem nomes)" do dia
- Quando o período tem **6 tipos de ocorrência ou mais**, a folha sai **deitada** sozinha — é o que segura a tabela larga sem espremer os números

### A coluna do setor se ajusta ao nome

- A coluna de setor era fixa em 26% da largura. Com 10 tipos de ocorrência sobrava espaço nela e faltava nos números, abrindo um vão no meio da linha. Agora ela se ajusta ao nome mais longo e a **barra de composição toma a sobra**: com poucos tipos a barra fica larga, com muitos ela cede espaço para os números
- Vale para a tela e para o papel
- De **7 tipos de ocorrência para cima**, a tabela impressa entra em modo compacto (fonte e espaçamento menores) — é o que faz o mês inteiro caber na folha em pé

### Rodapé de cada folha

- A tarja "Confidencial — uso interno" virou **rodapé de tabela** (`tfoot`), que o navegador repete em toda página **e cujo espaço ele reserva**. Antes era `position:fixed`, que não reserva altura: quando a tabela chegava no pé da página, a última linha saía por baixo da tarja
- Conferido em A4 retrato e paisagem, com 25 setores e 10 tipos de ocorrência: nenhuma linha cortada e a tarja em todas as folhas

## v2.11.0 — 14/08/2026

O resumo por setor ficou compacto e ganhou uma versão **do período**, na tela e na impressão.

### Resumo do dia mais baixo

- As horas saíram de baixo da quantidade e foram para o **lado dela**, na mesma linha: com 12 setores a tabela encolheu quase um terço da altura, e a largura que sobrava na tela virou uso
- As colunas de número agora ficam **juntas, logo depois do setor**, e a barra de composição toma a sobra — em tela larga não abre mais aquele vão no meio da linha
- Linha mais baixa (menos respiro em cima e embaixo): o dia inteiro cabe sem rolagem

### Novo quadro: "Por setor e tipo de ocorrência" do período

- Fica na aba **Onde**, abaixo dos setores: a mesma tabela da aba Hoje — quantidade e horas de cada tipo de ocorrência, total e a barra de composição —, só que com o **período filtrado** inteiro em vez de um dia
- O subtítulo traz o recorte: "Em Agosto · 111 lançamentos em 12 setores · 820h de ausência (falta 503,2h · férias 316,8h)"
- Segue os filtros do painel como o resto da aba, mês inclusive

### A mesma tabela no relatório impresso

- O **"Imprimir relatório"** ganhou a seção "Quantidade e horas por setor e tipo de ocorrência" do período, logo abaixo do resumo por setor
- O relatório do dia por setor passou a usar a mesma tabela: quantidade e horas dividem a célula, em vez de duas colunas por tipo de ocorrência. Assim cabe no A4 mesmo quando o mês traz Falta, Atestado, Atraso, Afastado, Just., Banco H. e Férias ao mesmo tempo
- Nome de setor só quebra no espaço, nunca no meio da palavra, e "12 89,6h" não se parte entre duas linhas

### Setor sem o código da planilha

- O prefixo numérico saiu de **toda a exibição**: `2-EMBALAGEM` vira **Embalagem**, `14-ALMOXARIFADO / ESTOQUE` vira **Almoxarifado / Estoque**. Vale para o gráfico de setores, o "Resumo por setor", a tabela de lançamentos, as listas de colaboradores, os relatórios impressos, as etiquetas de filtro e as duas caixas de seleção (Departamento e Setor)
- Por baixo, o nome continua **exatamente como está na planilha**: é ele que casa o filtro com a aba HORAS CARGA e é ele que sai no CSV. O que mudou foi só o rótulo na tela
- As caixas de seleção agora vêm **em ordem alfabética pelo nome que aparece**, e não pelo código — antes a lista começava em 10-Expedição, 11-Faturamento, 12-Linha de Pintura

### Paginação do relatório impresso

- Antes, cada seção era indivisível: uma tabela que não coubesse no que restava da folha pulava inteira para a próxima e **deixava meia página em branco**. Agora a tabela atravessa a quebra e a folha enche até o fim
- O **cabeçalho da tabela se repete** no alto da página seguinte, e nenhuma linha se parte no meio da quebra
- A margem de baixo passou de 16 mm para 22 mm: a tarja "Confidencial — uso interno" que se repete em toda folha ficava por cima da última linha da página. Agora sobram 5 mm de folga entre a última linha e a tarja
- Conferido imprimindo de verdade em A4: relatório do dia por setor em 1 página, faltas do dia em 2, período em 3 — sem buraco e sem linha cortada

## v2.10.0 — 14/08/2026

O filtro do painel agora **vale também para o dia**, e o resumo do dia passou a mostrar **horas**.

### O filtro alcança a aba Hoje, o WhatsApp e a impressão

- Departamento, setor, ocorrência e busca agora cortam **a aba Hoje** junto com o resto do painel. Filtrou `2-PRODUÇÃO`, o resumo do dia por setor, os blocos de quem está ausente, o texto do WhatsApp e os dois relatórios A4 do dia saem só com produção
- **Mês e período continuam de fora** do dia — o dia já é a data. Filtrar "Julho" não muda o que a aba Hoje mostra de hoje
- A data mostrada também não muda: o filtro corta o conteúdo, não pula para outro dia
- Quando há filtro ativo, aparece **uma tarja ao lado do subtítulo** ("filtro: 2-PRODUÇÃO · 5 de 12") — dá para ver de relance que o quadro está parcial
- Os relatórios impressos ganham a **faixa "Filtro aplicado"** logo abaixo do cabeçalho, e as mensagens de WhatsApp trazem a linha "_Filtro: …_" no topo. Quem recebe sabe que aquilo não é o dia inteiro
- Se o filtro zerar o dia, o quadro diz quantos lançamentos o dia tem no total e oferece o botão **"limpar filtros"** ali mesmo
- O modal "📤 Faltas do dia" avisa antes de enviar — "Filtro do painel aplicado: … — 5 de 12 lançamentos do dia" — com o botão **"usar o dia inteiro"** ao lado
- O **absenteísmo do mês** que fecha as mensagens e os PDFs do dia passou a respeitar o escopo do filtro (departamento e setor), com o escopo escrito ao lado do número: "Absenteísmo de Agosto (2-PRODUÇÃO): 0,68%". Ocorrência e busca ficam de fora dessa conta — cortariam as horas sem mexer na carga horária, e o percentual sairia torto

### Horas no resumo do dia

- Cada célula do **resumo do dia por setor** traz a quantidade em cima e as **horas embaixo** — falta, atestado, afastado, férias, cada tipo com as suas. A tabela não alargou
- Novo número no topo: **"Horas do dia"**, com a quebra em "falta X · férias Y"
- Os **blocos por setor** mostram o total de horas no cabeçalho, e cada pessoa ganhou a coluna de horas ao lado da ocorrência
- Mesma informação nas duas mensagens de WhatsApp e nos dois relatórios A4: o "Ausências do Dia por Setor" ficou com **duas colunas por tipo de ocorrência** (Qt e Horas), e o "Faltas do Dia" ganhou a coluna Horas na lista de cada tipo
- As horas vêm da planilha como estão: **HORAS FÉRIAS** para férias, **HORAS FALTA** para o resto. É o retrato do dia, e por isso não segue o botão "com/sem afastados" do absenteísmo — afastado no dia continua contando as horas dele

## v2.9.1 — 13/08/2026

- **Emojis removidos das mensagens do WhatsApp.** O WhatsApp para Windows recebe o texto pelo link e troca cada emoji por um losango de interrogação — a mensagem chegava suja no grupo, e não era a tela de quem enviou: o texto já saía quebrado. Testado com a fonte Noto Color Emoji instalada, e não muda nada, porque o emoji não chega até a fonte. O layout se sustenta em negrito, itálico e nas linhas divisórias, que atravessam íntegros em qualquer aparelho
- Vale para as duas mensagens: a lista com nomes ("📤 Faltas do dia") e o resumo por setor ("💬 Por setor no WhatsApp"). Os botões do painel continuam com ícone — ali é o navegador desenhando, e funciona

## v2.9.0 — 13/08/2026

O envio pelo WhatsApp da aba Hoje virou **o mesmo conteúdo do PDF por setor**.

- O botão da aba Hoje agora é **"💬 Por setor no WhatsApp"** e manda a versão **sem nomes** — igualzinha ao relatório A4 "Ausências do Dia por Setor" impresso pelo botão ao lado: total de ocorrências, quantos exigem ação e quantos são programados, a lista de setores com total, % do dia e composição por tipo de ocorrência, e os motivos informados no dia
- Como não sai nome de ninguém, **pode circular fora do DP** (produção, diretoria, grupo de gestores) sem passar por cima da LGPD — o rodapé da mensagem diz isso: "_Sem identificação de colaboradores — apenas quantidades por setor._"
- Setor com um tipo só de ocorrência sai em **uma linha** ("Faturamento — 1 (4,8%) · 🏖️ 1 Férias"); com mais de um, a composição vem na linha de baixo
- A lista **com nomes** continua saindo pelo botão "📤 Faltas do dia" do topo, onde também dá para escolher outra data

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
