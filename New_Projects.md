# Maneiras de criar ou clonar novos Projetos  
AutoresFábio Itturriet e Patrick Morás  
Data: 26/06/2021  
Versão: STM32Cube 1.6.1   


## Extensões necessárias para integração STM32CubeIDE e o GitHub

No cube IDE é necessário ter duas extensões instaladas para se ter acesso as ferramentas de integração
*Egit
*Gitflow Nightly

Para isso devemos acessar o mercado de soluções do eclipse

1. Vá até a aba Help > Eclipse Marketplace...
2. Na guia Search pesquise por "Egit"
3. Instale o "Egit - Git Integration for Eclipse"

<img src="https://user-images.githubusercontent.com/86391684/123888352-afb9ad80-d929-11eb-82f4-50ef6a981958.png" width="650" />

4. Concluindo a instalação volte em "Eclipse Marketplace"
5. Na aba "Installed" é possivel ver o Egit já instalado juntamente com o Gitflow Nightly
6. Nesta mesma aba, caso surja a opção, clique em "Update" para atualizar o Gitflow Nightly 

<img src="https://user-images.githubusercontent.com/86391684/123888719-7c2b5300-d92a-11eb-90a8-edfd57c3f5cf.png" width="650" />


## Clonando Projetos do GitHUB de dentro do Cube IDE

Com o Cube IDE aberto, clique na aba "Window" 

1. Clique na Opção Show View > Other...
2. Selecionar Git > Git Repositories

Uma janela abrirá na parte inferior à direita com as seguintes opções

![image](https://user-images.githubusercontent.com/86316296/123525033-7de3e500-d6a4-11eb-8575-15e311d8d85b.png)

Clicar na opção "Clone a git repository"

![image](https://user-images.githubusercontent.com/86316296/123525198-53465c00-d6a5-11eb-9c47-59b6a6c0754d.png)

No campo URL insira o link do repositório que pretende clonar. Após os arquivos serem baixados, será possivel visualizar o Repositorio na janela "Git Repositories". Para adicionar algum projeto do repositorio ao explorador de projetos da IDE, basta clicar com o botão direito no arquivo do repositório e pressionar em "Import Projects...", com isso é possivel trabalhar em cima do projeto clonado.


## Commit e Push de dentro do Cube IDE

##### Descrição breve dos comandos Commit e Push
O comando "commit" é utilizado para salvar uma nova versão do projeto dentro do repositório local, lembrando que o repositório local pode ser criado manualmente e também é criado automaticamente ao clonar um projeto do GitHub, a escolha do repositório para o commit é feita pelo usuário.
Feito o commit para o repositório local é possível utilizar o comando "Push" para enviar as atualizações para o repositório online, ou seja, pro GitHub.

obs.: Essa descrição parte da premissa que se tenha a última versão de um projeto em seu repositório local, projeto este de sua autoria no GitHub, ou a sua conta tenha acesso para edita-lo. No exemplo foi criado um projeto no GitHub apenas com o arquivo README.md:

<img src="https://user-images.githubusercontent.com/86391684/123891353-2c9b5600-d92f-11eb-8443-c86b26193cfb.png" width="900" />

Desta vez, ao clonar o repositório, insira seus dados de login ao GitHub nas opção de "Authentication"

<img src="https://user-images.githubusercontent.com/86391684/123891989-235eb900-d930-11eb-88df-ef1717aafda0.png" width="650" />

Feito as etapas anteriores, já temos o repositorio clonado que se deseja trabalhar, lembrando que podemos visualiza-lo na aba "Git Repositories". Seguinte crie um projeto no Cube IDE, ou caso queira enviar um projeto existente visualize-o na guia "Project Explorer", podemos então dar commit pro repositório local e um push para o GitHub

Na guia "Porject Explorer" clique com o botão direito em cima do projeto de sua escolha

1. Vá até Team > Share Project...
2. Na aba de seleção "Repository", escolha o repositório que se dará o Push > Finish

Surgirá um ponto de interrogação no ícone de seu projeto indicando que ele está no modo "untracked", isso significa que ele não foi adicionado a "Staging" (processo de revisão obrigatório antes do commit, uma analogia que refere-se a esse processo é a do contêiner que tem a sua carga depositada, o contêiner é então lacrado e é adicionado um número de identificação). Com o botão direito novamente no projeto

3. Siga em Team > Commit...

Abrirá a aba "Git Staging". Nesta aba, seguindo a analogia do contêiner, adicionaremos o conteúdo nele para então lacra-lo, para isto basta selecionar os arquivos de "Unstaged Changes" e move-los para "staged Changes". Em "Commit Message" escreva uma pequena descrição do que tem no "container", essa mensagem auxiará no controle de versão do GitHub, por exemplo dizendo, num todo, o que foi adicionado a um código de programação. clique em "Commit and Push" para prosseguir

<img src="https://user-images.githubusercontent.com/86391684/123897843-85bcb700-d93a-11eb-8162-ef5bb2df766c.jpg" width="900" />

Se tudo ocorrer bem o projeto surgira no GitHub 

<img src="https://user-images.githubusercontent.com/86391684/123898205-4d69a880-d93b-11eb-981e-ff87044259a6.png" width="900" />


## Importando examplos no STM32Cube IDE

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
  
  
## Ferramentas interessantes

**STMCube32Monitor**

Permite visualizar as variáveis em componentes gráficos como Gauges (medidores) de temperatura e etc;

Link: https://www.st.com/en/development-tools/stm32cubemonitor.html  
Vídeo Introdutório: https://www.youtube.com/watch?v=eIrTYMl7fD0

## Curiosidades sobre o STM32CubeIDE

É o primeiro ambiente de desenvolvimento integrado gratuíto da ST. Antes de seu lançamento, os desenvolvedores usando ambientes de terceiros como o IAR e o Arm Keil. Existia ainda a opção de usar o SW4STM32 como opção gratuíta de desenvolvimento.
