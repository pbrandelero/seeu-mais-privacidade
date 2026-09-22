# Política de Privacidade — SEEU+

*Última atualização: 21 de setembro de 2026 · versão 1.5.0*

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
cálculo: as frações da progressão com a data em que cada uma é alcançada, e a
conta do livramento —, previsão de prescrição das guias, penas e a situação de
cada uma, quem representa a parte, pendências de análise de juntada, situação
de peças no BNMP e local de prisão no SIPE.

Na ficha de uma pessoa no BNMP, ela lê também o CPF exibido ali, para conferir
se a ficha aberta é mesmo a da parte daquele processo — ver "o que ela faz por
conta própria".

Ela só age em seis endereços — `seeu.pje.jus.br`, `seeutreino.pje.jus.br` e
`seeuintegra.pje.jus.br` (as três bases do SEEU: produção, treino e testes),
`bnmp.pdpj.jus.br`, `sipe.sejus.ro.gov.br` e `sipe.treinamento.ro.gov.br`. Em
qualquer outra página, o código não é sequer carregado.

**Ela não tem acesso ao seu histórico de navegação, aos seus favoritos nem ao
conteúdo de outras abas.** As duas únicas permissões que ela pede são
`storage`, para guardar as suas preferências e as leituras já feitas, e
`scripting`, para reinjetar os próprios scripts em abas já abertas depois de
uma atualização e para acionar, na página do SEEU, funções que a própria
página define — as mesmas que os links dela acionam.

## O que ela faz por conta própria

Estas ações acontecem sem você pedir, e todas dentro dos sistemas oficiais:

- ao abrir a capa de um processo, ela **consulta o status no BNMP**, que é o
  mesmo clique que você daria;
- para ler o regime, as data-base, o livramento condicional e a previsão de
  prescrição — que só existem atrás da aba Informações Adicionais —, ela
  **carrega uma cópia da mesma página do processo fora da tela** e lê de lá,
  para não mexer na tela em que você está trabalhando. Essa leitura é refeita
  sempre que algo pode ter mudado — ao sair de qualquer aba do processo e
  voltar à capa, e quando uma janela do SEEU se fecha sobre ela —, para o
  valor mostrado ser o de agora e não o de antes da sua alteração. Se
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
- na aba Processos Criminais, **abre fora da tela a página de cada processo
  criminal**, pelo link que a própria árvore traz, para ler se a guia é
  provisória ou definitiva. Uma vez por processo criminal; a provisória é
  relida uma vez por dia, porque vira definitiva com o trânsito em julgado;
- na aba Processos Criminais, **abre a árvore de penas** e recolhe as que não
  estão ativas, usando as funções de abrir e fechar da própria página. É só
  exibição: nada é alterado, e você pode abrir ou fechar qualquer ramo à mão
  depois;
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

Sete caminhos da extensão terminam em tela de alteração. Todos começam num
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
- **redistribuir**: abre a redistribuição, dispensa sozinha o arquivo da tela
  do relatório — que não tem arquivo nenhum a juntar — e **para na tela das
  opções**, em branco. Comarca, competência, tipo e motivo são escolha sua, e
  não há clique em Finalizar;
- **alterar um cadastro da aba Processos Criminais**: abre o processo criminal,
  a pena ou o desmembramento **já no formulário de alteração**, sem preencher
  campo nenhum e sem salvar;
- **alterar um evento ou incidente**: nas abas Eventos, Incidentes Concedidos,
  Não-Concedidos e Pendentes, abre o item **já no formulário de alteração** —
  do mesmo jeito, sem preencher nem salvar;
- **remover um evento ou incidente**: nas mesmas abas, a lixeira ao lado do
  item abre o item e aperta Remover. **Quem decide é você**: o próprio SEEU
  pergunta se você confirma a remoção, e é a única pergunta — a extensão não
  responde a ela;
- **dispensar as juntadas pendentes de análise**: abre a tela de Análise de
  Juntadas e **marca as juntadas deste processo** — só as dele: uma linha que se
  declara de outro processo não é marcada, e você é avisado. Ela aperta
  Dispensar, e **é o próprio SEEU que pergunta** se você confirma — a extensão
  não responde a essa pergunta. Confirmada — o que ela confere vendo a tela
  recarregar sem as juntadas marcadas —, ela abre o processo e volta à aba em
  que você estava; recusada, nada muda;
- **habilitar ou desabilitar a Defensoria**: pelo atalho da capa, leva você
  até a tela do SEEU que pergunta, e para ali. Quem marca e salva é você. A
  única vez em que ela mesma habilita é depois de você remover o último
  advogado — é a segunda exceção, logo abaixo.

**As exceções são duas, e as duas habilitam representação.**

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
| Identificador interno da pessoa no BNMP | Abrir a ficha direto, sem passar pela busca |
| Local de prisão lido no SIPE, com a data da leitura | Mostrar na capa sem consultar de novo |
| Consulta pendente ao BNMP (processo, CPF ou RJI, e o nome da parte) | Levar a busca até a janela do BNMP e conferir, na ficha aberta, se é a pessoa certa; apagada assim que usada. O nome só aparece na mensagem que avisa quando a ficha é de outra pessoa |
| Os seis últimos passos da busca da ficha no BNMP — hora, tela e o que aconteceu (filtrou, achou a pessoa, abriu a ficha, conferiu) | A janela do BNMP não tem o ícone da extensão; é assim que o Diagnóstico, tirado no SEEU, sabe onde a busca parou. Não contém CPF, nome nem outro dado da pessoa |
| Posição e tamanho das janelas auxiliares | Reabrir onde você deixou |
| Lista dos recursos da própria extensão | Montar a tela do ícone; não é dado de processo |

Quando uma nova leitura mostra que uma informação deixou de existir no sistema
— uma previsão de prescrição apagada, por exemplo —, o que estava guardado é
substituído, e a capa deixa de mostrá-la.

Há ainda **vinte e oito registros temporários** gravados na própria aba
(`sessionStorage`). Todos existem pela mesma razão: clicar numa aba do SEEU
recarrega a página, e o que um caminho precisa lembrar do outro lado desse
recarregamento não pode ficar na memória, que a recarga destrói. Todos somem
quando a aba do navegador é fechada.

**O que está em curso** — o processo a reler, ou a dispensa de relê-lo logo depois de uma janela de advogados ou da Defensoria, que não mexem no sumário; a juntada do RESPE em andamento e
o clique em "Assinar" dentro da janela dela; a ação de movimentação pedida; o
incidente a cadastrar; a dispensa de arquivo a fazer do outro lado da
redistribuição; o cadastro — de processo criminal, evento ou incidente — a
abrir em alteração; as juntadas a marcar para dispensa, a identificação
interna das que foram marcadas, o endereço do processo para voltar a ele, em
que passo isso está e a aba para onde voltar depois; a Defensoria a habilitar, quando o
último advogado sai; o atalho de advogados ou de
Defensoria pedido; a escolha de advogado anotada; o lembrete em desativação; e
a ficha do BNMP a abrir depois do login.

**Onde você estava** — o nome da última aba do processo que você abriu
(`Movimentações`, `Partes`), a aba de onde um atalho saiu, e se a janela que
ele abriu chegou a ficar na tela. São três nomes de aba e um sim/não: é o que
permite devolver você ao lugar em que estava quando a janela fecha.

**O que ainda falta fazer ou dizer** — se houve um clique em "Remover" na
janela de advogados e, por isso, se é preciso conferir ao fechá-la se o
processo ficou sem ninguém habilitado; os números dos
processos criminais cuja página foi aberta, para reler se a guia é provisória
ou definitiva ao voltar à árvore; uma explicação a mostrar na primeira tela
depois de uma navegação; duas marcas de que um aviso técnico já saiu no
console nesta sessão; o maior tamanho de página que a lista de peças do BNMP
oferece; e duas linhas para o Diagnóstico — em que passo parou a última
dispensa de juntadas e quanto a tela da redistribuição rolou. As seis últimas
não guardam dado de processo nenhum.

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
