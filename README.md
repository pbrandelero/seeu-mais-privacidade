# Política de Privacidade — SEEU+

*Última atualização: 26 de agosto de 2026 · versão 1.3.0*

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
parte, CPF, RJI, regime de cumprimento, datas do cálculo da pena, situação de
peças no BNMP e local de prisão no SIPE.

Ela só age em cinco endereços — `seeu.pje.jus.br`, `seeutreino.pje.jus.br`,
`bnmp.pdpj.jus.br`, `sipe.sejus.ro.gov.br` e `sipe.treinamento.ro.gov.br`. Em
qualquer outra página, o código não é sequer carregado.

**Ela não tem acesso ao seu histórico de navegação, aos seus favoritos nem ao
conteúdo de outras abas.** As duas únicas permissões que ela pede são
`storage`, para guardar as suas preferências e as leituras já feitas, e
`scripting`, para reinjetar os próprios scripts em abas já abertas depois de
uma atualização e para acionar, na página do SEEU, uma função que a própria
página define.

## O que ela faz por conta própria

Três coisas acontecem sem você pedir, e todas dentro dos sistemas oficiais:

- ao abrir a capa de um processo, ela **consulta o status no BNMP**, que é o
  mesmo clique que você daria;
- para ler o regime e a data-base — que só existem atrás de uma aba interna do
  SEEU —, ela **carrega uma cópia da mesma página do processo fora da tela** e
  lê de lá, para não mexer na tela em que você está trabalhando;
- ao usar os atalhos do BNMP ou do SIPE, ela **abre uma janela auxiliar** com a
  consulta já preenchida;
- dentro dessa janela do SIPE — e só dentro dela —, ela aciona o botão
  **Compartilhar localização**, que o SIPE passou a exigir antes de deixar
  consultar. A extensão **não responde** ao pedido de permissão do navegador:
  esse é seu, e é ele que decide se a sua localização é compartilhada. Abrindo
  o SIPE numa aba comum, ela não toca nesse botão.

Nenhuma dessas ações altera dado nos sistemas. Ações que alteram — juntar a
situação carcerária, desativar um lembrete — só acontecem quando você pede, e a
juntada **pergunta antes de assinar**, porque assinatura é irreversível.

## O que ela guarda, onde e por quê

Tudo em `chrome.storage.local` — armazenamento do próprio navegador, nesta
máquina:

| O que | Para quê |
|---|---|
| Preferências: quais recursos ficam ligados | Lembrar a sua configuração |
| Regime e data-base já lidos, por processo | Não repetir a consulta a cada abertura da capa |
| CPF e RJI já vistos, por processo | Evitar nova visita à ficha da parte |
| Identificador interno da pessoa no BNMP | Abrir a ficha direto, sem passar pela busca |
| Local de prisão lido no SIPE, com a data da leitura | Mostrar na capa sem consultar de novo |
| Consulta pendente ao BNMP (processo, CPF ou RJI) | Levar a busca até a janela do BNMP; apagada assim que usada |
| Posição e tamanho das janelas auxiliares | Reabrir onde você deixou |
| Lista dos recursos da própria extensão | Montar a tela do ícone; não é dado de processo |

Há ainda seis registros temporários gravados na própria aba
(`sessionStorage`), que existem só para um fluxo atravessar um recarregamento
de página: o processo a reler, o lembrete em desativação, a juntada em
andamento, a ficha do BNMP a abrir depois do login, a ação de movimentação
pedida e o incidente a cadastrar. Todos somem quando a aba é fechada.

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
