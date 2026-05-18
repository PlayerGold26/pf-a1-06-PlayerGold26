# 20 Comandos do Git

## 1. git init
Inicializa um novo repositório Git.

Exemplo 1:
git init 

Exemplo 2:
git init projeto-git

---

## 2. git clone
Clona um repositório remoto.

Exemplo 1:
git clone https://github.com/user/repositorio1.git

Exemplo 2:
git clone https://github.com/user/repositorio2.git

---

## 3. git config
Configura informações do Git.

Exemplo 1:
git config --global user.name "PlayerGold26"

Exemplo 2:
git config --global user.email "eduardopascotiniterra@email.com"

---

## 4. git status
Mostra o estado atual do repositório.

Exemplo 1:
git status

Exemplo 2:
git status -s

---

## 5. git add
Adiciona arquivos para staging.

Exemplo 1:
git add text.txt

Exemplo 2:
git add README.md

---

## 6. git commit
Cria um commit.

Exemplo 1:
git commit -m "feat: adiciona tela de login"

Exemplo 2:
git commit -m "fix: corrige validação de senha"

---

## 7. git diff
Mostra diferenças entre arquivos.

Exemplo 1:
git diff

Exemplo 2:
git diff --staged

---

## 8. git branch
Gerencia branches.

Exemplo 1:
git branch

Exemplo 2:
git branch develop

---

## 9. git checkout
Troca de branch.

Exemplo 1:
git checkout main

Exemplo 2:
git checkout -b feature/login

---

## 10. git switch
Alternativa moderna ao checkout.

Exemplo 1:
git switch develop

Exemplo 2:
git switch -c hotfix/correcao-login

---

## 11. git merge
Realiza merge entre branches.

Exemplo 1:
git merge develop

Exemplo 2:
git merge feature/login

---

## 12. git pull
Atualiza o repositório local.

Exemplo 1:
git pull origin main

Exemplo 2:
git pull origin develop

---

## 13. git push
Envia commits para o remoto.

Exemplo 1:
git push origin main

Exemplo 2:
git push --all origin

---

## 14. git remote
Gerencia repositórios remotos.

Exemplo 1:
git remote add origin https://github.com/user/repositorio.git

Exemplo 2:
git remote -v

---

## 15. git log
Exibe histórico de commits.

Exemplo 1:
git log

Exemplo 2:
git log --oneline --graph

---

## 16. git reset
Remove alterações do staging ou commits.

Exemplo 1:
git reset HEAD README.md

Exemplo 2:
git reset --hard HEAD~1

---

## 17. git stash
Salva alterações temporariamente.

Exemplo 1:
git stash

Exemplo 2:
git stash pop

---

## 18. git tag
Cria tags de versão.

Exemplo 1:
git tag v1.0.0

Exemplo 2:
git tag -a v1.0.1 -m "Correção emergencial"

---

## 19. git flow feature start
Cria uma feature branch no GitFlow.

Exemplo 1:
git flow feature start login

Exemplo 2:
git flow feature start checkin-documentos

---

## 20. git flow hotfix start
Cria um hotfix branch no GitFlow.

Exemplo 1:
git flow hotfix start 1.0.1

Exemplo 2:
git flow hotfix start 1.0.2