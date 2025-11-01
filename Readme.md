# Minicurso de Git e Github 

Este é um guia de consulta rápida (um "cheatsheet") baseado nas anotações do minicurso, focado nos comandos essenciais.

## 1. Ciclo Básico de Trabalho

* `git init`: Inicia um novo repositório local na pasta atual.
* `git status`: Mostra o estado dos arquivos (modificados, em *stage*, etc.).
* `git add <arquivo>`: Adiciona um arquivo à área de *stage* (preparação).
* `git commit -m "Mensagem"`: Salva as mudanças do *stage* no repositório local.
* `git commit -am "Mensagem"`: (Atalho) Adiciona e commita todos os arquivos já monitorados que foram modificados.

## 2. Analisando o Histórico e Mudanças

* `git log`: Exibe o histórico de *commits*.
* `git log --graph`: Mostra o histórico de forma gráfica, com as *branches*.
* `git shortlog -sn`: Lista autores e a quantidade de *commits* de cada um.
* `git show <hash_do_commit>`: Detalha o que foi modificado em um *commit* específico.
* `git diff`: Exibe as mudanças nos arquivos que ainda não estão em *stage*.

## 3. Desfazendo Alterações

* `git checkout <arquivo>`: Reverte um arquivo para a versão do último *commit* (descarta mudanças locais).
* `git reset HEAD <arquivo>`: Retira um arquivo da área de *stage*, mas mantém as modificações.
* `git reset --soft <hash>`: Retorna para um *commit* anterior, mas mantém as mudanças em *stage*.
* `git reset --mixed <hash>`: (Padrão) Retorna e mantém as mudanças nos arquivos, mas fora do *stage*.
* `git reset --hard <hash>`: **(Cuidado)** Retorna para um *commit* anterior e descarta **todas** as mudanças.

## 4. Repositórios Remotos (GitHub)

* `git remote add origin <url_do_repositorio>`: Conecta o repositório local a um remoto.
* `git push -u origin main`: Envia os *commits* locais da *branch* `main` para o remoto `origin`.
* `git clone <url>`: Baixa (clona) um repositório remoto para a máquina local.
* **Fork**: Uma cópia de um repositório (feita no GitHub) para a sua própria conta.

## 5. Branches (Ramificações)

* `git checkout -b <nova_branch>`: Cria e já muda para a nova *branch*.
* `git checkout <nome_da_branch>`: Alterna entre *branches* existentes.
* `git branch -D <nome_da_branch>`: Deleta uma *branch* local.

### Unindo Branches

* `git merge <branch_para_unir>`: Une as mudanças de outra *branch* na *branch* atual. Cria um novo "commit de merge".
* `git rebase <branch_para_unir>`: Reorganiza os *commits* da *branch* atual "à frente" da outra, criando um histórico linear.

## 6. Ferramentas Adicionais

* `.gitignore`: Arquivo de texto que lista arquivos e pastas que o Git deve ignorar (ex: `node_modules/`, `.env`).
* `git stash`: Guarda temporariamente mudanças (que não estão prontas para *commit*) para limpar a área de trabalho.
* `git stash apply`: Aplica as últimas mudanças guardadas com o `stash`.
* `git tag -a 1.0.0 -m "Mensagem"`: Cria uma "tag" (marcador de versão) anotada.
* `git config --global alias.<atalho> <comando>`: Cria um apelido para um comando (ex: `alias.s status`).
