# Git e GitHub

Anotações do curso de Git e GitHub com Téo Calvo.

## Dia 01
### Sobre Git
* Histórico de criação do Git;
* Para que serve o Git;
* Ideal para arquivos de texto. Arquivos binários não são recomendados;
* Primeiros comandos no Git Bash;

Comando | Função
---|---
pwd | Mostra o repositório que você está.
ls | Mostra o que tem dentro do diretório onde você está.
ls -a | Mostra todas as pastas ocultas dentro de um diretório.
cd | Se move em direção ao diretório. Dando um Tab ele completa o nome da pasta.
cd .git/ | mostra tudo o que está na pasta git
clear | Limpa a tela (volta ao início).


    Você também pode clicar com o botão direito do mouse em cima da pasta e selecionar a opção "Open Git Bash here" que ele já vai iniciar um Bash para aquela pasta.

### Iniciar versionamento com Git (repositório local)

* `git init` . -> o ponto é para iniciar tudo o que está na pasta atual. Se o usar dois pontos consecutivos (..) é para subir a pasta anterior (hierarquicamente superior). Neste momento é criado uma pasta oculta chamada .git que irá gerenciar o git
* `git status` -> mostra o status da branch atual
* `git add` -> adiciona o arquivo na fase de stage para ser commitado
* `git commit -m "mensagem a ser adicionada no commit"` -> envia para o repositório local

    **Caso tenha dado erro no commit, você deve indicar o nome e e-mail de quem está commitando**
    * `git config --global user.name "Seu Nome"`
    * `git config --global user.email "seu-email@example.com"`


* `git log` -> mostra todo o histórico do git
* `git reset` -> Retorna para unstage. retira os arquivos que foram adicionados (stage) pelo git add e deixa unstaged. Desfaz o git add
* `git reset idCommit` -> retorna para o pós-commit
* `git branch` -> cria uma ramificação do projeto
* `git checkout -b nome_da_nova_branch` -> cria e mudar para a nova branch
* `git checkout nome_da_branch` -> mudar para outra branch

---
### Merge no repositório local

Para mesclar você precisa voltar para a branch main/master e depois passar o merge da branch alterada para que ela seja incorporada na main/master.
* `git merge nome_da_branch` -> mescla a branch com o main/master

        Após o git log o terminal Git Bash ficou como sem a parte de escrever os códigos. Basta digitar `q` e ele retornou.

* `git branch -D nome_da_branch` -> deleta a branch selecionada


## Dia 02 
Aprendemos sobre Git e GitHub.

### Comandos Git e GitHub (repositório remoto)

O primeiro passo é criar um repositório no GitHub e em seguida copiar o código https do repositório.

* `git clone enderecoHttps` -> copiar um repositório do GitHub na sua máquina (Git Bash)
    * pwd
    * ls
    * cd nome_da_pasta
    * git status
    * git add .
    * git commit -m "mensagem"

* `git push origin nome-da-branch` -> envia seus commits para o repositório remoto (GitHub)
        
            Merge pelo GitHub com Pull Request.

* `git pull` -> puxa a versão mais atual do GitHub (pode ser na main/master ou em outra branch). Puxa da main remota para a main local


### Para casos com problema de login você pode criar uma chave SSH pelo Bash.

`ssh-keygen -t rsa` -> clica enter <br>
`cat ~/.ssh/id_rsa.pub` -> Clica enter, seleciona e copia o código gerado

        Em seguida, abre o GitHub pelo navegador, clica em opções, SSH and GPG Keys, add SSH Key, adiciona um nome para a chave (ex.: meu-notebook), cola a chave no campo indicado e clica em Add SSH Key. 
        Com isso a sua máquina fica diretamente habilitada e você não precisa ficar fazendo login todas as vezes que iniciar um novo Git Bash. Cuidado para não utilizar esta função em computadores públicos. 
        Caso você queira remover a chave, basta clicar no mesmo campo das configurações de SSH and GPG Keys e deletar a chave.

        Uma vez que você configurou a chave SSH, quando você for clonar um repositório, você deve selecionar a opção SSH e colar após o `git clone` no Bash.

**Observações:**  Não é recomendado versionar arquivos `.ipynb`no github (a não ser que seja direto do Colab). O mais recomendado é versionar arquivos `.py`.

:part_alternation_mark:
:white_check_mark:


EudesCunha