# Desafio de Projeto 3 - Análise de Sentimentos com Language Studio no Azure AI

O *Natural Language Processing* (NLP) é uma disciplina da Inteligência Artificial que se concentra na interação entre a computação e a linguagem humana. Objetiva capacitar computadores a compreender, interpretar e gerar texto e fala de maneira semelhante aos seres humanos.

As aplicações do NLP são vastas e abrangem uma ampla gama de domínios, desde assistentes virtuais pessoais até análise de sentimentos em mídias sociais, tradução automática, resumo de texto, extração de informações de grandes volumes dados textuais, entre outros. A crescente demanda por comunicação eficaz entre humanos e máquinas impulsiona o interesse e a evolução rápida e exponencial recente dos algoritmos, aumento na capacidade de processamento computacional e a crescente quantidade de dados disponíveis.

Neste desafio de projeto, proposto no *Bootcamp AI Fundamentals* da DIO, são exploradas as capacidades do ***Azure AI Language*** ao analisar algumas avaliações de consumidores. No conjunto de ferramentas disponibilizadas pelo *Language Studio*, este projeto concentra na utilização de recursos para classificação de texto, especificamente voltados à análise de sentimentos e mineração de opiniões, visando entender se as avaliações possuem caráter mais positivo ou negativo.

Os textos aqui processados foram coletados diretamente do sistema de avaliações do Google.

## Passo-a-Passo

### Criação de um recurso de Linguagem

1. Para criação deste recurso é possível selecionar ***+ Create a resource*** na página inicial do [Azure portal](https://portal.azure.com). Na tela ***Create a resource***, procurar por *Language service*, selecionar ***Create*** e, em seguida, ***Language service***. Na página ***Select Aditional features*** que será aberta, manter as seleções padrão e selecionar ***Continue to create your resource***.

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/0c2fa777-310c-4652-954d-46c6442697f5)

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/9e48804f-e923-4a84-a9d5-6487fb3a9035)

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/4745c15c-2bea-4d79-b7ea-8e9013e5954c)

2. Na página ***Create Language***, realizar as configurações conforme sugerido abaixo, selecionar ***Review + Create*** e então, após revisar as configirações na próxima página, selecionar ***Create***. Esperar que os recursos sejam completamente provisionados.

* ***Subscription***: Escolher a assinatura a ser utilizada na criação do recurso;
* ***Resource Group***: Grupo de recursos onde será alocado. Caso não exista um grupo de recursos definido, um novo poderá ser criado neste passo através do link *Create New*;
* ***Region***: Selecionar a região em que serão provisionados os recursos, atentando-se para a diferença de precificação dos recursos em cada região;
* ***Name***: Escolher um nome único para o recurso;
* ***Princing tier***: *Free F0* ou *S* (caso o *Free F0* não estiver disponível);
* ***By checking this box I acknowledge that I have read and understood all the terms below***: Selecionar.

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/070e3955-ce37-4675-9794-08a9b4435a40)

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/a1f58836-221a-450a-962e-d30bb887ea66)

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/c51b5929-d6dd-4f9b-b67a-73b59010afa2)

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/7c20c77a-b40f-4fa3-9196-bb379e3da085)

### Configuração do recurso no *Azure AI Language Studio* 

1. Acessar a página do ***Language Studio*** à partir do portal ou através deste [link](https://language.cognitive.azure.com) e efetuar a devida autenticação.

2. Na tela ***Select an Azure resource***, escolher o recurso recém criado e então selecionar ***Done***.

* ***Azure directory***: Escolher *Default Directory* ou o diretório da assinatura utilizada;
* ***Azure subscription***: Escolher a assinatura utilizada na criação do recurso;
* ***Resource type***: Escolher *Language*;
* ***Resource name***: Escolher o serviço de Linguagem criado anteriormente. 

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/f51dbd8c-ca18-40a2-8224-5b90643e0295)

OBS: Caso a tela ***Select an Azure resource*** não seja apresentada ao efetuar a autenticação no ***Language Studio***, acessar a página ***Settings*** e na aba ***Resources*** escolher o recurso criado e selecionar ***Managed identity***.

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/531ba7f0-0224-4810-8aaa-068d1b410e45)

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/9ee41609-5d4a-4dc5-b553-7427ff90c2d6)

### Análise de sentimento no *Language Studio*

1. Na página inicial do ***Language Studio***, selecionar a aba ***Classify text*** e, em seguida, o bloco ***Analyze sentiment and mine opinions***.

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/c6d7217c-4334-493a-a919-7128341b7cbc)

2. Na tela ***Enter some text to try out***, escolher a linguagem do texto a ser analisado (neste caso *Portuguese (Brazil)*), selecionar o recurso criado anteriormente e digitar/colar o texto ou procurar localmente por um arquivo ".txt" a ser carregado. Marcar a *checkbox* reconhecendo que tal demonstração poderá gerar custos e, então, selecionar ***Run***. Depois de processado, será possível verificar os resultados obtidos na seção ***Examine the results***.

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/8f3e48e7-cfba-4afe-afea-31aa43edce1a)

OBS: São apresentados os sentimentos consolidados de todo documento ou detalhados em cada frase. São atribuídas notas que variam de 0 a 1, associadas a três categorias: positiva, neutra e negativa.

### IMPORTANTE: Limpeza dos recursos provisionados

1. Ao final do projeto, ao serem esgotadas as experimentações, recomenda-se que os recursos provisionados sejam removidos para evitar o desperdício e cobranças sobre custos não previstos. Para tal, retornar até o Portal do Azure e procurar pela página ***Resource Groups***, selecionar o grupo que contém o recurso criado anteriormente e em seguida ***Delete resource group***. Será solicitado que o nome do grupo de recursos seja informado para confirmar a remoção e é necessário finalmente selecionar ***Delete***.

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/30b19d82-0872-436b-b8cf-b37e0dc5856c)

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/1c01e07f-dc1f-419c-8498-2387eb0957f3)

![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/573c2b95-de51-4e9f-a087-f6f73fe8f0af)


2. Finalizado o processo, confirmar que realmente não sejam listados recursos remanescentes utilizados no projeto.

## Resultados obtidos

Foram realizados testes com três textos criados por consumidores reais sobre serviços prestados por um hotel específico, coletados diretamente do sistema de avaliações do Google. Os arquivos com os textos originais utilizados podem ser encontrados no diretório [inputs](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/blob/main/inputs) e os resultados em formato *.json* podem ser acessados no diretório [outputs](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/blob/main/outputs).

1.
    * Entrada:
      
        * Arquivo de texto: [avaliacao-1.txt](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/blob/main/inputs/avaliacao-1.txt)
  
        * ![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/a44d4eeb-6c40-4b87-b316-057884e70fe4)

    * Resultados:
      
        * JSON: [avaliacao-1.json](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/blob/main/outputs/avaliacao-1.json)
          
        * ![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/c8c0eeb3-d5de-4cfa-97e3-bae1b2771747)

2.
    * Entrada:
    
        * Arquivo de texto: [avaliacao-2.txt](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/blob/main/inputs/avaliacao-2.txt)
  
        * ![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/714c7fc8-8cac-4bea-b194-862c69429a27)

    * Resultados:
      
        * JSON: [avaliacao-2.json](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/blob/main/outputs/avaliacao-2.json)
          
        * ![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/03ffc89b-c062-4ab0-85f3-51ee78e0990a)

3. 
    * Entrada:
      
        * Arquivo de texto: [avaliacao-3.txt](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/blob/main/inputs/avaliacao-3.txt)
          
        * ![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/da124032-a048-46a5-8012-ba8f1745d4b2)
          
    * Resultados:
      
        * JSON: [avaliacao-3.json](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/blob/main/outputs/avaliacao-3.json)
          
        * ![image](https://github.com/danielfscosta/dio-aifundamentals-projeto3-azls/assets/69484807/376645ce-6572-49ed-82a2-25272307a6ca)
