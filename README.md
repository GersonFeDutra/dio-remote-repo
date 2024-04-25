# DIO | Resumos Git & GitHub

Repository to store resumes from the Git & GitHub course on code
versioning from [DIO.me](dio.me)

<details>

<summary>English</summary>

## 📚 Documentation

- [Git docs](https://git-scm.com/doc)

## 💻 Classes Resume

| Classes | Resumes |
| Saving changes on Local Repository | [Saving](#Saving) |
| Undoing changes on Local Repository | [Restore](#Restore)

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

<img src="https://i.stack.imgur.com/cZkcV.jpg" align="right" width="33%"
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

```

</details>

---

<details>

<summary>Português</summary>

## 📚 Documentação

- [Git docs](https://git-scm.com/doc)

## 💻 Resumo de aulas

| Aulas | Resumos |
| Salvando Alterações no Repositório Local | [Salvando](#Saving) |
| Desfazendo Alterações no Repositório Local | [Restaurando](#Restore)

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

</details>
