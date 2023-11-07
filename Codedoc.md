# Documentação Técnica da API CobSA

## Índice

- [Introdução](#introdução)
- [Autenticação](#autenticação)
- [Erro Handling](#erro-handling)
- [Clientes](#clientes)
  - [Listar Clientes](#listar-clientes)
  - [Obter Cliente](#obter-cliente)
  - [Criar Cliente](#criar-cliente)
  - [Atualizar Cliente](#atualizar-cliente)
  - [Deletar Cliente](#deletar-cliente)
- [Cobranças](#cobranças)
  - [Listar Cobranças](#listar-cobranças)
  - [Obter Cobrança](#obter-cobrança)
  - [Criar Cobrança](#criar-cobrança)
  - [Atualizar Cobrança](#atualizar-cobrança)
  - [Deletar Cobrança](#deletar-cobrança)
- [Modelos](#modelos)
  - [Cliente](#cliente)
  - [Cobrança](#cobrança)
- [Códigos de Resposta](#códigos-de-resposta)

## Introdução

Esta API fornece um conjunto de serviços para a gestão de clientes e suas cobranças. Os endpoints permitem operações CRUD padrão em duas entidades principais: `Cliente` e `Cobrança`.

## Autenticação

Detalhes sobre o método de autenticação utilizado pela API (por exemplo, Bearer Token).

## Erro Handling

Informação sobre como a API trata os erros e as respostas esperadas para os casos de erro.

## Clientes

### Listar Clientes

- **GET** `/customers`
- **Descrição**: Retorna uma lista de todos os clientes.
- **Respostas**:
  - `200 OK`: Sucesso.
  - `500 Internal Server Error`: Erro no servidor.

### Obter Cliente

- **GET** `/customers/{id}`
- **Descrição**: Retorna os detalhes de um cliente específico.
- **Parâmetros**:
  - `id`: ID do cliente (obrigatório).
- **Respostas**:
  - `200 OK`: Sucesso.
  - `404 Not Found`: Cliente não encontrado.
  - `500 Internal Server Error`: Erro no servidor.

### Criar Cliente

- **POST** `/customers`
- **Descrição**: Cria um novo cliente.
- **Body** (application/json):
  ```json
  {
    "nome": "Nome do Cliente",
    "email": "email@cliente.com",
    "document": "cpf ou cnpj",
    "telefone": "999999999"
  }
  ```
- Respostas:
 - `201 Created`: Cliente criado com sucesso.
 - `400 Bad Request`: Dados de entrada inválidos.
 - `500 Internal Server Error`: Erro no servidor.

## Atualizar Cliente

**PUT** `/customers/{id}`  
**Descrição**: Atualiza os detalhes de um cliente existente.  
**Parâmetros**:
- `id`: ID do cliente (obrigatório).

**Body** (application/json):  

```json
{
  "nome": "Novo Nome",
  "email": "novoemail@cliente.com",
  "telefone": "988888888"
}
```
## Respostas

- `200 OK`: Cliente atualizado com sucesso.
- `404 Not Found`: Cliente não encontrado.
- `400 Bad Request`: Dados de entrada inválidos.
- `500 Internal Server Error`: Erro no servidor.

## Deletar Cliente

**DELETE** `/customers/{id}`  
**Descrição**: Remove um cliente do sistema.  
**Parâmetros**:

- `id`: ID do cliente (obrigatório).

## Respostas

- `200 OK`: Cliente excluído com sucesso.
- `404 Not Found`: Cliente não encontrado.
- `500 Internal Server Error`: Erro no servidor.

# Cobranças

Detalhes similares aos fornecidos na seção de clientes, adaptados para as cobranças.

## Modelos

### Cliente

Estrutura do objeto `Cliente` com detalhes sobre cada campo (por exemplo, `nome`, `email`, `telefone`).

### Cobrança

Estrutura do objeto `Cobrança` com detalhes sobre cada campo (por exemplo, `valor`, `data_vencimento`, `status`).

## Códigos de Resposta

- `200 OK`: A operação foi bem-sucedida.
- `201 Created`: Um novo recurso foi criado com sucesso.
- `400 Bad Request`: A requisição é inválida ou malformada.
- `404 Not Found`: O recurso solicitado não foi encontrado.
- `500 Internal Server Error`: Ocorreu um erro interno no servidor.



