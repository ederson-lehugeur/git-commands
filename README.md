# comandos-git
Comandos básicos do Git

# Comandos básicos GitHub

# Lista as configurações.
git config --list

# Alterar nome e e-mail.
git config --global --replace-all user.name "Éderson Lehugeur"
git config --global --replace-all user.email "ederson-lehugeur@tjmrs.jus.br"

# Reset nome e e-mail
git config --global --unset-all user.name
git config --global --unset-all user.email

# Configurar editor
git config --global core.editor (emacs|vim|nano)

# Criar um repositório git ou reinicializar um existente.
git init

# Clonar de uma url.
git clone https://github.com/ederson-lehugeur/site

# Atualizar repositório local com a mais nova versão.
git pull
git stash
git stash pop

-----------------------------------------------------
# Listar todos os diretórios de trabalho na pilha.
git stash list

# Visualizar um diretório de trabalho.
git stash show | git stash show [stash@{1}]

# Deletar um diretório de trabalho.
git stash drop | git stash drop [stash@{1}]

# Deletar todos.
git stash clear

git stash

git pull --rebase | git pull

// Novas alterações
// git push

git stash pop | git stash apply [stash@{2}]
-----------------------------------------------------

# Status do repositório atual.
git status

# Mapeia um ou vários arquivos inserindo no arquivo index no 
# diretório .git. Preparar para o versionamento.
git add <arquivo> ou <--all>

# Dar commit dos arquivos modificados os preparando automaticamente.
git commit -am "Mensagem do commit"

# Atualizar repositório remoto com as novas alterações.
git push

# Log com todas as operações feitas.
git log
git log --decorate

# Log com filtros.
git log --author="Éderson"

# Mensurar os commits de cada autor.
git shortlog

# Apenas a quantidade de commits de cada autor.
git shortlog -sn

# Visualizar os logs de forma "gráfica".
git log --graph

# Corrigir autor do commit.
git commit --amend --author="Éderson Lehugeur <ederson-lehugeur@tjmrs.jus.br>"

# Criar um novo branch(ramificação).
git checkout -b <new_branch>

# Enviar um branch para o origin. Entrar no branch e:
git push --set-upstream origin <name_branch>

# Juntar uma ramificação em outra. (Respeita a ordem
# cronológica, porém cria um novo commit apenas para o merge)
git merge <name_branch>
# Exemplo (dev -> test)
git checkout test

git pull

git merge dev

# Juntar uma ramificação em outra com rebase. (Não respeita
# a ordem cronológica)
git rebase <name_branch>

# Mostrar todas as ramificações e a atual.
git branch [-a (Listar todos branches locais e remotos)][-r (Listar apenas os branches locais)]

# Trocar de branch.
git checkout <name_branch>

# Deletar um branch.
git branch -D <name_branch>

# Deletar um branch no origin.
git push origin :<name_branch>

# Voltar o código fonte para um commit especifico.
git reset --hard "nome da tag ou Hash do Commit!"
# Realizar o push da operação.
git push origin HEAD --force

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
