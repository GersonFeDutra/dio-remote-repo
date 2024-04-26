# DIO | Resumos Git & GitHub

Repository to store resumes from the Git & GitHub course on code
versioning from [DIO.me](dio.me)

<details>

<summary>English</summary>

## 📚 Documentation

- [Git docs](https://git-scm.com/doc)

## 💻 Classes Resume

| Classes | Resumes |
| ------- | ------- |
| Saving changes on Local Repository | [Saving](#Saving) |
| Undoing changes on Local Repository | [Restore](#Restore)
| Pull & Push changes on Local Repository | [Pull & Push](#Pull%20%26%20Push) |
| Working With Branches: Merge, Delete, Diff Conflicts | [Working with Branches](#Working%20with%20Branches) |
| Usefull Commands | [Usefull Commands](#Usefull%20Commands) |

### Saving

```sh
# Start git local repository
git init
# Add files
git add filename
git add .  # Add all files
# Save changes
git commit -m "chore: commit message"  # Tip: use [conventional commits]()
# Local repository status information
git status
```

### Restore

<img src="https://i.stack.imgur.com/cZkcV.jpg" align="right" width="40%"
    alt="Git Data Transport Commands" />

- **Working Tree:** local directory from the repository in its current physical
state (current files saved on user machine).
- **Stagin Area/ index:** preparation area, where changes are saved before
commit. Are stored as a single binary file in `.git/index`.
- **Local repository:** represent the project in the developer machine. It's
controlled by the `.git` directory which includes a directory `objects` with
all versions from each file in the repository (local branches and remote
branches copies).

```sh
# Commits information
git log
# Restore unstaged changes to last commit, discarding work tree state
git restore
git restore --staged  # Restore staged changes to working tree
# Change last commit message
git commit --ammend -m "fixed commit message"
git commit --ammend  # Open commit message on text editor
# Restore to a previous commit (using the hash code)
git reset --mixed  # Default - return changes to work tree
git reset --soft $(commit_hash)  # Return changes to stage area
git reset --hard $(commit_hash)  # Remove changes
# Detailed history of changes
git reflog
```

> [!CAUTION]
> You must only make changes on the local repository history from commits that
> were not sent to remote. If you need to restore some previous state, you must
> `rebase` (make a local commit for reset).

### Pull & Push

```sh
git remote add origin ${url}  # Connect via https or ssh
git push -u origin ${branch}  # Send changes to remote repository
git pull  # Fetch and merge changes from remote to local repository
```

### Working with Branches

A branch is a moving pointer at the changes' history, it points to the most
recent commit in that barnch, and can include other relative commits.

```sh
git checkout -b ${branch}  # Muda para o ramo indicada
git branch -v  # Lista os últimos commits de cada branch
git merge ${branch}  # Mescla o ramo indicado no atual
git branch -d ${branch}  # Delete a branch
```

> [!WARNING]
> Merge conflicts occur when sending changes from a branch to another. This
> includes changes between local to remote repository. When doing the merge,
> Git will generate a conflict in the files itself that must be resolved before
> merged.

### Useful commands

```sh
git fetch
git diff ${from_branch} ${to_branch}  # Verifica a diferença entre os arquivos
                                      # para detectar conflitos.
git clone ${remote_url} --branch ${branch} --single-branch  # Clona um ramo remoto
git stash  # Salva as alterações localmente sem adicionar a um ramo.
git stash --list  # Lista todas as alterações salvas para a árvore de trabalho.
git stash pop  # Remove as alterações salvas como stash
git stash apply  # Aplica as alterações salvas na stash
```

</details>

---

<details>

<summary>Português</summary>

## 📚 Documentação

- [Git docs](https://git-scm.com/doc)

## 💻 Resumo de aulas

| Aulas | Resumos |
| ----- | ------- |
| Salvando Alterações no Repositório Local | [Salvando](#Salvando) |
| Desfazendo Alterações no Repositório Local | [Restaurando](#Restaurando)
| Enviando e baixando alterações com repositório remoto | [Enviando & Baixando](#Enviando%20%26%20Baixando) |
| Trabalhando com Ramos | [Trabalhando com Ramos](#trabalhando%20com%20ramos) |
| Comandos Úteis | [Comandos Úteis](#Comandos%20Úteis) |

### Salvando

```sh
# Iniciar repositório local Git
git init
# Adicionar arquivcos
git add "filename"
git add .  # Adiciona todos os arquivos
# Salvar aleterações
git commit -m "chore: commit message"  # Dica: use [conventional commits]()
# Informação de estado do repositório local
git status
```

### Restaurando

<img src="https://i.stack.imgur.com/cZkcV.jpg" align="right" width="33%"
    alt="Comandos de transporte Git" />

- **Árvore de trabalho:** o diretório local do repositório em seu estado físico
atual (arquivos atuais salvos na máquina do usuário).
- **Área de preparação / index:** onde alterações são salvas aguardando o
commit. É armazenado como um único arquivo binário em `.git/index`.
- **Repositório local:** representa o projeto na máquina do desenvolvedor, é
controlado pelo diretório `.git` que inclui um diretório `objects` com todas as
versões de cada arquivo no repositório (ramos locais e cópias dos ramos remotos).

```sh
# Restaura alterações que não foram para área de preparação para o último commit,
# descartando o estado da árvore de trabalho
git restore
git restore --staged  # Restaura as mudanças da área de
                      # preparação para árvore de trabalho
# Informação sobre os commits
git log
# Altera a mensagem do último commit
git commit --ammend -m "fixed commit message"
git commit --ammend  # Abre a mensagem de commit no editor de texto
# Restaura para um commit anterior (usanso seu código hash)
git reset --mixed  # Padrão - retorna as mudanças para a árvore de trabalho
git reset --soft $(commit_hash)  # Retorna alterações para área de preparação
git reset --hard $(commit_hash)  # Remove as alterações
# Histórico detalhado de alterações
git reflog
```

> [!CAUTION]
> Você apenas deve fazer alterações no histórico do repositório local de comitts
> que não foram mandados para o remoto. Se você precisa restaurar um estado
> anterior você deve fazer um `rebase` (fazer um commit para resetar).

### Enviando & Baixando

```sh
git remote add origin ${url}  # Conecta via https ou ssh
git push -u origin ${branch}  # Envia as mudanças para o repositório remoto
git pull  # Busca e mescla alterações do repositório remoto no local
```

### Trabalhando com Ramos

Um ramo é um ponteiro móvel no histórico de alterações, ele aponta para o commit
mais recente naquele ramo, e pode incluir outros commits relativos a ele.

```sh
git checkout -b ${branch}  # Muda para o ramo indicada
git branch -v  # Lista os últimos commits de cada branch
git merge ${branch}  # Mescla o ramo indicado no atual
git branch -d ${branch}  # Remove um ramo
```

> [!WARNING]
> Conflitos de mesclagem ocorrem ao enviar alterações de um ramo à outro.
> Isto inclui alterações entre o repositório local e remoto. Ao fazer o merge,
> git irá gerar um conflito nos próprios arquivos que deverão ser resolvidos
> antes de serem enviados.

### Comandos Úteis

```sh
git fetch
git diff ${from_branch} ${to_branch}  # Verifica a diferença entre os arquivos
                                      # para detectar conflitos.
git clone ${remote_url} --branch ${branch} --single-branch  # Clona um ramo remoto  
git stash  # Salva as alterações localmente sem adicionar a um ramo.
git stash --list  # Lista todas as alterações salvas para a árvore de trabalho.
git stash pop  # Remove as alterações salvas como stash
git stash apply  # Aplica as alterações salvas na stash
```
</details>
