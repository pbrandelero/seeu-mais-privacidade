# Política de Privacidade — SEEU+

*Última atualização: 17 de novembro de 2026 · versão 1.5.11*

O SEEU+ é uma extensão de navegador que acrescenta atalhos e leituras
automáticas sobre sistemas que você já acessa com o seu próprio login: SEEU,
BNMP 3.0 e SIPE.

## Resumo

**A extensão não tem servidor, não faz nenhuma requisição para fora dos
sistemas oficiais e não envia dado nenhum para lugar nenhum.** Não há
telemetria, não há analytics, não há conta a criar, não há terceiros
envolvidos. Tudo o que ela faz acontece dentro do seu navegador.

## O que ela lê

Enquanto você está numa página do SEEU, do BNMP ou do SIPE, a extensão lê o
conteúdo daquela página para montar o que mostra: número do processo, nome da
parte, CPF, RJI, data de nascimento, regime de cumprimento, livramento
condicional e a data em que foi deferido, datas do cálculo da pena — inclusive
as duas data-base, a da progressão e a do livramento, e o detalhe de cada
cálculo: as frações da progressão com a data em que cada uma é alcançada, a
conta do livramento, e o que desloca o término (remição, com os dias perdidos,
interrupção e cômputo diferenciado) —, previsão de prescrição das guias, penas e a situação de
cada uma, quem representa a parte, pendências de análise de juntada, situação
de peças no BNMP e local de prisão no SIPE.

Parando o mouse num documento dos autos, ela mostra uma **prévia**: uma caixa
com uma moldura que abre o próprio endereço do documento no SEEU, com a sua
sessão — como o clique no link faria. A extensão não baixa, não lê e não
guarda o documento; fechada a caixa, ele não fica em lugar nenhum além do
cache comum do navegador.

Na ficha de uma pessoa no BNMP, ela lê também o CPF exibido ali, para conferir
se a ficha aberta é mesmo a da parte daquele processo — ver "o que ela faz por
conta própria".

Ela só age em sete endereços — `seeu.pje.jus.br`, `seeutreino.pje.jus.br`,
`seeuintegra.pje.jus.br` e `seeuimplantacao.pje.jus.br` (as quatro bases do
SEEU: produção, treino, testes e implantação),
`bnmp.pdpj.jus.br`, `sipe.sejus.ro.gov.br` e `sipe.treinamento.ro.gov.br`. Em
qualquer outra página, o código não é sequer carregado.

**Ela não tem acesso ao seu histórico de navegação, aos seus favoritos nem ao
conteúdo de outras abas.** As permissões que ela pede são três: `storage`,
para guardar as suas preferências e as leituras já feitas; `scripting`, para
reinjetar os próprios scripts em abas já abertas depois de uma atualização e
para acionar, na página do SEEU, funções que a própria página define — as
mesmas que os links dela acionam; e `system.display`, para saber quantos
monitores há e onde fica cada um, e assim abrir a janela do "Navegar" e os
PDFs dos autos no outro monitor. Ela lê só a posição e o tamanho dos
monitores — nada do que está na tela deles.

## O que ela faz por conta própria

Estas ações acontecem sem você pedir, e todas dentro dos sistemas oficiais:

- ao abrir a capa de um processo, ela **consulta o status no BNMP**, que é o
  mesmo clique que você daria. Se essa consulta abrir outra página — o que
  acontece com quem não tem acesso ao BNMP —, a consulta automática **para
  por 8 horas**, e volta assim que um status aparecer; o ícone, clicado
  por você, continua funcionando;
- ela **lê no cabeçalho do SEEU o tipo de perfil e a atribuição** em uso —
  se é de advogado ou da Defensoria, e se a atribuição é de vara (analista,
  técnico, juiz…). A consulta automática ao BNMP só acontece nas
  atribuições de vara, ou numa que já trouxe o status por um clique seu. Nesses perfis, os recursos que agem como
  cartório ou consultam sistemas externos sozinhos **não ligam** — eles
  foram feitos para o perfil de vara. Nada do cabeçalho é guardado além
  dessa palavra ("advogado" ou "defensoria"), e só na própria aba;
- para ler o regime, as data-base, o livramento condicional e a previsão de
  prescrição — que só existem atrás da aba Informações Adicionais —, ela
  **carrega uma cópia da mesma página do processo fora da tela** e lê de lá,
  para não mexer na tela em que você está trabalhando. Essa leitura é feita
  ao abrir o processo e refeita sempre que algo pode ter mudado — depois de
  um clique que grava (Salvar, Confirmar, Assinar, Finalizar e semelhantes),
  em qualquer tela ou janela do SEEU nesta aba, e a cada 30 minutos, para
  pegar alterações feitas por outra pessoa —, para o valor mostrado ser o de
  agora e não o de antes da sua alteração. A cópia só é aberta depois de a
  sua página terminar de carregar, e dentro dela a extensão não roda. Se
  essa cópia abrir sem o processo — acontece em bases em que o servidor não o
  reconstrói sozinho —, ela **pede a aba de novo informando o número dos
  autos**, que é a mesma coisa que o SEEU faz quando você clica numa aba;
- pelo mesmo caminho, **abre fora da tela a ficha da parte** do processo, para
  ler CPF, RJI e data de nascimento;
- ainda pelo mesmo caminho, ao usar o atalho de advogados, **abre fora da tela
  a aba Partes** para ler o endereço da tela de cadastro de advogados. Esse
  endereço muda a cada carregamento da página e não pode ser montado por fora;
  é ele que permite abrir a tela numa janela sobre a capa, sem tirar você do
  lugar em que estava. Não dando certo essa leitura, ela **vai à aba Partes**
  de verdade e abre a janela de lá, dizendo na tela por que trocou de aba;
- pela mesma regra (ao abrir o processo, depois de um clique que grava e a
  cada 30 minutos), **abre fora da tela a aba Informações Gerais** — de
  preferência na mesma cópia que lê o regime — para ler o juiz da execução e
  mostrá-lo ao lado do Juízo. Um nome de leitura vencida por essa regra não
  aparece;
- pela mesma regra, quando o processo está concluso e a capa traz o link
  "Pré-Analisar Conclusão", **abre fora da tela a pré-análise dessa
  conclusão** (pelo endereço do próprio link) para ler o agrupador
  escolhido, e, se a lista não estiver na tela, **a aba Movimentações**
  para achar a sequência do movimento de conclusão. Mostra os dois ao lado
  da pendência. Nada é clicado nem salvo na pré-análise; ficam guardados,
  por processo, só o agrupador, a sequência, o título do movimento e o texto
  da pendência, por no máximo um dia;
- pela mesma regra, **abre fora da tela a aba Outros Processos do
  Apenado** para contar quantos deles são de Execução da Pena, e realçar a
  aba quando houver algum. Só a contagem é guardada — nem número nem parte
  dos outros processos;
- na aba Processos Criminais, **abre fora da tela a página de cada processo
  criminal**, pelo link que a própria árvore traz, para ler se a guia é
  provisória ou definitiva. Uma vez por processo criminal; a provisória é
  relida uma vez por dia, porque vira definitiva com o trânsito em julgado;
- na aba Processos Criminais, **abre fora da tela a página de cada pena
  ativa e de cada desmembramento dela**, pelo link da árvore, para ler o
  campo Observações da pena e as frações do desmembramento (progressão e
  livramento). Os desmembramentos das demais penas só são lidos quando
  você passa o mouse sobre eles. Relidos uma vez por dia, ou logo depois de
  você abrir ou salvar a página de uma pena ou desmembramento daquele
  processo — para a fração alterada aparecer nova;
- na aba Processos Criminais, **abre a árvore de penas** e recolhe as que não
  estão ativas, usando as funções de abrir e fechar da própria página. É só
  exibição: nada é alterado, e você pode abrir ou fechar qualquer ramo à mão
  depois;
- nas abas Movimentações e Incidentes, **quando você digita no Filtrar**,
  ela abre e fecha de volta, em segundo plano, os "+" da lista que ainda não
  foram abertos — com as funções da própria página, como o seu clique —,
  para o filtro procurar também nos documentos e detalhes. Uma vez por
  página; o conteúdo fica só na tela, e nada é guardado;
- ao entrar em Informações Adicionais, **revela o quadro do cálculo do
  requisito temporal**, que a aba entrega recolhido. Uma vez por visita, e
  também só exibição: recolhendo-o de novo, ele fica recolhido;
- ao abrir a ficha de uma pessoa no BNMP pelo atalho, **confere o CPF exibido
  ali** contra o da parte do processo. Não batendo, ela esquece o cadastro que
  havia memorizado e refaz a busca pelo CPF — sem isso, um identificador
  aprendido errado abriria sempre a pessoa errada com cara de acerto;
- ao usar os atalhos do BNMP ou do SIPE, ela **abre uma janela auxiliar** com a
  consulta já preenchida. A consulta é feita pelo formulário do próprio
  sistema, como se digitada à mão: no SIPE, que pesquisa pelo endereço da
  página, o CPF buscado aparece nesse endereço e no histórico do SIPE, como
  aparece numa busca manual. No BNMP, o CPF vai pelo armazenamento da
  extensão, e não pelo endereço;
- dentro dessa janela do SIPE — e só dentro dela —, ela aciona o botão
  **Compartilhar localização**, que o SIPE passou a exigir antes de deixar
  consultar. A extensão **não responde** ao pedido de permissão do navegador:
  esse é seu, e é ele que decide se a sua localização é compartilhada. Abrindo
  o SIPE numa aba comum, ela não toca nesse botão;
- na lista de peças do BNMP, **troca o tamanho da página para o maior** que a
  própria tela oferece (hoje, 50 por página), quando há mais peças do que
  cabem na página — e refaz, até três vezes, se o BNMP a devolver ao padrão
  ao terminar de carregar. É só exibição; mexendo você no tamanho, fica como
  você deixou.

Nenhuma dessas ações altera dado nos sistemas.

## O que ela altera, e só quando você pede

Onze caminhos da extensão terminam em tela de alteração. Todos começam num
clique seu, e todos param antes da decisão — com duas exceções, ditas abaixo
com todas as letras.

- **juntar a situação carcerária (RESPE)**: a extensão abre a aba, escolhe o
  relatório e espera o servidor gerá-lo. E **para com o relatório aberto na
  tela, sem assinar**. Quem confere o documento e aperta Assinar é você.
  Versões anteriores clicavam em Assinar depois de perguntar; esta não clica —
  e, por isso, não há mais o que perguntar. Assinado, ela leva você à aba
  Movimentações, que é onde a peça juntada aparece; **fechando a janela sem
  assinar, ela devolve você à aba em que você estava** quando pediu o RESPE, e
  nada é juntado. Para saber qual dos dois aconteceu, ela anota apenas que
  houve um clique em "Assinar" — não acompanha a assinatura em si;
- **juntar um relatório das medidas diversas (MDP)**: ao passar o mouse no
  botão, a extensão lê a aba Medidas Diversas da Prisão numa cópia em segundo
  plano, só para listar os relatórios que ela oferece. Escolhido um, abre a
  aba, aciona o "Anexar … à Movimentação" daquele relatório e aperta o botão
  dele na janela — e **para com o relatório aberto, sem assinar**, como no
  RESPE, com o mesmo destino ao fechar a janela;
- **incluir um endereço novo do sentenciado**: a casinha ao lado da data de
  nascimento abre a ficha da parte numa janela sobre a capa, aperta o
  "Alterar" do endereço e o "Novo Endereço" — e **para no cadastro em
  branco**. Preencher e salvar são com você; depois do seu Salvar, a
  extensão seleciona o endereço novo como o atual — é a oitava exceção,
  logo abaixo;
- **redistribuir**: abre a redistribuição, dispensa sozinha o arquivo da tela
  do relatório — que não tem arquivo nenhum a juntar — e **para na tela das
  opções**, em branco. Comarca, competência, tipo e motivo são escolha sua, e
  não há clique em Finalizar;
- **alterar um cadastro da aba Processos Criminais**: abre o processo criminal,
  a pena ou o desmembramento **já no formulário de alteração**, sem preencher
  campo nenhum e sem salvar;
- **alterar um evento ou incidente**: nas abas Eventos, Incidentes Concedidos,
  Não-Concedidos e Pendentes, abre o item **já no formulário de alteração** —
  do mesmo jeito, sem preencher nem salvar. Depois que **você** salva, ela
  aperta o "Voltar" da tela seguinte, que é navegação e não altera nada;
- **remover um evento ou incidente**: nas mesmas abas, a lixeira ao lado do
  item abre o item e aperta Remover. **Quem decide é você**: o próprio SEEU
  pergunta se você confirma a remoção, e é a única pergunta — a extensão não
  responde a ela;
- **remover um cumprimento para expedir**: na capa, a lixeira ao lado de cada
  item de "Cumprimentos para Expedir" abre a tela daquele cumprimento e
  aperta Remover. **Quem decide é você**: o próprio SEEU pergunta "Deseja
  realmente remover?", e é a única pergunta — a extensão não responde a ela.
  Antes de apertar, ela confere que a tela é de um cumprimento deste
  processo. Confirmada, ela volta ao processo; recusada, nada é removido e
  ela também volta;
- **dispensar as juntadas pendentes de análise**: abre a tela de Análise de
  Juntadas e **marca as juntadas deste processo** — só as dele: uma linha que se
  declara de outro processo não é marcada, e você é avisado. Ela aperta
  Dispensar, e **é o próprio SEEU que pergunta** se você confirma — a extensão
  não responde a essa pergunta. Confirmada — o que ela confere vendo a tela
  recarregar sem as juntadas marcadas —, ela abre o processo e volta à aba em
  que você estava; recusada, nada muda;
- **dispensar a análise de decurso de prazo**: abre a lista de Decursos de
  Prazo do SEEU, filtra por este processo e **marca só as intimações dele** —
  cada linha é conferida pelo número do processo. Ela aperta "Dispensar em
  Lote", e **é o próprio SEEU que pergunta** se você confirma — a extensão
  não responde a essa pergunta. Confirmada, ela volta aos autos, na aba em
  que você estava; recusada, nada muda;
- **habilitar ou desabilitar a Defensoria**: pelo atalho da capa, leva você
  até a tela do SEEU que pergunta, e para ali. Quem marca e salva é você. A
  única vez em que ela mesma habilita é depois de você remover o último
  advogado — é a segunda exceção, logo abaixo.

**As exceções são doze: duas habilitam representação, a terceira troca o
assunto principal, a quarta salva o processo sem mudar nada, a quinta leva
um documento até a assinatura, a sexta finaliza a conclusão retornada, a
sétima cria ou adia um lembrete, a oitava seleciona como atual o endereço
que você acabou de cadastrar, a nona salva a Observação do processo que
você escreveu, a décima troca o juiz da execução, a décima primeira inclui
ou remove um assunto secundário e a décima segunda troca o nível de sigilo
do processo.**

A primeira é a **habilitação de advogado**. Depois que VOCÊ escolhe o advogado
na tela "Seleção de Advogado", a extensão marca a caixa do executado e
**salva** — que é o que se faria à mão, sempre igual, todas as vezes.

A segunda é a **habilitação da Defensoria quando o último advogado sai**.
Quando VOCÊ remove o último advogado do processo e fecha a janela, a extensão
abre a tela de Habilitar/Desabilitar Defensoria, marca a caixa do executado e
**salva** — e avisa na tela que fez isso. Ela confere duas vezes antes: pelo
campo Advogados/Defensoria da capa, e pelo aviso que o próprio SEEU mostra ao
lado da parte quando ainda há advogado habilitado. Havendo qualquer sinal de
advogado, ou mais de um executado, ela não marca nada e diz por quê.

As duas foram pedidas assim por quem usa, e o critério que as sustenta é o
mesmo: **se desfazem na mesma tela**, desmarcando e salvando. E as duas
acontecem na tela, à vista — nada é gravado em segundo plano. Cada uma pode
ser desligada sozinha no ícone da extensão; desligada, a tela fica pronta e
a decisão fica com você.

A terceira é a **troca do assunto principal**. Ao lado do assunto, o botão
"trocar" mostra os quatro assuntos da execução penal (pena privativa de
liberdade, pena restritiva de direitos, medidas de segurança e suspensão
condicional da pena). Quando VOCÊ escolhe um, a extensão abre a Alteração do
Processo **numa cópia fora da tela**, põe o assunto escolhido nos campos do
assunto e envia o formulário do próprio SEEU, com todos os demais campos
exatamente como o servidor os mandou. **É gravação feita fora da tela** — e
por isso confere a resposta do SEEU antes de mudar a capa: se o
assunto dos autos não for o escolhido, ela avisa e não muda nada. Desfaz-se
do mesmo jeito, escolhendo o assunto anterior. O recurso pode ser desligado
no ícone da extensão.

A quarta é o botão **Recarregar**, na barra dos autos. Quando VOCÊ o aperta,
a extensão faz, numa cópia fora da tela, o "Alterar" e o "Salvar" de
Informações Gerais **sem mudar campo nenhum** — é o que se faz à mão para
o SEEU refazer o cálculo dos requisitos temporais e da prescrição. O
formulário vai como o servidor o mandou, e a resposta do SEEU é conferida;
recusada, ela avisa. Depois a tela é recarregada.

A quinta é o botão **Salvar e assinar**, ao lado do "Continuar" do editor
de textos do SEEU — na juntada de documento, na expedição e na minuta.
Quando VOCÊ o aperta, a extensão faz o caminho que se faria à mão, na tela e
à vista: "Continuar", "Salvar" na prévia do documento, "Concluir" (quando a
tela o tem) e "Assinar". **Ela não para na prévia** — o aviso do próprio
botão, ao passar o mouse, diz isso. E **a assinatura não se completa sem
você**: o "Assinar" do SEEU abre a janela "Confirme seu código", com o
código que o SEEU envia ao seu e-mail, e quem o digita é você — cancelando
ali, nada é assinado. Se o SEEU recusar qualquer passo (um campo
obrigatório em branco, por exemplo), ela para e repete a mensagem dele. Na
juntada sem o Tipo Movimento escolhido, ela para antes do "Assinar". Na
minuta, o botão se chama **Salvar e concluir** e o caminho termina no
"Concluir" — quem assina é o magistrado, e ali ela nunca aperta "Assinar".
Para saber se o editor veio de uma minuta, ela anota, no clique em "Digitar
Texto", só isso: minuta ou não. Ao lado dele há o **Continuar e salvar**,
que faz só os dois primeiros passos — "Continuar" e o "Salvar" da prévia — e
para na tela de origem, com o documento salvo: não conclui nem assina.
Depois do "Assinar" pedido pelo Salvar e assinar, quando os autos voltam à
tela a extensão abre a aba Movimentações (e, numa tela de saída do mesmo
processo, aperta o "Voltar para o Processo", segue o link do número do
processo ou, sem nenhum dos dois, aperta o "Voltar" — para chegar a eles); clicando em "Voltar" ou
"Cancelar" na tela do Assinar, ela não faz isso. Para quem anexa um arquivo
em vez de digitar, o mesmo recurso põe o botão **Concluir e assinar** na
tela da expedição, ao lado do "Concluir". Quando VOCÊ o aperta,
ela aperta o "Enviar" (só se houver um arquivo que você escolheu e ainda não
enviou), o "Concluir" (quando a tela o tem) e o "Assinar", com as mesmas
contenções: a janela do código é sua, a recusa do SEEU para o caminho, e ele
não existe na juntada, na minuta nem na carta precatória. E a preferência memorizada que
termina em "Escolher arquivos" abre a janela de arquivos do sistema; o
arquivo quem escolhe é você, e, escolhido, ela aperta o "Enviar" da tela —
cancelando a janela, nada é enviado. O recurso pode ser desligado no ícone
da extensão.

A sexta é o botão **Finalizar Conclusão**, ao lado da pendência "Analisar
Conclusão Retornada". Quando VOCÊ o aperta, a extensão abre aquela
conclusão, aperta o "Finalizar Conclusão Pendente" do SEEU e volta ao
processo. **O SEEU não faz pergunta nesse botão** — por isso quem pergunta é
a extensão, uma vez, antes de sair da capa, dizendo qual conclusão é;
respondendo "Cancelar", nada acontece. Antes de apertar o botão do SEEU, ela
confere ainda que a tela aberta é a do mesmo processo; não sendo, não aperta
nada. O recurso
pode ser desligado no ícone da extensão.

A sétima é o **banco de lembretes**. O "Novo Lembrete" dos autos abre, por
cima deles, os modelos de lembrete que VOCÊ cadastrou ou importou (com o
recurso desligado, o botão fica com o SEEU ou com outra extensão que cuide
dele). Quando você clica num modelo, a extensão abre a tela do Novo Lembrete do SEEU
**numa cópia fora da tela**, preenche a data de ativação, o assunto e o
texto do modelo — com o número de processo e a sequência da movimentação
que você preencheu, quando o modelo os pede — e aperta o Salvar
daquela tela. Antes, confere que a tela é deste processo; depois, confere a
resposta do SEEU e, recusada, avisa. Criado, a tela é recarregada e o
lembrete aparece no quadro, de onde se desativa como qualquer outro. O texto
do modelo entra como texto, nunca como marcação. "Lembrete em branco" leva à
tela do SEEU, como sem a extensão, e o recurso pode ser desligado no ícone.

Na mesma exceção, o **adiar lembrete**: ao lado de cada lembrete da capa, o
calendário. Quando VOCÊ escolhe a data — e, se quiser, muda o assunto — e
aperta Salvar, a extensão abre o lembrete **numa cópia fora da tela**, aperta
Alterar, troca a data de ativação e, se você o mudou, o assunto, e aperta
Salvar — o texto vai como o SEEU o mandou. Antes, confere pelo campo
"Processo" da tela que o lembrete é deste processo; depois, que o SEEU gravou
o que você escolheu, e só então recarrega a tela.

A oitava é o **endereço novo do sentenciado**, pela casinha ao lado da data
de nascimento. A janela abre no cadastro em branco; **quem preenche e salva
é você** — a extensão não escreve campo nenhum. Depois que VOCÊ salva, ela
lê na tela de "Endereço cadastrado com sucesso" o logradouro e o CEP que
você gravou, volta à lista de endereços da parte, **marca aquele endereço e
aperta Confirmar Seleção** — o que o torna o endereço atual —, e fecha a
janela. É o passo que se faria à mão logo depois, sempre igual. Antes, confere
que a janela é deste processo; não achando o endereço na lista, não marca
nada e diz o que falta. Desfaz-se na mesma lista, selecionando outro
endereço. Fechada a janela sem salvar, nada fica armado. Passando o mouse na
casinha, ela lê a ficha numa cópia em segundo plano só para **mostrar o
endereço atual** — nada é guardado além da página aberta. O recurso pode ser
desligado no ícone da extensão.

A nona é a **Observação do processo**. A extensão mostra, numa linha logo
abaixo do Sumário da Pena e em todas as abas, a Observação que está em Informações Gerais —
lida da tela ou, fora dessa aba, na mesma leitura em segundo plano que traz o
juiz da execução. O lápis ao lado abre um painel: para trazer o texto como
está gravado, ela abre a Alteração do Processo **numa cópia fora da tela** e
lê o campo Observação. Só quando VOCÊ aperta "Salvar" no painel ela abre a
Alteração de novo, troca **apenas esse campo** pelo que você escreveu e
envia o formulário do próprio SEEU, com os demais campos exatamente como o
servidor os mandou. **É gravação feita fora da tela** — e por isso ela
confere, na página que o SEEU devolve, o texto que ficou, e avisa se não
conseguir conferir ou se ficou diferente. Fechando o painel ou cancelando,
nada é gravado. Desfaz-se do mesmo jeito, salvando o texto anterior. O
recurso pode ser desligado no ícone da extensão.

A décima é a **troca do juiz da execução**. Clicando no nome do juiz, no
cabeçalho, abre-se um painel com a lista de juízes que a Alteração do
Processo oferece — lida **numa cópia fora da tela**. Quando VOCÊ escolhe um,
a extensão troca **apenas esse campo** e envia o formulário do próprio SEEU,
com os demais campos como o servidor os mandou; confere na página devolvida
o juiz que ficou e só então muda o cabeçalho. Desfaz-se escolhendo o juiz
anterior. O recurso pode ser desligado no ícone da extensão.

A décima primeira são os **assuntos secundários**. Ao lado de cada um há uma
lixeira e, no fim da lista (ou, sem nenhum, no fim da linha do assunto
principal), "+ incluir". A lixeira pergunta na própria linha; quando VOCÊ
responde "Sim", a extensão abre a Alteração do Processo **numa cópia fora da
tela**, marca aquele assunto, faz o "Remover" e o "Salvar" do próprio SEEU e
confere nos autos devolvidos que ele saiu. O "+ incluir" abre um painel de
pesquisa: o termo que VOCÊ digita é pesquisado na Pesquisa de Assuntos do
SEEU, na mesma cópia; escolhido um resultado, ela faz o "Adicionar" do SEEU
(a escolha na pesquisa e a volta à Alteração) e o "Salvar", e confere nos
autos que ele entrou. **É gravação feita fora da tela.** Desfaz-se pelo
caminho oposto. O recurso pode ser desligado no ícone da extensão.

A décima segunda é o **nível de sigilo do processo**. O lápis ao lado do
"Nível de Sigilo" abre um painel com os níveis que a tela de sigilo do SEEU
oferece — lida **numa cópia fora da tela**. Quando VOCÊ escolhe um nível
MAIOR, a extensão troca **apenas esse campo** e envia o formulário do
próprio SEEU sem replicar o sigilo para os documentos, como o SEEU faz.
Quando VOCÊ escolhe um nível MENOR, o painel mostra antes a pergunta do
próprio SEEU — aplicar o nível apenas aos autos (a resposta recomendada)
ou replicá-lo também para os documentos dos autos — e só grava depois da
sua resposta. Nos dois casos confere, na página devolvida, o nível que
ficou, e só então muda a capa. **É gravação feita fora da tela.** Nada é
guardado. Desfaz-se escolhendo o nível anterior. O recurso pode ser
desligado no ícone da extensão.

O menu **Ordenar Cumprimentos**, na barra dos autos, não é exceção: ele
abre o Ordenar Cumprimentos do SEEU com o tipo que você escolheu já no
seletor e "Necessita Retorno" marcado "Não" — só quando nenhuma das duas
opções veio marcada —, e **para ali**. O resto do formulário e o "Ordenar"
são seus. O mesmo vale para o **Arquivar Processo** do menu das ações da
movimentação: a extensão abre a ação, e quem arquiva é você.

Desativar um lembrete também altera, e continua acontecendo só quando você
aperta o botão.

## O que ela guarda, onde e por quê

Tudo em `chrome.storage.local` — armazenamento do próprio navegador, nesta
máquina:

| O que | Para quê |
|---|---|
| Preferências: quais recursos ficam ligados | Lembrar a sua configuração |
| Regime, as duas data-base (a da progressão e a do livramento), livramento condicional (com a data do deferimento) e previsão de prescrição já lidos, por processo | Mostrar na capa sem repetir a consulta a cada abertura |
| CPF, RJI e data de nascimento já vistos, por processo | Evitar nova visita à ficha da parte |
| Resultado da última leitura da ficha da parte, por processo — quando foi e o que aconteceu (lida, demorou, não abriu) | Não repetir cedo demais uma leitura que falhou, e explicar a falha; não contém dado da parte |
| Número de cada processo criminal e se a guia é provisória ou definitiva, com a data da leitura | Mostrar na aba Processos Criminais sem abrir a página de cada processo a cada vez |
| Observações de cada pena ativa e frações de cada desmembramento lido, pelo rótulo do nó na árvore (processo, processo criminal, pena), com a data da leitura | Mostrar na aba Processos Criminais — as Observações abaixo da pena, as frações ao passar o mouse — sem abrir a página de cada pena a cada vez |
| Número do processo e o horário em que uma página de pena ou desmembramento dele foi aberta ou salva (só dos últimos dois dias) | Saber que as frações e Observações guardadas daquele processo podem ter mudado, e relê-las |
| Quantos outros processos de Execução da Pena o apenado tem, por processo, com a data da leitura | Realçar a aba Outros Processos do Apenado sem abri-la a cada visita |
| Nome do juiz da execução, por processo, com a data da leitura | Mostrá-lo ao lado do Juízo em todas as abas do processo — ele só aparece na aba Informações Gerais |
| Agrupador da conclusão, sequência e título do movimento de conclusão e o texto da pendência, por processo, com a data da leitura (só do último dia) | Mostrá-los ao lado da pendência "Conclusão" sem reabrir a pré-análise a cada troca de aba |
| Texto da Observação do processo (o de Informações Gerais), por processo, com a data da leitura (só do último dia) | Mostrá-lo no cabeçalho em todas as abas — ele só aparece na aba Informações Gerais |
| Identificador interno da pessoa no BNMP (apagado pela borracha ao lado de "Ficha no BNMP") | Abrir a ficha direto, sem passar pela busca |
| Local de prisão lido no SIPE, com a data da leitura e como foi identificado (CPF, RJI ou escolha sua, pelo botão "É esta pessoa") | Mostrar na capa sem consultar de novo |
| Consulta pendente ao BNMP (processo, CPF ou RJI, e o nome da parte) | Levar a busca até a janela do BNMP e conferir, na ficha aberta, se é a pessoa certa; apagada assim que usada. O nome só aparece na mensagem que avisa quando a ficha é de outra pessoa |
| Os seis últimos passos da busca da ficha no BNMP — hora, tela e o que aconteceu (filtrou, achou a pessoa, abriu a ficha, conferiu) | A janela do BNMP não tem o ícone da extensão; é assim que o Diagnóstico, tirado no SEEU, sabe onde a busca parou. Não contém CPF, nome nem outro dado da pessoa |
| Posição e tamanho das janelas auxiliares | Reabrir onde você deixou |
| O número interno (do navegador) da janela do Navegar e da janela dos documentos — em `chrome.storage.session`, que se apaga ao fechar o navegador | Pôr o PDF seguinte numa aba da mesma janela, e manter no mesmo monitor o PDF clicado dentro dela; não é dado de processo |
| Onde abrem o Navegar e os PDFs — como o SEEU faz, numa aba nova, num dos monitores ou o automático —, escolhido na pergunta do primeiro clique ou no ícone | Abrir sempre do mesmo jeito, sem perguntar de novo |
| Se a consulta automática do Status BNMP está parada, e desde quando | Não insistir numa consulta que abre a página do BNMP |
| As atribuições (fora as de vara) em que um clique seu trouxe o status do BNMP — só o nome da atribuição, como "distribuidor" | Passar a consultar sozinha nelas |
| Os modelos do banco de lembretes que você cria ou importa — assunto, texto e em quantos dias o lembrete ativa | Criar lembretes sem sair dos autos (o texto aparece para você conferir antes). Saem desta máquina só no arquivo que você mesmo exportar, para levar a outro computador ou compartilhar |
| As preferências que você memoriza nos formulários do SEEU — por tela (juntada, dados do cumprimento e da conclusão, audiência, instaurar incidente, Ordenar Cumprimentos, Enviar Concluso, Intimar Partes, Realizar Remessa), com o nome que você der: as escolhas (listas, opções, caixas e campos de busca como Tipo Movimento), o texto da Descrição do documento e os prazos em dias. No Ordenar Cumprimentos, no Intimar Partes e no Realizar Remessa, também os demais textos da tela que você preencheu (como Orientações/Observações) e as partes marcadas — guardadas só pela **posição** na lista (a primeira, a segunda…), nunca pelo nome ou número da parte. Nunca datas | Preencher a tela de novo num clique; nada é salvo nem enviado pela extensão |
| Lista dos recursos da própria extensão | Montar a tela do ícone; não é dado de processo |
| Quais gavetas da tela do ícone você deixou abertas | Reabri-las do mesmo jeito; não é dado de processo |

Quando uma nova leitura mostra que uma informação deixou de existir no sistema
— uma previsão de prescrição apagada, por exemplo —, o que estava guardado é
substituído, e a capa deixa de mostrá-la.

Há ainda **quarenta e seis registros temporários** gravados na própria aba
(`sessionStorage`). Todos existem pela mesma razão: clicar numa aba do SEEU
recarrega a página, e o que um caminho precisa lembrar do outro lado desse
recarregamento não pode ficar na memória, que a recarga destrói. Todos somem
quando a aba do navegador é fechada.

**O que está em curso** — a juntada do RESPE em andamento e
o clique em "Assinar" dentro da janela dela; a ação de movimentação pedida; o
incidente a cadastrar; a dispensa de arquivo a fazer do outro lado da
redistribuição; o cadastro — de processo criminal, evento ou incidente — a
abrir em alteração, e se ele já foi salvo — para o "Voltar" da tela seguinte; as juntadas a marcar para dispensa, a identificação
interna das que foram marcadas, o endereço do processo para voltar a ele, em
que passo isso está e a aba para onde voltar depois; a Defensoria a habilitar, quando o
último advogado sai; o atalho de advogados ou de
Defensoria pedido; a escolha de advogado anotada; o lembrete em desativação;
a ficha do BNMP a abrir depois do login; o tipo de perfil reconhecido no cabeçalho, quando é de advogado ou da Defensoria; o cumprimento para expedir que se pediu para analisar ou remover — número do processo, o nome do item na capa, em que passo está e o endereço dos autos para voltar; o tipo de cumprimento escolhido no menu Ordenar Cumprimentos, até a janela abrir; o passo do "Finalizar Conclusão" em curso, com o número do processo e o endereço dos autos para voltar; o nome do sentenciado e o da mãe, lidos da capa, para a Pesquisa de Sentenciado do botão "Pesquisar processos" — apagados assim que a janela da pesquisa os usa, ou em um minuto; o passo do "Salvar e assinar" em curso — só o nome do passo e a hora, sem o texto do documento — e se o editor veio de uma minuta; e o cadastro de CPF a abrir na Parte do
Processo, com a aba de onde se saiu e se o CPF já foi confirmado — para voltar
aos autos depois.

**Onde você estava** — os campos que identificam o processo aberto (os do
formulário dos próprios autos, com o número dele) e o nome da aba
Movimentações, guardados a cada passagem pelos autos para que a volta
depois do "Salvar e assinar" os abra direto nessa aba, numa carga só; a
marca dessa volta (o número do processo e quantos passos já deu), posta no
clique em "Assinar" e apagada na chegada, na desistência ou em dez minutos;
os processos cujas informações já foram mostradas
nesta visita (para não escondê-las de novo a cada troca de aba); o número do
processo aberto nesta aba e desde quando, a hora do último clique que
gravou algo e a do último que pode ter mudado o juiz (sem o que foi gravado)
— é o que diz se o que se leu em segundo plano ainda vale; o endereço da tela
de Alteração do Processo, visto em Informações Gerais, para o botão de trocar
o assunto funcionar nas outras abas do mesmo processo; o nome da
última aba do processo que você abriu
(`Movimentações`, `Partes`), a aba de onde um atalho saiu, e se a janela que
ele abriu chegou a ficar na tela. São três nomes de aba e um sim/não: é o que
permite devolver você ao lugar em que estava quando a janela fecha.

**O que ainda falta fazer ou dizer** — se houve um clique em "Remover" na
janela de advogados e, por isso, se é preciso conferir ao fechá-la se o
processo ficou sem ninguém habilitado; os números dos
processos criminais cuja página foi aberta, para reler se a guia é provisória
ou definitiva ao voltar à árvore; quantas vezes seguidas a leitura do regime falhou neste processo, para espaçar as tentativas; se falta a leitura de conferência que se faz logo depois de uma gravação, porque o SEEU recalcula os prazos um pouco depois de gravar; se a cópia dos autos veio sem abas nesta sessão, para as leituras irem direto pelo caminho que funciona; uma explicação a mostrar na primeira tela
depois de uma navegação; duas marcas de que um aviso técnico já saiu no
console nesta sessão; o maior tamanho de página que a lista de peças do BNMP
oferece; e quatro linhas para o Diagnóstico — em que passo parou a última
dispensa de juntadas, quanto a tela da redistribuição rolou, o que a volta
depois de salvar um incidente decidiu, e os passos do atalho de advogados e
da conferência da Defensoria. As oito últimas
não guardam dado de processo nenhum.

**Cópia de segurança.** Pelo ícone, "Exportar e importar…" abre uma página da
própria extensão que baixa um arquivo com o que você marcar — as chaves dos
recursos, a escolha de monitor, o banco de lembretes, as preferências
memorizadas nas telas — e importa esse arquivo de volta, mostrando antes o
que ele traz e gravando só o que você marcar — parte por parte, ou modelo
por modelo e preferência por preferência. **Nenhum dado de processo vai no arquivo**, e ele só sai desta máquina
se você o levar.

**Nada disso sai da máquina.** A sincronização de contas do Chrome não é usada
nesta versão.

## Quem tem acesso

Só você, no seu navegador. O autor da extensão não recebe, não vê e não tem
como ver nenhum desses dados.

## Como apagar

Desinstalar a extensão apaga tudo o que ela guardou. Para limpar sem
desinstalar, use as ferramentas do próprio navegador para dados de extensões.

## Alterações nesta política

Se uma versão futura passar a guardar ou transmitir algo diferente, esta
página é atualizada antes, e a data no topo muda junto.

## Contato

pbrandelero@gmail.com
