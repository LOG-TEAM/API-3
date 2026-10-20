# 📌 MVP — API de Análise e Otimização da Fiscalização (sprint 2)

## 🎯 Objetivo
Desenvolver o projeto focando na **distribuição e balanceamento equilibrado da demanda de fiscalização entre equipes** e na **padronização de procedimentos, critérios de avaliação e métricas de tempo de execução**, utilizando a infraestrutura de dados e geolocalização consolidadas na Sprint 1.
---

## 💡 Valor Entregue
* **Equilíbrio Operacional:** Distribuição justa e proporcional de tarefas entre as equipes de campo, prevenindo a sobrecarga de fiscais.
* **Padronização de Processos:** Definição formal do catálogo de itens e procedimentos a serem vistoriados por tipo de fiscalização.
* **Previsibilidade e Qualidade:** Estabelecimento de métricas de Tempo Médio de Atendimento (TMA) e critérios uniformes de classificação dos resultados.
* **Alocação Inteligente:** Integração com as matrizes geográficas e de deslocamento da Sprint 1 para alocar demandas de forma coerente.

---

## ⚙️ Escopo da Sprint 1 (Funcionalidades Principais)

1. **⚖ Balanceamento e Distribuição de Demandas **
   * *Insumos da Sprint 1 (Feito):* Uso da base de dados higienizada, agrupamentos por *clusters* geográficos e matriz de distâncias/tempos.
   * *Tarefas da Sprint 2 (A Fazer):*
     * Desenvolvimento do algoritmo de distribuição da carga de trabalho proporcional à capacidade operacional de cada equipe.
     * Definição de regras de negócio para limites de jornada e teto de atendimentos por fiscal/dia.
     * Implementação de restrições de proximidade para priorizar o atendimento dentro do mesmo *cluster* regional.

2. **📋 Padronização de Itens e Checklists de Fiscalização **
   * *Insumos da Sprint 1 (Feito):* Mapeamento dos tipos de inspeção e histórico operacional provenientes da análise exploratória descritiva.
   * *Tarefas da Sprint 2 (A Fazer):*
     * Estruturação do catálogo padronizado de itens inspecionados por categoria de fiscalização.
     * Definição de formulários e roteiros de checagem obrigatórios para uniformizar o trabalho em campo.

3. **⏱ Métricas de Tempo e Critérios de Resultado (US 7)**
   * *Insumos da Sprint 1 (Feito):* Levantamento dos tempos históricos de atendimento coletados na base sanitizada.
   * *Tarefas da Sprint 2 (A Fazer):*
     * Estipulação de tabelas de Tempo Médio de Atendimento (TMA) esperados por perfil de vistoria.
     * Formatação de padrões formais para o preenchimento de resultados (ex.: aprovado, notificado, autuado).

---

## ⚠️ Limitação do MVP
Nesta segunda etapa, o MVP **não contempla** a exibição de gráficos e relatórios visuais em dashboards (Power BI), simulações dinâmicas de variação de frotas ou a exportação formatada de rotas em arquivos PDF/Excel. O foco é estritamente a lógica de alocação e a padronização das regras operacionais.

#### 👥 Personas / Usuários Alvo
* **Analista de Fiscalização:** Necessita de rotinas padronizadas, metas de tempo claras e critérios objetivos de resultado para monitorar e avaliar a operação [3, 5, 6].
* **Gestor de Fiscalização:** Necessita de um mecanismo automatizado para distribuição das demandas que garanta equidade de trabalho e evite gargalos operacionais .

#### 🏁 Entregáveis e Próximos Passos

##### 📦 Entregáveis do MVP (Sprint 2)
1. Algoritmo de distribuição equilibrada de demandas integrado à API.
2. Roteiro padronizado com catálogo de itens por tipo de fiscalização.
3. Tabela de métricas de Tempo Médio de Atendimento (TMA) e critérios formais de resultado.
4. Regras de negócio de alocação validadas com base nos dados geográficos da Sprint 1.

##### 🔮 Evolução Futura (Sprint 3)
* **Comparação Real vs. Otimizado (US 8):** Confrontar indicadores históricos com o modelo de alocação para medir percentual de ganho de eficiência .
* **Dashboard Interativo em Power BI (US 9):** Construir painéis visuais para acompanhar os indicadores operacionais e o fluxo de fiscalização .
* **Simulação de Cenários Operacionais (US 10):** Permitir a simulação de alterações no tamanho das equipes ou aumentos atípicos de demanda .
* **Relatório Executivo Exportável (US 11):** Desenvolver a exportação de relatórios em PDF/Excel para direcionamento direto às equipes de campo .
