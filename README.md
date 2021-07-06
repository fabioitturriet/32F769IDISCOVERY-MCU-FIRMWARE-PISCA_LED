
# Experimento 01 - Pisca-Led
_____________________________________________________________________________________________________________________________________________
**Autores:** Patrick Morás e Fábio Itturriet  
**Data:** 23/06/2021           
**Objetivo:** Esse projeto visa a configuração da plataforma STM32F769NI para piscar um dos leds da plataforma com intervalo de tempo de 1s.  
**IDE=** STM32CUBE IDE v.1.6.1

_____________________________________________________________________________________________________________________________________________

# Esquemático do Experimento

Diagrama resumido das estapas do experimento

<img src="https://user-images.githubusercontent.com/86391684/124515737-8a5bf200-ddb6-11eb-902a-e5e8262e6ec3.jpg" width="900" />

### Começando um novo projeto

Inicialmente reproduzimos o STM32CubeIDE, na área de trabalho do Cube IDE criamos um novo projeto
  
  1. Vá até a guia File > New > STM32 Project

<img src="https://user-images.githubusercontent.com/86391684/124516208-87adcc80-ddb7-11eb-8ec8-adc3c2a376dc.png" width="800" />

  2. Aberta a janela de seleção de plataformas "Target selection"
  3. Escolha a plataforma de desenvolvimento a ser utilizada, nesse caso a STM32F769I-DISCO

<img src="https://user-images.githubusercontent.com/86391684/124516617-7d400280-ddb8-11eb-8277-5a0868bb48db.png" width="800" />

  4. Na janela de configuração, dê um nome ao seu projeto e prossiga com "Finish"

<img src="https://user-images.githubusercontent.com/86391684/124517087-72d23880-ddb9-11eb-8be0-ddbc4605f213.png" width="400" />

### Descrição do experimento

Antes da configuração da plataforma de fato, precisamos entender o que queremos que ela reproduza, nesse caso queremos piscar um LED!!!

Como é visto no manual [Discovery kit with STM32F769NI MCU 3.0](https://www.st.com/en/evaluation-tools/32f769idiscovery.html#documentation) a plataforma conta com três leds destinado ao usuário 

<img src="https://user-images.githubusercontent.com/86391684/124517747-24be3480-ddbb-11eb-9375-9ba392bfef0f.png" width="600" />

Dentre os Leds, foi escolhido o LD1 para o experimento, no manual encontramos uma descrição mais detalhada dele

<img src="https://user-images.githubusercontent.com/86391684/124518066-e7a67200-ddbb-11eb-923a-d6cc93c4fa17.png" width="500" />

Como é visto o LD1 tem a cor vermelha, outra informação importante exposta é o pino relacionado a esse Led, nesse caso o "PJ13". Outra forma de ver isso é no esquematico da plataforma. 

<img src="https://user-images.githubusercontent.com/86391684/124518296-70251280-ddbc-11eb-836b-d2557bf91c39.png" width="500" />
<img src="https://user-images.githubusercontent.com/86391684/124518305-73b89980-ddbc-11eb-90ce-d2c81ab013ef.png" width="500" />

Analizando o esquemático, observa-se a relação do LD1 com a conexão LD_USER1 que seguinte se relaciona com o PJ13.
_____________________________________________________________________________________________________________________________________________

# Configuração da Plataforma

Descrição da configuração da plataforma atravéz do CubeMX integrado na IDE STM32Cube, configurações não especificadas estão definidas como padrão 
para geração do código.

A partir de agora já temos a idéia do que será feito, e podemos prosseguir para a configuração do microcontrolador. na área de trabalho inicial de configuração, precisamos adicionar como será feito a comunicação da plataforma e o computador, nesse caso pela linha serial USB 

  1. Na guia "System Core" clique em SYS > Debug > Serial Wire

<img src="https://user-images.githubusercontent.com/86391684/124537839-070bc200-ddf1-11eb-8ccb-d9601a419d6e.png" width="800" />

É preciso definir também uma fonte de *clock* para o *hardware*, foi utilizado o circuito oscilador externo HSE 

  2. Ainda em "System Core" vá em RCC
  3. Habilite o "High Speed Clock (HSE)" Como "Crystal/Ceramic Resonator"

<img src="https://user-images.githubusercontent.com/86391684/124539281-869a9080-ddf3-11eb-9816-2cb537f7c4df.png" width="800" />

Subsequente temos que configurar o pino conectado ao LD1, é possivel pesquisar por ele para ajudar a achar na vizualização dos pinos

<img src="https://user-images.githubusercontent.com/86391684/124540467-d5e1c080-ddf5-11eb-84f7-64a5fbb77516.png" width="800" />

O pino então será definido como um pino de saída, pois queremos mandar um sinal por ele

  4. clique sobre o pino, selecione "GPIO_Output"

<img src="https://user-images.githubusercontent.com/86391684/124540816-9071c300-ddf6-11eb-8880-e5a47fda63d1.png" width="800" />

Assim finalizamos a configuração da plataforma. Podemos então salvar o projeto e gerar o código inicial, é possivel salvar o projeto atravéz do ícone de disquete :floppy_disk: ou pelo atalho "Ctrl+S" ou pela guia File > Save.

### Programação 

Para esse projeto o código se resume a dois comando "HAL" adicionado dentro do laço de repetição

'HAL_GPIO_TogglePin(GPIOx, GPIO_PIN_x);'

Essa função muda o nível lógico de um pino específico. o nível lógico vai para baixo caso esteja alto ou vice-versa, por isso a necessidade da função estar no laço de repetição. em GPIOx é colocado a família de pinos utilizada, nesse caso a família "J" é a utilizada, em GPIO_PIN_x é adicionado o número do pino, pino 13 como descrito anteriormente. Portanto cada execução dessa função faz com que o led apague ou ligue, em razão disso temos o LED piscando. Porém somente essa função acaba não realizando o que queremos (que o led pisque em intervalos de 1 segundo), pela velocidade do *clock* o led pisca tão rápido que é imperceptível, então devemos adicionar um atraso de tempo adequado no código

'HAL_Delay(tempo)'

Responsável por realizar o atraso essa função recebe como argumento o tempo em milissegundos. Dessa maneira tempo o código pronto

<img src="https://user-images.githubusercontent.com/86391684/124545125-d468c600-ddfe-11eb-8934-c9c0d20233f8.png" width="800" />

_____________________________________________________________________________________________________________________________________________

# Conclusões e observações

Rodando o Firmware notamos o piscar do LD1 vermelho em intervalos regulares de 1 segundo

<img src="https://user-images.githubusercontent.com/86391684/124545958-4c83bb80-de00-11eb-8b20-4b40e88a7a4d.jpg" width="600" />

Este projeto foi um teste inicial da comunicação geral que integra o STM32CubeIDE, o programador e o microcontrolador, além de marcar o início de uma gama de experimentos que será feito em conjuto pelo Github. 
