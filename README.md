# COMO USAR O GIT

Essa documentaçõ de como usar o git é um resumo dos comandos essenciais do git. Na primeria parte, vemos como setar um gerenciador de chaves ssh no git/github.
Na segunda parte é os comandos de usabilidade do git.

Sobre o gerenciador de chaves ssh: ele é muito útil para não ficarmos precisando de colocar a senha do github tova vez que formos usar o "git push" ou "git pull".

Sobre os comandos git: Usamos eles para controlar as versões que nossos programa vai receber antes de colocarmos no ar (main), essa usabilidade não é uma regra (visto que muitas pessoas usam o git/github como forma de backup) mas é uma boa prática. Dito isso, com uma ideia de projeto em mente, você cria seu repositório no github. Puxa ele para sua máquina com o **git clone**. Faz as mudanças/incrementos, então depois adiciona para faze de *stage* as suas mudanças com **git add arquivo**. Após isso você verciona seu código (empacota), mas vai ser empacotado tudo o que está na *stage* com **git commit -m "menssagem"**. Após isso, a versão do seu código está pronta para subir pro github com **git push origin main** ou **git push origin master** ou **git push origin nomeDaBranch**.

Sobre a usabilidade das branchs: Todo repositório tem uma branch principal, geralmente nomeados de *main* ou *master*, se você não tiver mudado para algum outro nome mais semântico em relação ao projeto. A boa prática seria, nunca fazer um **git push origin main** ou **git push origin branchPrincipal**. Então para contornar isso, você cria uma nova branch, que seria uma ramificação ou um clone do projeto principal, fazia as alterações la nessa nova branch, subia o código pra essa branch com **git push origin novaBranch**, testava la no github se tuda estava certo (geralmente tem um olheiro pra isso), e se tudo estiver dentro do planejato, fazia pull request no proprio github, para unir a novaBranch com a main. Dentro da branch main, usa-se o comando de unir a sua branch editada com a main **git merge novaBranch**.

## GERÊNCIADOR DE CHAVES SSH

CRIAR SHAVE SSH

> ssh-keygen -t ed25519 -C "email@mail.com"

- Ir até o diretório criado: .../.ssh

PEGAR CHAVE PUBLICA E COLAR NO GITHUB

> cat id_ed25519.pub

- Dentro do github: em configurações > gerenciar chaves > "criar novo perfil para essa nova chave".

 EVAL, GERENCIADOR AUTOMÁTICO DE CHAVES SSH

> eval $(ssh-agent -s)

> ssh-add id_ed25519

## COMANDOS GIT

### PRINCIPAIS

git clone

- puxa/clona um repositório para sua máquina

> git clone https://github.com/Pedrobolfute/git

git pull

- Puxar atualizações do repositórios

> git pull

git push

- Envio mudanças para o repositório

> git push origin main

git add

- adiciona mudanças para stage

> git add .

git commit
  
- verciona/empacota o stage

> git commit -m "menssagem"

### BRANCHS

git checkout

- Muda, lista e cria as branchs...

> git checkout -b criarNovaBranch

> git checkout branchAntiga

git merge

- Ajunta as mudanças de duas branchs

> git merge 

### VISUALIZAÇÃO E CONTROLE

git branch

- Mostra as branchs do projeto

> git branch

git status

- Mostra o status do git

> git status

git log

- Mostra seu footprint do projeto

> git log

git reflog

- Mostra o git log de outra forma...

> git reflog