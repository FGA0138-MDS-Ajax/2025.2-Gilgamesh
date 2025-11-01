# Documento de Arquitetura 

## Visão Geral

| Campo | Valor |
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

O presente documento descreve a arquitetura do sistema “Apoia+”, uma aplicação móvel desenvolvida com o objetivo de conectar pessoas dispostas a doar para instituições sociais e ONGs cadastradas, promovendo o engajamento solidário e facilitando o acesso a campanhas de apoio em diferentes regiões. O sistema busca centralizar informações sobre campanhas ativas, simplificar o processo de doação e fortalecer a visibilidade das organizações sociais, alinhando-se a objetivos de desenvolvimento sustentável, como redução das desigualdades e erradicação da pobreza.

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

A escolha da arquitetura em MVT é uma consequência direta da adoção dos frameworks Django e Flutter, que foram selecionados com base nas necessidades do projeto e no plano de capacitação da equipe.  

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

> **Nota:** Se você tiver a Figura 1 e a Figura 2, adicione o caminho da imagem aqui (ex: `![Diagrama de Arquitetura](img/figura1.png)`).

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

| Módulo (App) | Razão Lógica | Componentes Principais |
| :--- | :--- | :--- |
| **Autenticação** (`autenticacao`)  | Gerenciar cadastro, login e segurança  | Model: Usuário. View: RegisterView, LoginView. |
| **ONGs** (`ongs`) | Permite o CRUD de perfis de ONGs e a visualização pública  | Model: Usuário (tipo_usuario:ong). View: ONGView. |
| **Gestão de Eventos** (`eventos`)  | Permite a criação de eventos pela ONG e a inscrição de voluntários  | Model: Evento, Participação. View: EventoView, ParticipacaoView. |
| **Administração**  | Gerencia usuários e configurações do sistema [ | Utiliza o módulo `django.contrib.admin`. |

#### 2.6.2 Módulos do Sistema (Frontend - Flutter) 

| Módulo (App) | Telas | Serviços |
| :--- | :--- | :--- |
| **Autenticação**  | TelaLogin, TelaCadastroUsuario, TelaCadastroONG  | **AuthService** (chama HTTP para LoginView e RegisterView). |
| **ONGs e Eventos**  | Home, TelaListarEventos, TelaListarONGs, TelaDetalharEvento, TelaPerfilONG, TelaGerenciarEventos  | **EventoService** (Chama /eventos), **ONGService** (Chama /ongs). |

#### 2.6.3 Comunicação entre Módulos (Interfaces) 

* **APIs REST:** O Backend (Django) expõe endpoints RESTful (ex: `/api/v1/eventos`) que o Frontend (Flutter) consome via requisição HTTPS.
* **Banco de Dados:** PostgreSQL é acessado **apenas** pelo Backend (Django). O Frontend (Flutter) nunca se comunica diretamente com o banco de dados.

#### 2.6.4 Diagrama de Classes 

As entidades centrais são **Usuário**, **ONG**, **Evento** e **Participação**.

* A classe **Usuário** é a base para qualquer pessoa no sistema.
* Existe uma relação **um-para-um (1:1)** entre **Usuário** e **ONG**, onde o Usuário responsável é vinculado à ONG através do atributo `id_responsavel`.
* Um usuário do tipo ONG pode cadastrar múltiplos **Eventos** (**1:N**).
* A relação **muitos-para-muitos (N:M)** entre **Usuários** e **Eventos** é resolvida através da classe associativa **Participacao**.
* A classe **Participacao** conecta Usuário e Evento (usando `id_usuario`, `id_evento`) e armazena atributos da inscrição, como `status_confirmacao`.

#### 2.6.5 Diagrama de Pacotes 

O sistema é estruturado segundo uma arquitetura em camadas, dividida em três principais níveis: Camada de Apresentação, Camada de Lógica de Negócios e Camada de Dados.

| Camada | Responsabilidade | Pacotes Principais |
| :--- | :--- | :--- |
| **Apresentação**  | Interface do sistema com o usuário (telas e componentes visuais)  | TelaLogin, TelaCadastroUsuário, TelaHome, TelaListaEventos, TelaGerenciarEventos, etc. |
| **Lógica de Negócios**  | Centraliza regras, processamentos, validações e controles que definem o comportamento do sistema  | Controle de Usuário, Controle de Evento, CRUD de Perfis. |
| **Dados**  | Armazenamento, recuperação e persistência das informações  | **PostgreSQL** (SGBD Relacional) , **Django** (ORM e integração). |

### 2.7 Visão de Dados (MER) 

O modelo entidade-relacionamento representa a estrutura lógica dos dados do software Apoia+, descrevendo as entidades do sistema e a cardinalidade entre elas.

#### Entidades do Sistema 
| Entidades | Descrição |
| :--- | :--- |
| **Usuário** | Representa os usuários cadastrados (ONGs ou Voluntários). |
| **Evento** | Armazena informações sobre os eventos criados (nome, data, vagas, etc.). |
| **Participação** | Representa o vínculo e é o intermediário entre um usuário e um evento. |

#### Relação e Cardinalidade 

| Entidade A | Relação | Entidade B | Cardinalidade |
| :--- | :--- | :--- | :--- |
| Usuário | Cria | Evento | 1:N (uma ONG cria/edita vários eventos) |
| Usuário | Participa | Evento | N:N (um voluntário participa de vários eventos, um evento tem vários voluntários) |
| Participação | Associa | Usuário e Evento | Resolve a relação N:N (intermediário) |

#### Atributos das Tabelas 

##### Tabela: `usuario` 

| Atributos | Tipo de Dados | Chave | Descrição |
| :--- | :--- | :--- | :--- |
| `id_usuario` | INT | PK | Identificador único do usuário  |
| `nome` | VARCHAR(50) | | Nome do usuário  |
| `email` | VARCHAR(50) | | E-mail utilizado para login  |
| `tipo_usuario` | VARCHAR(20) | | Define o tipo de usuário (voluntario ou ong)  |
| `descricao_ong` | TEXT | | Descrição institucional da ONG (apenas para ONGs)  |
| `necessidades_ong` | TEXT | | Necessidades atuais da ONG (apenas para ONGs)  |
| `ong_id` | INT | FK $\rightarrow$ Usuário.id\_usuario | Identifica a ONG responsável pelo evento |

##### Tabela: `evento` 

| Atributos | Tipo de Dados | Chave | Descrição |
| :--- | :--- | :--- | :--- |
| `id_evento` | INT | PK | Identificador único do evento  |
| `nome_evento` | VARCHAR(150) | | Nome do evento |
| `data_evento` | DATE | | Data de realização do evento  |
| `vagas_total` | INT | | Número total de vagas disponíveis  |
| `numero_participantes` | INT | | Quantidade atual de participantes inscritos  |

##### Tabela: `participacao` 

| Atributos | Tipo de Dados | Chave | Descrição |
| :--- | :--- | :--- | :--- |
| `id_participacao` | INT | PK | Identificador único da participação  |
| `usuario_id` | INT | FK $\rightarrow$ Usuário.id\_usuario | Identifica o voluntário participante |
| `evento_id` | INT | FK $\rightarrow$ Evento.id\_evento | Identifica o evento em que o voluntário se inscreveu |
| `data_participacao` | DATE | | Data da inscrição ou confirmação de presença  |

### 2.8 Visão de Implantação 

O software será implantado em uma **infraestrutura de nuvem** para garantir alta disponibilidade, segurança e escalabilidade.

* **Servidor de Aplicação:** Será hospedado em um ambiente **Linux**, utilizando provedores como **Render, Railway ou AWS**, que suportam nativamente Django e PostgreSQL.
* **Backend:** Desenvolvido com **Django** (Python) em conjunto com **Django Rest Framework (DRF)**, fornecendo uma API RESTful robusta e segura.
* **Frontend:** Desenvolvido em **Flutter** (Dart), um framework multiplataforma para criar interfaces responsivas e consistentes em dispositivos móveis (Android e iOS) e web (PWA).
* **Banco de Dados:** Utilizará **PostgreSQL**, hospedado em uma instância separada na nuvem para maior segurança e isolamento.

A arquitetura final é composta por três camadas principais:

1.  **Frontend (Flutter)** – interface com o usuário.
2.  **Backend (Django/DRF)** – lógica e API RESTful.
3.  **Banco de Dados (PostgreSQL)** – armazenamento de informações.

### 2.9 Restrições Adicionais 

#### 2.9.1 Restrições de Acesso 

O software é acessado diretamente pelo aplicativo, mas requer **autenticação do usuário** para realizar ações como criar ou participar de eventos.

#### 2.9.2 Usabilidade 

O sistema deve ser **intuitivo** para ambos os perfis: o usuário com pouco conhecimento tecnológico e o usuário que possui conhecimentos na área.

#### 2.9.3 Segurança de Dados 

É essencial proteger os dados de ONGs e as informações pessoais dos usuários.

* Todo envio de dados será realizado com **conexão segura**, utilizando técnicas de criptografia.
* O acesso é feito mediante **senha pessoal**, evitando uso não autorizado.
* Essas medidas seguem boas práticas de segurança recomendadas pela **OWASP** (Open Web Application Security Project) para aplicativos móveis.

## 3. Bibliografia 

* DATAFLAIR TEAM. **Django architecture: understanding MVT pattern with a real-time Example**. DataFlair, 2023.. Disponível em: https://data-flair.training/blogs/django-architecture/. Acesso em: 31 de outubro 2025.
* OPEN WEB APPLICATION SECURITY PROJECT (OWASP). **Mobile application security verification standard (MASVS)**. 2023. Disponível em: https://owasp.org/www-project-mobile-security. Acesso em: 30 de outubro 2025.
* SERRANO, Milene. **Arquitetura de software: visão geral**. \[Apresentação de slides\]. Material de aula não publicado. Brasília: Universidade de Brasília, 2025.
