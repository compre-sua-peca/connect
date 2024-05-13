
# Integração CSP Connect

Ao lidar com informações de produtos, assumimos que cada negócio deve definir sua própria estrutura de catálogo. A interação entre Compre Sua Peça e os vendedores é baseada em ofertas, que incluem informações do produto, preço e quantidade em estoque.

Nós enquanto Marketplace recebemos e gerenciamos as ofertas feitas pelos vendedores, decidindo como elas devem ser incorporadas no catálogo por meio de correspondência de SKU.

Aos integradores (Sellers) cabe enviar as ofertas com informações do produto, preço e quantidade em estoque.

## Responsabilidades

### Preços e Promoções

Ao lidar com preços, assumimos que cada negócio deve definir sua **própria estratégia** de precificação.

**Compre Sua Peça**: Recebemos as notificações de alteração de preço e atualizamos os registros de preço conforme necessário.

**Integrador (Sellers)**: Define os preços e promoções a serem aplicados no Marketplace.


### Inventário e Envio

Ao lidar com logística, assumimos que os vendedores gerenciam sua **estratégia de envio**.

**Compre Sua Peça**: Recebe as notificações de alteração de inventário e atualiza o inventário conforme necessário.

**Integrador (Sellers)**: Define políticas de inventário e envio disponíveis para o Compre Sua Peça, envia notificações de alteração de inventário.


### Shelfs e Checkout

O Compre Sua Peça é responsável pelo fluxo de compra e pela realização correta do pedido ao vendedor.

**Compre Sua Peça**: Exibe os produtos em sua loja, realiza pedidos aos vendedores no checkout.

**Integrador (Sellers)**: Recebe pedidos realizados pelo marketplace.
Atendimento de Pedidos

Cada parte interessada é responsável por uma parte do fluxo de pedidos. Mudanças e cancelamentos podem ser feitos dentro de uma janela de tempo específica.


## Diagrama da Integração

![Diagrama de Integração](https://i.ibb.co/xjDdkrD/integra-o.jpg)



## Documentação da API

#### Retorna todos os itens

```http
  GET /api/items
```

| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `api_key` | `string` | **Obrigatório**. A chave da sua API |

#### Retorna um item

```http
  GET /api/items/${id}
```

| Parâmetro   | Tipo       | Descrição                                   |
| :---------- | :--------- | :------------------------------------------ |
| `id`      | `string` | **Obrigatório**. O ID do item que você quer |

#### add(num1, num2)

Recebe dois números e retorna a sua soma.

