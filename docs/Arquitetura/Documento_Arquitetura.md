# Documento de Arquitetura 

## Visão Geral

|  |  |
| :--- | :--- |
| **Projeto** | Apoia+  |
| **Disciplina** | Métodos de Desenvolvimento de Software (MDS)  |
| **Versão** | 1.0  |

## Histórico de Revisão 

| Data | Versão | Descrição | Autor(es) |
| :--- | :--- | :--- | :--- |
| 30/10 | 1.0 | Tópico 1.1 | Ester |
| 30/10 | 1.0 | Tópico 1.2 | Artur  |
| 30/10 | 1.0 | Tópicos 2.1, 2.2, 2.8 | Edson  |
| 30/10 | 1.0 | Tópico 2.3 | Lucas  |
| 30/10 | 1.0 | Tópico 2.4 | Guilherme Carvalho  |
| 31/10 | 1.0 | Tópico 2.6 | Edson e Lucas  |
| 31/10 | 1.0 | Tópico 2.7 | Guilherme Carvalho  |
| 31/10 | 1.0 | Tópico 2.8 | Artur e Ester  |
| 31/10 | 1.0 | Revisão ABNT | Maria Luana  |

## Autores 

| Matrícula | Nome | Descrição do papel assumido na equipe | % de contribuição ao trabalho (*) |
| :--- | :--- | :--- | :--- |
| 232024527 | Artur | |  |
| 232025730 | Edson | |  |
| 241012211 | Ester | |  |
| 241011822 | Guilherme C | |  |
| | Guilherme | |  |
| 231026456 | Lucas | |  |
| 231012002 | Luis Fernando | |  |
| 241011448 | Maria Luana | |  |
| 190129344 | Paulo Vinicius | |  |
| 241011878 | Thauany | |  |
| 241012392 | Vinicius | |  |

## 1. Introdução 

### 1.1 Propósito 

Este documento descreve a visão arquitetural abrangente do Apoia+, desenvolvido como parte de um projeto acadêmico da disciplina de Métodos de Desenvolvimento de Software (MDS), no segundo semestre de 2025. O propósito é registrar as decisões arquiteturais tomadas durante o planejamento e implementação do sistema, servindo como um guia para desenvolvedores e testadores.

Ele descreve as escolhas tecnológicas, os padrões de design e a decomposição de componentes adotados para atender aos requisitos específicos de conexão entre voluntários e ONGs no DF, facilitando a organização e participação em eventos para um desenvolvimento coeso e um produto escalável.

### 1.2 Escopo

O presente documento descreve a arquitetura do sistema **“Apoia+”**, uma aplicação móvel desenvolvida com o objetivo de conectar pessoas dispostas a doar para instituições sociais e ONGs cadastradas, promovendo o engajamento solidário e facilitando o acesso a campanhas de apoio em diferentes regiões. O sistema busca centralizar informações sobre campanhas ativas, simplificar o processo de doação e fortalecer a visibilidade das organizações sociais, alinhando-se a objetivos de desenvolvimento sustentável, como redução das desigualdades e erradicação da pobreza.

O escopo do projeto abrange o desenvolvimento de uma aplicação leve, acessível, responsiva e intuitiva, compatível tanto com dispositivos móveis quanto navegadores web, e que permita:

* O cadastro e autenticação de usuários (doadores e representantes de ONGs);
* O cadastro e a gestão de ONGs e campanhas de arrecadação;
* A busca e visualização de pontos de apoio e campanhas próximas;
* O acompanhamento do status das doações;
* A visualização de relatórios e indicadores sociais, facilitando a transparência e o engajamento;
* A comunicação entre usuários e ONGs por meio de um sistema de mensagens ou contato direto;
* A criação e divulgação de eventos por parte das ONGs cadastradas, com a possibilidade de usuários visualizarem e escolherem participar ou não.

Dessa forma, o Apoia+ visa criar um ambiente digital de impacto social positivo, promovendo a solidariedade e tornando o processo de doação mais simples, transparente e acessível a todos.

## 2. Representação Arquitetural 

### 2.1 Definições

O sistema seguirá uma arquitetura em camadas, com o modelo arquitetural escolhido **MVT (Model-View-Template)** com o Framework **Django**.

### 2.2 Justificativa 

A escolha da arquitetura em MVT é uma consequência direta da adoção dos frameworks **Django** e **Flutter**, que foram selecionados com base nas necessidades do projeto e no plano de capacitação da equipe.  

Derivada da arquitetura MVC, que possui como princípios a organização e a reutilização de código, a abordagem MVT do Django é adequada aos requisitos de nosso produto. Será principalmente por meio do Django que a lógica de negócios (Controller) e a estrutura de dados (Model) serão implementadas, o que é ideal para construir a API RESTful que o sistema necessita. 

Concluímos que esta arquitetura de backend se integra bem ao cliente desenvolvido em Flutter, que consumirá os endpoints (rotas da API) gerados pelo Django. 

Dessa forma, acreditamos que essa escolha será vantajosa não apenas em termos de organização, mas também por facilitar o desenvolvimento, a manutenção, os testes e as possíveis modificações futuras no projeto. 

### 2.3 Detalhamento 

O padrão arquitetural adotado para o desenvolvimento do sistema Apoia+ é o **MVT (Model-View-Template)**, implementado com o framework Django. Esse modelo segue o princípio da arquitetura em camadas, promovendo a separação de responsabilidades, a modularização do código e a facilidade na manutenção e evolução do sistema. 

Assim como o padrão MVC, o MVT organiza a aplicação em três componentes principais: Model, View e Template, adaptando o papel do Controller para o próprio framework, simplificando a estrutura de comunicação entre as camadas. 

O **Model** representa a camada de acesso e manipulação dos dados, concentrando a lógica de negócios e as regras de persistência da aplicação. No Apoia+, essa camada é responsável por gerenciar as informações armazenadas no banco de dados, como registros de usuários e ONGs, registros do status de doações e relatórios de eventos. 

A **View** é a camada que processa as requisições e retorna as respostas apropriadas ao usuário. Ela funciona como intermediária entre o Model e o Template, sendo responsável por aplicar as regras de negócio, processar formulários, realizar consultas no banco de dados e definir qual Template dever ser renderizado. Nesse caso, a View atua como o Controller do padrão MVC, gerenciando o fluxo de navegação do sistema, controlando ações como autenticação de usuários, criação de eventos e visualização de relatórios. 

Por último, a camada de **Template** é responsável pela apresentação das informações ao usuário final. Ela define a estrutura visual das páginas HTML, integrando dados enviados pela View e elementos de design definidos pela equipe para a interface. 


***

![Diagrama de Arquitetura, Elaborado por: Lucas Itacamby](imagens/Representacao_Arquitetura.png)

**Fonte:** elaborado por Lucas Chaves Itacaramby (2025)

***

### 2.4 Metas e Restrições Arquiteturais 

* **Disponibilidade:** O sistema deve visar uma disponibilidade de 99,5%, garantindo que os dados dos usuários estejam seguros, íntegros e acessíveis sempre que necessários .
* **Padrões de codificação:** O código deve seguir as melhores práticas de codificação para Python/Django (PEP 8).
* **Manutenibilidade:** O sistema deve ser modular e possuir baixo acoplamento entre os componentes em visão de um projeto mais fácil de se manter e realizar alterações.
* **Segurança:** As APIs desenvolvidas no backend Django devem seguir as melhores práticas possíveis e passar em testes como aqueles definidos pelo OWASP
* **Versionamento:** O padrão usado para realizar mudanças no código e utilizar a ferramenta Git eficientemente será o **Git Flow**.

Todos os elementos mencionados contribuem para um desenvolvimento de software mais ágil e eficiente, no qual os membros da equipe permanecem alinhados na codificação e nas metas estabelecidas. Em última instância, esses objetivos e restrições visam garantir um produto confiável e proporcionar uma experiência satisfatória ao usuário.

### 2.5 Backlog do Produto (Escopo do Produto) 

No escopo do projeto ‘Apoia+’, a equipe decidiu por uma aplicação mobile para Android com intuito de suprir a necessidade de voluntários e de Organizações Não Governamentais (ONGs) em causas humanitárias, mais especificamente em causas envolvendo indivíduos em situação de rua.

Assim, o produto de software tem como funcionalidades:

* Sistema de cadastro e login;
* Perfil público com informações pertinentes para voluntários e ONGs;
* CRUD (Create, Read, Update e Delete) de eventos para ONGs;
* Divulgação de eventos usando a localização do usuário como referência;
* Possibilidade de se inscrever antecipadamente em eventos;
* Geração de uma lista com participantes com presença confirmada no evento;
* Mapa interativo para melhor experiência dos usuários.

Essas funcionalidades surgem para permitir uma maior integração entres voluntários e ONGs, assim centralizando distribuição de informações em apenas um canal de comunicação. A partir disso, a escolha arquitetural do produto surge em razão da experiencia prévia da equipe, assim escolhendo modelo **MVC (Model–View–Controller)**, entretanto essa escolha juntamente com a decisão de adotar o *framework* Django, estabeleceu o padrão final sendo o **MTV (Model–Template–View)**, que é uma variação do tradicional MVC para o framework escolhido.

### 2.6 Visão Lógica 

O sistema Apoia+ é organizado em uma arquitetura **Cliente-Servidor em camadas**. A camada de Servidor (**Backend**) segue o padrão **MVT** (Model-View-Template) com Django , e a camada de Cliente (**Frontend**) é um aplicativo móvel (**Flutter**) que consome os dados do servidor.

#### 2.6.1 Módulos do Sistema (Backend - Django) 

| **Módulo (App)**                  | **Razão Lógica**                                                   | **Componentes Principais**                                                  |
| :-------------------------------- | :----------------------------------------------------------------- | :-------------------------------------------------------------------------- |
| **Autenticação** (`autenticacao`) | Gerenciar cadastro, login e segurança                              | **Model:** Usuário.<br>**View:** RegisterView, LoginView.                   |
| **ONGs** (`ongs`)                 | Permite o CRUD de perfis de ONGs e a visualização pública          | **Model:** Usuário (tipo_usuario: ong).<br>**View:** ONGView.               |
| **Gestão de Eventos** (`eventos`) | Permite a criação de eventos pela ONG e a inscrição de voluntários | **Model:** Evento, Participação.<br>**View:** EventoView, ParticipacaoView. |
| **Administração**                 | Gerencia usuários e configurações do sistema                       | Utiliza o módulo `django.contrib.admin`.                                    |


#### 2.6.2 Módulos do Sistema (Frontend - Flutter) 

| Módulo (App) | Telas | Serviços |
| :--- | :--- | :--- |
| **Autenticação**  | TelaLogin, TelaCadastroUsuario, TelaCadastroONG  | **AuthService** (chama HTTP para LoginView e RegisterView). |
| **ONGs e Eventos**  | Home, TelaListarEventos, TelaListarONGs, TelaDetalharEvento, TelaPerfilONG, TelaGerenciarEventos  | **EventoService** (Chama /eventos), **ONGService** (Chama /ongs). |

#### 2.6.3 Comunicação entre Módulos (Interfaces) 

* **APIs REST:** O Backend (Django) expõe endpoints RESTful (ex: `/api/v1/eventos`) que o Frontend (Flutter) consome via requisição HTTPS.
* **Banco de Dados:** PostgreSQL é acessado **apenas** pelo Backend (Django). O Frontend (Flutter) nunca se comunica diretamente com o banco de dados.

#### 2.6.4 Diagrama de Classes 

O diagrama de classes apresentado a seguir ilustra a estrutura básica do sistema Apoia+, mostrando os principais componentes e como eles se relacionam entre si. Essa representação permite visualizar os elementos fundamentais que compõem a aplicação, incluindo as entidades principais, suas características e as conexões existentes. 
***

![Diagrama de classes, Elaborado por: Edson Pereira](imagens/UML_Classes.png)

**Fonte:** elaborado por Edson Pereira (2025)

***

As entidades centrais são **Usuário**, **ONG**, **Evento** e **Participação**.

* A classe **Usuário** é a base para qualquer pessoa no sistema.
* Existe uma relação **um-para-um (1:1)** entre **Usuário** e **ONG**, onde o Usuário responsável é vinculado à ONG através do atributo `id_responsavel`.
* Um usuário do tipo ONG pode cadastrar múltiplos **Eventos** (**1:N**).
* A relação **muitos-para-muitos (N:M)** entre **Usuários** e **Eventos** é resolvida através da classe associativa **Participacao**.
* A classe **Participacao** conecta Usuário e Evento (usando `id_usuario`, `id_evento`) e armazena atributos da inscrição, como `status_confirmacao`.

---

### 2.6.5 Diagrama de Pacotes

O sistema é estruturado segundo uma arquitetura em camadas, dividida em três principais níveis: **Camada de Apresentação**, **Camada de Lógica de Negócios** e **Camada de Dados**. Essa organização visa promover a separação de responsabilidades, facilitando a manutenção, a escalabilidade e o entendimento geral da aplicação.

---

#### 1. Camada de Apresentação

A **Camada de Apresentação** é responsável pela interface do sistema com o usuário, englobando todas as telas e componentes visuais da aplicação. Nela estão definidos os módulos de interação e navegação, que permitem que usuários e ONGs acessem, visualizem e manipulem as informações disponíveis.

Os principais pacotes dessa camada incluem:

* **TelaLogin**: ponto central de acesso ao sistema, conectando tanto usuários quanto ONGs.
* **TelaCadastroUsuário** e **TelaCadastroONG**: responsáveis pelo processo de registro de novos usuários e organizações.
* **TelaHome**: página inicial, que serve como hub de navegação para outras funcionalidades.
* **TelaListaEventos** e **TelaDetalharEvento**: exibem eventos disponíveis e suas informações detalhadas.
* **TelaGerenciarEventos**: voltada à administração de eventos por parte das ONGs.
* **TelaListarONGs** e **TelaPerfilONG**: possibilita visualizar e acessar informações sobre as ONGs cadastradas.

---

#### 2. Camada de Lógica de Negócios

A **Camada de Lógica de Negócios** centraliza as regras e operações que definem o comportamento do sistema. É nessa camada que ocorrem os processamentos, validações e controles que sustentam o funcionamento das funcionalidades apresentadas ao usuário.

Os pacotes principais dessa camada são:

* **Controle de Usuário**: gerencia o fluxo de cadastro, autenticação e atualização de informações dos usuários.
* **Controle de Evento**: responsável pelas operações relacionadas aos eventos como criação, edição, exclusão e listagem.
* **CRUD de Perfis**: implementa as operações básicas de persistência (Criar, Ler, Atualizar e Deletar) para os perfis de usuários e ONGs.

---

#### 3. Camada de Dados

A **Camada de Dados** é responsável pelo armazenamento, recuperação e persistência das informações manipuladas pela aplicação. Ela integra o sistema com o banco de dados e define a estrutura de acesso e manipulação dos dados de forma segura e eficiente.

Os pacotes que compõem essa camada são:

* **PostgreSQL**: sistema gerenciador de banco de dados relacional utilizado para armazenar todas as informações da aplicação como dados de usuários, ONGs e eventos.
* **Django**: framework que intermedeia a comunicação entre a camada de lógica de negócios e o banco de dados, oferecendo ferramentas para o mapeamento objeto-relacional (ORM), além de facilitar a criação de modelos, migrações e consultas.


 
***

![Diagrama de pacotes, Elaborado por: Lucas Itacamby](imagens/Diagrama_Pacotes.png)

**Fonte:** elaborado por Lucas Itacamby (2025)

***
### 2.7 Visão de Dados (MER) 

O modelo entidade-relacionamento representa a estrutura lógica dos dados do software Apoia+, descrevendo as entidades do sistema, além de descrever a cardinalidade entre as entidades.

#### Tabela 1: Entidades do Sistema 
| Entidades | Descrição |
| :--- | :--- |
| **Usuário** | Representa os usuários cadastrados no sistema, podendo ser ONGs ou Voluntários, armazenando dados essenciais  |
| **Evento** | Armazena as informações sobre os eventos criados, como nome, descrição, data, local, vagas e número de participantes  |
| **Participação** | Representa o vínculo entre um usuário e um evento, atuando como intermediário  |

#### Tabela 2: Relação e Cardinalidade entre Entidades

| Entidade A | Relação | Entidade B | Cardinalidade |
| :--- | :--- | :--- | :--- |
| Usuário | Cria | Evento | 1:N (uma ONG cria/edita vários eventos) |
| Usuário | Participa | Evento | N:N (um voluntário participa de vários eventos, um evento tem vários voluntários) |
| Participação | Associa | Usuário e Evento | Resolve a relação N:N (intermediário) |

A partir da definição do papel assumido pelas entidades descritas, associamos estas às respectivas tabelas, de forma que cada linha (registro) da tabela representa uma instância da entidade, e cada coluna representa um atributo dessas entidades. Além disso, surge a necessidade de especificar os atributos de cada tabela para auxiliar o desenvolvimento. 

#### Tabela 3: Tabelas do Sistema
| Entidades | Descrição |
| :--- | :--- |
| **Usuário** | Implementação da entidade Usuário e seus atributos no banco de dados  |
| **Evento** | Implementação da entidade Evento e seus atributos no banco de dados  |
| **Participação** | Implementação da entidade Participação e seus atributos no banco de dados   |

##### Tabela 4 : Atributos de usuário

| Atributos | Tipo de Dados | Chave | Descrição |
| :--- | :--- | :--- | :--- |
| `id_usuario` | INT | PK | Identificador único do usuário  |
| `nome` | VARCHAR(50) | | Nome do usuário  |
| `email` | VARCHAR(50) | | E-mail utilizado para login  |
| `senha` | VARCHAR(50) | | Senha cripstografada do usuário  |
| `localizacao` | VARCHAR(50) | | Localização (fixa para ONG, dinâmica para voluntário)  |
| `contato` | VARCHAR(50) | | Telefone ou outro meio de contato |
| `tipo_usuario` | VARCHAR(20) | | Define o tipo de usuário (voluntario ou ong)  |
| `descricao_ong` | TEXT | | Descrição institucional da ONG (apenas para ONGs)  |
| `necessidades_ong` | TEXT | | Necessidades atuais da ONG (apenas para ONGs)  |

##### Tabela 5: Atributos de evento 

| Atributos | Tipo de Dados | Chave | Descrição |
| :--- | :--- | :--- | :--- |
| `id_evento` | INT | PK | Identificador único do evento  |
| `nome_evento` | VARCHAR(150) | | Nome do evento |
| `descricao_evento` | VARCHAR(150) | | Descrição detalhada do evento |
| `data_evento` | DATE | | Data de realização do evento  |
| `localizacao_evento` | VARCHAR(150) | | Local onde o evento ocorrerá |
| `vagas_total` | INT | | Número total de vagas disponíveis  |
| `numero_participantes` | INT | | Quantidade atual de participantes inscritos  |
| `ong_id ` | VARCHAR(150) |FK → Usuário.id_usuario  | Identifica a ONG responsável pelo evento  |

##### Tabela 6 : Atributos de participacao 

| Atributos | Tipo de Dados | Chave | Descrição |
| :--- | :--- | :--- | :--- |
| `id_participacao` | INT | PK | Identificador único da participação  |
| `usuario_id` | INT | FK $\rightarrow$ Usuário.id\_usuario | Identifica o voluntário participante |
| `evento_id` | INT | FK $\rightarrow$ Evento.id\_evento | Identifica o evento em que o voluntário se inscreveu |
| `data_participacao` | DATE | | Data da inscrição ou confirmação de presença  |

### 2.8 Visão de Implantação 

O software será implantado em uma infraestrutura de nuvem, a fim de garantir alta disponibilidade, segurança e escalabilidade. O servidor de aplicação será hospedado em um ambiente Linux, utilizando provedores como Render, Railway ou AWS, que oferecem suporte nativo a aplicações Django e bancos PostgreSQL. Essa escolha elimina a necessidade de infraestrutura física local, reduz custos de manutenção e permite o crescimento do sistema conforme a demanda de usuários aumenta. 

A camada de backend será desenvolvida com o framework **Django**, na **linguagem Python**, em conjunto com o Django Rest Framework (DRF). Essa tecnologia foi escolhida por sua robustez, segurança e grande ecossistema de bibliotecas, além de oferecer suporte nativo para **APIs RESTful**, facilitando a comunicação entre o servidor e o aplicativo **Flutter**. O backend será responsável pela lógica de negócios, autenticação, gerenciamento de campanhas e eventos, e persistência de dados. 

O frontend será desenvolvido em **Flutter**, framework multiplataforma baseado em **Dart**, que permite a criação de uma interface responsiva e consistente tanto para dispositivos móveis (Android e iOS) quanto para web (PWA). Essa escolha reduz a complexidade do projeto, pois um único código atende múltiplos dispositivos, mantendo a identidade visual e a fluidez da experiência do usuário. 

O banco de dados utilizado será o **PostgreSQL**, reconhecido por sua confiabilidade, escalabilidade e suporte a transações complexas. Ele será hospedado em uma instância separada na nuvem, garantindo isolamento dos dados, backup automatizado e maior segurança. A integração entre o Django e o banco será feita por meio do ORM (Object-Relational Mapper) do próprio framework, simplificando consultas e mantendo a integridade relacional do modelo de dados. 

A arquitetura final é composta por três camadas principais:

1.  **Frontend (Flutter)** – interface com o usuário.
2.  **Backend (Django/DRF)** – lógica e API RESTful.
3.  **Banco de Dados (PostgreSQL)** – armazenamento de informações.

Essa arquitetura garante que o Apoia+ seja modular, escalável, seguro e de fácil manutenção, permitindo que novas funcionalidades sejam adicionadas sem comprometer o desempenho do sistema. 

### 2.9 Restrições Adicionais 

#### 2.9.1 Restrições de Acesso 

O software é acessado diretamente pelo aplicativo, mas requer **autenticação do usuário** para realizar ações como criar ou participar de eventos.

#### 2.9.2 Usabilidade 

O sistema deve ser **intuitivo** para ambos os perfis: o usuário com pouco conhecimento tecnológico e o usuário que possui conhecimentos na área.

#### 2.9.3 Segurança de Dados 

Como o aplicativo irá coletar dados de ONGs e informações pessoais dos usuários, é essencial proteger essas informações.

* Todo envio de dados será realizado com **conexão segura**, utilizando técnicas de criptografia.
* O acesso é feito mediante **senha pessoal**, evitando uso não autorizado.
* Essas medidas seguem boas práticas de segurança recomendadas pela **OWASP** (Open Web Application Security Project) para aplicativos móveis.

## 3. Bibliografia 

* DATAFLAIR TEAM. Django architecture: understanding MVT pattern with a real-time Example. DataFlair, 2023. Disponível em: https://data-flair.training/blogs/django-architecture/. Acesso em: 31 de outubro 2025. 
* OPEN WEB APPLICATION SECURITY PROJECT (OWASP). **Mobile application security verification standard (MASVS)**. 2023. Disponível em: https://owasp.org/www-project-mobile-security. Acesso em: 30 de outubro 2025.
* SERRANO, Milene. **Arquitetura de software: visão geral**. \[Apresentação de slides\]. Material de aula não publicado. Brasília: Universidade de Brasília, 2025.
