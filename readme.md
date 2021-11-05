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

Para alterar o nome de uma branch no repositório utilizamos o seguinte comando: `git branch -M "*novo-nome*"` (**M** maiuscúlo)

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
