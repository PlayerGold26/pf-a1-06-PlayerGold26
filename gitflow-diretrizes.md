# Roteiro Completo — pf-a1-06-PlayerGold26
Todos os 20 comandos Git usados ao longo do ciclo de vida real do repositório

Arquivos do repo: README.md | git-comandos.md | text.txt | gitflow-diretrizes.md
Branch principal: main
Remote: https://github.com/PlayerGold26/pf-a1-06-PlayerGold26.git
══════════════════════════════════════════════════════════════════════════════

# FASE 1 — CONFIGURAÇÃO INICIAL DO AMBIENTE
# Comandos: git config · git init · git remote · git clone
 
[1] git config — antes de qualquer coisa, identificar quem está commitando
git config --global user.name "PlayerGold26"
git config --global user.email "seuemail@email.com"
 
# verificar se ficou certo
git config --list
 
 ─── OPÇÃO A: você criou o repo no GitHub e vai clonar ────────────────────
 
[2] git clone — clonar o repositório já criado no GitHub para sua máquina
git clone https://github.com/PlayerGold26/pf-a1-06-PlayerGold26.git
cd pf-a1-06-PlayerGold26
 
─── OPÇÃO B: você iniciou localmente e depois conectou ao GitHub ─────────
 
[1-alt] git init — inicializar o repositório localmente do zero
mkdir pf-a1-06-PlayerGold26
cd pf-a1-06-PlayerGold26
git init
Resultado: "Initialized empty Git repository in .../pf-a1-06-PlayerGold26/"
 
[14] git remote — conectar o repositório local ao GitHub
git remote add origin https://github.com/PlayerGold26/pf-a1-06-PlayerGold26.git
 
confirmar que o remote foi adicionado corretamente
git remote -v
origin  https://github.com/PlayerGold26/pf-a1-06-PlayerGold26.git (fetch)
origin  https://github.com/PlayerGold26/pf-a1-06-PlayerGold26.git (push)
 
 
# FASE 2 — PRIMEIROS ARQUIVOS E COMMITS NA MAIN
Comandos: git status · git add · git commit · git push · git log
 
O GitHub criou automaticamente o README.md ao criar o repositório.
Se você começou local, crie ele manualmente:
echo "# pf-a1-06-PlayerGold26" > README.md
 
[4] git status — verificar o estado antes de fazer qualquer commit
git status
On branch main
Untracked files:
 - README.md
 
[5] git add — adicionar o README ao staging
git add README.md
 
confirmar que entrou no staging
git status
Changes to be committed:
new file: README.md
 
[6] git commit — registrar o primeiro commit do projeto
git commit -m "chore: inicializa repositório com README"
 
[13] git push — enviar o commit para o GitHub
git push -u origin main
O -u cria o vínculo entre a branch local e a remota (só precisa na primeira vez)
 
[15] git log — confirmar que o commit foi registrado
git log --oneline
a1b2c3d (HEAD -> main, origin/main) chore: inicializa repositório com README
 
 
# FASE 3 — CRIANDO O text.txt E PRATICANDO reset E stash
Comandos: git diff · git reset · git stash
 
Criar o text.txt para usar como arquivo de prática dos comandos
 
echo "teste" > text.txt
 
git add text.txt
git commit -m "chore: cria text.txt para testes dos comandos git"
git push origin main
 
── Praticando git diff ───────────────────────────────────────────────────
 
Adicionar uma linha no arquivo
echo "nova linha" >> text.txt
 
[7] git diff — ver o que mudou antes de commitar
git diff text.txt
-teste
+teste
+nova linha
(mostra em vermelho o que foi removido e em verde o que foi adicionado)
 
git add text.txt
git commit -m "chore: adiciona linha de teste no text.txt"
git push origin main
 
── Praticando git reset ──────────────────────────────────────────────────
 
Adicionar mais uma linha
echo "linha reset" >> text.txt
 
Adicionar ao staging
git add text.txt
 
Perceber que não era pra ter adicionado ainda — remover do staging sem perder a alteração
[16] git reset — tirar o arquivo do staging e manter a alteração localmente
git reset HEAD text.txt
 
git status
Changes not staged for commit:
modified: text.txt
(o arquivo saiu do staging mas a linha "linha reset" ainda está lá)
 
Agora sim, adicionar e commitar de propósito
git add text.txt
git commit -m "chore: demonstra uso do git reset no text.txt"
git push origin main
 
── Praticando git stash ──────────────────────────────────────────────────
 
Começar a escrever algo no text.txt mas ser "interrompido"
echo "stash teste" >> text.txt
 
Não quer perder a alteração, mas precisa limpar o working directory
[17] git stash — guardar as alterações temporariamente
git stash push -m "wip: linha de stash em andamento"
 
git status
nothing to commit, working tree clean
(o arquivo voltou ao estado do último commit)
 
Recuperar o que estava guardado
git stash pop
 
Confirmar que a linha voltou
cat text.txt
teste
nova linha
linha reset
stash teste
 
git add text.txt
git commit -m "chore: demonstra uso do git stash no text.txt"
git push origin main
 
 
# FASE 4 — CRIANDO O git-comandos.md EM BRANCH DE FEATURE
Comandos: git branch · git checkout · git switch · git merge · git pull
 
Garantir que a main está atualizada antes de criar a branch
[12] git pull — baixar qualquer atualização que exista no remoto
git pull origin main
 
[8] git branch — criar a branch de feature para o arquivo de comandos
git branch feature/git-comandos
 
listar branches para confirmar
git branch
* main
feature/git-comandos
 
[9] git checkout — entrar na branch de feature (forma clássica)
git checkout feature/git-comandos
 
── alternativa moderna com switch ────────────────────────────────────────
[10] git switch — entrar/criar branch (forma moderna, mais legível)
git switch feature/git-comandos
ou criar e entrar direto:
git switch -c feature/git-comandos
 
Agora dentro da branch, criar o arquivo git-comandos.md
(copie o arquivo que geramos juntos com os 20 comandos e exemplos)
Após copiar o arquivo para a pasta do repositório:
 
git status
On branch feature/git-comandos
Untracked files:
git-comandos.md
 
git add git-comandos.md
git commit -m "docs: adiciona estrutura inicial do git-comandos.md com 20 comandos"
 
Adicionar os exemplos práticos (segunda parte do trabalho)
Após editar o arquivo com os exemplos contextualizados:
 
git add git-comandos.md
git commit -m "docs: adiciona exemplos práticos contextualizados para os 20 comandos"
 
Enviar a branch para o GitHub
git push --set-upstream origin feature/git-comandos
 
── Merge da feature na main ──────────────────────────────────────────────
 
[9] git checkout — voltar para a main
git checkout main
 
Garantir que a main está atualizada
git pull origin main
 
[11] git merge — integrar a branch de feature na main
git merge feature/git-comandos
 
git push origin main
 
Conferir o histórico com o merge registrado
[15] git log — visualizar o histórico completo de forma gráfica
git log --oneline --graph
* f3a1b2c (HEAD -> main, origin/main) docs: adiciona exemplos práticos contextualizados
* e2d4c5b docs: adiciona estrutura inicial do git-comandos.md com 20 comandos
* d1c3b4a chore: demonstra uso do git stash no text.txt
* c2b4a3f chore: demonstra uso do git reset no text.txt
* b3a5f2e chore: adiciona linha de teste no text.txt
* a1b2c3d chore: cria text.txt para testes dos comandos git
* 9f8e7d6 chore: inicializa repositório com README
 
 
# FASE 5 — CRIANDO O gitflow-diretrizes.md COM REBASE E CHERRY-PICK
Comandos: git rebase · git cherry-pick · git tag
 
Criar branch para o documento de diretrizes
[10] git switch — criar e entrar na branch (forma moderna)
git switch -c feature/gitflow-diretrizes
 
Copiar o gitflow-diretrizes.md para a pasta do repositório
Fazer commits incrementais conforme o documento é escrito:
 
Commit 1 — só a estrutura e sumário
git add gitflow-diretrizes.md
git commit -m "docs: cria estrutura inicial do gitflow-diretrizes"
git push --set-upstream origin feature/gitflow-diretrizes
 
Commit 2 — atividades 1.1 e 1.2 preenchidas
git add gitflow-diretrizes.md
git commit -m "docs: descreve atividades 1.1 e 1.2 no gitflow-diretrizes"
git push origin feature/gitflow-diretrizes
 
Commit 3 — atividades 1.3 e 1.4
git add gitflow-diretrizes.md
git commit -m "docs: descreve atividades 1.3 e 1.4 no gitflow-diretrizes"
git push origin feature/gitflow-diretrizes
 
Commit 4 — atividades 1.5 e 1.6, documento finalizado
git add gitflow-diretrizes.md
git commit -m "docs: descreve atividades 1.5 e 1.6 e finaliza documento"
git push origin feature/gitflow-diretrizes
 
── Praticando git rebase ─────────────────────────────────────────────────
 
Antes do merge final, atualizar a branch com qualquer mudança que tenha
ocorrido na main enquanto trabalhávamos nesta branch
 
git checkout main
git pull origin main
git checkout feature/gitflow-diretrizes
 
[19] git rebase — reaplicar os commits desta branch em cima da main atual
(deixa o histórico linear, sem merge commits desnecessários)
git rebase main
Se não houver conflitos: "Successfully rebased and updated refs/heads/feature/gitflow-diretrizes"
 
git push --force origin feature/gitflow-diretrizes
--force necessário após rebase porque o histórico foi reescrito
 
── Praticando git cherry-pick ────────────────────────────────────────────
 
Cenário: o commit "docs: cria estrutura inicial do gitflow-diretrizes"
precisa ir para a main AGORA (antes do merge completo da branch),
por exemplo para que o professor já veja o arquivo iniciado.
 
git checkout main
 
[15] git log — pegar o hash do commit que queremos
git log --oneline feature/gitflow-diretrizes
g7h8i9j docs: descreve atividades 1.5 e 1.6 e finaliza documento
f6g7h8i docs: descreve atividades 1.3 e 1.4 no gitflow-diretrizes
e5f6g7h docs: descreve atividades 1.1 e 1.2 no gitflow-diretrizes
d4e5f6g docs: cria estrutura inicial do gitflow-diretrizes   <-- queremos este
 
[20] git cherry-pick — aplicar apenas esse commit na main
git cherry-pick d4e5f6g
 
git push origin main
 
── Merge final da branch na main ─────────────────────────────────────────
 
git merge feature/gitflow-diretrizes
git push origin main
 
── Praticando git tag ────────────────────────────────────────────────────
 
Com o trabalho completo mergeado na main, marcar esta versão como entrega final
[18] git tag — criar uma tag anotada marcando o ponto de entrega
git tag -a v1.0 -m "Entrega final — todos os 20 comandos documentados com exemplos e gitflow-diretrizes"
git push origin v1.0
 
# VERIFICAÇÃO FINAL
 
[15] git log — ver o histórico completo e linear do repositório
git log --oneline --graph --all
 
[8] git branch — listar todas as branches para confirmar o que existe
git branch -a
 
[14] git remote — confirmar que o remote está apontando para o lugar certo
git remote -v
 
Estado final esperado do repositório:

main (HEAD)
├── text.txt
├── git-comandos.md
└── gitflow-diretrizes.md

Tags: v1.0

MAPA DE TODOS OS 20 COMANDOS USADOS NESTE ROTEIRO
══════════════════════════════════════════════════════════════════════════
1. git init        → Fase 1  — inicializa o repositório local
2. git clone       → Fase 1  — clona o repo do GitHub
3. git config      → Fase 1  — configura nome e email
4. git status      → Fase 2  — verifica estado do working directory
5. git add         → Fase 2  — adiciona arquivos ao staging
6. git commit      → Fase 2  — registra snapshots do projeto
7. git diff        → Fase 3  — revisa mudanças antes de commitar
8. git branch      → Fase 4  — cria e lista branches
9. git checkout    → Fase 4  — troca de branch (forma clássica)
10. git switch      → Fase 5  — troca/cria branch (forma moderna)
11. git merge       → Fase 4  — integra feature na main
12. git pull        → Fase 4  — atualiza branch local com o remoto
13. git push        → Fase 2  — envia commits para o GitHub
14. git remote      → Fase 1  — conecta local ao GitHub
15. git log         → Fase 4  — visualiza histórico de commits
16. git reset       → Fase 3  — remove arquivo do staging
17. git stash       → Fase 3  — salva alterações temporariamente
18. git tag         → Fase 5  — marca a versão de entrega final
19. git rebase      → Fase 5  — atualiza branch de forma linear
20. git cherry-pick → Fase 5  — aplica commit específico na main
