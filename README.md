# 🎙️ Azure AI Speech & Language Studio: Fala e Linguagem Natural

Repositório de documentação do desafio da **DIO** sobre análise de fala e linguagem natural com serviços de IA da Azure. Aqui registro o passo a passo, os resultados e os aprendizados de dois laboratórios práticos.

## 📌 Sumário

- [Objetivo](#-objetivo)
- [Conceitos-chave](#-conceitos-chave)
- [Laboratório 1: Azure AI Speech (fala → texto)](#-laboratório-1-azure-ai-speech-fala--texto)
- [Laboratório 2: Language Studio (análise de sentimento)](#-laboratório-2-language-studio-análise-de-sentimento)
- [Insights e aprendizados](#-insights-e-aprendizados)
- [Boas práticas e custos](#-boas-práticas-e-custos)
- [Referências](#-referências)

## 🎯 Objetivo

Praticar o uso do **Azure AI Speech** e do **Azure AI Language** para entender como a IA transcreve fala em texto e extrai significado de textos escritos, documentando o processo de forma clara e reutilizável.

## 🧠 Conceitos-chave

| Conceito | Descrição |
|---|---|
| **Speech to Text** | Converte áudio falado em texto (transcrição) |
| **Text to Speech** | Converte texto em fala sintetizada |
| **NLP** | Processamento de Linguagem Natural: extrai significado de texto ou fala |
| **Análise de sentimento** | Classifica um texto como positivo, neutro ou negativo, com scores de confiança de 0 a 1 |
| **Opinion mining** | Associa sentimentos a aspectos específicos do texto (ex.: quarto, localização, serviço) |

## 🔊 Laboratório 1: Azure AI Speech (fala → texto)

**Ferramenta:** Speech Playground (dentro do portal Azure AI Foundry)
**Recurso usado:** transcrição em tempo real (*Real-time transcription*)

### Passo a passo

1. Acessei o **Azure AI Foundry** e entrei com minha conta.
2. Criei um **projeto** (que gera hub, recurso Azure AI services, storage account, key vault e resource group). Selecionei uma região compatível com o lab (East US, France Central, Korea Central, West Europe ou West US).
3. No menu lateral do projeto, abri **AI Services** e selecionei o bloco **Speech**.
4. Em *Try out Speech capabilities*, escolhi **Real-time transcription**.
5. Fiz upload do arquivo de áudio `WhatAICanDo.m4a` (do pacote `speech.zip` fornecido pelo lab).
6. Acompanhei a transcrição sendo gerada em tempo real enquanto o áudio era reproduzido.

### Resultado

> ✍️ _Cole aqui o trecho transcrito e suas observações sobre a precisão (pontuação, nomes próprios, termos técnicos)._

![Transcrição em tempo real](images/speech-transcricao.png)

## 💬 Laboratório 2: Language Studio (análise de sentimento)

**Ferramenta:** Language Studio, recurso *Analyze sentiment and mine opinions*

### Passo a passo

1. No **portal Azure**, criei um recurso **Language service** (grupo de recursos, região, nome único e tier **Free F0**, ou **S** se o F0 não estivesse disponível).
2. Abri o **Language Studio** e vinculei o recurso criado (diretório, assinatura, tipo *Language* e nome do recurso).
3. Na aba **Classify text**, selecionei **Analyze sentiment and mine opinions**, com idioma **English**.
4. Testei **três avaliações de hotel**, uma por vez, e analisei o resultado de cada uma:

| # | Avaliação | Perfil do texto | Sentimento geral | Scores (pos / neu / neg) |
|---|---|---|---|---|
| 1 | *Tired hotel with poor service* (Royal Hotel, Londres) | Predominantemente negativa | _preencher_ | _preencher_ |
| 2 | *Good Hotel and staff* (Royal Hotel, Londres) | Predominantemente positiva | _preencher_ | _preencher_ |
| 3 | *Very noisy and rooms are tiny* (Lombard Hotel, São Francisco) | Mista, com críticas e elogios | _preencher_ | _preencher_ |

### Resultado

![Análise de sentimento](images/language-sentimento.png)

> ✍️ _Compare o sentimento retornado com o texto. Na avaliação 3, o serviço captou o equilíbrio entre pontos negativos (ruído, quartos pequenos) e positivos (limpeza, localização)?_

## 💡 Insights e aprendizados

- O **Speech Playground** permite testar transcrição sem escrever código, ótimo para validar a ideia antes de implementar via SDK ou API.
- A análise de sentimento retorna um resultado **por documento e por sentença**, o que permite localizar exatamente onde está a crítica ou o elogio.
- Os **scores de confiança** (0 a 1) mostram o quão certo o modelo está; textos mistos tendem a distribuir a pontuação entre as categorias.
- Textos longos e ambíguos, como a avaliação 3, são os melhores para entender os limites do modelo.
- Casos de uso reais: transcrição de reuniões e entrevistas, monitoramento de avaliações de clientes, triagem de atendimento e análise de feedback.
- Nota: a interface do Speech mudou ao longo do tempo (do antigo *Speech Studio* para o portal *Azure AI Foundry*), então conferir a documentação atual evita confusão.

## 🧹 Boas práticas e custos

- Usei o tier gratuito (**F0**) sempre que possível.
- Ao terminar os testes, **excluí o grupo de recursos** no portal Azure para evitar cobranças.

## 📚 Referências

- [Lab: Explore Speech](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/09-speech.html)
- [Lab: Analyze text with Language Studio](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/06-text-analysis.html)
- [Documentação do GitHub Markdown](https://docs.github.com/pt/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
