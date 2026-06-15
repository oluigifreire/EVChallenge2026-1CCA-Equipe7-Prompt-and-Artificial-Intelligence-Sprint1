# EVChallenge2026-1CCA-Equipe7-Prompt-and-Artificial-Intelligence-Sprint2
Nome do projeto: EV DashBot
- Integrantes: Luigi Freire RM569958 ; Victor Vidigal RM571318; Gabriel Savoy RM568991; Raphael Tien RM570261.
- Tecnologias selecionadas e justificativa técnica: ChatGPT: Trazer Inteligência e memória para o projeto, e apresentar os dados em linguagem natural; Plotly: Gerar Dashboards para melhor visualização dos dados.
- Link do Fluxograma no Miro: https://miro.com/app/board/uXjVHYF2IpI=/?share_link_id=332729434366

[Link do vídeo demonstrativo](https://youtu.be/FIchtJgQUaQ)

# ChargeGrid Intelligence

Dashboard gerencial com IA para monitoramento e análise operacional de eletropostos comerciais.

Projeto desenvolvido para demonstrar como modelos de IA podem transformar dados operacionais de carregadores de veículos elétricos em insights acionáveis para gestores de estacionamentos, shoppings, condomínios corporativos e operações de recarga.

---

# Problema

Operadores de eletropostos frequentemente possuem acesso apenas a métricas brutas:

* consumo de energia
* sessões realizadas
* potência demandada
* faturamento estimado

Entretanto, transformar esses dados em decisões operacionais exige análise especializada.

O ChargeGrid Intelligence atua como um copiloto gerencial, interpretando os dados e gerando recomendações sobre:

* riscos de demanda contratada
* utilização dos carregadores
* oportunidades de faturamento
* eficiência operacional
* planejamento preventivo

---

# Principais Funcionalidades

### Dashboard Gerencial

Geração automática de gráficos utilizando Plotly:

* curva de demanda ao longo do dia
* potência por carregador
* energia entregue por carregador
* sessões realizadas por carregador

### Briefing Matinal

Resumo executivo automático contendo:

* indicadores do dia anterior
* identificação de riscos
* carregadores críticos
* recomendações operacionais

### Chatbot Gerencial

Permite consultas em linguagem natural sobre:

* picos de demanda
* eficiência operacional
* riscos financeiros
* oportunidades de faturamento
* ações preventivas

---

# Arquitetura

```text
Dados Operacionais
        ↓
System Prompt
        ↓
GPT-4o-mini
        ↓
Extração Estruturada (JSON)
        ↓
Dashboard Plotly
        ↓
Chat Gerencial
```

---

# Tecnologias Utilizadas

* Python 3.10+
* OpenAI API
* Plotly
* Google Colab
* JSON

---

# Estrutura do Projeto

```text
chargegrid-intelligence/

├── main.py
├── README.md
└── Chatbot_ChargeGrid_IA.ipynb
```

---

# Dependências

Instale as dependências:

```bash
pip install openai plotly
```

ou:

```bash
pip install -r requirements.txt
```

---

# Variáveis de Ambiente

O projeto utiliza a API da OpenAI.

Defina:

```bash
OPENAI_API_KEY=sua_chave_aqui
```

Exemplo Linux/macOS:

```bash
export OPENAI_API_KEY="sk-..."
```

Exemplo Windows:

```cmd
set OPENAI_API_KEY=sk-...
```

---

# Configuração dos Dados

Atualmente os dados operacionais são fornecidos diretamente dentro do `SYSTEM_PROMPT`.

A seção abaixo deve ser atualizada sempre que houver novos dados:

```python
SYSTEM_PROMPT = """
...
"""
```

Os dados incluem:

* sessões realizadas
* energia entregue
* faturamento
* demanda por hora
* status dos carregadores

---

# Como Executar

Execute:

```bash
python main.py
```

Fluxo esperado:

```text
Extraindo dados do sistema...

Gerando dashboard...

Gerando briefing do dia anterior...
```

Após a geração do dashboard, o chatbot ficará disponível:

```text
Você:
```

Para encerrar:

```text
sair
```

---

# Exemplos de Perguntas

### Gestão de Demanda

```text
O que causou o pico de ontem às 14h?
```

```text
Qual foi o risco real para a operação?
```

```text
Se esse padrão se repetir hoje, o que devo fazer?
```

---

### Eficiência Operacional

```text
Algum carregador teve desempenho abaixo do esperado?
```

```text
Qual carregador apresentou maior ociosidade?
```

```text
Onde existe oportunidade de aumentar utilização?
```

---

### Financeiro

```text
Qual foi a principal perda de receita observada?
```

```text
Quais horários deveriam receber campanhas promocionais?
```

```text
Qual seria o impacto financeiro de aumentar a ocupação?
```

---

# Exemplo de Saída

```text
## Resumo Executivo

O pico de 78,4 kW foi causado principalmente pela operação simultânea de quatro carregadores em potência máxima.

## Evidências

EV-01, EV-02, EV-04 e EV-06 representaram aproximadamente 56% da demanda total.

## Impacto

A operação atingiu 98% do limite contratado.

## Recomendação

Monitorar a demanda a partir das 13h30 e preparar throttling preventivo acima de 76 kW.
```

---

# Limitações Atuais

Versão atual:

* dados inseridos manualmente no prompt
* não possui integração com carregadores reais
* não possui monitoramento em tempo real
* não executa throttling automaticamente
* não possui banco de dados operacional

---

# Roadmap

### Curto Prazo

* Integração com API dos carregadores GoodWe
* Ingestão automática de dados
* Relatórios diários automáticos

### Médio Prazo

* Agente de monitoramento em tempo real
* Recomendações preditivas
* Detecção automática de anomalias

### Longo Prazo

* Controle automático de potência
* Orquestração de múltiplos eletropostos
* IA operacional autônoma

---

# Aviso

As recomendações geradas são baseadas exclusivamente nos dados fornecidos ao modelo.

O sistema não substitui a supervisão humana nem executa ações diretamente sobre a infraestrutura elétrica.
