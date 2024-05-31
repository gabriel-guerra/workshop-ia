# workshop-ia

Software: [Weka](https://sourceforge.net/projects/weka/)
![WhatsApp Image 2024-05-21 at 19 10 36](https://github.com/gabriel-guerra/workshop-ia/assets/159430864/7bcafd26-8744-44b9-abe8-9e7d146e9266)

Momento propício para a IA por conta do hardware: hoje é mais acessível e robusto

Área de foco: Aprendizado de máquina

Próximo da mineração de dados, usam mesmos algoritmos:
- Mineração: Se mantém na mesma base de dados
- Aprend. Máquina: Busca extrapolar o modelo, alcançando novos insights e conjunto de dados; procura padrões 

Tipos:
- Supervisionado: Apresenta resultados direcionados, dentro da base de dados
    - Tarefas:
        - Classificação
        - Regressão: Resposta infos dados contínuos; pode se tornar classificação se colocado em faixa de valores
- Não-supervisionado
    - Tarefas
        - Clusterização: Agrupar dados por grupos, por similaridade que podem não ser tão claras
        - Associação: Fazer junção de informações inicialmente não relacionados
- Reforço
- Deep Learning: Processamento melhorado usando GPU


Supervisionado -> Tarefa -> Classificação

Pipeline: Conjunto de etapas em ordens específicas (foto do quadro)

Base de dados -> Pré-processamento -> Algoritmo de IA -> Modelo -> Predição -> Resultados


## Supervisionado -> Tarefa -> Classificação

Base de dados: Composta por atributos, instâncias, classe
- Atributos: "Colunas" da tabela; podem ser numéricos ou nominais (strings); maioria dos algoritmos trabalha com números
- Instâncias: cada "linha" da tabela; para as linhas se tornarem instâncias é necessário o pré-processamento; são usadas para treinar o modelo
- Classe: O que nós queremos como resultado

Base -> Treino -> MODELO -> Teste -> RESULTADO -> Validação

Etapas:
- Treino: Base de dados -> Modelos
- Teste : Modelo -> Teste em outra base
- Validação: Refazer o teste com mais insights

_Base de treino deve ser diferente da base de teste para eviar viéis_

Validação -> Análise de resultados
- Méticras: Formulações estatísticas para analisar o modelo
    - Mais conhecida: Acurácia (% acertos); mas sozinha essa métrica pode ainda apresentar viéis
    - Ideal usar mais métricas em conjunto

Classes naturalmente são desbalanceadas -> nem sempre tem valores "equilibrados"
Desbalanceamento de 10% para cima ou para baixo normalmente são aceitáveis

Quando há desbalanceamento, podemos "nivelar", elevando as que estão abaixo ou diminuindo as que estão acima; Uso de dados sintéticos

Maioria dos algoritmos não trabalha com dados nulos

### Pré-processamento
- Padronização de dados: simplifica o processamento dos algoritmos
- Podemos criar novos atributos, reduzir número de atributos
- Altamente envolvido com estatística
- Atributos de identificação (como: nome, id) normalmente não são relevantes
- Técnicas que ajudam a descartar atributos, encontrar semelhanças
- Documentar todos os passos (eliminação, inclusão, etc)
- Etapa mais demorada (cerca de 85% do tempo) 

### Algoritmos de IA
- Maior gargalo: Conhecimento dos algoritmos
- Existem diversos algoritmos de aprendizagem de máquina:
    - Lazy: Simples mas que resolvem alguns problemas
        - Naive Bayes: Considera cada atributo individualmente, sem nenhuma correlação
            - Ideal para problemas simples, binários
    - Distância: 
        - K-NN (ou IBK): Vê a proximidade de cada classe e assume um valor com base na proximidade
            - Podemos definir quantos vizinhos serão visitados (K)
    - Árvores de decisão
        - J48: Base de entropia
            - Bastante robustos, algoritmo potente para decisão
        - Random Forest: Cria uma floresta de árvores de decisão
            - Analisa a decisão de várias árvores
    - Redes neurais artificiais
        - Multi Layer Perceptron (MLP)
            - Criação do modelo é complexa
- Gerar o modelo a partir do algoritmo escolhido

### Predição
- Prever um base de testes com o modelo gerado
- Geração de um arquivo no formato: ID|Classe
- Resultados avaliados pela acurácia

## Weka (Java)
- Teste dos modelos que depois podem ser desenvolvidos em python e aplicados em produção 

### Nav
- Explorer (pré-processamento)
- Weka traz base de dados
- Selecionando uma base -> Selecionando um atributo ou instância -> Filter botão choose fornece alguns pré-tratamentos
- Na parte superior temos menus de classificação, clusterização, associação, etc

### Kaggle: Competição de aprendizado de máquina
- Utilizada por empresas para competições de IA
- Qualquer usuário pode criar uma competição, pública ou privada
- https://www.kaggle.com/
