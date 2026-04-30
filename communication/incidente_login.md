# Template Incidente

## 📌 TÍTULO
Login não realizado com credenciais válidas | Alta prioridade

## 🌍 AMBIENTE
Staging — Versão 147.0.7727.103 (Compilação oficial) (64 bits) — Windows 10 Home Single Language (versão 22H2) — 30/04/2026 às 10:10h

## 🔄 PASSOS PARA REPRODUZIR
1. Acessar o site de e-commerce  
2. Clicar em "Entrar" no canto superior direito  
3. Informar e-mail válido já cadastrado  
4. Informar senha correta  
5. Clicar no botão "Entrar"  

## ❌ COMPORTAMENTO OBSERVADO
O sistema não realiza o login mesmo com credenciais válidas. Após clicar em "Entrar", a página recarrega sem mensagem de erro ou feedback ao usuário, mantendo-o na tela de login.

## ✅ COMPORTAMENTO ESPERADO
O sistema deve autenticar o usuário com credenciais válidas e redirecioná-lo para a página inicial/logada ou dashboard da conta. Em caso de erro, deve exibir mensagem clara informando o problema.

## 💥 IMPACTO
Severidade alta, pois impede que usuários acessem suas contas, afetando diretamente a experiência de compra e podendo resultar em perda de vendas.  
Prioridade alta, pois impacta funcionalidade crítica do sistema (autenticação).

## 🟡 PRÓXIMO PASSO SUGERIDO
Verificar logs de autenticação no backend e possíveis falhas na API de login. Avaliar se houve mudança recente em validação de credenciais ou integração com serviço de autenticação. Considerar rollback caso o erro tenha sido introduzido na última release.

---

# Mensagem de Slack

Pessoal, identifiquei um bug crítico no login: usuários não conseguem acessar a conta mesmo com credenciais válidas.  
A API retorna 200, mas sem token — o frontend não dá feedback.  
Impacto direto em conversão (login bloqueado).  
Já registrei evidências e logs no ticket.  
Sugiro priorizarmos análise/rollback antes do próximo deploy.
