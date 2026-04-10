# 🧪 Exploratory Testing Findings – KaBuM!

Registro de achados de uma sessão de teste exploratório conduzida no site KaBuM

---

## 📌 Charter 001

| Campo              | Detalhe                                                                                                                           |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------- |
| ID do Charter      | 001                                                                                                                               |
| Área               | Explorar funcionalidades e o fluxo de adição ao carrinho de compras, assim como a aplicação de cupons de desconto                 |
| Missão             | Explorar comportamentos inesperados na busca de produtos, aplicação de filtros e gestão do carrinho de compras                    |
| Duração            | 20 minutos                                                                                                                        |
| Ambiente           | Chrome 146.0.7680.165 (64 bits)                                                                                                   |
| Data               | 28/03/2026                                                                                                                        |
| Tester             | Renato Paes                                                                                                                       |
| Hipóteses iniciais | O total do carrinho pode não atualizar corretamente ao alterar quantidade, filtros combinados podem retornar dados inconsistentes |

---

## 🔍 Heurísticas utilizadas

* CRUD: criação, leitura, atualização e remoção
* Vazio/Cheio/Limite: estados extremos
* Fluxo interrompido: voltar, recarregar e trocar de aba

---

## 🧪 Observações

### OBS-001 – Botão voltar e avançar

* **Área:** Navegação
* **Heurística:** Fluxo interrompido – o que acontece ao voltar e, recarregar
* **Ação:** Uso do botão voltar/avançar
* **Resultado esperado:** Preservar as informações de compras
* **Resultado obtido:** Funcionamento adequado com os itens no carrinho preservado
* **Classificação:** ✅ Funciona como esperado

---

### OBS-002 – Botão adicionar (+) e excluir (-) conforme quantidade no carrinho

* **Área:** Carrinho de compras
* **Heurística:** CRUD: criação, leitura, atualização e remoção
Vazio/Cheio/Limite: Testar campos e itens em estados extremos
* **Ação:** Alterar quantidade
* **Resultado esperado:** Atualizar a quantidade de itens e os respectivos valores no carrinho de compras
* **Resultado obtido:** Adequado funcionamento. Há limitação de quantidade de acordo com as regras do site, porém não apresenta clareza na quantidade do limite, sendo necessário adicionar um número máximo subjetivo
* **Classificação:** ⚠️ Sugestão de melhoria

---

### OBS-003 – Refresh (F5) preserva os itens do carrinho

* **Área:** Função refresh no site ou “F5” do teclado
* **Heurística:** Fluxo interrompido - o que acontece ao recarregar
* **Ação:** Função atualizar site
* **Resultado esperado:** Preservar as informações de compras
* **Resultado obtido:** Funcionamento adequado com os itens no carrinho preservado
* **Classificação:** ✅ Funciona como esperado

---

### OBS-004 – Cupom de desconto

* **Área:** Listagem de produtos e cupons
* **Heurística:** CRUD: leitura
* **Ação:** Cupom aplicado em diversos produtos
* **Resultado esperado:** Desconto do cupom aplicado corretamente
* **Resultado obtido:** Valor do desconto corresponde ao cupom aplicado, em conformidade com a quantidade dos produtos
* **Classificação:** ✅ Funciona como esperado

---

### OBS-005 – Múltiplos cupons

* **Área:** Listagem de produtos e cupons
* **Heurística:** CRUD: leitura
* **Ação:** Aplicação de outros cupons na mesma compra a ser realizada
* **Resultado esperado:** Não permitir acumulo de cupons conforme a regra do site
* **Resultado obtido:** Acumulo de cupons bloqueado corretamente com a mensagem “Limite de cupons atingido”
* **Classificação:** ✅ Funciona como esperado

---

### OBS-006 – Frete

* **Área:** Frete do cliente
* **Heurística:** CRUD: leitura, atualização e remoção de itens do carrinho
* **Ação:** Incluir frete, atualizar valores conforme quantidade de itens, assim como excluir o frete no caso de eliminação de todos os produtos do carrinho
* **Resultado esperado:** Correta identificação das informações do frete e atualizar seus valores conforme a quantidade de produtos no carrinho
* **Resultado obtido:** Frete não apresentou inconsistências e foi atualizado de acordo com a quantidade de itens no carrinho
* **Classificação:** ✅ Funciona como esperado

---

### OBS-007 – Favoritos

* **Área:** Produtos favoritos do cliente
* **Heurística:** CRUD: criação, leitura, atualização e remoção de itens da opção favoritos
* **Ação:** Criar, excluir e identificar itens na lista de favoritos, assim como adicionar os produtos favoritos no carrinho de compras
* **Resultado esperado:** Realizar a identificação correta dos itens na lista de favoritos e incluir no carrinho de comprar quando solicitado pelo cliente
* **Resultado obtido:** Itens adicionados corretamente à lista de favoritos. Porém, ao adicionar o produto favoritado no carrinho de compras o referido produto não é excluído da lista de favoritos, fato que pode gerar dúvida ao cliente
* **Classificação:** ⚠️ Sugestão de melhoria

---

### OBS-008 – Ícone carrinho

* **Área:** Ícone carrinho de compras na lista de favoritos
* **Heurística:** CRUD: leitura
* **Ação:** Verificar correta identificação do ícone “carrinho de compras” na lista de favoritos
* **Resultado esperado:** Fácil identificação visual que leva ao rápido entendimento do funcionamento pelo cliente
* **Resultado obtido:** O ícone do carrinho de compras não apresenta a identificação escrita ao passar o cursor sobre o mesmo. O referido ícone apresenta um círculo na parte superior esquerda de difícil entendimento
* **Classificação:** ⚠️ Sugestão de melhoria

---

### OBS-009 – Checkout

* **Área:** Checkout pelo menu do cliente
* **Heurística:** CRUD: leitura, atualização
* **Ação:** Realizar checkout da conta do cliente
* **Resultado esperado:** Informações específicas do ambiente do cliente não devem aparecer no site
* **Resultado obtido:** As informações do carrinho de compras permaneceram visíveis
* **Classificação:** ⚠️ Sugestão de melhoria

---

## 📊 Resumo dos Achados

| Classificação          | Quantidade |
| ---------------------- | ---------- |
| Bug                    | 0          |
| Sugestão de melhoria   | 4          |
| Funciona como esperado | 5          |

---

## 📌 Charter 002

| Campo         | Detalhe                                       |
| ------------- | --------------------------------------------- |
| ID do Charter | 002                                           |
| Área          | Explorar o fluxo de cadastro de novos usuários e a funcionalidade de busca                  |
| Missão        | Explorar comportamento inesperados na entrada de variados dados (CPF válido/inválido, CEPs diferentes, termos de busca variados) e observação da usabilidade para descobrir falhas na validação de campos, mensagens de erro pouco claras e inconsistências nos resultados de busca |
| Duração       | 20 minutos                                    |
| Ambiente      | Chrome 146.0.7680.165                         |
| Data          | 29/03/2026                                    |
| Tester        | Renato Paes                                   |
| Hipóteses iniciais | O cadastro de cliente pode apresentar falhas e dados inconsistentes nas informações pessoais e validação de campos |

---

## 🔍 Heurísticas utilizadas

* CRUD: criação, leitura, atualização e remoção

---

## 🔍 Observações

### OBS-001 – Telefone

* **Área:** Campo telefone do cliente
* **Heurística:** CRUD: criação, leitura, atualização e remoção
* **Ação:** Inserir número de telefone de contato com DDD - Brasil
* **Resultado esperado:** Aceitar apenas número de telefone válido
* **Resultado obtido:** Sistema aceitou os digitos “00” dois zeros considerados números de DDD inválidos (tel-invalido-01.png) e permitiu avançar para tela seguinte para informação do CEP (tel-invalido-02.png)
* **Classificação:** 🔴 Bug — o sistema aceita um valor inválido sem mensagem de erro
* **Evidência:** tel-invalido-01.png - tel-invalido-02.png

---

### OBS-002 – Data de nascimento

* **Área:** Campo de nascimento do cliente
* **Heurística:** CRUD: criação, leitura, atualização e remoção
* **Ação:** Cadastrar data de nascimento no formato válido - dd/mm/aaaa
* **Resultado esperado:** Permitir apenas data de nascimento no formato válido
* **Resultado obtido:** Adequado funcionamento. Porém inicialmente permitiu inserir data com limite mínimo de idade e gerou mensagem de bloqueio e aviso apenas ao final do cadastro
* **Classificação:** ⚠️ Sugestão de melhoria

---

## 📊 Resumo dos Achados

| Classificação          | Quantidade |
| ---------------------- | ---------- |
| Bug                    | 1          |
| Sugestão de melhoria   | 1          |
| Funciona como esperado | 0          |

---

## 🛠 Técnicas Aplicadas

* Teste exploratório com charter estruturado
* Heurísticas: CRUD, Vazio/Cheio/Limite, Fluxo interrompido

