# Construtores e Beans

Implementar um sistema que pode recuperar uma lista de livros de uma editora atraves de uma rota GET
A aplicação deverá ser desenvolvida seguindo a seguinte estrutura:

* controller
* service
* repository (mockado)
 
Tambem deverá possuir uma classe de modelo (model) representando cada livro.

Visando fixar o conteudo, seguir os seguintes passos:
* desenvolver a primeira versão sem utilizar o contexto de injeção de dependencia do Spring
* refatorar o codigo produzido para utilizar injeção de dependencia via construtor, definindo manualmente como os beans da camada Repository serão instanciados, de forma que o nome da editora possa ser recuperado do arquivo application.yml no momento da criação do objeto
