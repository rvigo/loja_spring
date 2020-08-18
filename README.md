# loja_spring

Realizar o Fork deste projeto e implementar:

## Rotas:
__/produtos__: GET (cliente consulta produto por id), GET (cliente consulta todos os produtos), POST (cliente compra produto)  
__/estoque__: GET (gestor consulta produto por id), GET (gestor consulta todos os produtos), POST (gestor insere/repõe produtos), PUT (gestor altera informações do produto), DELETE(gestor desativa um produto) 

## Requisitos funcionais:
### Produtos:
* Ao vender um produto, a quantidade de itens no estoque deverá ser atualizada
* Não se deve vender um produto que contenha menos de 5 unidades no estoque
* Não se deve vender um produto em quantidade maior do que a quantidade do estoque
* Ao consultar um unico produto atraves da rota "produtos", retornar 404 caso o valor do estoque seja menor que 5 unidades.
* Ao consultar todos os produtos atraves da rota "produtos", não exibir os itens com estoque menor que 5 unidades.
* A quantidade em estoque e a data da ultima atualização não deverão ser retornadas em nenhuma consulta atraves da rota "produtos".
* Produtos com a o indicador de status "ATIVO" como FALSO não deverão aparecer em consultas atraves da rota "produtos"


### Estoque:
* Não se deve inserir um novo produto com o estoque menor do que 5 unidades
* Ao chamar a rota de delete, o produto deverá ter seu estoque zerado e o indicador "ATIVO" setado para FALSO.
* Todos os registros deverão aparecer nas consultas atraves da rota "estoque"
* Ao repor um produto, a data de ultima reposição deverá ser atualizada com a data atual
* Ao inserir um novo produto, a data da ultima reposição deverá ser preenchida com a data da inserção do registro.
* Nenhum produto deverá ter o preço igual ou menor a 0


### Requisitos Técnicos:
* Os campos do tipo String deverão ter no minimo 3 caracteres e no maximo 20
* O id de cada produto deverá ser unico e do tipo UUID 
* As camadas de repositorio deverão retornar objetos mockados, simulando o acesso ao banco de dados.
(BONUS: usar o banco de dados in memory H2)
* Criar collections no POSTMAN para testar a aplicação e adicionar uma pasta chamada POSTMAN na estrutura do projeto.
* O projeto deverá ser feito utilizando o __Java 8/Spring__
* Nesta etapa, testes unitarios __*não*__ serão necessarios.

Exemplo de payload que será enviado à aplicação em caso de POST/PUT:
```json
{
    "id_produto":"ecc329c3-ee84-45eb-b28c-95b68caca1d5",
    "qtd_estoque":5,
    "preco":6.99,
    "nome_produto":"livro",
    "desc_produto":"qualquer coisa",
    "status_item_ativo": true
}
```

Exemplo de payload que sera devolvido pela aplicação em caso de POST/PUT:
```json
{
    "id_produto":"ecc329c3-ee84-45eb-b28c-95b68caca1d5",
    "qtd_estoque":5,
    "preco":6.99,
    "nome_produto":"livro",
    "desc_produto":"qualquer coisa",
    "data_ultima_atualizacao":"20-12-2020",
    "status_item_ativo": true
}
```
