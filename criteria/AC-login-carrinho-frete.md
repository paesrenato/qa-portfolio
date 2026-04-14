# 📌 Critérios de Aceite em Gherkin

---

# 🔐 Funcionalidade 1 — Login

## 🧾 User Story

> Como usuário, quero fazer login no site para acessar minha conta.

---

## ✅ AC 01 — Login com credenciais válidas

```gherkin
Cenário: Login com credenciais válidas
  Dado que o usuário acessa a página inicial do site https://www.kabum.com.br/
  E clica em "Minha conta"
  E informa credenciais válidas
  Quando clica no botão "Avançar"
  Então o sistema deve autenticar o usuário com sucesso
  E o usuário deve ser redirecionado para sua conta
```

---

## ❌ AC 02 — Login com credenciais inválidas

```gherkin
Cenário: Login com credenciais inválidas
  Dado que o usuário acessa a página inicial do site https://www.kabum.com.br/
  E clica em "Minha conta"
  E informa credenciais inválidas
  Quando clica no botão "Avançar"
  Então o sistema não deve autenticar o usuário
  E deve exibir a mensagem "Credenciais inválidas"
```

---

## ⚠️ AC 03 — Login com campos vazios

```gherkin
Cenário: Login com campos obrigatórios vazios
  Dado que o usuário acessa a página inicial do site https://www.kabum.com.br/
  E clica em "Minha conta"
  E não preenche os campos de login
  Quando clica no botão "Avançar"
  Então o sistema não deve autenticar o usuário
  E deve exibir a mensagem "Preencha os campos obrigatórios"
```

---

# 🛒 Funcionalidade 2 — Carrinho de Compras

## 🧾 User Story

> Como cliente, quero gerenciar produtos no carrinho para realizar compras.

---

## ➕ AC 01 — Adicionar produto ao carrinho

```gherkin
Cenário: Adicionar produto ao carrinho
  Dado que o cliente acessa o site https://www.kabum.com.br/
  E visualiza um produto disponível
  Quando clica em "Adicionar ao carrinho"
  Então o produto deve ser incluído no carrinho
  E o sistema deve exibir o carrinho atualizado
```

---

## ➖ AC 02 — Remover produto do carrinho

```gherkin
Cenário: Remover produto do carrinho
  Dado que o cliente possui um produto no carrinho
  Quando acessa o carrinho de compras
  E clica no botão de remover produto
  Então o produto deve ser removido do carrinho
  E o carrinho deve ser atualizado
```

---

# 🚚 Funcionalidade 3 — Frete

## 🧾 User Story

> Como cliente, quero que o frete seja calculado corretamente para minha compra.

---

## 🎁 AC 01 — Frete grátis para compras ≥ 50€

```gherkin
Cenário: Aplicar frete grátis
  Dado que o cliente possui produtos no carrinho
  E o valor total da compra é maior ou igual a 50 euros
  Quando informa o endereço de entrega
  Então o sistema deve calcular o frete como 0 euros
  E deve exibir a informação de "Frete grátis"
```

---

## 💸 AC 02 — Frete pago para compras < 50€

```gherkin
Cenário: Calcular frete para compras abaixo de 50 euros
  Dado que o cliente possui produtos no carrinho
  E o valor total da compra é menor que 50 euros
  Quando informa o endereço de entrega
  Então o sistema deve calcular o frete com base no CEP informado
  E deve exibir o valor do frete corretamente
```