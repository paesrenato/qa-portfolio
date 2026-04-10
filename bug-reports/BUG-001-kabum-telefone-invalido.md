# 🐞 BUG-001: Campo "Telefone celular" aceita DDD inválido ('00')

## 📌 Descrição
O sistema de cadastro do site KaBuM! permite inserir um número de telefone celular com DDD inválido ("00"), sem realizar validação adequada, permitindo que o utilizador avance para a próxima etapa do cadastro.

---

## 🌐 Ambiente
- **Browser:** Chrome 146.0.7680.165 (64 bits)  
- **Sistema Operacional:** Windows 10 Home Single Language (versão 22H2)  
- **Dispositivo:** Desktop  
- **URL:** https://www.kabum.com.br/  
- **Estado da conta:** Novo cadastro  

---

## 🔁 Passos para Reproduzir

1. Aceder ao site https://www.kabum.com.br/  
2. No menu superior direito, clicar em **"Cadastre-se"**  
3. Informar e-mail ou CPF ou CNPJ  
4. Clicar em **"Entrar"**  
5. Preencher os dados cadastrais, incluindo um telefone celular com DDD **"00"**
6. Definir uma senha válida  
7. Aceitar as políticas de privacidade  
8. Clicar em **"Continuar"**  

---

## ❌ Resultado Obtido
O sistema aceita o número de telefone celular com DDD inválido ("00") e permite avançar para a próxima etapa do cadastro sem apresentar qualquer mensagem de erro.

---

## ✅ Resultado Esperado
O sistema deve validar o campo "Telefone celular" e:
- Rejeitar DDDs inválidos (como "00")  
- Exibir uma mensagem de erro clara ao utilizador  
- Impedir o avanço no cadastro até que o valor informado seja válido  

---

## ⚠️ Severidade
**A definir (TBD)**  
Sugestão: Média — afeta a qualidade dos dados e pode comprometer a comunicação com o cliente.

---

## ⏱️ Prioridade
**Média (P2)**  
A falha não bloqueia o cadastro, mas pode impactar processos dependentes de contacto telefónico.

---

## 📎 Evidências
- `tel-invalido-01.png`  
- `tel-invalido-02.png`  

---

## 💡 Observações Adicionais
A ausência de validação adequada para o campo de telefone pode resultar no armazenamento de dados incorretos, afetando notificações, validações de segurança e processos de suporte ao cliente.

---
