# Git generic notes

Anotações avulsas sobre git e github.

commando | descrição
---|---
`git rm -r --cached <folder>/<subfolder>` | remover arquivos da posição de stagged (caso tenha dado um `git add .` e adicionado arquivos indesejados)
`git rm -r <file/folder>` | envia um comando para o repositório remoto que também remova um arquivo deletado do repositório local
`git branch -d nomeDaBranchLocal`| excluir uma branch no repositório local
`git push origin --delete nomeDaBranchRemoto` | excluir uma branch no repositório remoto