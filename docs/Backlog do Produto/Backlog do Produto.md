# Backlog do Produto - Projeto Apoia+

## 1. Referencial Teórico
> **Definição:** O Backlog do Produto é uma lista de histórias (e outros itens de trabalho relevantes),
ordenada por prioridades. Assim como em XP, as histórias são escritas e priorizadas pelo Dono
do Produto e constituem uma descrição resumida das funcionalidades que devem ser
implementadas no projeto. É importante mencionar ainda que o Backlog do Produto é um
artefato dinâmico, isto é, ele deve ser continuamente atualizado, de forma a refletir mudanças
nos requisitos e na visão do produto. Por exemplo, à medida que o desenvolvimento avança,ideias de novas funcionalidades podem surgir, enquanto outras podem perder importância.
Todas essas atualizações devem ser realizadas pelo Dono do Produto. Na verdade, é o fato de
ser o dono do Backlog do Produto que faz o Dono do Produto receber esse nome. [P.299]*
>
> **Histórias de Usuário:** Portanto, especificações de requisitos por meio de histórias não consistem apenas de duas ou três
sentenças, como alguns críticos de métodos ágeis podem afirmar. A maneira correta de interpretar
uma história de usuário é a seguinte: a história que se escreve no cartão é um lembrete do
representante dos clientes para os desenvolvedores. Por meio dele, o representante dos clientes
declara que gostaria de ver um determinado requisito funcional implementado na próxima iteração
(ou sprint). Mais ainda, durante todo o sprint ele se compromete a estar disponível para refinar a
história e explicá-la para os desenvolvedores. [P.37]*

---

## 2. Histórias de Usuário e Critérios de Aceite

### Épico A: Gestão de ONGs (Ator: Representante da ONG)

**US01 - Cadastro de ONG**
> "Eu, como representante de uma ONG, gostaria de me cadastrar na plataforma, para que eu possa começar a divulgar projetos e receber doações."
* **Critérios de Aceite:**
    * [ ] O sistema deve exigir o preenchimento de: Nome Fantasia, Endereço, CNPJ, UF e Telefone.
    * [ ] Cada conta deverá ter apenas um e-mail vinculado (não permitir duplicidade).
    * [ ] A senha deve ser forte (mínimo 8 caracteres, letras e números).
    * [ ] O CNPJ deve ser validado quanto ao formato e existência.

**US02 - Criação de Eventos**
> "Eu, como representante de uma ONG, gostaria de criar eventos na plataforma, para que possamos aumentar o efetivo de voluntários em nossas ações."
* **Critérios de Aceite:**
    * [ ] É obrigatório o preenchimento da Descrição, Data, Horário e Local.
    * [ ] A data do evento não pode ser anterior à data atual.
    * [ ] O sistema deve permitir definir um número máximo de voluntários.

**US03 - Edição de Eventos**
> "Eu, como representante de uma ONG, gostaria de editar informações sobre eventos na plataforma, para que possamos ter flexibilidade em nossas ações sociais."
* **Critérios de Aceite:**
    * [ ] A edição só é permitida para eventos que ainda não aconteceram.
    * [ ] Se a data ou local forem alterados, os voluntários inscritos devem ser notificados.

**US04 - Cancelamento de Eventos**
> "Eu, como representante de uma ONG, gostaria de cancelar eventos na plataforma, para que eu possa evitar deslocamentos desnecessários em caso de imprevistos."
* **Critérios de Aceite:**
    * [ ] Ao clicar em cancelar, o sistema deve pedir uma confirmação ("Tem certeza que deseja cancelar este evento?").
    * [ ] É obrigatório inserir uma justificativa para o cancelamento.
    * [ ] Todos os voluntários inscritos devem receber um e-mail de aviso imediato.

**US05 - Perfil Informativo**
> "Eu, como representante de uma ONG, gostaria de criar um perfil informativo na plataforma, para que pudéssemos centralizar informações acerca de nossa instituição e mantê-las atualizadas."
* **Critérios de Aceite:**
    * [ ] Permitir upload de logotipo da instituição.
    * [ ] Campo de texto livre para "História da ONG" e "Missão".

**US06 - Gestão de Voluntários**
> "Eu, como representante de uma ONG, gostaria de visualizar a lista de voluntários inscritos em um evento, para que eu possa controlar a presença e organizar a logística da ação."
* **Critérios de Aceite:**
    * [ ] A lista deve exibir Nome, Telefone e E-mail de cada voluntário.
    * [ ] Deve ser possível exportar a lista para PDF ou Excel.

---

### Épico B: Experiência do Voluntário (Ator: Voluntário)

**US07 - Cadastro de Voluntário**
> "Eu, como voluntário, gostaria de me cadastrar na plataforma, para que eu possa me inscrever em eventos."
* **Critérios de Aceite:**
    * [ ] Cadastro simplificado exigindo: Nome completo, E-mail, Senha e Data de Nascimento.
    * [ ] Validação de e-mail único.

**US08 - Pesquisa de Eventos**
> "Eu, como voluntário, gostaria de pesquisar eventos disponíveis, para que possa contribuir com ações sociais."
* **Critérios de Aceite:**
    * [ ] A busca deve permitir filtrar por Cidade/UF.
    * [ ] A busca deve permitir filtrar por causa (ex: Animais, Educação, Saúde).
    * [ ] A listagem deve ordenar eventos por data (mais próximos primeiro).

**US09 - Informações de ONGs**
> "Eu, como voluntário, gostaria de verificar informações sobre ONGs, para que possa contribuir com doações diretamente a elas."
* **Critérios de Aceite:**
    * [ ] O perfil da ONG deve exibir os dados bancários ou chave PIX para doação.
    * [ ] Deve exibir o histórico de eventos realizados pela ONG.

**US10 - Inscrição em Evento**
> "Eu, como voluntário, gostaria de confirmar participação em um evento, para que eu possa garantir minha vaga e receber as instruções de local e horário."
* **Critérios de Aceite:**
   * [ ] Permitir alteração de senha (exigindo a senha antiga).
    * [ ] Permitir alteração de telefone e foto de perfil.

## Fonte:
Marco Tulio Valente. Engenharia de Software Moderna: Princípios e Práticas para Desenvolvimento de Software com Produtividade, Editora: Independente, 2020. Disponível em: <https://https://engsoftmoderna.info/>. Acesso em: 4 dez. 2025.

          
