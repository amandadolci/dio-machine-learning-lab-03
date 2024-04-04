# Análise de Sentimentos com Language Studio no Azure AI

## Explorar o Estúdio de Fala

O serviço **Azure AI Speech** transcreve a fala em texto e o texto em fala audível. Você pode usar o AI Speech para criar um aplicativo que possa transcrever notas de reuniões ou gerar texto a partir da gravação de entrevistas.

Neste exercício, você experimentará os recursos do Azure AI Speech usando o Azure AI Speech Studio.

### Criar um recurso de fala do Azure AI

Você pode usar o serviço de Fala criando um recurso **de Fala** ou um recurso **de serviços de IA do Azure**.

Neste exercício, você criará um recurso AI Speech, a menos que já tenha um recurso que possa usar.

1. Em outra guia do navegador, abra o Azure AI Speech Studio , entrando com sua conta da Microsoft.

2. Selecione Configurações e depois Crie um recurso. Configure-o com as seguintes configurações:

   - **Nome do novo recurso**: _Insira um nome exclusivo_.
   - **Assinatura**: _sua assinatura do Azure_.
   - **Região**: _Selecione uma região suportada_.
   - **Nível de preços**: _FO gratuito (se disponível, caso contrário, selecione Padrão S0)_.
   - **Grupo de recursos**: _Selecione ou crie um grupo de recursos com um nome exclusivo_.

3. Selecione Criar recurso. Aguarde até que o recurso seja criado e selecione Usar recurso . A página Introdução à Fala é exibida.

### Explore a fala para texto no Speech Studio

1. Selecione **https://aka.ms/mslearn-speech-files** para baixar o **speech.zip**. Abra a pasta.

2. Na página Introdução à fala, em Fala para texto, localize Fala em tempo real para texto . Selecione **Experimente a fala em tempo real para texto**.

3. Em Escolher arquivos de áudio, selecione **Procurar arquivos** e navegue até a pasta onde você salvou o arquivo. Selecione **WhatAICanDo.m4a** e depois **Abrir**.

4. O serviço Speech transcreve e exibe o texto em tempo real. Se você tiver áudio em seu computador, poderá ouvir a gravação enquanto o texto é transcrito.

5. Revise a saída, que deve ter reconhecido e transcrito com êxito o áudio em texto.

Neste exercício você criou um recurso AI Speech no Speech Studio. Em seguida, você usou o serviço de fala em texto em tempo real para transcrever uma gravação de áudio. Você pôde ver a transcrição do texto sendo gerada à medida que o arquivo de áudio era reproduzido.

## Analise texto com Language Studio

Neste exercício, você explorará os recursos da linguagem Azure AI analisando alguns exemplos de avaliações de hotéis. Você usará o Language Studio para entender se as avaliações são em sua maioria positivas ou negativas.

O Processamento de Linguagem Natural (PNL) é um ramo da IA ​​que lida com a linguagem escrita e falada. Você pode usar a PNL para construir soluções que extraiam significado semântico de texto ou fala, ou que formulem respostas significativas em linguagem natural.

Por exemplo, suponha que a agência de viagens fictícia Margie's Travel incentive os clientes a enviar avaliações sobre estadias em hotéis. Você pode usar o serviço de idiomas para identificar frases-chave, determinar quais avaliações são positivas e quais são negativas ou analisar o texto da avaliação em busca de menções a entidades conhecidas, como locais ou pessoas.

O Azure AI Language Service inclui análise de texto e recursos de PNL. Isso inclui a identificação de frases-chave no texto e a classificação do texto com base no sentimento.

### Crie um recurso de idioma

Você pode usar muitos recursos do Azure AI Language com um recurso **de idioma** ou **de serviços do Azure AI**. Existem alguns casos em que apenas um recurso Idioma pode ser usado. Para o exercício abaixo, utilizaremos um recurso **Linguagem**. Se ainda não o fez, crie um recurso **de idioma** na sua assinatura do Azure.

1. Em outra guia do navegador, abra o portal do Azure em https://portal.azure.com , entrando com a conta da Microsoft associada à sua assinatura do Azure.

2. Clique no botão **＋ Criar um recurso** e pesquise Serviço de idioma. Selecione **criar** um plano **de serviço de idiomas**. Você será levado a uma página para **selecionar recursos adicionais**. Mantenha a seleção padrão e clique em **Continuar para criar seu recurso**.

3. Na página **Criar Idioma**, configure-o com as seguintes configurações:
   - **Assinatura**: _sua assinatura do Azure_.
   - **Grupo de recursos**: _Selecione ou crie um grupo de recursos com um nome exclusivo_.
   - **Região**: _Leste dos EUA_.
   - **Nome**: _Insira um nome exclusivo_.
   - **Nível de preços**: _F0 grátis ou S se F0 grátis não estiver disponível_
   - **Ao marcar esta caixa, confirmo que li e compreendi todos os termos abaixo**: _Selecionado_.
4. Selecione **Revisar + criar** e depois **Criar** e aguarde a conclusão da implantação.

### Configure seu recurso no Azure AI Language Studio

1. Em outra guia do navegador, abra o Language Studio em https://language.cognitive.azure.com e entre.

2. Quando solicitado com Select an Azure resource , faça as seguintes configurações:
   - **Diretório do Azure**: _diretório padrão, o diretório que você está usando_
   - **Assinatura do Azure**: _selecione a assinatura que você está usando_
   - **Tipo de recurso**: _Idioma_
   - **Nome do recurso**: _selecione o recurso de serviço de idioma que você acabou de criar_

Em seguida, selecione **Concluído**.

### Analise avaliações no Language Studio

1. Num navegador web, navegue até **Language Studio** em https://language.cognitive.azure.com.

2. Na página inicial **Bem-vindo ao Language Studio**, **selecione a guia Classificar texto** e, em seguida, selecione o bloco **Analisar sentimento e extrair opiniões**.

3. Em _Selecionar idioma do texto_, selecione **Inglês**.

4. Em _Selecione seu recurso do Azure_, selecione seu recurso.

5. Em _Digite seu próprio texto, carregue um arquivo ou use um de nossos textos de exemplo_, copie e cole a seguinte revisão:

   ```.txt
   Tired hotel with poor service
   The Royal Hotel, London, United Kingdom
   5/6/2018
   This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
   ```

6. Marque a caixa para confirmar que a demonstração incorrerá em uso e poderá gerar custos e selecione **Executar**.

7. Revise a saída. Observe que o _documento_ é analisado quanto ao sentimento, assim como cada _frase_. Selecione **Frase 1** para mostrar a análise de sentimento dessa frase.

Observe que há um sentimento geral seguido por pontuações próximas a três categorias: _pontuação positiva , pontuação neutra e pontuação negativa_. Em cada uma das categorias é atribuída uma pontuação entre 0 e 1. Essas pontuações de confiança indicam a probabilidade do texto fornecido ser um sentimento específico.

Selecione **a frase 1** novamente para fechar.

1. Role para cima para selecionar **Limpar caixa de texto** e copie e cole a seguinte revisão:

   ```.txt
   Good Hotel and staff
   The Royal Hotel, London, UK
   3/2/2018
   Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
   ```

2. Selecione **Executar**. Revise o resultado e o sentimento e o nível de confiança.

3. Selecione **Limpar** caixa de texto novamente e copie e cole a seguinte revisão:

   ```.txt
   Very noisy and rooms are tiny The Lombard Hotel, San Francisco, USA 9/5/2018 Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep–was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds–but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they’ve made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
   ```

4. Selecione **Executar** e analise o sentimento juntamente com o nível de confiança. Dê uma olhada no texto e compare-o com a análise de sentimento que o serviço retornou.

Neste exercício você usou o Language Studio para criar um novo recurso de idioma ou usar um recurso de idioma existente. Você habilitou o recurso em Configurações antes de experimentar o serviço de mineração de sentimento e opinião. Em seguida, você testou o serviço com três trechos de texto.

## Limpar

Se não pretende fazer mais exercícios, exclua todos os recursos que não precisa mais. Isso evita acumular custos desnecessários.

Abra o [portal do Azure](https://portal.azure.com/) e selecione o grupo de recursos que contém o recurso que você criou.
Selecione o recurso e selecione **Excluir** e depois **Sim** para confirmar. O recurso é então excluído.

#

_Instruções de uso dos laboratórios extraídas e traduzidas para pt-BR dos seguintes links:_

*https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/09-speech.html*

*https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/06-text-analysis.html*
