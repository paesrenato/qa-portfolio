# 🧪 QA Portfolio — Renato Paes

Bem-vindo ao meu portfólio de Quality Assurance.  
Este repositório reúne artefatos práticos de testes de software, simulando cenários reais de mercado e demonstrando minhas habilidades como QA.

---

## 📌 O que você encontrará aqui

- ✅ Casos de teste formais  
- 🔍 Testes exploratórios  
- 🐞 Bug reports profissionais  
- 📊 Pensamento crítico aplicado à qualidade  
- 🔌 Testes de API  
- 🧪 Collections Postman  
- 🗄️ Validação de dados em banco  

---

## 📂 Estrutura do Repositório

qa-portfolio/
├── README.md ← descrição do portfólio  
├── cases/ ← casos de teste formais  
│ └── CT-Parabank-login.md  
├── exploratorio/ ← artefatos de teste exploratório  
│ └── sessao-kabum-cadastro.md  
├── bug-reports/ ← bug reports profissionais  
│ └── BUG-001-kabum-telefone-invalido.md  
├── api/ ← documentação e testes de API  
├── postman/ ← collections e testes automatizados  
└── database/ ← cenários e validações de dados  

---

## 🧾 Conteúdo

### 🧾 Cases

Casos de teste estruturados com abordagem profissional, contendo:

- Cenários  
- Pré-condições  
- Passos  
- Resultado esperado  
- Prioridade  
- Severidade  

📁 **Local:** `cases/`  

**Exemplo:**  
- `CT-Parabank-login.md`

---

### 🔍 Teste Exploratório

Sessões documentadas de testes exploratórios utilizando técnicas como:

- Charter  
- Time-box  
- Notas da sessão  
- Riscos identificados  
- Bugs encontrados  

📁 **Local:** `exploratorio/`  

**Exemplo:**  
- `sessao-kabum-cadastro.md`

---

### 🐞 Bug Reports

Bug reports estruturados seguindo padrões profissionais de mercado:

- Título claro  
- Passos para reproduzir  
- Resultado esperado vs obtido  
- Severidade e prioridade  
- Evidências  

📁 **Local:** `bug-reports/`  

**Exemplo:**  
- `BUG-001-kabum-cadastro.md`

---

## 🔌 Testes de API

Documentação e validação de endpoints REST, simulando cenários reais de consumo de serviços.

### 📍 O que é coberto

- Endpoints (GET, POST, PUT, DELETE)  
- Parâmetros e payloads  
- Autenticação  
- Códigos de resposta  
- Validação de regras de negócio  

### 📄 Estrutura da documentação

Cada endpoint documentado contém:

- Descrição  
- URL  
- Método HTTP  
- Headers  
- Body (request)  
- Response esperado  
- Casos de sucesso e erro  

📁 **Local:** `api/`

---

## 🧪 Postman

Utilização do Postman para execução e automação de testes de API.

### 📁 Collections

Collections organizadas por domínio funcional, contendo:

- Fluxos completos de teste  
- Requisições encadeadas  
- Variáveis de ambiente  

📁 **Local:** `postman/`

---

### ✅ Assertions (Testes Automatizados)

Exemplo de validações implementadas:

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response contains expected data", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property("id");
});
```

### 🔄 Variáveis utilizadas

- `base_url`  
- `token`  
- `user_id`  

---

## 🗄️ Database

Validação de dados diretamente no banco, garantindo consistência entre backend e persistência.

### 📌 O que é testado

- Integridade de dados  
- Persistência correta  
- Regras de negócio no banco  
- Impacto de operações CRUD  

---

📁 **Local:** `database/`

---

## 🎯 Objetivo do Portfólio

Este portfólio tem como objetivo demonstrar:

- Pensamento analítico  
- Capacidade investigativa  
- Escrita técnica clara  
- Mentalidade de qualidade  
- Experiência prática em testes  

---

## 🛠️ Habilidades Demonstradas

- Testes Manuais  
- Testes Exploratórios  
- Escrita de Casos de Teste  
- Bug Reporting  
- Análise de Requisitos  
- Test Design  
- Heurísticas de Teste  
- Testes de API  
- Automação com Postman  
- Validação de Banco de Dados  

---

## 👩‍💻 Sobre Mim

**Renato Paes**  
QA Manual | Analista de Qualidade | QA Analyst  

Profissional de qualidade com foco em estratégia de testes, melhoria contínua e entrega de software com alto nível de confiabilidade.

---

## 📬 Contato

- LinkedIn: www.linkedin.com/in/paesrenato  
- GitHub: https://github.com/paesrenato/qa-portfolio.git  
- Email: paesrenato@gmail.com  

---

⭐ Este repositório está em constante evolução conforme novos artefatos são adicionados.
