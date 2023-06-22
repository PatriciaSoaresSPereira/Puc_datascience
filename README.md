# Puc_datascience


Processamento de dados - UCI: Heart disease

• Qual é a descrição do problema?

Este diretório contém 4 bancos de dados sobre diagnóstico de doenças cardíacas. Todos os atributos têm valor numérico. Os dados foram colhidos do quatro locais a seguir:

  1. Cleveland Clinic Foundation (cleveland.data)
  2. Instituto Húngaro de Cardiologia, Budapeste (hungarian.data)
  3. V.A. Centro Médico, Long Beach, CA (long-beach-va.data)
  4. Hospital Universitário, Zurique, Suíça (suíça.data)

Cada banco de dados tem o mesmo formato de instância. Enquanto os bancos de dados têm 76 atributos brutos, apenas 14 deles são realmente usado.
Você tem premissas ou hipóteses sobre o problema? Quais?

Problema de Classificação,tentar prever se um paciente tem ou não uma doença cardíaca, a partir de informações como idade, sexo, pressão arterial, entre outras coisas. Obtendo no dataframe disponível 13 atributos e 303 instancias, pagarei o dataframe final farei treino e teste , atributos brutos, apenas 14 deles são realmente usados.

Assim eu peguei o liberdade de fazer 2 cópias de cada dataframe: uma com todos os atributos e 1 com os 14 atributos realmente usados em experimentos anteriores.

Informações do atributo: -- Apenas 14 usados -- 1. #3 (idade) -- 2. #4 (sexo) -- 3. #9 (pc) -- 4. #10 (trestbps) -- 5. #12 (col) -- 6. #16 (fbs) -- 7. #19 (restecg) -- 8. #32 (thalach) -- 9. #38 (exang) -- 10. #40 (velho pico) -- 11. #41 (inclinação) -- 12. #44 (ca) -- 13. #51 (tal) -- 14. #58 (num) (o atributo previsto

   Documentação completa do atributo:
   1 id: número de identificação do paciente
   2 ccf: número do seguro social (substituí por um valor fictício de 0)
   3 idade: idade em anos
   4 sexo: sexo (1 = masculino; 0 = feminino)
   5 painloc: localização da dor no peito (1 = subesternal; 0 = caso contrário)
   6 painexer (1 = provocado por esforço; 0 = caso contrário)
   7 relrest (1 = aliviado após repouso; 0 = caso contrário)
   8 pncaden (soma de 5, 6 e 7)
   9 cp: tipo de dor no peito
     -- Valor 1: angina típica
     -- Valor 2: angina atípica
     -- Valor 3: dor não anginosa
     -- Valor 4: assintomático
  10 tretbps: pressão arterial em repouso (em mm Hg na admissão ao
     hospital)
  11 horas
  12 col: colesterol sérico em mg/dl
  13 fumo: acredito que seja 1 = sim; 0 = não (é ou não fumante)
  14 cigs (cigarros por dia)
  15 anos (número de anos como fumante)
  16 fbs: (açúcar no sangue em jejum > 120 mg/dl) (1 = verdadeiro; 0 = falso)
  17 dm (1 = história de diabetes; 0 = sem tal história)
  18 familiares: história familiar de doença arterial coronariana (1 = sim; 0 = não)
  19 restecg: resultados eletrocardiográficos em repouso
     -- Valor 0: normal
     -- Valor 1: com anormalidade da onda ST-T (inversões da onda T e/ou
                 elevação ou depressão de > 0,05 mV)
     -- Valor 2: mostrando hipertrofia ventricular esquerda provável ou definitiva
                 pelos critérios de Estes
  20 ekgmo (mês de leitura de ECG de exercício)
  21 ekgday (dia da leitura do ECG do exercício)
  22 ekgyr (ano de exercício de leitura de ECG)
  23 dig (digitalis usado para exercício ECG: 1 = sim; 0 = não)
  24 prop (Beta bloqueador usado durante o exercício ECG: 1 = sim; 0 = não)
  25 nitr (nitratos usados durante o exercício ECG: 1 = sim; 0 = não)
  26 pro (bloqueador de canal de cálcio usado durante exercício ECG: 1 = sim; 0 = não)
  27 diurético (diurético usado durante o exercício ECG: 1 = sim; 0 = não)
  28 proto: protocolo de exercícios
       1 = Bruce
       2 = Kottus
       3 = McHenry
       4 = Balke rápido
       5 = Balke
       6 = Noughton
       7 = bicicleta 150 kpa min/min (Não tenho certeza se "kpa min/min" é o que estava
           escrito!)
       8 = bicicleta 125 kpa min/min
       9 = bicicleta 100 kpa min/min
      10 = bicicleta 75 kpa min/min
      11 = bicicleta 50 kpa min/min
      12 = ergômetro de braço
  29 thaldur: duração do teste de esforço em minutos
  30 thaltime: hora em que a depressão da medida ST foi observada
  31 atingidos: metas alcançadas
  32 thalach: frequência cardíaca máxima alcançada
  33 thalrest: frequência cardíaca em repouso
  34 tpeakbps: pico de pressão arterial de exercício (primeira de 2 partes)
  35 tpeakbpd: pico de pressão arterial de exercício (segundo de 2 partes)
  36 manequim
  37 trestbpd: pressão arterial em repouso
  38 exang: angina induzida por exercício (1 = sim; 0 = não)
  39 xhypo: (1 = sim; 0 = não)
  40 oldpeak = depressão do ST induzida pelo exercício em relação ao repouso
  41 slope: a inclinação do pico do segmento ST do exercício
     -- Valor 1: ascendente
     -- Valor 2: plano
     -- Valor 3: descendente
  42 rldv5: altura em repouso
  43 rldv5e: altura no pico do exercício
  44 ca: número de vasos principais (0-3) coloridos por fluoroscopia
  45 restckm: irrelevante
  46 exerckm: irrelevante
  47 restef: fração de ejeção do radionuclídeo de repouso (sp?)
  48 restwm: anormalidade de movimento da parede de descanso (sp?)
     0 = nenhum
     1 = leve ou moderado
     2 = moderado ou grave
     3 = acinesia ou discemem (sp?)
  49 exeref: exercício radinalid (sp?) fração de ejeção
  50 exerwm: exercício parede (sp?) movimento
  51 tal: 3 = normal; 6 = defeito corrigido; 7 = defeito reversível
  52 talsev: não usado
  53 talpul: não usado
  54 lóbulo da orelha: não usado
  55 cmo: mês de cateterismo cardíaco (sp?) (talvez "chamada")
  56 cdia: dia do cateterismo cardíaco (sp?)
  57 cir: ano do cateter cardíaco (sp?)
  58 num: diagnóstico de doença cardíaca (estado angiográfico da doença)
     -- Valor 0: < 50% de estreitamento do diâmetro
     -- Valor 1: > 50% de estreitamento do diâmetro
     (em qualquer embarcação principal: os atributos 59 a 68 são embarcações)
  59 lmt
  60 ladprox
  61 ladista
  62 dias
  63 cxmain
  64 ramos
  65 om1
  66 om2
  67 rcaprox
  68 rcadista
  69 lvx1: não usado
  70 lvx2: não usado
  71 lvx3: não usado
  72 lvx4: não usado
  73 lvf: não usado
  74 catef: não usado
  75 lixo: não usado
  76 nome: sobrenome do paciente
(Eu substituí isso pela string fictícia "nome")

• Que restrições ou condições foram impostas para selecionar os dados?

Ao abrir o dataset, podemos perceber que não há nomes nas colunas. Tanto que ao utilizar a função pd.read_csv(), a primeira entrada das informações foi utilizada como se fosse o nome.

Obs.: A função pd.read_csv() foi utilizada para abrir o arquivo .data, pois o mesmo estava estruturado como um arquivo csv. Se não estivesse, teriamos que utilizar outro método para converter os dados em um DataFrame.

• Descreva o seu dataset (atributos, imagens, anotações, etc)

De acordo com o dicionário de variáveis, o dataset de Cleveland, possui 14 variáveis e 303 entradas, que é exatamente o tamanho do nosso DataFrame

È importante conhecer o nome e a ordem das variáveis, e a razão disso é para que possamos atribuir a cada coluna o atributo certo. Trocar a ordem ou algum nome traria problemas sérios na hora de analisar os dados.







