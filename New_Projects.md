# Maneiras de criar ou clonar novos Projetos  
AutoresFábio Itturriet e Patrick Morás  
Data: 26/06/2021  
Versão: STM32Cube 1.6.1   

## Extensões necessárias para integração STM32CubeIDE e o GitHub

No cube IDE é necessário ter duas extensões instaladas para se ter acesso as ferramentas de integração
-Egit
-Gitflow Nightly

Para isso devemos acessar o mercado de soluções do eclipse

1. Vá até a aba Help > Eclipse Marketplace...
2. Na guia Search pesquise por "Egit"
3. Instale o "Egit - Git Integration for Eclipse"

imagem 

4. Concluindo a instalação volte em "Eclipse Marketplace"
5. Na aba "Installed" é possivel ver o Egit já instalado juntamente com o Gitflow Nightly
6. Nesta mesma aba clique em "Update" para atualizar o Gitflow Nightly

imagem

# Clonando Projetos do GitHUB de dentro do Cube IDE

Com o Cube IDE aberto, clique na aba "Window" 

1. Clique na Opção Show View > Other...
2. Selecionar Git > Git Repositories

Uma janela abrirá na parte inferior à direita com as seguintes opções:

![image](https://user-images.githubusercontent.com/86316296/123525033-7de3e500-d6a4-11eb-8575-15e311d8d85b.png)

Clicar na opção "Clone a git repository"

![image](https://user-images.githubusercontent.com/86316296/123525198-53465c00-d6a5-11eb-9c47-59b6a6c0754d.png)

No campo URL insira o link do repositório que pretende clonar. Após os arquivos serem baixados, será possivel visualizar o Repositorio na janela "Git Repositories". Para adicionar algum projeto do repositorio ao explorador de projetos da IDE, basta clicar com o botão direito no arquivo do repositório e pressionar em "Import Projects...", com isso é possivel trabalhar em cima do projeto clonado.

## Commit e Push de dentro do Cube IDE

##### Descrição breve dos comandos Commit e Push
O comando "commit" é utilizado para salvar uma nova versão do projeto dentro do repositório local, lembrando que o repositório local pode ser criado manualmente e também é criado automaticamente ao clonar um projeto do GitHub, a escolha do repositório para o commit é feita pelo usuário.
Feito o commit para o repositório local é possível utilizar o comando "Push" para enviar as atualizações para o repositório online, ou seja, pro GitHub.

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
