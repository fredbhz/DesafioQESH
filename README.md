# REQUESTS and RESPONSES

#Tipos de requicição:

ADICIONAR PRODUTO
grpcurl -plaintext -d '{"name": "foo", "price": 10.20}'  localhost:8080 product.v1.ProductService/AddProduct
RESPONSE
{
  "productId": "8b8e27b0-03bc-49eb-bcda-b551a07116da"
}

grpcurl -plaintext -d '{"name": "bar", "price": 5.10}'  localhost:8080 product.v1.ProductService/AddProduct
RESPONSE
{
  "productId": "732b1840-c724-43df-9276-c786dcc41566"
}

DELETAR PRODUTO
grpcurl -plaintext -d '{"product_id": "<ID do foo>"}'  localhost:8080 product.v1.ProductService/DeleteProduct

RESPONSE
{
  "product": {
    "id": "8b8e27b0-03bc-49eb-bcda-b551a07116da",
    "name": "foo",
    "price": 10.2
  }
}

LISTAR PRODUTOS
grpcurl -plaintext -d '{}'  localhost:8080 product.v1.ProductService/ListProducts
RESPONSE
{
  "products": [
    {
      "id": "8b8e27b0-03bc-49eb-bcda-b551a07116da",
      "name": "foo",
      "price": 10.2
    },
    {
      "id": "732b1840-c724-43df-9276-c786dcc41566",
      "name": "bar",
      "price": 5.1
    }
  ]
}