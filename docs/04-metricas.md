# Avaliação e Métricas

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** | O agente respondeu o que foi perguntado? | Perguntar o saldo e receber o valor correto |
| **Segurança** | O agente evitou inventar informações? | Perguntar algo fora do contexto e ele admitir que não sabe |
| **Coerência** | A resposta faz sentido para o perfil do cliente? | Sugerir investimento conservador para cliente conservador |

---

## Exemplos de Cenários de Teste

Crie testes simples para validar seu agente:

### Teste 1: Consulta de gastos
- **Pergunta:** "Quanto gastei com alimentação?"
- **Resposta esperada:** Valor baseado no `transacoes.csv`
- **Reposta obtida:** 
"A soma dos gastos em alimentação em outubro foi de R 570,00 (R 450,00 no supermercado + R$ 120,00 no restaurante)"
- **Resultado:** [X] Correto  [ ] Incorreto

### Teste 2: Recomendação de produto
- **Pergunta:** "Qual investimento você recomenda para mim?"
- **Resposta esperada:** Produto compatível com o perfil do cliente
- **Reposta obtida:** 
"João, seu objetivo é aumentar a reserva de emergência para cobrir cerca de 6 meses de gastos, que, com os valores que você tem, ficaria em torno de R$15.000. Como seu perfil é moderado e a prioridade é a liquidez e segurança, eu recomendaria investir o restante do patrimônio que você puder destinar em Tesouro Selic (rendimento 100 % da Selic) ou, se preferir, em um CDB Liquidez Diária (rentabilidade 102 % do CDI). Ambos têm risco baixo e liquidez diária, permitindo que você acesse os recursos rapidamente em caso de necessidade.
Se quiser diversificar um pouco mais ao nível de risco moderado, poderia combinar uma aplicação maior em Tesouro Selic com um pequeno aporte (R$500 ‑ R$1.000) em um Fundo Multimercado, que oferece potencial de retorno superior ao CDI + 2 % e tem menor volatilidade que fundos de ações. Lembre‑se de que, apesar de ser considerado de baixo risco, nenhum investimento é 100 % livre de risco."
- **Resultado:** [X] Correto  [ ] Incorreto

### Teste 3: Pergunta fora do escopo
- **Pergunta:** "Qual a previsão do tempo?"
- **Resposta esperada:** Agente informa que só trata de finanças
- **Reposta obtida:**
Desculpe, mas não tenho acesso a informações de previsão do tempo.
- **Resultado:** [X] Correto  [ ] Incorreto

### Teste 4: Informação inexistente
- **Pergunta:** "Quanto rende o produto XYZ?"
- **Resposta esperada:** Agente admite não ter essa informação
- **Resposta obtida:**
Não disponho dos dados atuais sobre a rentabilidade de BBDC3, pois a minha base de informações não inclui cotações em tempo real nem resultados futuros. Para saber o retorno do papel na Bovespa, sugiro consultar plataformas de corretoras, relatórios de analistas ou sites de informações financeiras confiáveis, onde normalmente trazem o histórico de desempenho e projeções.
Lembre‑se de que a rentabilidade de ações costuma variar conforme mercado e volatilidade, e não há garantia de retorno. Se precisar de ajuda para entender os relatórios de desempenho ou comparar opções de investimento, posso oferecer orientações gerais sobre análise de ações e risco. 
- **Resultado:** [X] Correto  [ ] Incorreto

---

## Resultados

Após os testes, registre suas conclusões:

**O que funcionou bem:**
- Todas as perguntas foram respondidas com o teor certo, respondeu com base somente nos dados fornecidos, sempre deixou claro que nenhum investimento é 100% seguro e análisou bem o perfil da Pessoa.

**O que pode melhorar:**
- Respostas mais curtas e objetivas, porém estou bem satisfeito com as respostas obtidas

---
