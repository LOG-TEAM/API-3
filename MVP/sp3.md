# 📌 MVP — API de Análise e Otimização da Fiscalização (Sprint 3)

## 🎯 1. Objetivo do MVP e Propósito da Solução
O propósito deste MVP é entregar a **camada de inteligência visual, simulação estratégica e exportação executiva** da API de Análise e Otimização da Fiscalização. Após a consolidação do tratamento de dados (Sprint 1) e da criação do motor de otimização/padronização (Sprint 2), esta terceira e última fase conecta os algoritmos aos tomadores de decisão, oferecendo transparência total sobre os ganhos de produtividade, ferramentas de simulação operacional em tempo real e relatórios executivos prontos para distribuição em campo.

* **Problema Resolvido:** Falta de visibilidade executiva dos indicadores de fiscalização, impossibilidade de simular cenários de variação de frota/demanda e a necessidade de converter dados de otimização em roteiros práticos para a equipe de campo.
* **Hipótese Validada:** É possível demonstrar a eficácia do modelo prescritivo da Sprint 2 comparado ao histórico real da Sprint 1 através de um ecossistema visual no Power BI, permitindo simulações dinâmicas de carga e exportação automatizada de relatórios em PDF e Excel.
* **Valor Entregue:** Transparência nos ganhos de equidade (queda do Gini para 0,003), capacidade de tomada de decisão estratégica via simulador *What-If*, acompanhamento em tempo real via Power BI e agilidade na transmissão de ordens de serviço para os fiscais.

---


## 📝 2. Descrição Detalhada da Solução Entregue & Como Foi Feito (Sprint 3)

### 2.1. Comparativo de Performance Real vs. Otimizado (US8)
* **Como Foi Feito:** Desenvolvimento de rotinas de auditoria na API para cruzar a base histórica sanitizada (Sprint 1) com as saídas geradas pelo algoritmo de redistribuição (Sprint 2).
* **Métricas de Ganho Mensuradas:**
  * **Índice de Gini das Horas Totais:** Reduzido de **0,201 (histórico real)** para **0,003 (plano otimizado)**, alcançando equidade praticamente perfeita entre a equipe.
  * **Coeficiente de Variação Mensal de Locais:** Reduzido de 0,855 para 0,031.
  * **Coeficiente de Variação Semanal de Locais:** Reduzido de 1,209 para 0,030.
  * **Dimensionamento Individual de Carga:** Homogeneização das horas anuais entre **733 h e 745 h por fiscal** (variação máxima de apenas ~12 horas/ano).
  * **Compensação Logística (*Trade-Off*):** Identificação de que o equilíbrio exigiu um acréscimo planejado no tempo de deslocamento (+26,5%) e quilometragem (+27,4%), absorvido dentro do teto de jornada diária.

### 2.2. Dashboard Interativo em Power BI (US9)
* **Como Foi Feito:** Conexão e modelagem da base de dados gerada pela API no Power BI, construindo painéis visuais interativos para acompanhamento de KPIs estratégicos e táticos.
* **Painéis Desenvolvidos:**
  * **Painel de Equilíbrio Individual:** Gráficos comparativos lado a lado (Atual vs. Plano) para as métricas anuais de Horas Trabalhadas, Quilômetros Percorridos, Itens Fiscalizados e Locais Visitados por fiscal.
  * **Painel de Acompanhamento Mensal:** Visão temporal dividida nos 12 meses do ano para monitoramento contínuo da aderência à meta (~740h anuais por fiscal).
  * **Painel Geográfico & Zonas Operacionais:** Mapeamento espacial das zonas de fiscalização (Z1 a Z5) com filtros por município, espécie de instrumento (balanças IPNA vs. bombas medidoras) e taxonomia de resultados (Classes C1 a C6).

### 2.3. Motor de Simulação de Cenários Operacionais (*What-If Analysis*) (US10)
* **Como Foi Feito:** Criação de um módulo de simulação paramétrica na API que permite à gestão recalcular dinamicamente a alocação da fiscalização diante de mudanças nas variáveis de contexto.
* **Cenários Simulados:**
  * **Variação do Quadro de Fiscais:** Readequação imediata da carga horária ao alterar a quantidade de fiscais disponíveis (ex.: simulação de cenários com 6, 7 ou 8 fiscais).
  * **Surtos de Demanda Regional:** Rebalanceamento rápido em caso de aumentos atípicos de solicitações por município (ex.: acréscimo de 20% em inspeções no litoral/Z1 em períodos de alta temporada).
  * **Ajustes de Parâmetros de Jornada:** Recomputo das rotas ao alterar os limites de jornada diária (ex.: 6h vs 8h por saída) ou disponibilidade de motoristas dedicados.

### 2.4. Exportação Automatizada de Relatórios Executivos e Operacionais (US11)
* **Como Foi Feito:** Implementação de scripts em Python (`pandas`, `openpyxl`, `FPDF`/geradores de relatórios) integrados à API para transformar dados brutos otimizados em entregáveis prontos para uso.
* **Formatos de Exportação:**
  * **Relatório Executivo em PDF:** Documento sintético com gráficos comparativos, indicadores de conformidade e mapas regionais direcionado à diretoria do IPEM-SP.
  * **Planilhas Operacionais em Excel (.xlsx):** Roteiros detalhados por fiscal contendo ordem das visitas, estabelecimentos geocodificados, checklist de itens inspecionados e previsão de Tempo Médio de Atendimento (TMA).

---

## 👥 3. Personas / Usuários-Alvo
* **Analista de Fiscalização:** Utiliza os painéis do Power BI para monitorar a execução das metas mensais, avaliar a taxa de conformidade por classe (C1 a C6) e auditar os tempos médios em campo.
* **Gestor de Fiscalização:** Utiliza o simulador de cenários para planejar contingências operacionais e emite relatórios executivos/operacionais em PDF/Excel para distribuir rotas equilibradas aos fiscais.

---

## 🔑 4. User Stories do MVP (Sprint 3)

| ID | User Story | Prioridade | Status |
| :--- | :--- | :--- | :--- | :--- |
| **US8** | Como analista/gestor, quero comparar os indicadores históricos (reais) com os otimizados, para mensurar o percentual de ganho. | Baixa | **Andamento** |
| **US9** | Como analista/gestor, quero visualizar um Dashboard interativo em Power BI, para acompanhar os indicadores operacionais de forma visual. | Média | **Andamento** |
| **US10** | Como analista/gestor, quero simular a variação do número de equipes ou aumento de demandas, para apoiar a tomada de decisão estratégica. | Média | **Andamento** |
| **US11** | Como analista/gestor, quero exportar relatórios e resumos operacionais, para compartilhar os dados de rotas com a equipe de campo (PDF/Excel). | Baixa  | **Andamento** |

---


## 📊 5. Critérios de Aceitação & Métricas de Validação

### Critérios de Aceitação
* Disponibilização de Dashboard interativo no Power BI alimentado pelos dados consolidados da API.
* Módulo de simulação funcional capaz de recalcular o balanceamento de carga para alterações de equipe ou demanda em poucos segundos.
* Exportação automatizada de relatórios de rotas individuais em Excel (.xlsx) e relatórios executivos em PDF.
* Demonstração clara e quantitativa dos ganhos entre a operação histórica e o modelo prescritivo.

### Métricas de Validação Coletadas
* **Ganho de Equidade:** Redução do Índice de Gini em 98,5% (de 0,201 para 0,003).
* **Usabilidade Visual:** 100% das métricas operacionais (horas, km, locais, itens) visualizáveis em visões anuais e mensais no Power BI.
* **Agilidade Operacional:** Redução no tempo de geração de escalas e relatórios de rotas de dias para emissão instantânea.

---

## 📌 6. Considerações Finais
Com a entrega da Sprint 3, a **API de Análise e Otimização da Fiscalização** atinge a sua **versão final completa**, cobrindo o ciclo ponta a ponta desde o tratamento de dados brutos até a inteligência prescritiva e visualização executiva.

---

## 📊 7. Relatório de Avaliação de Desempenho — Sprint 3

---

## 📚 8. Referências Normativas

* **BRASIL.** Lei nº 9.933, de 20 de dezembro de 1999. Dispõe sobre as competências do Conmetro e do Inmetro, institui a Taxa de Serviços Metrológicos e dá outras providências.
* **INMETRO.** Portaria nº 157, de 31 de março de 2022. Regulamento técnico metrológico aplicável aos instrumentos de pesagem não automáticos.
* **INMETRO.** Portaria nº 227, de 26 de maio de 2022. Regulamento técnico metrológico aplicável aos sistemas de medição e abastecimento de combustíveis líquidos.

**Observação:** antes da entrega acadêmica ou institucional, recomenda-se conferir as referências normativas, suas alterações e a vigência dos regulamentos aplicáveis diretamente nas publicações oficiais do Inmetro e do Diário Oficial da União.

---

## 9. Anexos

