# Natural_Language_Processing com Pyspark

Natural Language Processing refere-se a um conjunto de técnicas para lidar com dados de texto usando o PySpark. Os dados de texto podem ser:

   * estruturados ou não estruturados
    
e temos que aplicar várias etapas para torná-los prontos para análise. O NLP já é um grande contribuidor para vários aplicativos. Atualmente, existem muitos aplicativos de NLP que são muito usados pelas empresas, como:
   1. chatbot
   2. reconhecimento de fala
   3. tradução de idiomas
   4. sistemas de recomendação
   5. detecção de spam 
   6. análise de sentimento
   
Ou seja, área de ciência se preocupa em oferecer uma série de etapas para processar dados de texto e aplicar um Algoritmo de Aprendizado de Máquina sobre eles.

# Etapas envolvidas no NLP

Do ponto de vista de Machine Learning, existem cinco etapas principais que devem ser seguidas para preparar os dados de texto para análise. 
    1. Reading the corpus
    2. Tokenization
    3. Cleaning /Stopword removal
    4. Stemming
    5. Converting into Numerical Form 
---    
**Corpus**

Um corpus é conhecido como a coleção inteira de documentos de texto. Por exemplo, suponha que temos milhares de e-mails em uma coleção que precisamos processar e analisar para nosso uso. Esse grupo de e-mails é conhecido como corpus, pois contém todos os documentos de texto.
---

**Tokenizar**

O método de dividir uma determinada frase ou coleção de palavras de um documento de texto em palavras separadas/individuais é conhecido como tokenização. Ele remove os caracteres desnecessários, como pontuação. Por exemplo, se tivermos uma frase como: 
    1. Entrada: ** Ele gostou muito da cidade de Londres. Ele está lá por mais dois dias.**
    2. Tokens: ** Ele, realmente, gostou de, Londres, Cidade, Ele, está, lá, por, dois, mais, dias **
Terminamos com 13 fichas para a frase de entrada acima.

---
**Stopwords Removal**

Palavras como: 'this', 'the', 'to' , 'was', 'that', etc. são conhecidas como stopwords e agregam muito pouco valor à análise

    * Se forem usados na análise, aumentam a sobrecarga de computação sem agregar muito valor ou insight.
    
    * Portanto, é importamte eliminar essas palavras irrelevantes dos tokens. No PySpark, usamos StopWordsRemover para remover as stopwords.

Como você pode observar, a coluna de tokens contém palavras muito comuns como 'this', 'the', 'to' , 'was', 'that', etc. Essas palavras são conhecidas como stopwords e parecem agregar muito pouco valor à análise. Se forem usados na análise, aumentam a sobrecarga de computação sem agregar muito valor ou insight. Portanto, é sempre considerado uma boa ideia eliminar essas palavras irrelevantes dos tokens. No PySpark, usamos StopWordsRemover para remover as stopwords.
---

**Bag of Words**

Consiste em representar os dados do texto em forma numérica para que sejam utilizados por Machine Learning ou qualquer outra análise. 

  * Os dados de texto geralmente não são estruturados e variam em seu comprimento. O BOW (Bag of Words) nos permite converter a forma de texto em uma forma de vetor numérico considerando:
  
      *. a ocorrência das palavras em documentos de texto. Por exemplo,
      
          Doc 1: **O melhor da vida é viajar**
          Doc 2: **Viajar é o melhor remédio**
          Doc 3: **Deve-se viajar com mais frequência**
          
Vocabulário: A lista de palavras únicas que aparecem em todos os documentos. No exemplo acima, temos 13 palavras únicas que fazem parte do vocabulário. **Cada documento pode ser representado por este vetor de tamanho fixo 13**.

      *. Outro elemento é a representação da palavra no documento específico usando um valor booleano. Ou seja, se no documento aparece a palavra única, recebe 1, caso contrário, recebe zero.
      
O **BOW** não considera a ordem das palavras no documento e o significado semântico da palavra e, portanto, é o método mais básico para representar os dados do texto em forma numérica.
---

**Count Vectorizer**

Count Vectorizer faz a contagem da palavra que aparece no documento específico. 

---
**Term Frequency – Inverse Document Frequency (TF-IDF)**

É outra abordagem para converter dados de texto em formato numérico.

Este método tenta normalizar a frequência de ocorrência de palavras com base em outros documentos. A ideia é dar mais peso à palavra se ela aparecer mais vezes no mesmo documento, mas penalizar se ela aparecer mais vezes em outros documentos também.

Isso indica que uma palavra é comum em todo o corpus e não é tão importante quanto indica sua frequência no documento atual. 

**Term Frequency**: Pontuação com base na frequência da palavra no documento atual. 

**Inverse Document Frequency**: Pontuação com base na frequência de documentos que contém a palavra atual.
