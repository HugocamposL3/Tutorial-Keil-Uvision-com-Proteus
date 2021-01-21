# Objetivo 

Como fazer um projeto utilizando o compilador Keil Uvision e simular ele no VSM do Proteus Labcenter.

## Softwares Necessários

* Keil Uvision (MDK-ARM) [link](https://www.keil.com/download/product/)
* Proteus (Labcenter)    [link](https://www.labcenter.com/downloads/)

## Introdução

Nesse projeto será feito o famoso "hello world" ou o famoso "blink", que consiste em acender e apagar um led em uma faixa de tempo estipulada pelo o programador.

# Inicilizando o Keil

- **1º Passo:** Após baixar o Keil Uvision eu seu computador, será necessário que faça um novo projeto (New Project) localizado na parte superior do seu compilador, clique em **Project -> New Uvison Project** e crie um novo projeto e salve onde preferir no computador, indico que faça uma "nova pasta" com o nome do projeto e assim salve nela.

<a href="https://imgur.com/lhk6OW6"><img src="https://imgur.com/lhk6OW6.jpg" title="source: imgur.com" /></a>

- **2º Passo:** Feito isso vai abrir uma janela para que você escolha qual chip você vai utilizar no seu projeto, nesse caso iremos escolher o  STM32 F103R6, na caixa de pesquisa (Search) você pode escrever esse código (F103R6) que o software já vai localizar automaticamente, ou se preferir pode seguir o seguinte caminho **STMicroeletronics -> STM32F1 Series -> STM32F103 -> STM32F103R6** selecione o chip e clique "Ok"

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

- Terceira Janela: Selecione **Device -> Startup**

<a href="https://imgur.com/TbFLGQX"><img src="https://imgur.com/TbFLGQX.jpg" title="source: imgur.com" /></a>

- Quarta Janela: Ainda com **Device** selecionado clique em **StdPeriph Drivers** e depois escolha **Framework, GPIO & RCC**:

<a href="https://imgur.com/ZFAdTQI"><img src="https://imgur.com/ZFAdTQI.jpg" title="source: imgur.com" /></a>

Logo Após de escolher os componetes de softwares, clique em Ok.

**4º Passo:** Após o clicar Ok em componetes de softwares, a janela vai fechar e o software voltar para a tela principal do Keil Uvision, algo parecido com a imagem abaixo:

<a href="https://imgur.com/ra1EGpw"><img src="https://imgur.com/ra1EGpw.jpg" title="source: imgur.com" /></a>

Na janela **Projetc** clique no (+) ao lado do icone **Target 1** vai abrir outras ramificações iguais a imagem a abaixo:

<a href="https://imgur.com/PKhx7lu"><img src="https://imgur.com/PKhx7lu.jpg" title="source: imgur.com" /></a>

Clique com o botão direito do mouse em cima do icone **Source Group** e selecione **"" Add New Item to Group 'Souce Group 1'...""** de acordo com a imagem abaixo:

<a href="https://imgur.com/VM4R9OR"><img src="https://imgur.com/VM4R9OR.jpg" title="source: imgur.com" /></a>

Clicando em **"" Add New Item to Group 'Souce Group 1'...""** vai abrir uma outra janela onde você vai selecionar **C File (.c)** e na barra nomeada por **Name:** escreva **main** e clique em **Add**:

<a href="https://imgur.com/90ZpJG4"><img src="https://imgur.com/90ZpJG4.jpg" title="source: imgur.com" /></a>

A janela irá fechar e a parte principal do Keil Uvision onde era cinza vai ficar branca e esperando que incie o código:

<a href="https://imgur.com/RgTVDvG"><img src="https://imgur.com/RgTVDvG.jpg" title="source: imgur.com" /></a>

## Iniciando o Código:

- Para começar o código, inclua 3 blibliotecas:

```javascript
#include "stm32f10x_rcc.h"
#include "stm32f10x_gpio.h"
#include "stm32f10x.h"
```
- Uma embaixo da outra conforme a imagem abaixo:

<a href="https://imgur.com/B5oQr0h"><img src="https://imgur.com/B5oQr0h.jpg" title="source: imgur.com" /></a>

- Feito isso, é hora de colocar as prototipações das funções que vão ser usadas no decorrer do código, são elas:

```javascript
void PORTB_GPIO_Configuration(void);  
void Delay(__IO uint32_t nCount);			
void NMI_Handler(void);
void SetClk(uint32_t PLLMul);
```
- Conforme a imagem abaixo:

<a href="https://imgur.com/AD7yJg3"><img src="https://imgur.com/AD7yJg3.jpg" title="source: imgur.com" /></a>

- Escreva a variavel do tipo Clock para o cristal interno e também uma variavel tipo **int** para a função de **delay** inciando ela a 500ms:

```javascript
RCC_ClocksTypeDef ClksFreq;
int delay_time = 500;
```
- Conforme a imagem abaixo:

<a href="https://imgur.com/lTHFDup"><img src="https://imgur.com/lTHFDup.jpg" title="source: imgur.com" /></a>

- Escreva o programa principal **(int main)** e logo após inicie o **clock** e também o PORT do chip em que utilizará o pino de saida dele, nesse código foi configurado o PORT B, seguindo as instruções abaixo:

```javascript
int main()
{
	//==================System Clock Init==================
	//Inicia o clock
	SetClk(2);
  //======================GPIO Init======================
	PORTB_GPIO_Configuration();
```

- Agora será feita a lógica para que o led pisque de acordo com o delay que foi estipulado, nesse código está 500ms e com isso ele vai fechar o programa principal com a cheva final:

```javascript
while(1)
	{
		GPIO_WriteBit(GPIOB, GPIO_Pin_8,  Bit_SET);
		Delay(delay_time);
		GPIO_WriteBit(GPIOB, GPIO_Pin_8,  Bit_RESET);
		Delay(delay_time);
	}
}
```

- Habilite o PORTB para que o pino 8 seja utilizado como OUTPUT (sáida), seguindo as instruções abaixo:

```javascript
void PORTB_GPIO_Configuration(void)
{
	GPIO_InitTypeDef GPIO_InitStructure;
	//Allow clock to GPIOB
	RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOB, ENABLE);
	
	//Configure output pins
	GPIO_InitStructure.GPIO_Pin = GPIO_Pin_8;
	GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
	GPIO_InitStructure.GPIO_Speed = GPIO_Speed_2MHz;
	GPIO_Init(GPIOB, &GPIO_InitStructure);
}
```

Até esse momento o código está do jeito que a imagem abaixo mostra:

<a href="https://imgur.com/1KXost8"><img src="https://imgur.com/1KXost8.jpg" title="source: imgur.com" /></a>

- Agora o que vai ser escrito abaixo dessa parte do código é uma configuração de Clock e também a configuração entre cristal interno (o qual está configurado nesse código) com o cristal externo, esse tipo de configuração vai ser um padrão para os outros códigos que serão mostrados em outras publicações desse GitHub.

- Prossiga o seu código escrevendo os seguintes comandos:

```javascript
void NMI_Handler()
{
	//Clear CSS interrupt flag - RCC (REGISTER CLOCK CONTROL) 
	RCC->CIR |= RCC_CIR_CSSC; // |= INVERSÃO 
	//Wait couple of time, if it recovers
	//feasible to restart again
	Delay(100);
	//Try to start HSE (HIGH SPEED EXTERNAL)- TENTA LIGAR DE NOVO O CLOCK EXTERNO 
	RCC_HSEConfig(RCC_HSE_ON);
	//Delay to start crystal
	Delay(1);
	if (RCC_WaitForHSEStartUp() == SUCCESS)
	{
		//If starts - set HSE as system clock source
		RCC_SYSCLKConfig(RCC_SYSCLKSource_HSE);
		//Stop HSI
    //DESLIGA O HIGH SPEED INTERNAL - CLOCK INTERNO
		RCC_HSICmd(DISABLE);
	}
}
```

- E após isso é hora de configurar o Clock:

```javascript
//CONFIGURAÇÃO DO CLOCK 

void SetClk(uint32_t PLLMul) {
      RCC_DeInit();
	  //Run HSE
	  RCC_HSEConfig(RCC_HSE_ON);
	  //Wait until HSE starts up
	  while(RCC_WaitForHSEStartUp() != SUCCESS);
	  //Turn on Clock Security System
	  RCC->CR |= RCC_CR_CSSON;
	  //Make HSE as system main clock source
	  //RCC_SYSCLKConfig(RCC_SYSCLKSource_HSE);
	  //Power off HSI to reduce energy
	  RCC_HSICmd(DISABLE);

      // PLL provides frequency multiplier of (HSI/2) i.e. 4MHz x ...
      RCC_PLLConfig(RCC_PLLSource_HSE_Div2, PLLMul);
      // Enable PLL
      RCC_PLLCmd(ENABLE);
      // Wait till PLL is ready
      while (RCC_GetFlagStatus(RCC_FLAG_PLLRDY) == RESET);
      // Select PLL as system clock source
      RCC_SYSCLKConfig(RCC_SYSCLKSource_PLLCLK);
      // Wait till PLL is used as system clock source
      while (RCC_GetSYSCLKSource() != 0x08);
      // AHB, AP2 and AP1 clock are necessary for the peripherals to function
      // HCLK for AHB = SYSCLK (max is SYSCLK, up to 72MHz)
      RCC_HCLKConfig(RCC_SYSCLK_Div1);
      // PCLK2 for APB2 = HCLK (max is SYSCLK, up to 72MHz)
      RCC_PCLK2Config(RCC_HCLK_Div1);
      // PCLK1 for APB1 = HCLK (HCLK <= 36MHz)
      RCC_PCLK1Config(RCC_HCLK_Div1);

      RCC_GetClocksFreq(&ClksFreq); // update SYSCLK, HCLK, PCLK1 and PCLK2 in ClksFreq
}
```

- O código estará mais ou menos de acordo com a imagem abaixo:

<a href="https://imgur.com/hVttCkK"><img src="https://imgur.com/hVttCkK.jpg" title="source: imgur.com" /></a>

- E por fim configure a função **delay** escrevendo as instruções a seguir:

```javascript
void Delay(__IO uint32_t nCount)
{
	uint32_t i = 0;
	for (; nCount != 0; i++)
	{
		if (i == 1000)
		{
			i = 0;
			nCount--;
		}
	}
}
```
- E com isso o código foi finalizado.

## Gerando o Arquivo .HEX 

Para que esse cógido seja simulado no Software Proteus, é necessário gerar o arquivo **.hex** dele, para fazer isso é seguir as seguintes instruções:

- Clique no icone em qual tem uma varinha de condão que é nomeado de **Options for Target**:

<a href="https://imgur.com/WCAMeV4"><img src="https://imgur.com/WCAMeV4.jpg" title="source: imgur.com" /></a>

- Na janela que irá abrir selecione **Output -> "Create HEX file"** e aperte Ok:

<a href="https://imgur.com/WvRdCEm"><img src="https://imgur.com/WvRdCEm.jpg" title="source: imgur.com" /></a>

- Pronto, agora o Keil irá criar um arquivo .hex na hora de compilar o seu código.

## Compilando o Código:

- No campo superior do Keil tem um icone com duas setinhas para baixo nomeado por **Rebuild** clique nele e aguarde para que o seu código seja compilado:

<a href="https://imgur.com/LJmNiKw"><img src="https://imgur.com/LJmNiKw.jpg" title="source: imgur.com" /></a>

- Após ele compilar na parte inferior do software (Build Outputs) deverá aparecer sem erros e sem warnings:

<a href="https://imgur.com/npveZOV"><img src="https://imgur.com/npveZOV.jpg" title="source: imgur.com" /></a>

- Pronto, a parte que era para ser feito no Keil Uvision está pronta, provavelmente o software já criou um arquvio .hex para que ele possa ser simulado no proteus.

# Inicializando o Proteus:

- Após baixar o Proteus no computador e abrí-lo vai aparecer uma tela com três icones **"Open Project, New Project & Open Sample"** escolha **New Project**:

<a href="https://imgur.com/qzlWRKT"><img src="https://imgur.com/qzlWRKT.jpg" title="source: imgur.com" /></a>

- Vai abrir uma outra janela para que escolha o nome do projeto e também onde quer salvá-lo, indico que salve na mesma pasta onde está os arquivos salvos do Keil Uvison e clique em Next:

<a href="https://imgur.com/qJQrTng"><img src="https://imgur.com/qJQrTng.jpg" title="source: imgur.com" /></a>

- A próxima janela é para escolher o tamanho da zona de esquemático, indico escolher "Landscape A3" e aperte Next:

<a href="https://imgur.com/vAusinB"><img src="https://imgur.com/vAusinB.jpg" title="source: imgur.com" /></a>

- As próximas janelas que o proteus abrir não é de importância para esse projeto então, pode dá **Next** em todas as janelas e no final clique em **Finish**:

<a href="https://imgur.com/oezLHtj"><img src="https://imgur.com/oezLHtj.jpg" title="source: imgur.com" /></a>

## Fazendo o Esquemático:

- Feita todaa configuração inicial do proteus, é hora de selecionar o chip (STM32 F103R6), colocar o led e o resistor, para que o proteus possa simular o software feito no Keil Uvision. Siga as instruções abaixo:

**1º Passo:** Na janela que abrir após ter clicado **Finish** na última janela. Selecione icone de **Component Mode** parece com uma porta lógica NOT:

<a href="https://imgur.com/3qTjYy6"><img src="https://imgur.com/3qTjYy6.jpg" title="source: imgur.com" /></a>

- Após isso, clique na letra **P** que está do lado da letra L na janela **DEVICES** para que consiga colocar todos os componentes que serão utilizados nese projeto:

<a href="https://imgur.com/nYQov1R"><img src="https://imgur.com/nYQov1R.jpg" title="source: imgur.com" /></a>

- Irá abrir uma janela chamada **Pick Devices**. Em **Keywords** pesquise **F103R6** selecione ele e depois clique em Ok:

<a href="https://imgur.com/TXdMcAj"><img src="https://imgur.com/TXdMcAj.jpg" title="source: imgur.com" /></a>

- A janela irá fechar pois o Chip já foi selecionado e já está aba **Devices**:

<a href="https://imgur.com/kLLJ20n"><img src="https://imgur.com/kLLJ20n.jpg" title="source: imgur.com" /></a>

- Faça os mesmo procedimento para escolher o **Led** e também o **Resistor**:

Para selecionar o resistor, na aba keywords escreva **MINRES120R**:

<a href="https://imgur.com/umj0uQu"><img src="https://imgur.com/umj0uQu.jpg" title="source: imgur.com" /></a>

Para selecionar o led, coloque a palavra **LED-RED**:

<a href="https://imgur.com/4DSRLsb"><img src="https://imgur.com/4DSRLsb.jpg" title="source: imgur.com" /></a>

-Pronto os componentes já estão na sua aba **DEVICES**:

<a href="https://imgur.com/SIs2RNi"><img src="https://imgur.com/SIs2RNi.jpg" title="source: imgur.com" /></a>

# Montando o Circuito:

- Com todos os componentes na aba Devices, você vai selecionar um componete por vez e vai colocar ele dentro da area de esquemático proteus (Não prcisa manter o o mouse pressionado) só siga conforme o GIF abaixo:

<a href="https://imgur.com/n3RTluA"><img src="https://imgur.com/n3RTluA.jpg" title="source: imgur.com" /></a>

- Faça o mesmo procedimento para outros componetes, o circuito deverá ficar parecido com a imagem abaixo:

<a href="https://imgur.com/uRZ6tY2"><img src="https://imgur.com/uRZ6tY2.jpg" title="source: imgur.com" /></a>

- Para conectar os componentes um com o outro, é preciso clicar na ponta do terminal de um e ligar até a ponta do terminal do outro na qual queira interligar:

**LEMBRE-SE NO CÓDIGO FEITO NO KEIL Uvision FOI ESCOLHIDO O PINO PB8 (PINO 8 DO PORT B) POR ISSO NO GIF ABAIXO ELE JÁ ESTÁ SENDO LIGADO NESE PINO.**

<a href="https://imgur.com/c7zZTsz"><img src="https://imgur.com/c7zZTsz.jpg" title="source: imgur.com" /></a>

- Feito isso é hora de colocar o terra (Ground) no circuito, no canto esquerdo do proteus vai ter um icone chamado **Terminals Mode** clique nele e depois selecione o **GROUND** e adcione ele no circuito em que está sendo feito:

<a href="https://imgur.com/TixZo1z"><img src="https://imgur.com/TixZo1z.jpg" title="source: imgur.com" /></a>

- Uma outra configuração necssária, é da alimentação do chip em que está sedo utilizado, para fazer essa configuração vá até **Design** na parte superior do proteus e depois clique em **Configura Power Rails...**

<a href="https://imgur.com/HkvJorl"><img src="https://imgur.com/HkvJorl.jpg" title="source: imgur.com" /></a>

- Na janela que abrir na parte de **Unconnected power nets:** vão ter duas alimentações **VDDA & VSSA** selecione os dois e depois clique em **Add** ec lique Ok:

<a href="https://imgur.com/CieCiFH"><img src="https://imgur.com/CieCiFH.jpg" title="source: imgur.com" /></a>

- Agora é hora de configurar a frequência do cristal interno do chip:

Clique com o botão direito em cima do chip e depois escolha **Edit Properties**

<a href="https://imgur.com/Iy63ZHs"><img src="https://imgur.com/Iy63ZHs.jpg" title="source: imgur.com" /></a>

Vai abrir uma janela chamada **Edit Component** na parte nomeada como **Crystal Frequency:** escreva **16MHz**:

<a href="https://imgur.com/uEPyrQU"><img src="https://imgur.com/uEPyrQU.jpg" title="source: imgur.com" /></a>

- Sem fechar essa janela essa janela, já coloque o arquivo .Hex do código feito no Keil Uvision na parte de **Program File** clique na pastinha do lado dessa barra e depois selecione a pasta onde está salva os arquivos do Keil Uvisi, feito isso vá em **Objects** e selecione o seu arquivo .hex e depois pode clicar em ok, pois todas as configurações já foram feitas:

<a href="https://imgur.com/ldOI4OO"><img src="https://imgur.com/ldOI4OO.jpg" title="source: imgur.com" /></a>

# Simulando e Finalizando:

## Simulando:

- Colocando o arquivo .hex e apertando Ok, é hora de verificar o código simulando ele no proteus:

Na parte inferios do proteus vai ter um icone de play e quando é passado o mouse em cima dele aparece **Run the Simulation** clique nele e o proteus vai demorar alguns segundo para carregar:

<a href="https://imgur.com/p711f3M"><img src="https://imgur.com/p711f3M.jpg" title="source: imgur.com" /></a>

- Carregado o código o proteus deverá piscar o led, de acordo que foi configurado no Keil Uvision:

<a href="https://imgur.com/ZDxjQQn"><img src="https://imgur.com/ZDxjQQn.jpg" title="source: imgur.com" /></a>

## Finalizando:

Pronto a simulação foi feita, qualquer duvida que tenha tido no meio desse tutorial entre em contato com o autor por via desse e-mail: camposhugo029@gmail.com e bons projetos para você.

# Créditos: 

- Arnaldo Junior  [link](https://github.com/arnaldojr) - Auxilio na Formatação no GitHub.
- Hugo Lara Campos - Código Keil Uvision, Simualação no Proteus e Formatação no GitHub.
- Marcelo Costanzo Miranda [link](https://github.com/Marcelocm1995)  - Código no Keil Uvision.


















































































































