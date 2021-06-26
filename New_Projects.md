# Maneiras de criar ou clonar novos Projetos  
AutoresFábio Itturriet e Patrick Morás  
Data: 26/06/2021  
Versão: STM32Cube 1.6.1   

# Clonando Projetos do GitHUB de dentro do Cube IDE

Com o Cube IDE aberto, clique na aba "Window" 

1. Clique na Opção Show View > Other...
2. Selecionar Git > Git Repositories

Uma janela abrirá na parte inferior à direita com as seguintes opções:

![image](https://user-images.githubusercontent.com/86316296/123525033-7de3e500-d6a4-11eb-8575-15e311d8d85b.png)

Clicar na opção "Clone a git repository"

![image](https://user-images.githubusercontent.com/86316296/123525198-53465c00-d6a5-11eb-9c47-59b6a6c0754d.png)

No campo URL insira o link do repositório que pretende clonar.


# Importando examplos no STM32Cube IDE

Os exemplos estão armazanados no GitHUb da fabricante (ST). 
https://github.com/STMicroelectronics/STM32CubeF7/tree/master/Projects/STM32F769I-Discovery/Examples

Sequencia de Passos:
1. Abra o Cube
2. Selecione o diretório de trabalho na janela "Select a directory as workspace"
3. Na janela "STM32CubeIDE Home" clique na opção "Import STM32Cube example"
4. Clique na aba "Example Selector" na parte superior.
5. No campo Name digite o modelo da placa Ex. "STM32F769I-DISCO"
6. Escolha o projeto.  
7. "Finish"  
  
  
# Ferramentas interessantes

**STMCube32Monitor**

Permite visualizar as variáveis em componentes gráficos como Gauges (medidores) de temperatura e etc;

Link: https://www.st.com/en/development-tools/stm32cubemonitor.html  
Vídeo Introdutório: https://www.youtube.com/watch?v=eIrTYMl7fD0

# Curiosidades sobre o STM32CubeIDE

É o primeiro ambiente de desenvolvimento integrado gratuíto da ST. Antes de seu lançamento, os desenvolvedores usando ambientes de terceiros como o IAR e o Arm Keil. Existia ainda a opção de usar o SW4STM32 como opção gratuíta de desenvolvimento.
