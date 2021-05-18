# DSVendas - back end

https://fabricio-macedo-dsvendas.netlify.app/

DsVendas é uma aplicação que analisa o desempenho de vendedores em diferentes perspectivas, trazendo informações sobre o valor total de vendas além do número de clientes visitados e negócios fechados.
  
# Modelo Conceitual
![Modelo Conceitual](https://github.com/fabriciio95/arquivos-read-me/blob/master/arquivos-dsvendas/modelo-conceitual.png)
                     
# Padrão camadas adotado
![Padrão camadas](https://github.com/fabriciio95/arquivos-read-me/blob/master/arquivos-dsvendas/padrao-camadas.png)
                  
# Tecnologias utilizadas
- Java
- Spring Boot
- Spring Data JPA
- Spring Security
- Maven

# Arquitetura
- REST

# Implantação em produção
**Para acessar a aplicação clique no link abaixo e aguarde alguns instantes até o servidor no Heroku onde a API está implantada inicializar para que os dados apareçam.**
- [DSVendas](https://fabricio-macedo-dsvendas.netlify.app)
- Banco de dados: Postgresql

# Testando a API no Heroku
Pré-requisitos: Postman

## Buscando todos vendedores cadastrados
Para realizar uma busca de todos vendedores cadastrados no banco de dados você deve fazer uma requisição utilizando o método GET do protocolo HTTP pela URL:
```url
  https://vendasds.herokuapp.com/sellers
```
Dessa maneira será retornado o status 200 e no corpo uma lista em formato JSON contendo objetos com atributos **id** e **name** de cada um dos vendedores cadastrados.
                     
![All-sellers](https://github.com/fabriciio95/arquivos-read-me/blob/master/arquivos-dsvendas/request-all-sellers.png)                  
               
## Buscando vendas realizadas de forma paginada
Para realizar uma busca de todas as vendas realizadas de forma paginada, você deve fazer uma requisição utilizando o método GET do protocolo HTTP pela URL:
```url
  https://vendasds.herokuapp.com/sales?page=0&size=20&sort=date,desc
```
**Sendo que é possivel passar parâmetros na url para manipular o resultado da paginação onde:**
- **page :** É o número da página que deseja obter os dados.
- **size :** É o número máximo de elementos que a página deve conter.
- **sort :** Estabelece uma ordenação na paginação a partir de um atributo dos objetos pertencentes a lista.
- **,desc :** Estabelece que a ordenação seja feita de forma decrescente ou **asc** para crescente.

Dessa maneira será retornado o status 200 e no corpo um objeto com o atributo **content** que é uma lista com os objetos páginados além de outros atributos com informações sobre a paginação.

![Pagination](https://github.com/fabriciio95/arquivos-read-me/blob/master/arquivos-dsvendas/request-pagination.png)               
               
## Buscando o soma de todas as vendas por vendedor
Para realizar uma busca da soma de todas as vendas realizadas por vendedor, você deve fazer uma requisição utilizando o método GET do protocolo HTTP pela URL:
```url
  https://vendasds.herokuapp.com/sales/amount-by-seller
```
Dessa maneira será retornado o status 200 e no corpo uma lista em formato JSON contendo objetos com atributos **sellerName** e **sum** de cada um dos vendedores cadastrados.

![Soma Vendas](https://github.com/fabriciio95/arquivos-read-me/blob/master/arquivos-dsvendas/request-amount-by-seller.png)
               
## Buscando todas as visitas e negócios fechados por vendedor
Para realizar uma busca das visitas e negócios fechados de todos vendedores, você deve fazer uma requisição utilizando o método GET do protocolo HTTP pela URL:
```url
  https://vendasds.herokuapp.com/sales/success-by-seller
```
Dessa maneira será retornado o status 200 e no corpo uma lista em formato JSON contendo objetos com atributos **sellerName**, **visited** e **deals** de cada um dos vendedores cadastrados.

![Visitas e Negócios Fechados](https://github.com/fabriciio95/arquivos-read-me/blob/master/arquivos-dsvendas/request-success-by-seller.png)
                               
**Lembrando que caso o servidor não esteja ativo no Heroku as primeiras requisições podem não funcionar, então apenas faça uma requisição e aguarde alguns instantes para que o servidor seja inicializado no Heroku.**

## Autor

Fabricio Siqueira Macedo

https://linkedin.com/in/fabricio-siqueira-macedo
               
