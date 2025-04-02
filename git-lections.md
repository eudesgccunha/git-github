# Git

## Comandos Bash

ls  | lista arquivos
cd  | move entre diretórios
pwd | mostra diretório de trabalho
cat | exibe conteúdo do arquivo
rm  | remove arquivo ou diretório
rm -rf | remove de forma recursiva e forçada todos diretórios
mkdir | cria pasta (Ex.: mkdir Git)
touch | cria arquivo (Ex.: touch README.md)

## Comandos Git

- git --help
- git log
- git status
- git diff <nome do arquivo>: exibe as ultimas modificações realizadas no arquivo selecionado
- git diff .: exibe as ultimas modificações realizadas em todos os arquivos da pasta do projeto
- git reset <nome do arquivo>: retirar um arquivo da fase de stage (após um git add)
- git merge <branch-secundaria>: pra mesclar, uma vez que a modificação esteja numa branch secundária, você deve voltar para a branch principal (main) e passar o comando com o nome da branch secundária. O merge puxa as infomações pra si. Então, se eu estiver uma branch secundária, terciária ou qualquer que estiver atualizada, posso utilizar o merge como se fosse um pull. 
- git branch -D <nome-da-branch>: deletar uma branch
- HEAD: É o último commit da branch 
- git push origin <branch>: a recomendação é que é melhor trabalhar com os comandos explícitos (ao invés de configurar o push e depois só enviar git push)
- Sync fork: clicando neste botão dentro do seu fork no github você atualiza a sua cópia do fork com base no arquivo original (do qual você fez o fork)
- git fetch: atulizar os dados do repositório remoto (github)
- git branch: mostra as branches que estão na sua máquina
- git checkout <develop>: muda para a branch de interesse
- git pull origin <develop>: para garantir que a branch está com a versão mais atual do repositório (mesmo que tenha dado git fetch a poucos minutos)
- git checkout -b <nova-branch>: cria uma branch e já muda para ela (sai da branch anterior para a recém criada)



## Git Flow

O Git Flow é um modelo de ramificação (branching model) que organiza e estrutura o uso de branches em projetos de software utilizando o Git, visando melhorar o gerenciamento de versões e o fluxo de trabalho colaborativo.

### Convenção para nomenclatura de branch

O Git Flow define algumas convenções e recomendações para como usar diferentes branches em um repositório Git.

As principais branches do Git Flow são:

1. master (ou main): Esta é a branch principal do projeto. Ela contém a versão estável do software, ou seja, a versão que foi lançada para produção.

2. develop: A branch de desenvolvimento. É onde as funcionalidades novas são integradas e testadas antes de serem lançadas na versão estável. A partir dessa branch, novas funcionalidades são desenvolvidas.

Além dessas, o Git Flow também usa branches auxiliares, como:

3. feature/: São branches criadas a partir da develop para o desenvolvimento de novas funcionalidades. Quando a funcionalidade é concluída, ela é mesclada de volta na develop.

4. release/: Usada para preparar o lançamento de uma nova versão. Ela é criada a partir da develop quando as funcionalidades estão prontas para uma nova versão. Durante o tempo em que está na branch de release, são feitas correções e ajustes. Depois disso, é mesclada na master e develop.

5. hotfix/: Usada para corrigir problemas urgentes em produção. A branch hotfix é criada a partir da master e, após a correção, a alteração é mesclada de volta tanto em master quanto em develop.


### Convenção para nomenclatura de commit

O commit possui os elementos estruturais abaixo (tipos), que informam a intenção do seu commit ao utilizador(a) de seu código.

- fix: Commits do tipo fix indicam que seu trecho de código commitado está solucionando um problema (bug fix), (se relaciona com o PATCH do versionamento semântico).
Ex.: git commit -m "fix: changes in login button" 

- feat: Commits do tipo feat indicam que seu trecho de código está incluindo um novo recurso (se relaciona com o MINOR do versionamento semântico).

- docs: Commits do tipo docs indicam que houveram mudanças na documentação, como por exemplo no Readme do seu repositório. (Não inclui alterações em código).

- style: Commits do tipo style indicam que houveram alterações referentes a formatações de código, semicolons, trailing spaces, lint... (Não inclui alterações em código).

- refactor: Commits do tipo refactor referem-se a mudanças devido a refatorações que não alterem sua funcionalidade, como por exemplo, uma alteração no formato como é processada determinada parte da tela, mas que manteve a mesma funcionalidade, ou melhorias de performance devido a um code review.

- build: Commits do tipo build são utilizados quando são realizadas modificações em arquivos de build e dependências.

- test: Commits do tipo test são utilizados quando são realizadas alterações em testes, seja criando, alterando ou excluindo testes unitários. (Não inclui alterações em código)

- chore: Commits do tipo chore indicam atualizações de tarefas de build, configurações de administrador, pacotes... como por exemplo adicionar um pacote no gitignore. (Não inclui alterações em código)


## Git rebase

- Estando na branch de desenvolvimento (develop ou feature) você passar o comando git rebase <main-ou-branch-de-desenvolvimento>, ele vai dar um erro de conflito
- Você deverá resolver o conflito manualmente e dar o ok (merge)
- Em seguida, git add <file>
- git rebase --continue: Após isso, o git vai ajustar os commits de acordo com o ultimo commit da main ou develop.

O arquivo [git-rebase.md](https://github.com/eudesgccunha/git-github/blob/main/git-rebase.md) traz uma ordem de comandos gits comuns ao rebase.


## Referências

1. [Repositório do projeto no GitHub](https://github.com/TeoMeWhy/curso-git-github-2025)
2. [Resolvendo conflitos](https://www.youtube.com/watch?v=IRmjluONHxU)
3. [Pull Request](https://youtu.be/Y_fFZjzw-D4?t=2012)
4. [Conflitos após o Fork](https://www.youtube.com/watch?v=vWtrTmjis2w)
5. [Conventional Commits Pattern](https://medium.com/linkapi-solutions/conventional-commits-pattern-3778d1a1e657)
6. [Nomenclatura para branch](https://medium.com/prolog-app/nossos-padr%C3%B5es-de-nomenclatura-para-branches-e-commits-fade8fd17106)
7. [Git Flow](https://www.youtube.com/watch?v=l44uGe-sxgM)