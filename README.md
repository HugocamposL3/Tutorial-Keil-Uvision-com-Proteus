## Objetivo 

Como fazer um projeto utilizando o compilador Keil Uvision e simular ele no VSM do Proteus Labcenter.

## Softwares Necessários

* Keil Uvision (MDK-ARM) [link](https://www.keil.com/download/product/)
* Proteus (Labcenter)    [link](https://www.labcenter.com/downloads/)

## Introdução

Nesse projeto será feito o famoso "hello world" ou o famoso "blink", que consiste em acender e apagar um led em uma faixa de tempo estipulada pelo o programador.

# Inicilizando o Keil

- **1º Passo:** Após baixar o Keil Uvision eu seu computador, será necessário que faça um novo projeto (New Project) localizado na parte superior do seu compilador, clique em **Project -> New Uvison Project** e crie um novo projeto e salve onde preferir no computador, indico que faça uma "nova pasta" com o nome do projeto e assim salve o projeto nela.

<a href="https://imgur.com/lhk6OW6"><img src="https://imgur.com/lhk6OW6.jpg" title="source: imgur.com" /></a>

- **2º Passo:** Feito isso vai abrir uma janela para que você qual chip você vai utilizar no seu projeto, nesse caro iremos escolher o  STM32 F103R6, na caixa de pesquisa (Search) você pode escrever ese código (F103R6) que o sotware já vai localizar automaticamente, ou se preferir pode seguir o seguinte caminho **STMicroeletronics -> STM32F1 Series -> STM32F103 -> STM32F103R6** selecione o chip e clique "Ok"

<a href="https://imgur.com/AMruIOs"><img src="https://imgur.com/AMruIOs.jpg" title="source: imgur.com" /></a>

- **Observação:** Caso não aparece nenhum chip para escolha logo após a criação do projeto, será necessário instalar o seu pacote no "Pack Instaler" no Keil Uvision, o que é extremamente facil. 
Feche a janela que abriu para escolha de chip e clique no icone onde a seta está apontando na imagem abaixo:

<a href="https://imgur.com/kcs5Z91"><img src="https://imgur.com/kcs5Z91.jpg" title="source: imgur.com" /></a>

Logo após vai abrir uma outra janela, que possivelmente demore alguns segundo para que carregue todos os seus arquivos, será necessário aguardar um pouco. Carregando vai aparecer algo parecido com a imagem abaixo:

<a href="https://imgur.com/myP7YUe"><img src="https://imgur.com/myP7YUe.jpg" title="source: imgur.com" /></a>

Na aba **Device** siga o caminho **STMicroeletronics -> STM32F1 Series -> STM32F103 -> STM32F103R6** após seguir esse caminho, na parte de **pack** vai aparecer (Device Specific) e logo de frente na aba **Action** vai está escrito **Install** clique em install, o que vai demorar alguns segundos ou minutos para que ele instale os pacotes necessários desse chip.

<a href="https://imgur.com/esAnGLU"><img src="https://imgur.com/esAnGLU.jpg" title="source: imgur.com" /></a>

Após a instalação, a janela vai ficar dessa forma:

<a href="https://imgur.com/fYy9n1g"><img src="https://imgur.com/fYy9n1g.jpg" title="source: imgur.com" /></a>

Feita a instalação do pacote do chip, volte ao **1º Passo** e reinicie o projeto, agora já com o chip instalado. 

- **3º Passo:** Após fazer o 2º passo e escolher o chip, o software vai abrir outra janela chamada **Manage Run-Time Environment** onde escolherá os seus Componentes de Softwares (Softwares Components) nesse projeto será necessário de 5 componentes, siga e selecione os componetes de acordo as imagens abaixo:

- Primeira Janela: 

<a href="https://imgur.com/a48E6vg"><img src="https://imgur.com/a48E6vg.jpg" title="source: imgur.com" /></a>

- Segunda Janela: Selecione **CMSIS -> CORE**

<a href="https://imgur.com/pWpFviR"><img src="https://imgur.com/pWpFviR.jpg" title="source: imgur.com" /></a>

















