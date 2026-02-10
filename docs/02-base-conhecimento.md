# Base de Conhecimento

## Dados Utilizados

| Arquivo | Formato | Qual a funcionalidade no FIAI ?|
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores, ou seja, dar continuidade ao atendimento de forma mais eficiente. |
| `perfil_investidor.json` | JSON | Personalizar recomendações e explicar detalhadamente o porque da recomendação |
| `produtos_financeiros.json` | JSON | Sugerir produtos adequados ao perfil |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente |

---

## Adaptações nos Dados

Não houve

---

## Estratégia de Integração

### Como os dados são carregados?

Para carregar dados, utilizar o prompt diretamente ou carregar arquivos via código python.

`Exemplo`

```python
import pandas as pd
import json

perfil = json.load(open('.\data\perfil_investidor.json'))
transacoes = pd.read_csv('.\data\transacoes.csv')
historico = pd.read_csv('.\data\historico.csv')
produtos = json.load(open('.\data\produtos.json'))  

```

### Como os dados são usados no prompt?

Para simplificar, podemos "injetar" os dados em nosso prompt, garantindo que o agente tenha o melhor contexto possível. Lembrando que, em soluções mais robustas, o ideal é que esas informações sejam carregadas dinamicamente para que possamos ganhar flexibilidade

  `DADOS DO CLIENTE`
```
    Nome:
    Idade:
    Renda:
    Objetivo:
    Sálario:
```

  `HISTÓRICO DE TRANSAÇÕES`
```
    Valor:
    Tipo:
    Valor da transação em relação ao salario: %
```

  `HOSTÓRICO DE ATENDIMENTOS`
```
  Dia/Mês/Ano: 
  Prompt utilizado: 
  Investimento sugerido: 
```

  `RECOMENDAÇÕES DE INVESTIMENTO`
```
  Com base em seu perfil e sua situação financeira, os investimentos mais adequados são:

  INVESTIMENTO 1
    Aporte minimo: 
    Rentabilidade mensal: 
    Risco: 

  INVESTIMENTO 2
    Aporte minimo: 
    Rentabilidade mensal: 
    Risco: 

   INVESTIMENTO 3
    Aporte minimo: 
    Rentabilidade mensal: 
    Risco: 
```

---

## Exemplo de Contexto Montado

Este é a estrutura funcional para gastar menos tokens e ainda assim dar as informações relevantes para ajudar o usuario a tomar uma decisão

```
Dados do Cliente:
- Nome:
- Objetivo:
- Salario:

Histórico de transações:
- Valor:
- Tipo:

Histórico de atendimentos:
- Data:
- Promp utilizado:
- Investimento sugerido

Recomendações de investimentos:
- Investimento 1:
- Investimento 2:
- Investimento 3:

```
