# 📘 Documentação da API --- ServeRest

**Base URL:**\
https://serverest.dev

------------------------------------------------------------------------

## 🔐 Cenário 1 --- Login do Usuário

**Endpoint:** `/login`\
**Método:** `POST`

### ✅ Resposta de Sucesso

-   **Status Code:** `200 OK`
-   **Mensagem:** `login realizado com sucesso`

``` json
{
  "message": "Login realizado com sucesso",
  "authorization": "Bearer <token_jwt>"
}
```

------------------------------------------------------------------------

## 👤 Cenário 2 --- Criar Usuário Administrador

**Endpoint:** `/usuarios`\
**Método:** `POST`

### ✅ Resposta de Sucesso

-   **Status Code:** `201 Created`
-   **Mensagem:** `usuário cadastrado com sucesso`

``` json
{
  "message": "Usuário cadastrado com sucesso",
  "id": "GptUCWmKbEa7mljp"
}
```
------------------------------------------------------------------------

## 📦 Cenário 3 --- Listar Produtos

**Endpoint:** `/produtos`\
**Método:** `GET`

### ✅ Resposta de Sucesso

-   **Status Code:** `200 OK`

``` json
{
  "quantidade": 6,
  "produtos": []
}
```

------------------------------------------------------------------------

## ➕ Cenário 4 --- Cadastrar Produto

**Endpoint:** `/produtos`\
**Método:** `POST`

### ⚠️ Sem autenticação

-   **Status Code:** `401 Unauthorized`

``` json
{
  "message": "Token de acesso ausente, inválido ou expirado"
}
```

### ✅ Com autenticação

**Header:** Authorization: Bearer `<token>`{=html}

-   **Status Code:** `201 Created`

``` json
{
  "message": "Cadastro realizado com sucesso",
  "id": "<id_produto>"
}
```

------------------------------------------------------------------------

## ❌ Cenário 5 --- Deletar Produto

**Endpoint:** `/produtos/{id}`\
**Método:** `DELETE`

### ⚠️ Tentativa incorreta

-   **Status Code:** `405 Method Not Allowed`

``` json
{
  "message": "Necessário id do produto e token do usuário"
}
```

### ✅ Requisição correta

-   **Status Code:** `200 OK`

``` json
{
  "message": "Registro excluído com sucesso"
}
```
------------------------------------------------------------------------