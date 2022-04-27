# GIT & GIT HUB

### Configurando a chave SSH para primeiro acesso.
Dentro do **GitBash** use o seguinte comando:
**_ssh-keygen -t ec25519 -C < e-mail_do_usuário >**

- O Git vai gerar uma chave pública e uma chave privada dentro de um diretório
criado por ele mesmo chamado **_".ssh"._**
**_OBS:_** _Precisa usar a senha de acesso a conta do GitHub._

- Feito isto pasta entrar na pasta **_.ssh"_** e copiar a chave pública. Para visualizar
a chave dentro do **GitBash** use o seguinte comando:
**_cat id_25519.pub_** (id_25519.pub é a chave pública gerada dentro do diretório)

- Copie e cole no site do Git Hub clicando na **_foto do seu perfil >> settings >> SSH and GPG keys._**

- Agora obrigatoriamente precisamos iniciar o **ssh agent.** Para isso digite o seguinte
código:
**_eval $(ssh-agent -s)_** O GitBash vai mostrar o Agent pid que um número do projeto como processo. (Número do processo)

- Agora precisamos adicionar a nossa chave **PRIVADA** para sincronizar com a chave
**PÚBLICA** que foi adicionada no site. Use o seguinte código:
**_ssh-add id_ed25519_** (Mais uma vez terá que usar a senha de usuário do GitHub)

----

### Entendendo os comando básicos do GIT

**GIT INIT** => Ao entrar em um diretório no GIT BASH e digitar _GIT INIT_ automaticamente o diretório passa a ser um repositório local.

----

**GIT CONFIG**=> Ao usar o repositório criado pela primeira vez, devemos adicionar algumas informações como o _AUTOR_ do projeto. Para isso vamos usar as seguintes linhas de comando:

**_ GIT CONFIG --GLOBAL USER.EMAIL "e-mail do autor"_**

**_ GIT CONFIG --GLOBAL USER.NAME "nome do autor"_**

-----

**GIT CONFIG --LIST** => Mostra a lista de configuração do seu GIT. Para apagar o nome do Autor e o e-mail que já estão configurados nesta lista de configurações, basta digitar o seguinte código:

- **_GIT CONFIG --GLOBAL UNSET "e-mail do autor"_**
- **_GIT CONFIG --GLOBAL UNSET "nome do autor"_**

-----------

**GIT ADD** => Logo após criar o arquivo do projeto, este arquivo é considerado **não rastreavel**, pois ainda não foi adicionado no _STAGE_ (onde vai ser preparado/editado/modificado). Para isso usamos o comando _GIT ADD "nome do arquivo"_ para adicionar no _STAGE_.

**Também podem ser usados:**

- **GIT ADD *** => Adiciona todos as modificações para a _STAGE AREA_.
- **GIT ADD .** => Adiciona todos as modificações do repositório local para a _STAGE AREA_.

------------------

**GIT COMMIT** => Este comando CONFIRMA a modificação dos arquivos no repositório, e também adiciona um breve comentário sobre a modificação do arquivo. Neste momento os arquivos modificados saem da _STAGE AREA_ para o repositório com status de _MODIFIED_.

**_ GIT COMMIT -M "Comentário sobre a modificação"_**

-------

**GIT STATUS** => Este comando mostra se existe algum arquivo na _STAGE AREA_ pronto para ser confirmado (_COMIITED_). Quando aparecem arquivos _UNTRACKED_ quer dizer que ainda não foram adicionados na _STAGE AREA_ em nenhum momento.

----------

### Como clonar um repositório já existente.

Para copiar um repositório local basta usar o seguinte comando:

- **_GIT CLONE /caminho/do/repositório_**

- **_GIT CLONE  https://github.com/victorpessanha/DIO-everis-New-Talents-java.git_**

  ou

- **_GIT CLONE git@github.com:victorpessanha/victorpessanha.github.io.git_** (validando com ssh)

Para copiar um repositório remoto basta usar o seguinte comando:

- **_GIT CLONE USUARIO@SERVIDOR:/caminho/do/repositório_**

-----

### Interagindo com o GIT HUB

O GIT HUB é um repositório remoto e podemos interagir com ele usando o GIT.

**GIT REMOTE ADD ORIGIN** => Adiciona um link para o repositório remoto criado no GIT HUB.

- Exemplo: **_GIT REMOTE ADD ORIGIN https://github.com/victorpessanha/DIO-everis-New-Talents-java.git_**

**GIT REMOTE -V** => Verifica os links para empurrar os dados com o comando _PUSH_.

**GIT PUSH ORIGIN MASTER** => Empurra o conteúdo para o repositório que esta setado no alias _ORIGIN_.

