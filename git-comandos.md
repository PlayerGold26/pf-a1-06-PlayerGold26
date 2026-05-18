# 20 Comandos do Git

## 1. git init
Inicializa um novo repositório Git.

 - Exemplo 1: Você acabou de criar uma pasta para um projeto pessoal de portfólio e quer começar a versionar o código antes mesmo de subir para o GitHub.

 - Exemplo 2: Você recebeu um projeto legado da empresa em um ZIP, sem histórico de versão nenhum. Antes de começar a modificar, você inicializa um repositório para que cada mudança fique registrada.

---

## 2. git clone

 - Exemplo 1: Você entrou em um time novo e o tech lead te mandou o link do repositório no GitHub. Para começar a trabalhar, você clona o projeto completo com todo o histórico de commits.

 - Exemplo 2: Você quer contribuir com uma biblioteca open source que usa bastante no trabalho. Primeiro você faz um fork no GitHub e depois clona o seu fork — não o repositório original — para que suas alterações fiquem no seu controle.

---

## 3. git config
Configura informações do Git.

 - Exemplo 1: Você instalou o Git em um computador novo e precisa configurar seu nome e e-mail antes de fazer o primeiro commit — sem isso, o Git não sabe quem está commitando.

 - Exemplo 2: Você usa o mesmo computador para projetos pessoais (com seu e-mail do Gmail) e para um projeto de freelance com um cliente específico que exige seu e-mail corporativo. Você configura o e-mail diferente apenas dentro da pasta daquele projeto, sem afetar o restante.

---

## 4. git status
Mostra o estado atual do repositório.

 - Exemplo 1: Você passou a tarde modificando vários arquivos e, antes de fazer o commit, quer ter certeza de que está incluindo exatamente o que precisa — sem commitar algo que não devia.

 - Exemplo 2: Você voltou de um fim de semana longo e não lembra exatamente o que tinha deixado em andamento no projeto. Antes de qualquer coisa, roda o git status para se orientar.

---

## 5. git add
Adiciona arquivos para staging.

 - Exemplo 1: Você corrigiu um bug no arquivo carrinho.js e também fez ajustes visuais no estilo.css. São duas mudanças independentes e você quer criar commits separados para cada uma. Então você adiciona apenas o arquivo do bug primeiro.

 - Exemplo 2: Você criou uma nova feature inteira com vários arquivos novos e modificados. Em vez de adicionar um por um, você adiciona tudo de uma vez para um commit de entrega completa.

---

## 6. git commit
Cria um commit.

 - Exemplo 1: Você terminou de implementar o formulário de cadastro e quer registrar esse progresso com uma mensagem clara, seguindo o padrão Conventional Commits que o time adotou.

 - Exemplo 2: Você percebeu que esqueceu de incluir um arquivo no último commit. Em vez de criar um commit novo só para isso, você adiciona o arquivo e emenda o commit anterior sem criar um novo registro no histórico.

---

## 7. git diff
Mostra diferenças entre arquivos.

 - Exemplo 1: Antes de fazer o commit, você quer revisar linha a linha o que mudou no arquivo de lógica de negócio para ter certeza de que não subiu nenhum console.log de debug acidentalmente.

 - Exemplo 2: A pipeline de CI quebrou na branch da colega. Ela te pede para comparar a branch dela com a main para identificar o que pode ter causado o problema.

---

## 8. git branch
Gerencia branches.

 - Exemplo 1: Você precisa implementar uma funcionalidade nova de exportar relatórios em PDF. Para não trabalhar direto na main e correr o risco de quebrar o que está funcionando, você cria uma branch isolada para isso.

 - Exemplo 2: Ao final de uma sprint, o tech lead pediu para você listar todas as branches que existem no repositório para fazer uma limpeza das que já foram mergeadas. 

---

## 9. git checkout
Troca de branch.

 - Exemplo 1: Você está no meio do desenvolvimento de uma feature, mas seu líder pede urgência em um hotfix de produção. Você precisa trocar para a branch da correção imediatamente.

 - Exemplo 2: Você deletou acidentalmente um arquivo importante e ainda não fez commit. Você usa o git checkout para restaurar o arquivo ao estado do último commit, desfazendo a deleção.

---

## 10. git switch
Alternativa moderna ao checkout.

 - Exemplo 1: O time adotou o comando git switch por ser mais intuitivo e menos ambíguo que o checkout. Você troca para a branch de desenvolvimento após terminar uma revisão de código.

 - Exemplo 2: Você está começando a trabalhar em um novo card do Jira e precisa criar a branch e já entrar nela ao mesmo tempo, usando a flag -c (create).

---

## 11. git merge
Realiza merge entre branches.

 - Exemplo 1: Você terminou de implementar e testar a feature de login social. A branch passou no code review e está aprovada. Agora você integra o trabalho na branch principal do time.

 - Exemplo 2: A main recebeu outros commits enquanto você trabalhava na sua feature. Para evitar conflitos na hora do merge final, você traz as atualizações da main para dentro da sua branch periodicamente.

---

## 12. git pull
Atualiza o repositório local.

 - Exemplo 1: Você chega de manhã, abre o computador e, antes de começar a codar, sincroniza sua branch com o que os colegas subiram durante o dia anterior — para não trabalhar em cima de código desatualizado.

 - Exemplo 2: Você e um colega estavam trabalhando na mesma branch de feature (o que é incomum, mas acontece). Antes de commitar suas mudanças, você faz um pull para integrar o que ele subiu e evitar conflito no push.

---

## 13. git push
Envia commits para o remoto.

 - Exemplo 1: Você trabalhou o dia inteiro localmente e fez vários commits. No final do expediente, você sobe tudo para o GitHub para não perder o trabalho e para que o time possa ver seu progresso.

 - Exemplo 2: Você acabou de criar uma branch local nova e quer fazer o primeiro push. O Git avisa que a branch ainda não existe no remoto e você usa a flag --set-upstream para criá-la lá e associar.

---

## 14. git remote
Gerencia repositórios remotos.

 - Exemplo 1: Você clonou um repositório e quer verificar para qual endereço seus pushes estão sendo enviados — especialmente útil quando você suspeita que está apontando para o fork errado.

 - Exemplo 2: Você está contribuindo com um projeto open source. Clonou o seu fork, mas precisa manter ele sincronizado com o repositório original. Você adiciona o repositório original como um segundo remoto chamado upstream.

---

## 15. git log

 - Exemplo 1: Um bug apareceu em produção e você precisa identificar qual commit introduziu o problema. Você consulta o histórico recente para ver o que foi alterado nos últimos dias.

 - Exemplo 2: O cliente quer saber tudo que foi alterado no módulo de relatórios nos últimos 30 dias para validar as entregas da sprint. Você filtra o log por pasta e período.

---

## 16. git reset
Remove alterações do staging ou commits.

 - Exemplo 1: Você rodou git add . no automático e acabou adicionando ao staging um arquivo .env com credenciais que não deveria ir para o repositório. Você remove esse arquivo do staging sem perder as alterações.

 - Exemplo 2: Você fez dois commits locais que ainda não foram para o remoto, mas percebeu que a abordagem estava errada. Você desfaz os dois últimos commits e volta o código para o staging para reescrever do jeito certo.

---

## 17. git stash
Salva alterações temporariamente.

 - Exemplo 1: Você está no meio de uma feature e recebe uma mensagem de pânico: tem um bug crítico em produção que precisa ser corrigido agora. Você não quer commitar o código inacabado, então guarda tudo temporariamente com o stash.

 - Exemplo 2: Você começou a trabalhar na branch errada sem querer. As mudanças estão na main e deveriam estar numa branch de feature. Você usa o stash para salvar e mover para o lugar certo.

---

## 18. git tag
Cria tags de versão.

 - Exemplo 1: O time acabou de aprovar a versão 2.1.0 do sistema para ir para produção. Você cria uma tag anotada marcando exatamente esse ponto do histórico para referência futura.

 - Exemplo 2: Um cliente reportou um bug que só acontece na versão 1.8.3, que foi lançada há 4 meses. Você usa a tag dessa versão para criar uma branch de investigação a partir daquele ponto exato do código.

---

## 19. git rebase
Reaplica commits de uma branch sobre outra, deixando o histórico mais linear.

 - Exemplo 1: Você trabalhou 3 dias numa feature e a main recebeu vários commits nesse período. Antes de abrir o Pull Request, você faz um rebase para que sua branch apareça como se tivesse sido criada a partir do estado atual da main, facilitando o code review.

 - Exemplo 2: Você fez 8 commits pequenos durante o desenvolvimento — vários com mensagens como "wip", "fix typo", "teste". Antes de fazer o merge, você usa o rebase interativo para combinar e reescrever esses commits em algo mais limpo e significativo.

---

## 20. git cherry-pick
Aplica um commit específico de outra branch na branch atual.

 - Exemplo 1: Um colega corrigiu um bug crítico na branch de feature dele, mas o merge completo dessa branch ainda não foi aprovado. Você precisar da correção agora na main, então aplica apenas aquele commit específico.

 - Exemplo 2: Você está mantendo duas versões do produto em paralelo (v1 e v2). Uma correção de segurança foi feita na v2. Você precisa aplicar exatamente essa correção na v1 também, sem pegar mais nada da v2.
