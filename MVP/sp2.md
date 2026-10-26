# 📌 MVP — API de Análise e Otimização da Fiscalização



## 🎯 1. Objetivo do MVP e Propósito da Solução

O objetivo deste MVP é implementar um modelo de **otimização operacional, balanceamento da carga de trabalho e padronização dos procedimentos de fiscalização**.

A solução evolui a base descritiva e sanitizada desenvolvida na Sprint 1, buscando resolver problemas relacionados à desigualdade na atribuição de inspeções, à falta de critérios uniformes de tempo de execução e à ausência de padronização na classificação dos resultados obtidos em campo.

### 🔎 Problemas Identificados

* Sobrecarga e distribuição desigual das demandas entre os fiscais.
* Falta de critérios uniformes para estimar o tempo de execução das fiscalizações.
* Ausência de padronização na classificação dos resultados das vistorias metrológicas.
* Necessidade de melhorar a distribuição geográfica das inspeções.
* Dificuldade de estabelecer metas operacionais previsíveis.

### 💡 Hipótese Validada

É possível redistribuir **100% da demanda histórica**, composta por 5.366 locais/visitas e 23.202 itens, entre os sete fiscais ativos no plano, sem excluir demandas e buscando maior equidade na distribuição da jornada de trabalho.

### 🚀 Valor Entregue

* Equidade operacional na distribuição das horas de trabalho.
* Maior previsibilidade dos tempos de execução.
* Organização geográfica das atividades por zonas.
* Padronização da classificação dos resultados de fiscalização.
* Estabelecimento de indicadores para monitoramento da operação.
* Base técnica para o desenvolvimento de ferramentas de análise e otimização.

---

## 📝 2. Descrição da Solução Implementada

### 2.1. Balanceamento e Redistribuição da Carga de Trabalho

Foi realizada a retirada de um fiscal da base original, Renato Ferreira de Lima, com redistribuição de suas demandas entre os sete fiscais ativos no plano operacional.

As demandas foram redistribuídas entre municípios como Jacareí, Jambeiro, Guararema e São José dos Campos.

#### 📊 Redução da Desigualdade Operacional

O Índice de Gini foi utilizado para avaliar a desigualdade na distribuição das horas de trabalho entre os fiscais.

| Indicador                               | Cenário Histórico |      Plano Otimizado |
| --------------------------------------- | ----------------: | -------------------: |
| Índice de Gini das horas trabalhadas    |             0,201 |                0,003 |
| Menor carga horária anual por fiscal    |                 — |                733 h |
| Maior carga horária anual por fiscal    |                 — |                745 h |
| Diferença entre a menor e a maior carga |                 — | Aproximadamente 12 h |

**Resultado:** o Índice de Gini caiu de 0,201 para 0,003, indicando uma distribuição quase homogênea das horas de trabalho entre os sete fiscais.

#### 📈 Estabilização da Carga de Trabalho

Os coeficientes de variação (CV) foram utilizados para avaliar a dispersão das demandas operacionais.

| Indicador           | Cenário Histórico | Plano Otimizado |
| ------------------- | ----------------: | --------------: |
| CV anual de locais  |             0,341 |           0,030 |
| CV mensal de locais |             0,855 |           0,031 |
| Regularidade mensal |             0,508 |           0,003 |

**Resultado:** houve redução expressiva da variabilidade das demandas, indicando maior regularidade na distribuição mensal e anual das atividades.

#### 🚚 Trade-off Logístico: Equidade versus Deslocamento

O balanceamento das horas de trabalho exigiu alterações na distribuição territorial das fiscalizações, provocando aumento nas saídas operacionais e nos deslocamentos.

| Indicador             | Cenário Histórico | Plano Otimizado | Variação |
| --------------------- | ----------------: | --------------: | -------: |
| Saídas operacionais   |               787 |             964 |     +177 |
| Tempo de deslocamento |        2.102,01 h |      2.659,52 h |   +26,5% |
| Quilometragem total   |     100.675,49 km |   128.270,26 km |   +27,4% |

**Análise operacional:** o plano otimizado apresentou maior equilíbrio na distribuição da carga horária, mas também aumentou os custos logísticos potenciais associados aos deslocamentos.

Esse resultado evidencia um trade-off entre equidade operacional e eficiência logística, que deverá ser investigado na Sprint 3 por meio da comparação entre os cenários histórico e otimizado.

---

### 2.2. Padronização dos Resultados Técnicos — Classes C1 a C6

A solução estabeleceu uma proposta de classificação padronizada dos resultados das fiscalizações, contemplando diferentes situações encontradas durante as verificações de instrumentos de pesagem não automáticos (IPNA) e bombas medidoras de combustível.

O enquadramento regulatório considera a Lei nº 9.933/1999, a Portaria Inmetro nº 157/2022, referente a instrumentos de pesagem não automáticos, e a Portaria Inmetro nº 227/2022, referente a sistemas de medição e abastecimento de combustíveis líquidos.

> **Nota:** a aplicação de cada medida administrativa deve observar o regulamento específico do instrumento, a natureza da irregularidade e os procedimentos legais aplicáveis. A taxonomia C1–C6 é uma proposta de classificação operacional do projeto e não deve ser confundida com uma classificação oficial do Inmetro.

#### 📋 Catálogo de Classificação

| Classe | Denominação         | Efeito Operacional                                                                                                  |               Ocorrências Históricas |
| ------ | ------------------- | ------------------------------------------------------------------------------------------------------------------- | -----------------------------------: |
| **C1** | Conforme            | Instrumento aprovado e liberado, com aplicação das marcações e dos procedimentos de verificação pertinentes.        |    20.377, incluindo 15.051 balanças |
| **C2** | Não Conforme        | Instrumento não aprovado, com registro da irregularidade e adoção das providências cabíveis.                        |                                  867 |
| **C3** | Não Conforme Grave  | Possibilidade de interdição, apreensão cautelar e autuação, conforme a irregularidade e a legislação aplicável.     | 43, incluindo 31 em bombas medidoras |
| **C4** | Não Avaliado        | Verificação não executada ou não registrada, exigindo análise da pendência e eventual reprogramação.                |                                  495 |
| **C5** | Fora de Escopo      | Registro excluído do universo analítico após o saneamento da base de dados.                                         |                                1.613 |
| **C6** | Pendente de Análise | Classificação provisória para casos que aguardam laudo, retorno de oficina ou outra evidência necessária à decisão. |                      Classe proposta |

**Importância operacional:** a padronização permite uniformizar os registros, melhorar a rastreabilidade dos resultados e facilitar a geração de indicadores de conformidade, irregularidades e pendências.

**Atenção:** a classe C5 representa uma condição de tratamento analítico dos dados, e não necessariamente um resultado de fiscalização de campo. Para evitar distorções, ela deve ser diferenciada das classes utilizadas para medir o resultado efetivo das inspeções.

---

### 2.3. Métricas de Tempo e Modelagem de Esforço

A modelagem dos tempos de execução foi desenvolvida para estimar o esforço operacional necessário às fiscalizações, considerando a quantidade de itens inspecionados e o tempo de deslocamento entre localidades.

#### ⏱️ Tempo por Visita — `TV_VISITA`

A estimativa foi calculada a partir de aproximadamente 3.876 a 3.914 pares válidos de visitas consecutivas.

| Estatística        |        Tempo |
| ------------------ | -----------: |
| Média              | 26,3 minutos |
| Mediana            | 14,8 minutos |
| Percentil 25 (P25) |  8,3 minutos |
| Percentil 75 (P75) | 31,3 minutos |
| Percentil 90 (P90) | 65,9 minutos |

**Interpretação:** a média superior à mediana indica uma distribuição assimétrica dos tempos, possivelmente influenciada por atendimentos mais demorados. Por esse motivo, a análise utiliza medidas de tendência central e percentis para caracterizar o comportamento operacional.

#### 📦 Tempo por Faixa de Itens — `TV_FAIXA`

| Quantidade de Itens | Tempo Médio | Tempo Mediano |
| ------------------- | ----------: | ------------: |
| 1 item              |    19,4 min |      11,3 min |
| 2 a 3 itens         |    22,8 min |      13,7 min |
| 4 a 6 itens         |    24,7 min |      16,9 min |
| 7 ou mais itens     |    63,2 min |      52,7 min |

**Resultado:** as fiscalizações com sete ou mais itens apresentam tempo médio superior a três vezes o tempo médio observado nas fiscalizações com um item.

Esses resultados demonstram a importância de considerar a quantidade de instrumentos ou itens fiscalizados no planejamento da carga de trabalho.

#### 🧮 Fórmula de Esforço Municipal

O esforço total estimado por município é calculado pela soma das horas de fiscalização e das horas de deslocamento:

```text
H_total = H_fiscalização + H_deslocamento
```

Onde:

* `H_total`: esforço total estimado para atendimento da demanda.
* `H_fiscalização`: tempo necessário para executar as atividades de fiscalização.
* `H_deslocamento`: tempo estimado de deslocamento necessário para atender às localidades.

#### ⚙️ Parâmetros Operacionais

| Parâmetro                        |          Valor |
| -------------------------------- | -------------: |
| Limite de jornada por saída      |        8 horas |
| Velocidade média de deslocamento |        68 km/h |
| Fator de distância               |           1,28 |
| Disponibilidade anual por fiscal | 249 dias úteis |

Esses parâmetros são utilizados como premissas do modelo de planejamento operacional e devem ser documentados para permitir a reprodução dos cálculos.

---

### 2.4. Agrupamento Territorial e Matriz de Responsabilidades

A distribuição territorial foi organizada em cinco zonas operacionais, com o objetivo de facilitar o planejamento das rotas, a atribuição das demandas e o acompanhamento da cobertura geográfica.

#### 🗺️ Zonamento Regional

| Zona   | Municípios de Referência      |
| ------ | ----------------------------- |
| **Z1** | Caraguatatuba e Ubatuba       |
| **Z2** | São José dos Campos e Jacareí |
| **Z3** | Cruzeiro e Queluz             |
| **Z4** | Taubaté e Pindamonhangaba     |
| **Z5** | Guaratinguetá e Lorena        |

*Os municípios apresentados são exemplos de referência territorial. A composição completa de cada zona deve ser consultada na matriz operacional do projeto.*

#### 👥 Matriz de Responsabilidades

A matriz estabelece a distribuição das demandas municipais entre os fiscais, permitindo identificar responsáveis principais e situações de compartilhamento de atendimento.

Exemplos identificados no plano:

* **Aparecida:** concentração de 100% das 16 saídas planejadas em um único fiscal.
* **Bananal:** distribuição das demandas entre três fiscais.

Essa organização permite avaliar a cobertura territorial, a concentração de responsabilidades e a necessidade de ajustes na distribuição das rotas.

---

## 👥 3. Personas e Usuários-Alvo

### 3.1. Analista de Fiscalização

**Necessidades:**

* Consultar resultados de fiscalização padronizados.
* Utilizar critérios uniformes de classificação.
* Acompanhar tempos médios de atendimento.
* Identificar pendências e irregularidades.
* Consultar informações sobre instrumentos e itens fiscalizados.

**Valor entregue:** maior consistência dos registros e melhor rastreabilidade dos resultados técnicos.

### 3.2. Gestor de Fiscalização

**Necessidades:**

* Distribuir demandas entre os fiscais.
* Acompanhar metas anuais, mensais e semanais.
* Monitorar a carga horária individual e coletiva.
* Avaliar a cobertura territorial.
* Identificar desequilíbrios e oportunidades de otimização.

**Valor entregue:** maior previsibilidade operacional e suporte quantitativo à tomada de decisão.

---

## 🔑 4. User Stories do MVP — Sprint 2

| ID      | User Story                                                                                                                                     | Prioridade | Status   |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | -------- |
| **US5** | Como gestor, quero um algoritmo de distribuição de demandas para equilibrar a carga horária entre fiscais sem deixar municípios desatendidos.  | Alta       | Entregue |
| **US6** | Como analista, quero um catálogo e checklist padronizado de itens de fiscalização para uniformizar as vistorias de balanças e bombas.          | Alta       | Entregue |
| **US7** | Como analista, quero tabelas de tempo de execução e critérios padronizados de resultado para mensurar a duração e a gravidade das ocorrências. | Média      | Entregue |

---

## 📅 5. Histórico e Status das Sprints

| Sprint       | Foco e Entregas Principais                                                                                                           | Status    |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------ | --------- |
| **Sprint 1** | Higienização dos dados, análise descritiva, clusters geográficos e matriz inicial de tempos e distâncias.                            | Concluída |
| **Sprint 2** | Balanceamento da carga de trabalho, classificação dos resultados C1–C6 e definição de metas operacionais anuais, mensais e semanais. | Concluída |
| **Sprint 3** | Comparativo Real vs. Otimizado, dashboard em Power BI, simulação de cenários e relatórios exportáveis.                               | Planejada |

---

## 📊 6. Critérios de Aceitação e Métricas de Validação

### 6.1. Critérios de Aceitação

| Critério                       | Meta                                           | Resultado Informado                    | Situação                                |
| ------------------------------ | ---------------------------------------------- | -------------------------------------- | --------------------------------------- |
| Distribuição das horas anuais  | Índice de Gini ≤ 0,01                          | 0,003                                  | Atingido                                |
| Cobertura da demanda histórica | 100% dos 5.366 locais e 23.202 itens           | 100% de acordo com o plano apresentado | Atingido, sujeito à conferência da base |
| Padronização dos resultados    | Classificação de 100% dos resultados elegíveis | Taxonomia C1–C6 definida               | Validar cobertura efetiva               |
| Jornada por saída              | Máximo de 8 horas                              | Limite estabelecido no modelo          | Validar todas as saídas                 |

### 6.2. Indicadores de Validação

| Indicador                        | Histórico | Plano Otimizado |
| -------------------------------- | --------: | --------------: |
| Índice de Gini das horas         |     0,201 |           0,003 |
| CV anual de locais               |     0,341 |           0,030 |
| CV mensal de locais              |     0,855 |           0,031 |
| Indicador de regularidade mensal |     0,508 |           0,003 |
| CV de variabilidade semanal      |     1,209 |           0,030 |

**Síntese dos resultados:** o plano apresenta melhora expressiva nos indicadores de equidade e regularidade da distribuição das demandas. Entretanto, o aumento das distâncias e dos tempos de deslocamento exige avaliação complementar para verificar se o ganho de equilíbrio operacional compensa o custo logístico adicional.

---

## 🚀 7. Transição para a Sprint 3

A Sprint 3 dará continuidade ao projeto, ampliando a capacidade de análise, visualização e simulação dos resultados operacionais.

### US8 — Comparativo Real vs. Otimizado

**Objetivo:** comparar os indicadores do cenário histórico, desenvolvido na Sprint 1, com os resultados do plano otimizado da Sprint 2.

**Entregas previstas:**

* Comparação da distribuição de horas entre fiscais.
* Análise das quantidades de saídas operacionais.
* Comparação das distâncias e dos tempos de deslocamento.
* Avaliação da cobertura territorial.
* Identificação de ganhos e perdas operacionais.
* Cálculo das variações absolutas e percentuais dos indicadores.

### US9 — Dashboard Interativo em Power BI

**Objetivo:** desenvolver um painel gerencial para acompanhar os principais indicadores da fiscalização.

**Entregas previstas:**

* Visualização da carga horária por fiscal.
* Distribuição das demandas por município e zona.
* Indicadores de conformidade e irregularidades.
* Comparação entre cenário histórico e otimizado.
* Filtros por período, fiscal, município, zona e tipo de instrumento.
* Indicadores de distância, tempo e quantidade de saídas.

### US10 — Simulador de Cenários

**Objetivo:** permitir a avaliação de diferentes configurações operacionais antes da implementação de alterações na distribuição das demandas.

**Entregas previstas:**

* Simulação de mudanças na quantidade de fiscais.
* Avaliação de picos de demanda.
* Análise de diferentes distribuições territoriais.
* Comparação dos impactos sobre horas trabalhadas.
* Avaliação dos efeitos sobre deslocamentos e cobertura.
* Registro das premissas utilizadas em cada cenário.

### US11 — Relatórios Executivos

**Objetivo:** disponibilizar relatórios estruturados para apoiar a gestão e o planejamento das operações de campo.

**Entregas previstas:**

* Relatórios exportáveis em PDF e Excel.
* Resumo dos indicadores operacionais.
* Detalhamento da carga de trabalho por fiscal.
* Relatórios de cobertura municipal e territorial.
* Comparação entre cenários.
* Identificação de pendências e oportunidades de melhoria.

---

## 🧭 8. Resultados Esperados para a Sprint 3

Ao final da Sprint 3, espera-se que a solução permita:

1. Comparar quantitativamente o cenário histórico e o plano otimizado.
2. Visualizar os principais indicadores operacionais em um dashboard interativo.
3. Simular alterações na equipe e na distribuição das demandas.
4. Avaliar o impacto das decisões sobre horas trabalhadas, deslocamentos e cobertura.
5. Gerar relatórios para apoiar a tomada de decisão gerencial.
6. Estabelecer uma base para futuras melhorias no algoritmo de otimização.

---

## 📌 9. Considerações Finais

A Sprint 2 representa uma evolução do MVP ao transformar a análise histórica dos dados em um plano de distribuição operacional com critérios quantitativos de equilíbrio, estimativa de esforço e organização territorial.

A redução do Índice de Gini de 0,201 para 0,003 demonstra melhora significativa na distribuição das horas de trabalho entre os fiscais, enquanto a redução dos coeficientes de variação indica maior regularidade na distribuição das demandas.

Entretanto, o aumento de 27,4% na quilometragem e de 26,5% no tempo de deslocamento evidencia a necessidade de avaliar conjuntamente a equidade operacional e a eficiência logística.

A Sprint 3 deverá aprofundar essa análise por meio de comparações entre cenários, visualizações gerenciais e simulações, permitindo verificar os resultados do plano e identificar oportunidades adicionais de otimização.

---

## 📚 10. Referências Normativas

* **BRASIL.** Lei nº 9.933, de 20 de dezembro de 1999. Dispõe sobre as competências do Conmetro e do Inmetro, institui a Taxa de Serviços Metrológicos e dá outras providências.
* **INMETRO.** Portaria nº 157, de 31 de março de 2022. Regulamento técnico metrológico aplicável aos instrumentos de pesagem não automáticos.
* **INMETRO.** Portaria nº 227, de 26 de maio de 2022. Regulamento técnico metrológico aplicável aos sistemas de medição e abastecimento de combustíveis líquidos.

**Observação:** antes da entrega acadêmica ou institucional, recomenda-se conferir as referências normativas, suas alterações e a vigência dos regulamentos aplicáveis diretamente nas publicações oficiais do Inmetro e do Diário Oficial da União.

---

**Projeto:** API de Análise e Otimização da Fiscalização
**Etapa documentada:** Sprint 2
**Próxima etapa:** Sprint 3 — Análise Comparativa, Dashboard e Simulação de Cenários
