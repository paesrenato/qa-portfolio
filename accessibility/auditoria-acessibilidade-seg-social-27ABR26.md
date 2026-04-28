# Auditoria de Acessibilidade – Segurança Social Direta

**Data da auditoria:** 27 de abril de 2026  
**Site auditado:** [https://www.seg-social.pt/]
**Ferramentas utilizadas:** Lighthouse + axe DevTools  

---

## Resumo da auditoria

| Indicador               | Resultado |
|------------------------|-----------|
| Total de violações     | 3         |
| Severidade geral       | `Serious` |

---

## Violações encontradas

### 1. Elementos com `[aria-hidden="true"]` contêm descendentes focáveis

- **Severidade:** `Serious`
- **Usuários impactados:** Leitores de tela (ex.: pessoas com deficiência visual)
- **Como são impactados:** Conteúdo que deveria estar oculto para tecnologias assistivas pode se tornar focado acidentalmente, causando confusão e perda de contexto.

#### Sugestão de melhoria
> Conteúdo focalizável dentro de elementos com `aria-hidden="true"` deve receber `tabindex="-1"` ou ser removido do DOM para evitar interações inesperadas.

---

### 2. Documento sem ponto de referência principal (`<main>`)

- **Severidade:** `Serious`
- **Usuários impactados:** Leitores de tela (ex.: pessoas com deficiência visual, mobilidade reduzida)
- **Como são impactados:** A navegação por marcos (landmarks) fica comprometida, dificultando saltar diretamente para o conteúdo principal da página.

#### Sugestão de melhoria
> Incluir um elemento `<main>` ou equivalente com `role="main"` para melhorar a navegação por pontos de referência.

---

### 3. Links idênticos com finalidades diferentes

- **Severidade:** `Serious`
- **Usuários impactados:** Leitores de tela e usuários de navegação por links
- **Como são impactados:** Links com textos iguais, mas que levam a destinos diferentes, geram ambiguidade e frustração.

#### Sugestão de melhoria
> Links com o mesmo destino devem ter descrições consistentes. Links com destinos diferentes devem ter textos distintos ou contexto adicional (ex.: atributos `aria-label`).

---

## Público impactado

- **Empregadores e empresas** que acessam a área exclusiva da Segurança Social.
- A falta de acessibilidade pode dificultar ou impedir a realização de tarefas essenciais, como consultas, submissão de documentos ou agendamentos.

---

## Evidências

![Screenshot da auditoria de acessibilidade]

> `acessibilidade...png`

---

## Conclusão

Embora o número de violações seja baixo (3), todas possuem severidade `Serious` e impactam diretamente a experiência de usuários com deficiência. Recomenda-se a correção imediata para garantir conformidade com as **WCAG 2.1** (níveis A e AA).

---

📎 **Relatório gerado por:** [Renato Paes]  
📅 **Data do documento:** 27 de abril de 2026