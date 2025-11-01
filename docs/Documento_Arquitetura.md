\[Apoia+\]

**Documento de Arquitetura**

Versão \[1.1\]

**Histórico de Revisão**

|          |            |               |               |
|----------|------------|---------------|---------------|
| **Data** | **Versão** | **Descrição** | **Autor(es)** |
|     30/10     |     1.0       |      Tópico 1.1          |        Ester       |
|     30/10     |     1.0       |       Tópico 1.2         |        Artur       |
|     30/10     |     1.0       |     Tópico 2.1, 2.1, 2.8           |      Edson         |
|     30/10     |     1.0       |      Tópico 2.3          |       Lucas        |
|     30/10     |     1.0       |      Tópico 2.4          |       Guilherme Carvalho        |
|     31/10     |     1.0       |      Tópico 2.6          |    Edson e Lucas           |
|     31/10     |     1.0       |     Tópico 2.7          |      Guilherme Carvalho         |
|     31/10     |     1.0       |     Tópico 2.8           |     Artur e Ester          |
|     31/10     |     1.0       |     Revisão ABNT           | Maria Luana              |

Autores:

|               |          |                                            |                                            |
|---------------|----------|--------------------------------------------|--------------------------------------------|
| **Matrícula** | **Nome** | **Desccrição do papel assumido na equipe** | % de contribuição ao trabalho (\*)|
|      232024527         |     Artur     |                                            |                                            |
|    232025730           |    Edson      |                                            |                                            |
|      241012211          |    Ester       |                                            |                                            |
|      241011822          |    Guilherme Carvalho       |                                            |                                            |
|      231026456          |    Lucas       |                                            |                                            |
|      231012002          |   Luis Fernando      |                                            |                                            |
|      241011448          |    Maria Luana      |                                            |                                            |
|      190129344          |    Paulo Vinícius       |                                            |                                            |
|      241011878         |    Thauany       |                                            |                                            |
|      241012392        |    Vinícius      |                                            |                                            |


***Lembre-se que o alinhamento de documentos entre entregas Aprender3 e
GIthub é da responsabilide da equipe. Assim sendo, faz parte da
avaliação da entrega.***

**Sumário**

[1 Introdução [4](#introdução)](#introdução)

[1.1 Propósito [4](#propósito)](#propósito)

[1.2 Escopo [4](#escopo)](#escopo)

[2 Representação Arquitetural
[4](#representação-arquitetural)](#representação-arquitetural)

[2.1 Definições [4](#definições)](#definições)

[2.2 Justifique sua escolha.
[4](#justifique-sua-escolha.)](#justifique-sua-escolha.)

[2.3 Detalhamento [4](#detalhamento)](#detalhamento)

[2.4 Metas e restrições arquiteturais
[4](#metas-e-restrições-arquiteturais)](#metas-e-restrições-arquiteturais)

[2.5 Backlog do Produto (escopo do produto)
[4](#backlog-do-produto-escopo-do-produto)](#backlog-do-produto-escopo-do-produto)

[2.6 Visão lógica \<relembrem o material da Profa. Milene Serrano\>
[4](#visão-lógica-relembrem-o-material-da-profa.-milene-serrano)](#visão-lógica-relembrem-o-material-da-profa.-milene-serrano)

[2.7 Visão de Dados (MER) [5](#visão-de-dados-mer)](#visão-de-dados-mer)

[2.8 Visão de Implantação \<relembrem o material da Profa. Milene
Serrano\>
[5](#visão-de-implantação-relembrem-o-material-da-profa.-milene-serrano)](#visão-de-implantação-relembrem-o-material-da-profa.-milene-serrano)

[2.9 Restrições adicionais
[5](#restrições-adicionais)](#restrições-adicionais)

[3 Bibliografia [5](#bibliografia)](#bibliografia)

# Introdução

## Propósito

*Este documento descreve a visão arquitetural abrangente do Apoia+, desenvolvido como parte de um projeto acadêmico da disciplina de Métodos de Desenvolvimento de Software (MDS), no segundo semestre de 2025. O propósito é registrar as decisões arquiteturais tomadas durante o planejamento e implementação do sistema, servindo como um guia para desenvolvedores e testadores. Ele descreve as escolhas tecnológicas, os padrões de design e a decomposição de componentes adotados para atender aos requisitos específicos de conexão entre voluntários e ONGs no DF, facilitando a organização e participação em eventos para um desenvolvimento coeso e um produto escalável.*

## Escopo

O presente documento descreve a arquitetura do sistema “Apoia+”, uma aplicação móvel desenvolvida com o objetivo de conectar pessoas dispostas a doar para instituições sociais e ONGs cadastradas, promovendo o engajamento solidário e facilitando o acesso a campanhas de apoio em diferentes regiões. 

O sistema busca centralizar informações sobre campanhas ativas, simplificar o processo de doação e fortalecer a visibilidade das organizações sociais, alinhando-se a objetivos de desenvolvimento sustentável, como redução das desigualdades e erradicação da pobreza. 

O escopo do projeto abrange o desenvolvimento de uma aplicação leve, acessível, responsiva e intuitiva, compatível tanto com dispositivos móveis quanto navegadores web, e que permita: 

  -O cadastro e autenticação de usuários (doadores e representantes de ONGs); 

  -O cadastro e a gestão de ONGs e campanhas de arrecadação; 

  -A busca e visualização de pontos de apoio e campanhas próximas; 

  -O acompanhamento do status das doações; 

  -A visualização de relatórios e indicadores sociais, facilitando a transparência e o engajamento; 

  -A comunicação entre usuários e ONGs por meio de um sistema de mensagens ou contato direto. 

  -A criação e divulgação de eventos por parte das ONGs cadastradas, com a possibilidade de usuários visualizarem e escolherem participar ou não; 

Dessa forma, o Apoia+ visa criar um ambiente digital de impacto social positivo, promovendo a solidariedade e tornando o processo de doação mais simples, transparente e acessível a todos. 

# Representação Arquitetural

## Definições

O sistema seguirá uma arquitetura *\<nomeie a decisão do grupo a
respeito do estilo arquitetural escolhido na proposta de solução\>*

## Justifique sua escolha.  {#justifique-sua-escolha.}

\<*A justificativa deve levar em conta o que for pertinente nos
documentos Visão do produto e do projeto, e Declaração de escopo do
produto, já entregues\>.*

- *Esses documentos podem ser referenciados para evitar redundâncias,
  mas as partes deles usadas nas definições das arquiteturas devem ser
  ressaltadas, nas referências usadas de forma inequívoca.*

## Detalhamento

*\<Detalhe sua escolha, acrescentando uma figura esquemática que
represente o estilo arquitetural escolhido.  
Instancie os elementos do estilo arquiterural, conforme as suas escolhas
para o sistema sendo desenvolvido pela equipe\>.*

*Além disso, deixe claro na figura e nos comentários explicativos dela
as responsabilidades dos elementos constituintes do estilo arquiteturarl
escolhido e as comunicaçoes entre eles.*

*Deve ser uma imagem que reflita uma visão geral da arquitetura,
tecnologias, protocolos de comunicação.*

## Metas e restrições arquiteturais

*Identifique-as se existirem.Exemplos de metas e restrições podem ser:*

- *O sistema deve responder a 95% das consultas em até 2 segundos*

- *Deve seguir o padrão XHZ para API's.*

- *Deve seguir o padrão "tal" de codificação. Caso o grupo desenvolvolva
  um padrão de codificação específico, ele entre como anexo com todas as
  suas diretrizes.*

- *Outros elementos de importância e interesse para desenvolvedores*

*Todos eles devem ser explicados e justificdos*

## Backlog do Produto (escopo do produto)

*\<Não se trata aqui de repetir o detalhamento do que já foi colocado no
Backlog do Produto no Zenhub, mas sim, de explicar em linhas gerais o
funcionamento do sistema. Para tanto, isso precisa estar diretamente
refletido no backlog do produto, dinâmico, mantido na ferramenta
zenhub.\>*

*Um, ponto importante aqui é ressaltar requisitos que tenham contribuído
na escolha do estilo arquitetural escolhido pela equipe. Neste sentido
vale, inclusive, citar a experiência e conhecimento de integrantes da
quipe, detalhes técnicos, etc\>.*

## Visão lógica \<relembrem o material da Profa. Milene Serrano\> {#visão-lógica-relembrem-o-material-da-profa.-milene-serrano}

*O sistema é subdividido nos seguintes módulos \<listar os módulos\>*

*\<incluir e explicar o diagrama de pacotes uml de cada módulo\>*

*\<explicar como eles se comunicam -- interfaces, protocolos\>*

*\<incluir e explicar um diagrama de classes EM ALTO NÍVEL que
represente como os dados são persistidos pela aplicação\>  
Apresentar e explicar os pacotes que compõem o código da aplicação
(incluir um diagrama de pacotes), subidividindo em:*

- *Camada e apresentação -- interface com usuários (sugere-se um
  protótipo de baixa fidelidade);*

- *Lógica de negócios e regras de negócios -- identificar e explicar*

- *Comunicação com o banco de dados -- identificar e explicar*

## Visão de Dados (MER)

*Apresentar e explicar o modelo Entidade Relacionamento*

- *Principais tabelas*

- *Relações entre as tabelas e suas respectivas cardinalidades*

- *Atributos das entidades*

## Visão de Implantação \<relembrem o material da Profa. Milene Serrano\> {#visão-de-implantação-relembrem-o-material-da-profa.-milene-serrano}

*\<O software será implantado \<descrever e justificar a infraestrurura
de hardware para a implantação do software\>, segundo as tecnologias
\<descrever e justificar\>, assim como o banco de dados (descrever e
justificar)\>.*

## Restrições adicionais

*\< descrever e justificar restrições adicionais ao software. Tais
restrições podem estar relacionadas a aspectos negociais (ex.: É suposto
que o software deve ser usado a partir da Intranet da empresa que, por
sua vez exige a identificação e login do usuário; ou o software é
acessível diretamente pela Internet, mas exige login do usuário; ou o
software é preparado para atender xxx usuários logados
concomitantemente), ou de qualidade de software tais como:*

*Citar, explicar e justificar as características de qualidade relevantes
para o software (usabilidade, Confiabilidade, Portabilidade, etc, etc,
etc)\>*

# Bibliografia

*\<Use padrão ABNT em todos os documentos da disciplina\>.*

[^1]: (\*) -- para cada integrante da equipe, considere sua participação
    tanto no Documento de Arquitetura, quando nos demais documentos já
    entregues pela equipe (Visaão do produto e do projeto; Declaração de
    escopo) e atribua um, percentual. A soma dos percentuais de todos os
    integrantes deve fechar em 100%)
