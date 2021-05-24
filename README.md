# Comandos git

### Configurações
```
git config --list
```
Alterar nome e e-mail.
```
git config --global --replace-all user.name "Éderson Lehugeur"
git config --global --replace-all user.email "ederson-lehugeur@email"
```
Resetar nome e e-mail.
```
git config --global --unset-all user.name
git config --global --unset-all user.email
```
Configurar editor
```
git config --global core.editor (emacs|vim|nano)
```

### Stash
```
git stash
git stash list
git stash apply | git stash pop
```
```
git stash show | git stash show [stash@{1}]
git stash drop | git stash drop [stash@{1}]
git stash clear
```

### Logs
```
git log
git log --decorate
git log --author="Éderson"
```
Commits de cada autor.
```
git shortlog
```
Quantidade de commits de cada autor.
```
git shortlog -sn
```
Visualizar os logs de forma gráfica.
```
git log --graph
```

### Commits
Corrigir autor do commit.
```
git commit --amend --author="Éderson Lehugeur <ederson-lehugeur@email>"
```

### Branches
```
git checkout -b [NEW_BRANCH]
```
Enviar branch para o origin.
```
git push --set-upstream origin [BRANCH]
```
Listar branches
```
git branch -a
git branch -r
```
Deletar branch no origin.
```
git push origin :[BRANCH]
```
# Voltar para um commit específico.
```
git reset --hard "tag ou hash do commit"
```
```
git push origin HEAD --force
```
###--------------------------------------------
# Reseta o HEAD. Permite a atualização do repositório local 
# sobrescrevendo o conteúdo existente.
git reset --hard origin/master
# ou
git reset --hard origin/<branch_name>

# Remover arquivo do staged.
git reset HEAD <file>

# Voltar para um commit específico com os arquivos em staged,
# ou seja, prontos para o commit.
git reset --soft <hash do commit>

# Voltar para um commit específico com os arquivos modificados.
git reset --mixed <hash do commit>

# Voltar para um commit específico excluindo os commits acima.
git reset --hard <hash do commit>

# Se um commit for removido e for enviado para o diretório
# remoto, é necessário usar o parâmetro force.
# Cuidado ao fazer isso e mandar as alterações para o diretório
# remoto onde outras pessoas também estão trabalhando.
git push -f

# Atualizar repositório quando já foi dado um commit.
git pull --rebase

# Verificar diferença entre os arquivos.
git diff

# Verificar diferença entre os arquivos modificados mostrando 
# somente o nome dos arquivos.
git diff --name-only

# Verificar arquivos já adicionados para commit.
git diff --cached

# Ver alterações do último commit.
git show
git show <hash do commit>
# Arquivos modificados.
git show --stat <hash do commit>

# Tirar um arquivo da área de seleção.
git reset HEAD <file>
//git rm --cached [-f] <file> (to unstage)

# Desfazendo um arquivo modificado.
git checkout -- <file>

# Endereço do origin(Repositório remoto).
git remote -v

-------------------------------------------------------------------------

# Criar um novo repositório na linha de comando.
echo "# Descrição do Projeto" >> README.md
git init
git add README.md
# BitBucket = "Initial commit" | GitHub = "first commit"
git commit -m "Initial commit"
git remote add origin git@bitbucket.org:ederson-lehugeur/thirdproject.git
# Atualizar o endereço do repositório.
#git remote set-url origin git@bitbucket.org:ederson-lehugeur/thirdproject.git
# O repositório no GitHub ou BitBucket já deve estar criado.
git push -u origin master

-------------------------------------------------------------------------

# Adicionar tag de versão.
git tag -a 1.0.0 -m "Versão 1.0.1"
git push --tags

# Listar todas as tags.
git tag

# Deletar tags.
git tag -d <tag>

# Deletar tags no origin.
git push origin :<tag>

# Alias
git config --global alias.s status
git config --global alias.g git
git config --global alias.pl pull
git config --global alias.ps push

# Reverter um commit.
git revert <hash do commit>

# Atualizar as referências remotas.
git fetch
