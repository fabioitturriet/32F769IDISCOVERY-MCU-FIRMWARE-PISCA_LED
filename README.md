
# Experimento 01 - Pisca-Led
_____________________________________________________________________________________________________________________________________________
**Autores:** Patrick Morás e Fábio Itturriet  
**Data:** 23/06/2021           
**Objetivo:** Esse projeto visa a configuração da plataforma STM32F769NI para piscar um dos leds da plataforma com intervalo de tempo de 1s.  
**IDE=** STM32CUBE IDE v.1.6.1

_____________________________________________________________________________________________________________________________________________

# Esquemático do Experimento

Diagrama resumido das estapas do experimento

![Esquemático do experimento](https://user-images.githubusercontent.com/86391684/124515737-8a5bf200-ddb6-11eb-902a-e5e8262e6ec3.jpg)

_____________________________________________________________________________________________________________________________________________

# Configuração da Plataforma

Descrição da configuração da plataforma atravéz do CubeMX integrado na IDE STM32Cube, configurações não especificadas estão definidas como padrão 
para geração do código.

### Começando um novo projeto

Inicialmente reproduzimos o STM32CubeIDE, na área de trabalho do Cube IDE criamos um novo projeto
  
  1. Vá até a guia File > New > STM32 Project

![Captura de Tela (1)](https://user-images.githubusercontent.com/86391684/124516208-87adcc80-ddb7-11eb-8ec8-adc3c2a376dc.png)

  2. Aberta a janela de seleção de plataformas "Target selection"
  3. Escolha a plataforma de desenvolvimento a ser utilizada, nesse caso a STM32F769I-DISCO

![Captura de Tela (3)](https://user-images.githubusercontent.com/86391684/124516617-7d400280-ddb8-11eb-8277-5a0868bb48db.png)

  4. Na janela de configuração, dê um nome ao seu projeto e prossiga com "Finish"

![Captura de Tela (4)](https://user-images.githubusercontent.com/86391684/124517087-72d23880-ddb9-11eb-8be0-ddbc4605f213.png)

### Configuração 

Antes da configuração da plataforma de fato, precisamos entender o que queremos que ela reproduza, nesse caso queremos piscar um LED!

Como é visto no manual [Discovery kit with STM32F769NI MCU 3.0](https://www.st.com/en/evaluation-tools/32f769idiscovery.html#documentation) a plataforma conta com três leds destinado ao usuário 

![Captura de Tela (14)](https://user-images.githubusercontent.com/86391684/124517747-24be3480-ddbb-11eb-9375-9ba392bfef0f.png)

Dentre os Leds, foi escolhido o LD1 para o experimento, no manual encontramos uma descrição mais detalhada dele

![Captura de Tela (5)](https://user-images.githubusercontent.com/86391684/124518066-e7a67200-ddbb-11eb-923a-d6cc93c4fa17.png)

Como é visto o LD1 tem a cor vermelha, outra informação importante exposta é o pino relacionado a esse Led, nesse caso o "PJ13". Outra forma de ver isso é no esquematico da plataforma. 

![Captura de Tela (6)](https://user-images.githubusercontent.com/86391684/124518296-70251280-ddbc-11eb-836b-d2557bf91c39.png)
![Captura de Tela (7)](https://user-images.githubusercontent.com/86391684/124518305-73b89980-ddbc-11eb-90ce-d2c81ab013ef.png)

Analizando o esquemático, observa-se a relação do LD1 com a conexão LD_USER1 que seguinte se relaciona com o PJ13.

_____________________________________________________________________________________________________________________________________________

# Conclusões e observações
