📌 MVP — API de Análise e Otimização da Fiscalização

🎯 Objetivo do MVP

O objetivo deste MVP é desenvolver uma primeira versão da API capaz de organizar, analisar e preparar dados históricos de fiscalização, criando uma base confiável para apoiar a tomada de decisão e, posteriormente, alimentar um modelo de otimização das operações.

Problemas que o MVP busca resolver

- Dados históricos podem apresentar inconsistências, duplicidades ou diferentes padrões de preenchimento.
- Dificuldade para visualizar a distribuição das fiscalizações por equipe, região e tipo de inspeção.
- Falta de uma visão geográfica sobre a concentração dos locais fiscalizados.
- Ausência de uma matriz estruturada de distâncias e tempos de deslocamento para utilização em futuros modelos de otimização.

Hipótese a ser validada

A hipótese é que a organização, padronização e análise dos dados históricos de fiscalização permitirão identificar padrões operacionais e geográficos relevantes, possibilitando posteriormente uma melhor distribuição das equipes e um planejamento mais eficiente dos deslocamentos.

Valor entregue ao usuário

O MVP deverá entregar ao analista/gestor uma base de dados confiável e estruturada, acompanhada de análises exploratórias, informações geográficas e uma matriz de distâncias e tempos de deslocamento.

---

📝 Descrição da Solução

Nesta primeira versão será desenvolvida uma API voltada ao tratamento e à análise de dados históricos de fiscalização.

O escopo da Sprint 1 contempla quatro funcionalidades principais:

1. Limpeza e padronização dos dados utilizando Python, garantindo maior qualidade e confiabilidade da base.
2. Análise exploratória descritiva, permitindo analisar as fiscalizações por equipe, região e tipo de inspeção.
3. Mapeamento geográfico e identificação de clusters, possibilitando compreender onde existe maior concentração de locais fiscalizados.
4. Cálculo da matriz de distâncias e tempos de deslocamento utilizando Python, preparando os dados que serão utilizados posteriormente em um modelo de otimização.

Limitações do MVP

Nesta primeira etapa, o MVP não contempla necessariamente a execução do modelo de otimização ou a definição automática das melhores rotas e alocação das equipes.

O foco da Sprint 1 é construir uma base de dados confiável e analiticamente preparada para as próximas etapas do projeto.

---

Necessidades:

- Dados confiáveis e padronizados;
- Facilidade para realizar análises;
- Identificação de padrões nas fiscalizações;
- Visualização da distribuição geográfica das operações.

Dores atendidas:

- Dados desorganizados;
- Dificuldade de análise;
- Falta de visão consolidada das operações.

Persona 2 — Gestor de Fiscalização

Responsável pelo planejamento e acompanhamento das equipes de fiscalização.

Necessidades:

- Conhecer a distribuição das operações;
- Identificar regiões com maior concentração de demanda;
- Avaliar deslocamentos;
- Obter informações para apoiar decisões futuras.

Dores atendidas:

- Dificuldade para visualizar a demanda por região;
- Falta de informações estruturadas para planejamento;
- Dificuldade em estimar distâncias e tempos de deslocamento.

---

🔑 User Stories — Backlog do MVP

ID| User Story| Prioridade| Estimativa
US1| Como analista/gestor, quero ter os dados históricos limpos e padronizados via Python, para garantir a confiabilidade das análises.| Alta| A definir
US2| Como analista/gestor, quero analisar o histórico de fiscalizações por equipe, regiões e tipo de inspeção, para mapear a operação atual por meio de análise exploratória descritiva.| Alta| A definir
US3| Como analista/gestor, quero identificar a distribuição geográfica dos locais fiscalizados, para compreender a concentração de demanda por meio de mapeamento de geolocalização e clusters.| Alta| A definir
US4| Como analista/gestor, quero calcular a matriz de distâncias e tempos de deslocamento usando Python, para servir de entrada no modelo de otimização.| Alta| A definir

---

📅 Sprint(s) Relacionadas

Sprint| Entregas Principais| Status
01| Limpeza e padronização dos dados; análise exploratória; mapeamento geográfico e clusters; matriz de distâncias e tempos| Pendente

Entregas esperadas da Sprint 1

US1 — Tratamento dos dados

- Importação da base histórica;
- Identificação de inconsistências;
- Tratamento de dados ausentes;
- Padronização dos campos;
- Remoção ou tratamento de duplicidades;
- Geração da base limpa.

US2 — Análise exploratória

- Análise das fiscalizações por equipe;
- Análise por região;
- Análise por tipo de inspeção;
- Identificação de padrões e concentrações.

US3 — Análise geográfica

- Identificação/localização dos pontos fiscalizados;
- Visualização da distribuição espacial;
- Identificação de regiões com maior concentração;
- Análise de clusters.

US4 — Matriz de deslocamento

- Identificação dos pontos de origem e destino;
- Cálculo das distâncias;
- Cálculo/estimativa dos tempos de deslocamento;
- Estruturação da matriz para utilização futura no modelo de otimização.

---

📊 Critérios de Aceitação

US1 — Dados limpos e padronizados

- O sistema deve permitir processar os dados históricos utilizando Python.
- Os dados devem possuir padrão consistente de preenchimento.
- Dados duplicados devem ser identificados e tratados.
- Dados ausentes ou inconsistentes devem ser identificados.
- A base final deve estar estruturada para utilização nas análises posteriores.

US2 — Análise exploratória

- O sistema deve permitir analisar as fiscalizações por equipe.
- O sistema deve permitir analisar as fiscalizações por região.
- O sistema deve permitir analisar as fiscalizações por tipo de inspeção.
- Os resultados devem permitir identificar padrões e características da operação atual.

US3 — Geolocalização e clusters

- Os locais fiscalizados devem ser representados geograficamente quando houver dados suficientes para sua localização.
- Deve ser possível identificar regiões com maior concentração de fiscalizações.
- Os agrupamentos encontrados devem auxiliar na interpretação da distribuição da demanda.

US4 — Matriz de distância e tempo

- O sistema deve calcular as distâncias entre os pontos considerados.
- O sistema deve calcular ou estimar os respectivos tempos de deslocamento.
- Os resultados devem ser organizados em formato de matriz.
- A matriz deve estar estruturada para servir como entrada do futuro modelo de otimização.

---

📈 Métricas de Validação

Para avaliar o sucesso do MVP, poderão ser utilizadas as seguintes métricas:

Qualidade dos dados

- Percentual de registros tratados;
- Quantidade de registros duplicados identificados;
- Quantidade de dados ausentes identificados;
- Percentual de registros considerados válidos após o tratamento.

Análise das fiscalizações

- Quantidade total de fiscalizações analisadas;
- Distribuição das fiscalizações por equipe;
- Distribuição por região;
- Distribuição por tipo de inspeção.

Análise geográfica

- Quantidade de locais fiscalizados identificados;
- Número de regiões/áreas analisadas;
- Quantidade de clusters identificados;
- Concentração percentual das fiscalizações nos principais clusters.

Matriz de deslocamento

- Quantidade de pontos considerados;
- Quantidade de pares origem-destino calculados;
- Percentual de pontos com distância calculada;
- Percentual de pontos com tempo de deslocamento calculado.

---

🚀 Próximos Passos

Após a conclusão da Sprint 1, os resultados deverão servir como base para as próximas etapas do projeto.

Próximas evoluções

- Implementação do modelo de otimização;
- Utilização da matriz de distância e tempo como parâmetros do modelo;
- Definição da melhor distribuição das equipes;
- Avaliação de possíveis rotas e deslocamentos;
- Desenvolvimento de indicadores para acompanhamento da operação;
- Integração dos resultados com ferramentas de visualização, quando aplicável;
- Validação dos resultados com usuários/gestores da operação.

Resultado esperado após o MVP

Ao final desta primeira etapa, o projeto deverá possuir uma base histórica tratada, análises exploratórias realizadas, distribuição geográfica mapeada e matriz de distâncias/tempos estruturada, criando os fundamentos necessários para a etapa de otimização da fiscalização.
