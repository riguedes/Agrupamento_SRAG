# Uso de Algoritmos de Agrupamento para Identificar Pacientes com Síndrome Respiratória Aguda Grave (SRAG)

A Síndrome Respiratória Aguda Grave (SRAG) é uma condição clínica caracterizada por dificuldades respiratórias graves que apresenta como principais sintomas: falta de ar, febre alta, tosse e, em casos severos, a necessidade de suporte ventilatório, se tornando uma preocupação de saúde pública, especialmente em populações vulneráveis, como idosos, crianças e pessoas com comorbidades. Para este projeto foi utilizado uma base de dados do Ministério da Saúde para analisar a situação do Brasil em relação à SRAG. Em 2019, o Ministério da Saúde começou a coletar de forma sistemática dados dos formulários de atendimento médio de pacientes em todo território nacional, formando um dicionário de dados contendo 78 variáveis além de incluir informações pessoais e demográficas, também são armazenados dados sobre os sintomas apresentados durante o atendimento.

Utilização da Base-INFLUD-14-09-2020 particionada para conter somente informações demográficas e pessoais sobre os pacientes, além dos sintomas apresentados durante a consulta. Devido à outras informações numéricas que não seguem a mesma escala de valores dos Sintomas, foi realizado um processo de normalização dos dados, sendo adotada a Standard Scaler, onde se atinge uma média = 0 e o desvio padrão = 1 para cada feature.

Levando em consideração as QPs, utiliza - se como variáveis para o agrupamento apenas os sintomas, por serem valores numéricos e para evitar agrupamentos tendenciosos a partir de informações discretas. Para garantir a qualidade da clusterização, utiliza - se o índice de silhueta, que mede o quão bem uma instância está agrupada com outros semelhantes e quão bem o cluster está separado de outros clusters. Seu valor varia de -1 a 1.

## Objetivos
1. Realizar a mineração de dados sobre a Síndrome Respiratória Aguda Grave (SRAG) no Brasil durante o primeiro semestre de 2020, que representa o período marcado pelo impacto inicial da COVID-19

2. Agrupar pacientes com características em comum, com base nos sintomas apresentados

3. Identificar e classificar o grau de SRAG em cada grupo gerado

4. Identificar relações entre informações pessoais e demográficas dos pacientes com os agrupamentos gerados

## Questões Norteadoras
1. Quais variáveis influenciam diretamente a severidade dos casos de SRAG?

2. Como o algoritmo de agrupamento (K-Means) distingue pacientes com casos severos de SRAG daqueles com casos menos graves?

3. Qual o grau de correlação entre os sintomas apresentados em cada grau de SRAG? 

4. Quais fatores demográficos e pessoais se destacam podem ser relacionados em cada grupo?

## Resultados e Conclusões
1. Todos as variáveis são altamente relevantes, mas a Tosse, Dor de Garganta e Febre se sobressaem enquanto que o Desconforto e a Saturação são sintomas discriminativos na diferenciação dos graus de SRAG, entretanto, os sintomas considerados neste trabalho não explicam a variação do Risco, o que implica que os outros sintomas que não estão no contexto da SRAG são altamente influentes para definir se o paciente está em situação de risco.

2. O K-Means conseguiu diferenciar os pacientes em 6 grupos diferentes de forma considerável, como provado pelo Índice de Silhueta igual a 0.47, sendo a clusterização feita pelos fatores numéricos (sintomas) que conseguiu expor características em comum nos fatores discretos (informações pessoais).

3. Os sintomas tendem a acontecer juntos de forma positiva, isto é, quando um sintoma está alto, os outros tendem a aumentar também. Isto é especialmente verdadeiro para a correlação entre Febre e a Tosse. Além disso, o Desconforto e a Saturação, Febre e Tosse, e a Dor de Garganta são sintomas que, em conjunto, diferenciam o grau de SRAG. Por fim, a Dispneia se mostrou relevante apenas para o grupo de maior risco.

4. Os estados de São Paulo, Rio de Janeiro e Minas Gerais apresentam o maior acúmulo de pacientes, independente da zona de habitação, os clusters 0 e 5 – característicos pela Tosse e Dor de Garganta – apresentam um volume maior de pacientes jovens, seja masculino ou feminino. Assim, para o sexo Indefinido, também há uma maior concentração de jovens, destacando-se por fazerem parte dos clusters de pacientes que não estão em grupos de SRAG.







