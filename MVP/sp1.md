# 📌 MVP — API de Análise e Otimização da Fiscalização

## 🎯 Objetivo
Desenvolver a primeira versão de uma API para organizar, analisar e padronizar dados históricos de fiscalização, criando a base necessária para alimentar um modelo futuro de otimização de operações, rotas e alocação de equipes.

---

## 💡 Valor Entregue
* **Base de Dados Confiável:** Padronização e higienização dos registros históricos.
* **Análise Exploratória:** Diagnóstico detalhado por equipe, região e tipo de inspeção.
* **Mapeamento Geográfico:** Visualização espacial da demanda e identificação de agrupamentos (*clusters*).
* **Matriz de Deslocamento:** Cálculo estruturado de distâncias e tempos entre pontos de fiscalização.

---

## ⚙️ Escopo da Sprint 1 (Funcionalidades Principais)

1. **🧹 Limpeza e Padronização dos Dados**
   * Tratamento de inconsistências, remoção de duplicidades e validação de campos via Python.
   
2. **📊 Análise Exploratória Descritiva**
   * Mapeamento da operação atual segregada por equipe, município/região e tipo de inspeção.

3. **🗺️ Mapeamento Geográfico e Clusters**
   * Representação espacial dos locais fiscalizados e identificação de regiões com alta concentração de demanda.

4. **📍 Matriz de Distâncias e Tempos**
   * Cálculo de trajetos e tempos estimados de deslocamento para servir de insumo ao modelo matemático futuro.

---

## ⚠️ Limitação do MVP
Nesta primeira etapa, o MVP **não contempla** a execução do modelo de otimização final nem a definição automática de rotas/alocações. O foco exclusivo é a preparação técnica e analítica da base de dados.

---

## 👥 Personas / Usuários-Alvo

* **Analista de Fiscalização:** Necessita de dados limpos, padronizados e consolidados para identificar padrões da operação.
* **Gestor de Fiscalização:** Necessita de visibilidade sobre a distribuição regional da demanda e custos de deslocamento para tomada de decisão.

---

## 🏁 Entregáveis e Próximos Passos

### 📦 Entregáveis do MVP
1. Base histórica tratada e estruturada.
2. Relatórios de análises exploratórias da operação.
3. Mapeamento geográfico e *clusters* de atendimento.
4. Matriz de distâncias e tempos pronta para algoritmos de otimização.

### 🔮 Evolução Futura (Próximas Sprints)
* Implementação dos algoritmos de otimização de rotas e equipes.
* Integração da matriz de deslocamento como parâmetro operacional.
* Criação de painéis e indicadores de acompanhamento em tempo real.


https://github.com/user-attachments/assets/160ae7f6-de92-4cb3-85c5-114a158d9f9f

