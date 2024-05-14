
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

### URL Base

Vamos enviar a URL base com o email e nela vai conter o ID de seller no Marketplace

Genérica: www.urlbase.com/seller_id

Exemplo: www.urlbase.com/superpecas001

#### Enviar Novos Produtos

```http
  POST /product

  EX: www.urlbase.com/superpecas001/product
```

## Product Information

| Campo                     | Valor                                                                                      |
|---------------------------|--------------------------------------------------------------------------------------------|
| **id**                    | 441393295                                                                                  |
| **idMapeamento**          | 1304432                                                                                    |
| **skuMapeamento**         |                                                                                            |
| **nome**                  | Exemplo de produto pai                                                                     |
| **codigo**                | ex-pai                                                                                     |
| **unidade**               | UN                                                                                         |
| **preco**                 | 150.0000                                                                                   |
| **precoPromocional**      | 120.0000                                                                                   |
| **ncm**                   | 1001.10.10                                                                                 |
| **origem**                | 0                                                                                          |
| **gtin**                  | 789116565465                                                                               |
| **gtinEmbalagem**         |                                                                                            |
| **localizacao**           | Corredor A                                                                                 |
| **pesoLiquido**           | 1.000                                                                                      |
| **pesoBruto**             | 1.500                                                                                      |
| **estoqueMinimo**         | 2.00                                                                                       |
| **estoqueMaximo**         | 50.00                                                                                      |
| **idFornecedor**          | 439246919                                                                                  |
| **codigoFornecedor**      |                                                                                            |
| **codigoPeloFornecedor**  | ex-pai-fab                                                                                 |
| **unidadePorCaixa**       | 5                                                                                          |
| **estoqueAtual**          | 0                                                                                          |
| **precoCusto**            | 0.0000                                                                                     |
| **precoCustoMedio**       | 0.0000                                                                                     |
| **situacao**              | A                                                                                          |
| **descricaoComplementar** | <p>Descri\u00e7\u00e3o complementar do produto</p>                                         |
| **obs**                   | Observa\u00e7\u00f5es                                                                      |
| **garantia**              | 30 dias                                                                                    |
| **cest**                  | 10.003.00                                                                                  |
| **sobEncomenda**          | N                                                                                          |
| **marca**                 | Tiny                                                                                       |
| **tipoEmbalagem**         | 2                                                                                          |
| **alturaEmbalagem**       | 21.0                                                                                       |
| **larguraEmbalagem**      | 26.0                                                                                       |
| **comprimentoEmbalagem**  | 1.0                                                                                        |
| **diametroEmbalagem**     | 0.0                                                                                        |
| **classeProduto**         | V                                                                                          |
| **idCategoria**           | 439714230                                                                                  |
| **descricaoCategoria**    | categoria filho 1                                                                          |
| **descricaoArvoreCategoria** | categoria pai > categoria filho 1                                                      |
| **arvoreCategoria**       | [{"id": "439714228", "idPai": 0, "descricao": "categoria pai", "descricaoCompleta": "categoria pai"}, {"id": "439714230", "idPai": "439714228", "descricao": "categoria filho 1", "descricaoCompleta": "categoria pai > categoria filho 1"}] |
| **variacoes**             | [{"id": "441393302", "idMapeamento": "1304433", "skuMapeamento": "", "codigo": "ex-pai-1", "gtin": "789116565465", "preco": "150.0000", "precoPromocional": "120.0000", "estoqueAtual": 0, "grade": [{"chave": "Cor", "valor": "Azul"}, {"chave": "Tamanho", "valor": "P"}], "anexos": []}, {"id": "441393310", "idMapeamento": "1304434", "skuMapeamento": "", "codigo": "ex-pai-2", "gtin": "789116565465", "preco": "150.0000", "precoPromocional": "120.0000", "estoqueAtual": 0, "grade": [{"chave": "Cor", "valor": "Azul"}, {"chave": "Tamanho", "valor": "G"}], "anexos": []}, {"id": "441393318", "idMapeamento": "1304435", "skuMapeamento": "", "codigo": "ex-pai-3", "gtin": "789116565465", "preco": "150.0000", "precoPromocional": "120.0000", "estoqueAtual": 0, "grade": [{"chave": "Cor", "valor": "Branco"}, {"chave": "Tamanho", "valor": "P"}], "anexos": []}, {"id": "441393326", "idMapeamento": "1304436", "skuMapeamento": "", "codigo": "ex-pai-4", "gtin": "789116565465", "preco": "150.0000", "precoPromocional": "120.0000", "estoqueAtual": 0, "grade": [{"chave": "Cor", "valor": "Branco"}, {"chave": "Tamanho", "valor": "G"}], "anexos": []}]  |
| **anexos**                | [{"url": "https:\/\/s3-sa-east-1.amazonaws.com\/tinylocal-testes\/erp\/MzUwMTY3MjMy\/4f6d30a1777b7d6fc294f757b470b6e0.jpeg", "nome": "441393296_headset-steelseries-arctis-3-vermelho.jpeg", "tipo": "jpeg"}]                                                                 |
| **seo**                   | {"title": "", "description": "", "keywords": "", "linkVideo": "", "slug": ""}                |
| **kit**                   | [{"id": 3279328, "quantidade": 2}, {"id": 3274333, "quantidade": 5}]                       |
| **diasPreparacao**        | 5                                                                                          |

```json
 {
	"id": "441393295",
	"idMapeamento": "1304432",
	"skuMapeamento": "",
	"nome": "Exemplo de produto pai",
	"codigo": "ex-pai",
	"unidade": "UN",
	"preco": "150.0000",
	"precoPromocional": "120.0000",
	"ncm": "1001.10.10",
	"origem": "0",
	"gtin": "789116565465",
	"gtinEmbalagem": "",
	"localizacao": "Corredor A",
	"pesoLiquido": "1.000",
	"pesoBruto": "1.500",
	"estoqueMinimo": "2.00",
	"estoqueMaximo": "50.00",
	"idFornecedor": "439246919",
	"codigoFornecedor": "",
	"codigoPeloFornecedor": "ex-pai-fab",
	"unidadePorCaixa": "5",
	"estoqueAtual": 0,
	"precoCusto": "0.0000",
	"precoCustoMedio": "0.0000",
	"situacao": "A",
	"descricaoComplementar": "<p>Descri\u00e7\u00e3o complementar do produto<\/p>",
	"obs": "Observa\u00e7\u00f5es",
	"garantia": "30 dias",
	"cest": "10.003.00",
	"sobEncomenda": "N",
	"marca": "Tiny",
	"tipoEmbalagem": "2",
	"alturaEmbalagem": "21.0",
	"larguraEmbalagem": "26.0",
	"comprimentoEmbalagem": "1.0",
	"diametroEmbalagem": "0.0",
	"classeProduto": "V",
	"idCategoria": "439714230",
	"descricaoCategoria": "categoria filho 1",
	"descricaoArvoreCategoria": "categoria pai > categoria filho 1",
	"arvoreCategoria": [
		{
			"id": "439714228",
			"idPai": 0,
			"descricao": "categoria pai",
			"descricaoCompleta": "categoria pai"
		},
		{
			"id": "439714230",
			"idPai": "439714228",
			"descricao": "categoria filho 1",
			"descricaoCompleta": "categoria pai > categoria filho 1"
		}
	],
	"variacoes": [
		{
			"id": "441393302",
			"idMapeamento": "1304433",
			"skuMapeamento": "",
			"codigo": "ex-pai-1",
			"gtin": "789116565465",
			"preco": "150.0000",
			"precoPromocional": "120.0000",
			"estoqueAtual": 0,
			"grade": [
				{
					"chave": "Cor",
					"valor": "Azul"
				},
				{
					"chave": "Tamanho",
					"valor": "P"
				}
			],
			"anexos": []
		},
		{
			"id": "441393310",
			"idMapeamento": "1304434",
			"skuMapeamento": "",
			"codigo": "ex-pai-2",
			"gtin": "789116565465",
			"preco": "150.0000",
			"precoPromocional": "120.0000",
			"estoqueAtual": 0,
			"grade": [
				{
					"chave": "Cor",
					"valor": "Azul"
				},
				{
					"chave": "Tamanho",
					"valor": "G"
				}
			],
			"anexos": []
		},
		{
			"id": "441393318",
			"idMapeamento": "1304435",
			"skuMapeamento": "",
			"codigo": "ex-pai-3",
			"gtin": "789116565465",
			"preco": "150.0000",
			"precoPromocional": "120.0000",
			"estoqueAtual": 0,
			"grade": [
				{
					"chave": "Cor",
					"valor": "Branco"
				},
				{
					"chave": "Tamanho",
					"valor": "P"
				}
			],
			"anexos": []
		},
		{
			"id": "441393326",
			"idMapeamento": "1304436",
			"skuMapeamento": "",
			"codigo": "ex-pai-4",
			"gtin": "789116565465",
			"preco": "150.0000",
			"precoPromocional": "120.0000",
			"estoqueAtual": 0,
			"grade": [
				{
					"chave": "Cor",
					"valor": "Branco"
				},
				{
					"chave": "Tamanho",
					"valor": "G"
				}
			],
			"anexos": []
		}
	],
	"anexos": [
		{
			"url": "https:\/\/s3-sa-east-1.amazonaws.com\/tinylocal-testes\/erp\/MzUwMTY3MjMy\/4f6d30a1777b7d6fc294f757b470b6e0.jpeg",
			"nome": "441393296_headset-steelseries-arctis-3-vermelho.jpeg",
			"tipo": "jpeg"
		}
	],
	"seo": {
		"title": "",
		"description": "",
		"keywords": "",
		"linkVideo": "",
		"slug": ""
	},
	"kit": [
		{
			"id": 3279328,
			"quantidade": 2
		},
		{
			"id": 3274333,
			"quantidade": 5
		}
	],
	"diasPreparacao": "5"
}
```

#### Retorno 
| Status   |
| :---------- |
| `202`      | 

#### Exemplo de Retorno

```json
[
	{
		"idMapeamento": "1304280",
		"skuMapeamento": "exemplo-1"
	},
	{
		"idMapeamento": "1304281",
		"skuMapeamento": "exemplo-1-1",
		"urlProduto": "https://www.lojaexemplo.com.br/produto/exemplo-1-1",
		"urlImagem": "https://www.lojaexemplo.com.br/produto/exemplo-1-1/principal.jpg"
	},
	{
		"idMapeamento": "1304282",
		"skuMapeamento": "exemplo-1-2",
		"error": "Produto sem marca"
	}
]
```


