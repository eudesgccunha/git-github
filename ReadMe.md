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

* `git init .` -> o ponto é para iniciar tudo o que está na pasta atual. Se o usar dois pontos consecutivos (..) é para subir a pasta anterior (hierarquicamente superior). Neste momento é criado uma pasta oculta chamada .git que irá gerenciar o git
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

### Fork

Abre o repositório que quer criar um Fork e clica em fork. Após isso, em Code, seleciona o url HTTPS ou SSH (depende de como você está usando na sua máquina) e copia.

No seu terminal Bash você escreve:
- `cd ~`
- `cd pasta-selecionad`a (ex.: cd Área\ de\ Trabalho/)

Ou você pode clicar com o botão direito na pasta que deseja e seleciona "Open Git Bash here".

- `git clone url-do-fork` -> clonar o repositório que você fez o fork
- `cd nome-da-pasta-do-fork` -> entrar dentro da pasta do fork
- `git checkout -b nome-da-nova-branch` -> cria uma branch para você com um nome que você queira
- `git branch` -> para ver qual branch você está

Quando você fizer alterações (no código ou criando outros arquivos para o repositório) faz o:
```
git add
git commit -m "mensagem"
git push origin nome-da-branch
```

No GitHub, se você quiser sugerir essas alterações para o repositório original (do proprietário) basta clicar em Compare and pull request. Se o proprietário achar legal, ele pode adicionar a sua sugestão em forma de branch ao repositório main dele. 
Após isso você pode sincronizar o repositório original clicando em Sync e Update branch (no GitHub) e depois fazer um git pull no seu Bash.

Você também pode fazer forks de vários projetos do GitHub que achar legal para salvar no seu repositório e de tempos em tempos sincronizar (Sync - Update branch).

## Dia 03

### Git Ignore

Na pasta raiz criar, pelo vscode um arquivo escrito `.gitignore` (esse é o formato dele). Dentro desse arquivo você deve escrever o nome dos arquivos para serem ignorados e não sofrerem commit.

Você tem a opção de passar o nome completo e extensão do arquivo ou selecionar todos os arquivos de uma extensão com um asterisco (ex.: *.csv, *.xlsx).

No Windows, todos os arquivos que começam com . são arquivos ocultos (ex.: `.git`, `.gitignore`)


### Git Keep

Caso você queira manter um arquivo (desfazer o `.gitignore`) pode usar o `.gitkeep`. 
Neste caso você cria um arquivo `.gitkeep` dentro da pasta que deseja manter. Então essa pasta vai entrar no commit, mas todos os arquivos com extensões contempladas no `.gitingore` serão ignorados.

---
EudesCunha
