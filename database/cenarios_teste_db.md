# 🧪 Cenários de Teste - E-commerce (SQL)

Este documento apresenta cenários de teste validados por queries SQL em um e-commerce fictício.

---

## 📌 Cenário 1: Pedidos pendentes criados em 2026-04-21

**Dado** que existem pedidos criados na data atual  
**Quando** consulto os pedidos no sistema  
**Então** devo obter apenas pedidos com status `pending` criados em 2026-04-21  

```sql
SELECT * 
FROM orders 
WHERE status = 'pending' 
  AND (created_at) = ('2026-04-21');
```

---

## 📌 Cenário 2: Usuários sem e-mail cadastrado

**Dado** todos os usuários cadastrados  
**Quando** consulto o campo de e-mail  
**Então** devo encontrar usuários com e-mail nulo ou vazio  

```sql
SELECT *
FROM users
WHERE email IS NULL
   OR email = '';
```

---

## 📌 Cenário 3: Produtos com estoque zerado

**Dado** todos os produtos cadastrados  
**Quando** verifico o estoque  
**Então** devo encontrar produtos com estoque igual a zero  

```sql
SELECT *
FROM products
WHERE stock = 0;
```

---

## 📌 Cenário 4: Pedidos com cupom aplicado

**Dado** todos os pedidos realizados  
**Quando** verifico o campo de cupom  
**Então** devo obter apenas pedidos com cupom aplicado  

```sql
SELECT *
FROM orders
WHERE coupon IS NOT NULL
  AND coupon <> '';
```

---

## 📌 Cenário 5: Total de pedidos por status

**Dado** todos os pedidos realizados  
**Quando** agrupo os pedidos por status  
**Então** devo obter o total de pedidos em cada status  

```sql
SELECT status,
       COUNT(*) AS total_pedidos
FROM orders
GROUP BY status;
```

---
