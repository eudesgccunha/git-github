# Git e GitHub

Curso de Git e GitHub com Téo Calvo.

## Dia 01
    ### Aprendemos sobre Git.
        * Histórico de criação;
        * Para que serve o Git;
        * Ideal para arquivos de texto. Arquivos binários não são recomendados;
        * Iniciar os primeiros comandos no Git Bash
            Comando | Função
            pwd | Mostra o repositório que você está.
            ls | Mostra o que tem dentro do diretório onde você está.
            ls -a | Mostra todas as pastas ocultas dentro de um diretório.
            cd | Se move em direção ao diretório. Dando um Tab ele completa o nome da pasta.
            clear | Limpa a tela (volta ao início).

            Você também pode clicar com o botão direito do mouse em cima da pasta e selecionar a opção "Open Git Bash here" que ele já vai iniciar um Bash para aquela pasta.


    ### Iniciar versionamento com Git (repositório local)

        * git init . -> o ponto é para iniciar tudo o que está na pasta atual. Se o usar dois pontos consecutivos (..) é para subir a pasta anterior (hierarquicamente superior). Neste momento é criado uma pasta oculta chamada .git que irá gerenciar o git

        * git status -> mostra o status da branch atual

        * git add -> adiciona o arquivo na fase de stage para ser commitado

        * git commit -m "mensagem a ser adicionada no commit"


        **Caso tenha dado erro no commit, você deve indicar o nome e e-mail de quem está commitando**
        * git config --global user.name "Seu Nome"
        * git config --global user.email "seu-email@example.com"

        * git log -> mostra todo o histórico do git
        * git reset -> Retorna para unstage. retira os arquivos que foram adicionados (stage) pelo git add e deixa unstaged. Desfaz o git add
        * git reset idCommit -> retorna para o pós-commit

        * git branch -> cria uma ramificação do projeto
        * git checkout -b nome_da_nova_branch -> cria e mudar para a nova branch
        * git checkout nome_da_branch -> mudar para outra branch

        ---

        MERGE

        Para mesclar você precisa voltar para a branch main/master e depois passar o merge da branch alterada para que ela seja incorporada na main/master.

        * git merge nome_da_branch

        * Após o git log o terminal Git Bash ficou como sem a parte de escrever os códigos. Digitei Q e ele retornou.

        * git branch -D nome_da_branch -> deleta a branch selecionada


## Dia 02 
    Aprendemos sobre Git e GitHub.

    Comandos Git e GitHub (repositório remoto)

        O primeiro passo é criar um repositório no GitHub e em seguida copiar o código https do repositório.

        * git clone endereço-https -> copiar um repositório do GitHub na sua máquina (Git Bash)
        * pwd
        * ls
        * cd nome_da_pasta

        * git status
        * git add .
        * git commit -m "mensagem"

        * git push origin nome-da-branch -> envia seus commits para o repositório remoto (GitHub)
