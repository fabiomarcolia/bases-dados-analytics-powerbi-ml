
# 📊 Bases de Dados para Portfólio e Treinamento

Este repositório agrupa **bases de dados fictícias**, separadas por área:

- Finanças
- RH 
- Logística
- Vendas
- Compras 
- Projetos 

Você poderá praticar modelagem, análise exploratória, dashboards em Power BI ou projetos de Data Science/ML. 

Na pasta **dados** contém o arquivo de dados original e uma versão CSV normalizada.

> **Bases vs Ferramenta** Veja as bases que irá encontrar e a sugestão de onde usar:

| # | Base                                  | Arquivo                             | Linhas × Colunas | Melhor Caso¹                |
| - | ------------------------------------- | ----------------------------------- | ---------------- | --------------------------- |
| 1 | Demonstração de Resultados (DRE 2019) | `1-DRE 2019.xlsx`                   | 140 × 4          | Dashboard/Power BI          |
| 2 | Cadastro de Funcionários (RH)         | `2-RH Cadastro de Funcionarios.csv` | 494 × 20         | Data Science / ML           |
| 3 | Estoque Mínimo                        | `3-Estoque.csv`                     | 33 × 2           | EDA / Tratamento            |
| 4 | Cadastro de Clientes Financeiro       | `4-Financeiro.xlsx`                 | 812 × 6          | Modelagem Dimensão Cliente  |
| 5 | Rotas & Prazo de Entrega (Logística)  | `5-Logistica.xlsx`                  | 1 000 × 3        | Modelagem + EDA             |
| 6 | Vendas 2024                           | `6-Vendas.xlsx`                     | 526 × 16         | Dashboard / Forecasting     |
| 7 | Portfólio de Projetos                 | `7-Projetos.xlsx`                   | 2 633 × 10       | Dashboard / Status Tracking |
| 8 | Cadastro de Compradores               | `8-Compras.xlsx`                    | 6 × 2            | Modelagem (Dim Comprador)   |

¹ *Melhor Caso* é uma sugestão inicial; fique livre para explorar outros cenários.



## Casos de Uso ou Projetos Sugeridos

| Área                 | Ideia de Projeto                                                  | Stack Recomendada              |
| -------------------- | ----------------------------------------------------------------- | ------------------------------ |
| Financeiro           | **Dashboard de P&L**: interativo, drill‑down de níveis da DRE     | Power BI ou Metabase           |
| RH                   | **Churn/Attrition Prediction**: classificar risco de desligamento | Python, scikit‑learn           |
| Estoque + Vendas     | **Alerta de Ruptura**: combinar estoque mínimo com vendas diárias | SQL, Python, Airflow           |
| Clientes + Logística | **Mapa de Lead Time**: geovisualizar tempo de entrega médio       | Power BI, Mapbox               |
| Vendas               | **Forecast de Demanda**: modelo Prophet/ARIMA ou LSTM             | Python, statsmodels, fbprophet |
| Projetos             | **Kanban Financeiro**: custo vs. cronograma                       | Power BI, SQL                  |
| Compras              | **Análise ABC de Fornecedores**                                   | Excel / Python                 |

## Estrutura Sugerida para Seu Projeto(Portifólio)

```
📁Projeto/
  📁 data/
     ├── 1-DRE 2019.xlsx
     ├── 1-DRE 2019.csv
     ├── ...
  📁 notebooks/
     ├── explore.ipynb
     ├── 01-eda-rh.ipynb
  📁 dashboards/
   ├── dre_dashboard.pbix
  📁 ml/
     ├── 00-baseline-churn.ipynb
📄 README.md (Documentação dos seu projeto ou projetos)
```

#

## Prompt de IA para Gerar Ideias de Projeto

- Caso esteja sem idéia, use esse PROMPT no ChatGPT, GEMINI ou Claude, anexe a base escolhida e execute o PROMPT abaixo, substituindo os texto entre '[]' pelo seu caso.

```text
Você é um(a) consultor(a) de dados sênior.

Contexto
- Área de negócio: [ÁREA — ex.: Finanças, RH, Vendas]
- Dataset escolhido: [ARQUIVO — ex.: 6-Vendas.xlsx]
- Tamanho / granularidade: [LINHAS × COLUNAS]
- Objetivo de negócio principal: [PERGUNTA‑CHAVE ou KPI]

Solicitações
1. Liste **5 explorações iniciais (EDA)** úteis para compreender o conjunto.
2. Sugira **3 possíveis modelagens** (dimensional, predição, clustering…).
3. Defina **indicadores‑chave** (nomes, fórmulas, insight de negócio).
4. Proponha **2 esboços de dashboards** focados em storytelling executivo.
5. Aponte desafios ou limitações potenciais dos dados e como mitigá‑los.

Formato de resposta: bullet points em português, indicando ferramentas (Python, Power BI, SQL…).
```

## Template de README para seus Projetos

```markdown
# [Título do Projeto]

↳ Base utilizada: **[ARQUIVO]** (Área: [ÁREA])

## 1- Pergunta de Negócio / Objetivo
Descreva em 2–3 linhas a dor ou oportunidade.

## 2- Exploração (EDA)
- **Análise 1** – insight …
- **Análise 2** – …

## 3- Modelagem / Tratamento
| Passo | Ferramenta | Resultado |
| ----- | ---------- | --------- |
| Limpeza | Python (pandas) | … |
| Modelo  | scikit‑learn     | … |

## 4- Indicadores Principais
- **KPI 1** – definição e meta

## 5- Dashboard
Screenshot ou link.

## 6- Conclusões & Próximos Passos
Resumo acionável.

```
### Dica: Siga a Regra no Portifólio
- 1-Contexto: Qual problema você quis resolver?
- 2-Fonte de dados: Onde encontrou? É pública?
- 3-Ferramentas usadas - Python, SQL, Power BI, etc.
- 4-Etapas - Limpeza, análise, visualização, modelo…
- 5-Resultados - O que descobriu? Que decisões isso ajudaria?
- 6-Link do projeto - GitHub, Power BI, Medium ou Notion

## Exemplo Prático — Criando o Projeto “Vendas Forecast” no VS Code

1- **Criar diretório**

```bash
mkdir vendas-forecast && cd vendas-forecast
```

2- **Abrir no VS Code**

```bash
code .
```

3- **Estrutura**

```bash
mkdir -p data notebooks dashboards ml docs
 touch README.md requirements.txt .gitignore LICENSE
```

4- **Adicionar dataset** (`data/6-Vendas.xlsx`) e converter p/ CSV.

5- **Preencher README** usando o template acima.

6- **Inicializar Git & primeiro commit**

```bash
git init -b main
git add .
git commit -m "feat: estrutura inicial"
```

7- **Publicar no GitHub** via *Git: Publish to GitHub* ou CLI.

8- **Fluxo de trabalho**

```bash
git checkout -b feature/modelo-arima
# trabalho …
git add . && git commit -m "feat: modelo ARIMA baseline"
git push -u origin feature/modelo-arima
```

---

## Dicionário de Dados das Bases

### 1. DRE 2019

| Coluna           | Tipo    | Descrição                                |
| ---------------- | ------- | ---------------------------------------- |
| `CC`             | inteiro | Código da Conta contábil                 |
| `DescricaoConta` | texto   | Nome da conta no plano de contas         |
| `Nivel1`         | texto   | Agrupador de nível 1 (Receita, Despesa…) |
| `Nivel2`         | texto   | Agrupador de nível 2                     |

### 2. RH – Cadastro de Funcionários (principais campos)

| Coluna                     | Tipo     | Descrição                          |
| -------------------------- | -------- | ---------------------------------- |
| `ID RH`                    | inteiro  | Identificador único do colaborador |
| `Nome Completo`            | texto    | Nome do colaborador                |
| `Estado Civil`             | texto    | Solteiro, Casado…                  |
| `Sexo`                     | texto    | M, F                               |
| `Data de Nascimento`       | data     |                                    |
| `Data de Contratacao`      | data     |                                    |
| `Data de Demissao`         | data     | Null se ativo                      |
| `Salario Base`             | numérico | Salário bruto mensal               |
| `Cargo`                    | texto    | Função atual                       |
| `Área`                     | texto    | Departamento (TI, Finanças…)       |
| `Avaliação do Funcionário` | numérico | Score de 1 a 5                     |

*(Arquivo tem outros campos sobre benefícios, performance e soft skills.)*

### 3. Estoque

| Coluna           | Tipo    | Descrição                     |
| ---------------- | ------- | ----------------------------- |
| `ID Produto`     | inteiro | SKU/produto                   |
| `Estoque Mínimo` | inteiro | Quantidade mínima em unidades |

### 4. Financeiro – Clientes

| Coluna          | Tipo    | Descrição                |
| --------------- | ------- | ------------------------ |
| `Id Cliente`    | inteiro | Identificador do cliente |
| `Razao Social`  | texto   | Nome jurídico            |
| `Nome Fantasia` | texto   | Nome comercial           |
| `Tipo Pessoa`   | texto   | Físico ou Jurídico       |
| `Municipio`     | texto   | Cidade                   |
| `UF`            | texto   | Unidade Federativa       |

### 5. Logística

| Coluna       | Tipo    | Descrição           |
| ------------ | ------- | ------------------- |
| `ID Cliente` | inteiro | Chave para clientes |
| `Cidade`     | texto   | Local de entrega    |
| `UF`         | texto   | Estado              |

### 6. Vendas (principais campos)

| Coluna            | Tipo     | Descrição          |
| ----------------- | -------- | ------------------ |
| `Data da Venda`   | data     | Data do pedido     |
| `Ordem de Compra` | texto    | Nº do pedido       |
| `SKU`             | texto    | Código do produto  |
| `ID Cliente`      | inteiro  | Cliente            |
| `Qtd Vendida`     | inteiro  | Quantidade         |
| `Preço Unitário`  | numérico | Valor unitário     |
| `Desconto`        | numérico | % desc.            |
| `Canal`           | texto    | Loja, E‑commerce…  |
| `ID Loja`         | texto    | Filial responsável |

### 7. Projetos

| Coluna           | Tipo     | Descrição                 |
| ---------------- | -------- | ------------------------- |
| `Código Projeto` | texto    | Chave do projeto          |
| `Setor`          | texto    | Área solicitante          |
| `Valor Orçado`   | numérico | Budget aprovado           |
| `Valor Real`     | numérico | Valor gasto até o momento |
| `Status`         | texto    | Em Andamento, Concluído…  |
| `Data Início`    | data     |                           |
| `Data Termino`   | data     |                           |
| `Responsável`    | texto    | Gerente                   |

### 8. Compras

| Coluna             | Tipo    | Descrição                  |
| ------------------ | ------- | -------------------------- |
| `Codigo Comprador` | inteiro | Identificador do comprador |
| `Nome Comprador`   | texto   | Nome completo              |

---

### Se Conecte e Fale comigo no Linkedin🤝

[![Linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=black)](https://www.linkedin.com/in/fabiomarcolia/)


### Autor

- [Fabio Marçolia](https://github.com/fabiomarcolia)



