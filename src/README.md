# Código da Aplicação

Esta pasta contém o código do seu agente financeiro.

## Estrutura Sugerida

```
src/
├── app.py              # Aplicação principal (Streamlit/Gradio)
└── requirements.txt    # Dependências
```

## Setup do Ollama (5 minutos)

```
  #1. Instalar o Ollama (ollama.ai)
  #2. Baixar um modelo leve
  ollama pull gpt-oss

  #3. Testar se funciona
  ollama run gpt-oss "Olá!"

           OU

 (RECOMENDADO)
  Não precisa baixar o modelo
  Criar uma conta no site da ollama.ia e utilizar uma das versões cloud
```

## Exemplo de requirements.txt

```
import pandas as pd
import json
import requests
import streamlit as st

```

## Como Rodar

```bash
# Instalar dependências
pip install -r requirements.txt

# Rodar a aplicação
streamlit run .\src\app.py
```
