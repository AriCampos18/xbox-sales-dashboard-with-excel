##### English Version Bellow

# Xbox Sales Dashboard

## Sobre o Projeto

O **Xbox Sales Dashboard** é um projeto desenvolvido no Microsoft Excel com o objetivo de transformar dados de assinaturas do Xbox Game Pass em informações visuais que facilitem a análise do desempenho comercial e a tomada de decisões baseadas em dados.

O dashboard reúne indicadores e visualizações relacionados aos planos de assinatura, à renovação automática e às vendas de serviços adicionais, como EA Play e Minecraft Season Pass.

O projeto utiliza tabelas de dados, Tabelas Dinâmicas, segmentações de dados e recursos de visualização do Excel para organizar as informações e responder a perguntas relevantes para o negócio.

## Objetivos

- Organizar e analisar dados de assinaturas do Xbox.
- Transformar dados brutos em informações visuais claras e úteis.
- Visualizar informações relevantes sobre vendas e receitas.
- Comparar diferentes tipos de assinatura.
- Analisar a receita dos planos anuais considerando a renovação automática.
- Explorar as vendas de serviços adicionais.
- Apoiar a tomada de decisões por meio de indicadores e visualizações.

## Dados Utilizados

O projeto utiliza uma base de dados com **295 registros de assinantes**, referentes ao período de **1º de janeiro a 31 de dezembro de 2024**.

A base contém informações sobre os assinantes, seus planos de assinatura, as datas de início, as configurações de renovação automática, os serviços adicionais contratados e os valores associados a cada registro.

Entre os principais campos estão:

- **Subscriber ID:** identificador do assinante.
- **Name:** nome associado ao registro.
- **Plan:** plano contratado, como Core, Standard e Ultimate.
- **Start Date:** data de início da assinatura.
- **Auto Renewal:** indica se a renovação automática está habilitada.
- **Subscription Price:** preço registrado para o plano principal.
- **Subscription Type:** periodicidade da assinatura, classificada como Monthly, Quarterly ou Annual.
- **EA Play Season Pass:** indica se o serviço adicional EA Play foi contratado.
- **EA Play Season Pass Price:** preço associado ao EA Play.
- **Minecraft Season Pass:** indica se o Minecraft Season Pass foi contratado.
- **Minecraft Season Pass Price:** preço associado ao Minecraft Season Pass.
- **Coupon Value:** valor do desconto aplicado por cupom.
- **Total Value:** valor total calculado para cada registro, considerando o plano principal, os serviços adicionais e o desconto aplicado.

Os dados permitem analisar tanto as receitas relacionadas às assinaturas quanto os valores associados aos serviços adicionais.

### Regra de cálculo do Total Value

O campo `Total Value` considera a soma do preço da assinatura principal e dos serviços adicionais contratados, subtraindo o desconto aplicado por cupom.

A lógica de cálculo é representada pela seguinte fórmula:

**Total Value = Subscription Price + EA Play Season Pass Price + Minecraft Season Pass Price - Coupon Value**

Quando um serviço adicional não é contratado, seu valor não deve contribuir para o total. Valores representados por hífen (`-`), quando não aplicáveis, devem ser tratados adequadamente nos cálculos.

A base não especifica uma moeda para os valores registrados. Por isso, os resultados são apresentados em unidades monetárias, sem atribuição de uma moeda específica.

## Perguntas de Negócio

O projeto foi desenvolvido para responder às seguintes perguntas de negócio.

### 1. Qual é a receita total proveniente da venda de planos anuais, incluindo todas as assinaturas agregadas?

Essa análise considera os registros classificados como `Annual` no campo `Subscription Type` e soma os valores do campo `Total Value`.

Dessa forma, são considerados o preço do plano principal, os serviços adicionais registrados e os descontos aplicados por cupom.

**Resultado identificado na base:** 1.754 unidades monetárias.

### 2. Qual é a receita total dos planos anuais, separada entre assinaturas com renovação automática e sem renovação automática?

Essa análise considera os planos anuais e separa os valores de acordo com o campo `Auto Renewal`, permitindo comparar a receita das assinaturas com e sem renovação automática.

Os resultados identificados na base são:

| Renovação automática | Receita total |
|---|---:|
| Sim (`Yes`) | 1.537 |
| Não (`No`) | 217 |
| **Total** | **1.754** |

A análise permite observar como a receita dos planos anuais está distribuída entre as duas modalidades de renovação.

### 3. Qual é o total de vendas de assinaturas do EA Play?

Essa pergunta busca identificar o valor total das vendas do serviço adicional EA Play.

A análise utiliza os campos `EA Play Season Pass` e `EA Play Season Pass Price` para identificar as assinaturas contratadas e seus respectivos valores.

Os resultados podem ser explorados por meio das Tabelas Dinâmicas e dos filtros disponíveis no dashboard, permitindo analisar os dados conforme a periodicidade da assinatura e os demais critérios disponíveis.

### 4. Qual é o total de vendas de assinaturas do Minecraft Season Pass?

Essa análise busca identificar o valor total das vendas do serviço adicional Minecraft Season Pass.

Para isso, são utilizados os campos `Minecraft Season Pass` e `Minecraft Season Pass Price`, que permitem identificar os registros associados ao serviço e os valores correspondentes.

Assim como na análise do EA Play, os dados podem ser explorados por meio das Tabelas Dinâmicas e dos filtros do dashboard, possibilitando diferentes perspectivas de análise conforme os critérios selecionados.

> **Observação:** os resultados das análises de EA Play e Minecraft Season Pass podem variar de acordo com os filtros aplicados e com os dados utilizados. Por esse motivo, não são apresentados valores fixos para essas duas perguntas neste documento.

## Estrutura do Arquivo

O arquivo Excel está organizado em quatro planilhas principais:

| Planilha | Descrição |
|---|---|
| `Assets` | Reúne referências visuais utilizadas no projeto, como elementos gráficos e a paleta de cores. Oculta |
| `Bases` | Contém a base de dados dos assinantes e os campos utilizados nas análises. |
| `Cálculos` | Reúne as perguntas de negócio e as Tabelas Dinâmicas utilizadas para resumir os dados. |
| `Dashboard` | Apresenta o painel visual, os indicadores e os controles de filtragem. |

Cada planilha possui uma função específica na organização e apresentação das informações, contribuindo para a estrutura geral do projeto.

## Funcionalidades do Dashboard

- **Visualização consolidada:** apresenta informações relevantes sobre as assinaturas em um painel visual.
- **Filtros interativos:** permite explorar diferentes subconjuntos da base por meio de segmentações de dados.
- **Análise de receita:** facilita a consulta dos valores associados aos planos de assinatura.
- **Análise de renovação automática:** permite comparar as assinaturas com e sem renovação automática.
- **Análise por plano:** possibilita explorar os planos Core, Standard e Ultimate.
- **Análise de serviços adicionais:** permite examinar os valores associados ao EA Play e ao Minecraft Season Pass.
- **Organização visual:** utiliza gráficos, indicadores e elementos visuais para facilitar a interpretação dos dados.

Os valores apresentados no dashboard podem variar conforme os filtros selecionados e as atualizações realizadas na base.

## Tecnologias e Recursos Utilizados

- **Microsoft Excel:** ferramenta utilizada para organizar os dados, realizar cálculos e desenvolver o dashboard.
- **Tabelas do Excel:** utilizadas para estruturar os dados e facilitar sua manutenção.
- **Tabelas Dinâmicas:** utilizadas para resumir, agrupar e analisar os dados conforme diferentes categorias.
- **Segmentações de dados (Slicers):** utilizadas para disponibilizar filtros visuais e interativos.
- **Gráficos do Excel:** utilizados para apresentar os resultados de forma visual.
- **Formatação condicional e recursos visuais:** utilizados para melhorar a organização e a legibilidade das informações.

## Como Reproduzir e Utilizar o Projeto

### Requisitos

Para utilizar o projeto, é necessário ter:

- Microsoft Excel para desktop, com suporte a Tabelas Dinâmicas e segmentações de dados.
- O arquivo `Xbox Sales Dashboard with Excel.xlsx`.

### Passo a Passo

1. Baixe ou clone o repositório do projeto.
2. Abra o arquivo `Xbox Sales Dashboard with Excel.xlsx` no Microsoft Excel.
3. Acesse a planilha `Dashboard`.
4. Utilize as segmentações de dados disponíveis para filtrar as informações.
5. Observe como os indicadores e gráficos se ajustam aos filtros selecionados.
6. Para consultar os dados originais, acesse a planilha `Bases`.
7. Para examinar as Tabelas Dinâmicas utilizadas nas análises, acesse a planilha `Cálculos`.
8. Consulte a planilha `Assets` para visualizar os recursos gráficos utilizados no projeto.

## Observações e Limitações

- Os resultados documentados correspondem aos registros presentes na base analisada.
- Os valores refletem os preços e descontos registrados em cada linha da planilha.
- A moeda dos valores não está especificada na base de dados.
- O dashboard é uma ferramenta de análise descritiva e não realiza previsões de vendas futuras.
- Os resultados das análises de EA Play e Minecraft Season Pass dependem dos dados e dos filtros utilizados.
- O projeto foi desenvolvido no Microsoft Excel. A aparência e o comportamento de alguns recursos interativos podem variar em outros aplicativos de planilhas.
- A data de referência e os intervalos de dados devem ser verificados sempre que a base for atualizada.

###### English Version

# Xbox Sales Dashboard

## About the Project

The **Xbox Sales Dashboard** is a project developed in Microsoft Excel to transform Xbox Game Pass subscription data into visual information that supports sales performance analysis and data-driven decision-making.

The dashboard brings together indicators and visualizations related to subscription plans, auto-renewal, and sales of additional services, such as EA Play and Minecraft Season Pass.

The project uses structured data tables, PivotTables, slicers, and Excel visualization features to organize information and answer relevant business questions.

## Objectives

- Organize and analyze Xbox subscription data.
- Transform raw data into clear and useful visual information.
- Visualize relevant sales and revenue information.
- Compare different subscription types.
- Analyze annual-plan revenue based on auto-renewal status.
- Explore sales of additional services.
- Support decision-making through organized information and visualizations.

## Data Used

The project uses a subscriber dataset containing **295 records**, covering the period from **January 1 to December 31, 2024**.

The dataset contains information about subscribers, their subscription plans, start dates, auto-renewal settings, subscribed add-on services, and the values associated with each record.

The main fields include:

- **Subscriber ID:** subscriber identifier.
- **Name:** name associated with the record.
- **Plan:** subscribed plan, such as Core, Standard, and Ultimate.
- **Start Date:** subscription start date.
- **Auto Renewal:** indicates whether automatic renewal is enabled.
- **Subscription Price:** recorded price of the main subscription.
- **Subscription Type:** subscription frequency, classified as Monthly, Quarterly, or Annual.
- **EA Play Season Pass:** indicates whether the EA Play add-on was subscribed to.
- **EA Play Season Pass Price:** price associated with EA Play.
- **Minecraft Season Pass:** indicates whether Minecraft Season Pass was subscribed to.
- **Minecraft Season Pass Price:** price associated with Minecraft Season Pass.
- **Coupon Value:** discount value applied through a coupon.
- **Total Value:** total value calculated for each record, considering the main subscription, add-on services, and applied discount.

The dataset allows the analysis of both subscription revenue and the values associated with additional services.

### Total Value Calculation Rule

The `Total Value` field considers the sum of the main subscription price and the subscribed add-on services, minus the coupon discount.

The calculation logic is represented by the following formula:

**Total Value = Subscription Price + EA Play Season Pass Price + Minecraft Season Pass Price - Coupon Value**

When an add-on is not subscribed to, its value should not contribute to the total. Values represented by a hyphen (`-`), when not applicable, should be handled appropriately in calculations.

The dataset does not specify a currency for the recorded values. Therefore, results are presented in monetary units without assigning a specific currency.

## Business Questions

The project was developed to answer the following business questions.

### 1. What is the total revenue from annual subscription plans, including all aggregated subscriptions?

This analysis considers records classified as `Annual` in the `Subscription Type` field and sums the values in the `Total Value` field.

This includes the main subscription price, recorded add-on services, and coupon discounts.

**Result identified in the dataset:** 1,754 monetary units.

### 2. What is the total revenue from annual plans, broken down by subscriptions with and without auto-renewal?

This analysis considers annual plans and separates the values according to the `Auto Renewal` field, allowing a comparison of revenue from subscriptions with and without automatic renewal.

The results identified in the dataset are:

| Auto-Renewal Status | Total Revenue |
|---|---:|
| Yes (`Yes`) | 1,537 |
| No (`No`) | 217 |
| **Total** | **1,754** |

This analysis helps illustrate how annual-plan revenue is distributed between the two renewal options.

### 3. What is the total sales revenue from EA Play subscriptions?

This question aims to identify the total sales value associated with the EA Play add-on service.

The analysis uses the `EA Play Season Pass` and `EA Play Season Pass Price` fields to identify subscribed add-ons and their corresponding values.

The results can be explored through PivotTables and the dashboard filters, allowing the data to be analyzed according to subscription frequency and other available criteria.

### 4. What is the total sales revenue from Minecraft Season Pass subscriptions?

This analysis aims to identify the total sales value associated with the Minecraft Season Pass add-on service.

The `Minecraft Season Pass` and `Minecraft Season Pass Price` fields are used to identify records associated with the service and their corresponding values.

As with the EA Play analysis, the data can be explored through PivotTables and dashboard filters, allowing different perspectives based on the selected criteria.

> **Note:** EA Play and Minecraft Season Pass results may vary depending on the selected filters and the dataset used. Therefore, fixed values are not provided for these two business questions in this document.

## File Structure

The Excel workbook is organized into four main worksheets:

| Worksheet | Description |
|---|---|
| `Assets` | Contains visual references used in the project, such as graphic elements and the color palette. |
| `Bases` | Contains the subscriber dataset and the fields used for analysis. |
| `Cálculos` | Contains the business questions and PivotTables used to summarize the data. |
| `Dashboard` | Displays the visual dashboard, indicators, and filtering controls. |

Each worksheet has a specific role in organizing and presenting information, contributing to the overall project structure.

## Dashboard Features

- **Consolidated visualization:** presents relevant subscription information in a visual dashboard.
- **Interactive filters:** allows users to explore different subsets of the dataset through slicers.
- **Revenue analysis:** facilitates the review of values associated with subscription plans.
- **Auto-renewal analysis:** enables comparisons between subscriptions with and without automatic renewal.
- **Plan analysis:** allows users to explore Core, Standard, and Ultimate plans.
- **Add-on service analysis:** allows users to examine values associated with EA Play and Minecraft Season Pass.
- **Visual organization:** uses charts, indicators, and visual elements to make data easier to interpret.

The values displayed on the dashboard may change depending on the selected filters and dataset updates.

## Technologies and Features Used

- **Microsoft Excel:** used to organize data, perform calculations, and develop the dashboard.
- **Excel Tables:** used to structure data and facilitate maintenance.
- **PivotTables:** used to summarize, group, and analyze data across different categories.
- **Slicers:** used to provide visual and interactive filters.
- **Excel Charts:** used to present results visually.
- **Conditional formatting and visual elements:** used to improve information organization and readability.

## How to Reproduce and Use the Project

### Requirements

To use the project, you need:

- Microsoft Excel desktop with support for PivotTables and slicers.
- The `Xbox Sales Dashboard with Excel.xlsx` file.

### Step-by-Step Instructions

1. Download or clone the project repository.
2. Open `Xbox Sales Dashboard with Excel.xlsx` in Microsoft Excel.
3. Go to the `Dashboard` worksheet.
4. Use the available slicers to filter the information.
5. Observe how the indicators and charts respond to the selected filters.
6. To inspect the source data, open the `Bases` worksheet.
7. To examine the PivotTables used in the analyses, open the `Cálculos` worksheet.
8. Open the `Assets` worksheet to view the visual resources used in the project.

## Notes and Limitations

- The documented results correspond to the records included in the analyzed dataset.
- Values reflect the prices and discounts recorded in each row of the workbook.
- The currency of the recorded values is not specified in the dataset.
- The dashboard is a descriptive analysis tool and does not forecast future sales.
- EA Play and Minecraft Season Pass results depend on the dataset and the selected filters.
- The project was developed in Microsoft Excel. The appearance and behavior of some interactive features may differ in other spreadsheet applications.
- The reference date and data ranges should be checked whenever the dataset is updated.
