# Classificação com Naive Bayes

## Objetivo

Os objetivos deste trabalho são consolidar uma base de dados (dataset), explorar o pré-processamento de texto no contexto de NLP e testar o algoritmo de classificação probabilística Naive Bayes para determinar se o comentário contido na base é negativo ou positivo. 

## Metodologia

O projeto foi desenvolvido seguindo as etapas abaixo, sendo possível definir as etapas chaves como aquisição dos dados, definição da base textual, pré-processamento dos dados, treinamento do modelo e apresentação de resultados. Todos os processos do projeto foram feitos com a linguagem Python e sua bibliotecas no ambiente Jupyter Notebook.

### Pré-processamento dos dados
O pré-processamento dos dados começa com a normalização das palavras, que caracteriza o processo de colocar todas as palavras em um determinado padrão como minúscula ou maiúscula. A próxima fase é a tokenização, que diz respeito à quebra das frases em palavras, seguido disso, é a fase de remover as stop words, que são palavras que não possuem importância na classificação, como preposições, artigos, conjunções e pronomes. Feito isso, a primeira versão da base textual está concretizada, agora é possível fazer o processo de stemização. Com as três bases criadas, a próxima fase é a vetorização da base, seguida pela normalização dos valores, treinamento e validação do modelo e apresentação dos resultados.

A normalização das palavras foi feita transformando toda a frase em formato minúsculo e a tokenização foi feita através da função word_tokenize da biblioteca  Natural Language Toolkit (NLTK) juntamente com a função isalpha()  do Python, que verifica se o vetor de caracteres contém somente letras.

As Stop Words foram removidas com base nas  palavras geradas através da  função stopwords.words('english'), a lógica é salvar todas as palavras que  não estejam nesse conjunto de palavras.

A Lematização é o processo de reduzir uma palavra ao seu sufixo inicial da desinência gramatical (PLISSON; LAVRAC; MLADENIC et al., 2004), já a Stemização é caracterizada por reduzir a palavra ao seu radical, não gerando necessariamente uma palavra que exista. Abaixo, na tabela, está um exemplo das transformações em algumas palavras.

| Original   | Stemização | Lematização |
|------------|------------|-------------|
| amigos     | amig       | amigo       |
| amigas     | amig       | amigo       |
| amizade    | amizade    | amizade     |
| carreira   | carr       | carreira    |
| carreiras  | carr       | carreira    |

A vetorização da base foi feita através da função CountVectorizer() da biblioteca Scikit Learn, que tem como objetivo converter a base de dados em uma matriz com os quantificação dos tokens, separados anteriormente, em cada frase.

### Treinamento do modelo

O modelo escolhido foi o MultinomialNB e foi treinado com 70% dos dados e testado com 30%, a validação foi feita por meio do cross_validate. As métricas usadas foram a acurácia, recall, precisão e o f1_score.

## Resultados

O modelo treinado com base stemizada obteve um resultado melhor em comparação com o modelo treinado com a base se esse tipo de transfomração. Segue os resultados com a matriz de confusão e as métricas.
![image](https://github.com/user-attachments/assets/5778e3fb-1827-422b-a9aa-b153c6fa220c)

|            | Precision | Recall | F1-Score | Support |
|------------|-----------|--------|----------|---------|
| 0          | 0.84      | 0.80   | 0.82     | 305     |
| 1          | 0.80      | 0.84   | 0.82     | 294     |
| **Accuracy**    |           |        | 0.82     | 599     |
| **Macro Avg**   | 0.82      | 0.82   | 0.82     | 599     |
| **Weighted Avg**| 0.82      | 0.82   | 0.82     | 599     |

## Conclusões

Ao fim do trabalho, pode-se perceber e entender como o Naive Bayes realiza as classificações, além de como é a rotina de pré-processamento de dados textuais.

## Autor

Felipe Lapa do Nascimento.
18 de set. de 2023.
