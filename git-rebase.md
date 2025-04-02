# Git rebase flow

comando|descrição
---|---
git clone <repo> | clona o repositório
git branch -r | mostra todas as branches remotas
git checkout <branch> | muda para a branch desejada (nesse caso deve-se escolher de qual branch irá fazer a sua branch (main, dev ou outra))
git checkout -b <nova-branch> | cria sua branch (seguir recomendações de nomenclaura)
git add <arquivo-alterado> | adiciona seu arquivo modificado ao stage
git commit -m "" | commita sua alteração (seguir recomendações de nomenclaura)
git push --set-upstream origin/<nova-branch> | envia as alterações para o repositório remoto
*Se tiver conflito, seguir os passos abaixo:*
git fetch | atualiza as informações de modificação no repositório remoto
git pull | baixar as modificações do repositório remoto
git rebase <branch-main/dev> | ajusta seu commit à branch principal. Nessa etapa, se houver alguma linha em que conflitar com o arquivo da branch, você deve editar manualmente e salvar.
git add <arquivo> | adiciona seu arquivo modificado ao stage
git rebase --continue | vai indicar que você já fez as correções e deseja continuar. Caso queira modificar o nome do Commit, é nessa etapa que corrige. Para sair, clica Crtl + X.
git push -f | esse comando força o push
Após isso, você deve abrir o repositório no GitHub e abrir um pull request da sua branch para a branch que quer mesclar. Escolha um revisor para o seu PR. | Caso tenha alguma modificação a ser corrigida após o PR (reprovação do PR), você deve alterar na sua máquina e subir novamente (git add, commit e push -f).