# Minhas anotações do Git

## Primeiros comandos

### Iniciando um repositório

Vamos criar os diretórios locais e no github e fazer a preparação dos arquivos locais

* Criar uma pasta local com o nome do repositório
* Criar o repositório no Github com o mesmo nome da pasta local (apenas por questão de organização)
* Colocar na pasta os arquivos do repositório
* Iniciar o repositório com o comando `git init`
* Use agora o comando `git add .` para adicionar todos os arquivos
    * Caso queira adicionar apenas um ou outro arquivo indique o caminho do arquivo no lugar do ponto

#### Fazendo o primeiro *commit* e subindo para o servidor

* Digite o comando `git commit -m "comentário"` para inserir o *commit* e uma breve descrição
* Copie da página do repositório no Github o endereço para upload (escolha entre SSH e HTML)
* Use o comando `git remote add origin <endereço>` para se conectar ao servidor do Github e permitir que o repositório local e o remoto sejam sincronizados
* Agora para enviar os arquivos/alterações use `git push -u origin master`
    * A opção `-u` só deve ser utilizada da primeira vez que se faz o *push* dos arquivos neste repositório.

#### Uma breve observação sobre o nome da branch principal

Atualmente o Github esta usando um novo padrão para o nome da branch principal, deixando de lado *master* em prol do nome *main*. Portando é razoável passar a utilizar este nome nos novos repositórios criados.

Para alterar o nome de uma branch no repositório utilizamos o seguinte comando: `git branch -M "novo-nome"` (**M** maiuscúlo)

## *Branchs* e *merging*

Uma *branch* é uma divisão no repositório, onde ele se divide e uma parte segue seu fluxo natural e na outra são trabalhadas outras alterações.
A utilidade do *branch* é manter uma versão estável daquele projeto enquanto se trabalham em atualizações e novas funções sem prejudicar a versão principal.
Quando as novas atualizações e funções forem consideradas prontas suas alterações são inseridas na versão principal, através do *merge*.

### Criando e mudando de ramo: *branch*

* Para criar um novo *branch* do repositório basta utilizar um comando: `git checkout -b "<nome-da-branch>"`. O argumento `-b` só precisa ser utilizado na criação da *branch*. 
* Para mudar de *branch* basta utilizar o comando `git checkout "<nome-da-branch>"`.
    * **ATENÇÃO:** antes de mudar de *branch* é necessário fazer *push* das alterações, ou estas serão perdidas.

### Mesclando ramos diferentes de um projeto: *merge*

* Quando se desejar juntar dois ramos distintos de um projeto utiliza-se o seguinte comando para efetuar o *merge*: `git merge <branch-destino>`.
    * **ATENÇÃO:** o *merge* utiliza a *branch* atual como a fonte das alterações e a *branch* de destino como a base. Então para se alterar arquivos no *master* é preciso estar na *branch* de origem das alterações.

## Trabalhando com um repositório remoto

### Clonando os arquivos localmente

Um repositório remoto pode ser baixado diretamente para o computador local. Caso ele esteja hospedado no Github ele precisa ser do próprio usuário, ou ser um repositório público no caso de pertencer a outro usuário.

* O comando `git clone <endereço HTTP ou SSH>` clona o repositório e faz o download deste na pasta atual do *bash*.
    * **ATENÇÃO:** não faça clones de respositório dentro de pastas que já possuem outros repositórios.

Ao clonar um repositório este é baixado apenas localmente, mas não é copiado no Github, caso queira copiar o repositório para o seu repositório do Github utilize a opção *fork* no próprio Github, onde os arquivos e todo o histórico será copiado para a sua conta.

### Atualizando os arquivos locais

Quando uma equipe trabalha em um projeto, a versão remota pode estar mais atualizada que a versão local, neste caso é necessário atualizar os arquivos locais com a última versão dos arquivos remotos.

* Estando no diretório do repositório e na branch que se quer atualizar basta usar o comando `git pull` que os arquivos locais ficarão pareados com os arquivos remotos.

### Solicitando alterações nos arquivos remotos

Novamente, em um projeto feito em equipe é necessário um controle das versões, por isso não é possível apenas enviar as alterações feitas localmente para o servidor, é necessário enviar uma solicitação ao administrador do projeto, isso chama-se *pull request*.

A forma mais prática de se fazer um *pull request* é utilizando a interface gráfica do Github. Após alterar os arquivos localmente e enviar a versão para o servidor do Github, haverá na sua versão do repositório uma opção de fazer um *pull request*, basta clicar e seguir as instruções.

## Observações finais

* [Vídeo da Rafaella Ballerini explicando sobre Git e Github](https://www.youtube.com/watch?v=UBAX-13g8OM)
* [Repositório do Github com o roteiro do vídeo](https://github.com/rafaballerini/GitTutorial)
* [Dica de como trabalhar com dois repositórios](https://www.codegrepper.com/code-examples/shell/git+how+to+switch+to+another+repository)
* [Como mudar o endereço do repositório remoto](https://xenovation.com/blog/source-control-management/git/how-to-change-remote-git-repository)
* [Como atualizar, fazer um *pull*, de apenas um arquivo local](https://stackoverflow.com/questions/28375418/git-how-to-pull-a-single-file-from-a-server-repository-in-git)