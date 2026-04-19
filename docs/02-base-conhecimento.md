# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores, ou seja dá continuidade ao atendimento de forma mais eficiente |
| `perfil_investidor.json` | JSON | Personalizar as explicações sobre as dúvidas e necessidades do cliente evitando recomendações recomendações diretas |
| `produtos_financeiros.json` | JSON | Sugerir produtos adequados ao perfil |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente e usar essa informações de forma mais didática  | 

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.
> Sim, troquei os fundos multi mercado pelos fundos imobiliário pois estou mais familiarizado pelo produto.

[Sua descrição aqui]

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.
> Existem duas possibilidades , injetar dados diretamente no prompt(control c + control v )ou carregar os arquivos via código, como no exemplo abaixo:
> import pandas as pd
> import json
> 
> # CSVs
> historico = pd.read_csv('data/hitorico_atendimento.csv')
> transacoes = pd.read_csv('data/transacoes.csv')
>
> # JSON
>  whith open('data/perfil_investidor.json,'r',encoding='utf-8') as f:
> perfil=json.load(f)
> with open('data/produtos_financeiros.json','r',encoding='utf-8') as f:
> produtos=json.load(f)

[ex: Os JSON/CSV são carregados no início da sessão e incluídos no contexto do prompt]

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?
> Vão estar disponiveis nos arquivos (historico_atendimento; perfil_investidor; produtos_financeiros; transacoes.csv)



---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Cliente:
- Nome: João Silva
- Perfil: Moderado
- Saldo disponível: R$ 5.000

Últimas transações:
- 01/11: Supermercado - R$ 450
- 03/11: Streaming - R$ 55
...
```
