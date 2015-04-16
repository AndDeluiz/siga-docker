# sigaDocker

O aplicativo sigaDocker foi criado para ajudar a equipe integrante do time do [Projeto Siga](https://github.com/projeto-siga) na utilização da plataforma [Docker](http://docker.io).

Neste momento a aplicação é voltada exclusivamente para uso com o ambiente DEV do Siga DOC, possibilitando controle das imagens e dos contêineres criados no ambiente. A aplicação pode ser utilizada em outros ambientes, mas seu funcionamento não foi testado com tal propósito.

## Utilização

```
Uso: sigaDocker COMANDO [ARGS]

Provê funções básicas de uso para imagens Docker utilizadas pela aplicação SIGA.

Comandos:

   build <buildType> [buildDirectory]
        Cria uma imagem a partir de um Dockerfile.
        Argumentos:
           buildType - especifica que tipo de imagem sera criada.
              Tipo de imagem:
                 app - Servidor de aplicação JBoss standalone
                 web - Servidor Apache HTTPD
           buildDirectory - diretório onde está localizado o arquivo Dockerfile.

   help
        Exibe esta mensagem de utilização do aplicativo.

   logs
        Mostra os logs de um contêiner (stdout).

   restart
        Reinicia o ambiente Siga Docker, parando e iniciando automaticamente os
        contêineres de aplicação e servidor web na ordem correta.

   rm
        Remove contêineres do sistema. Caso o contêiner esteja em execução,
        força a parada do contêiner antes de removê-lo.

   rmi <ImageType> [BuildNumber]
        Remove imagem do tipo indicado por ImageType. Caso não seja informado o
        BuildNumber, serão mostradas todas as imagens disponíveis para escolha.
        Argumentos:
           ImageType - especifica que tipo de imagem sera executada.
              Tipo de imagem:
                 app - Servidor de aplicação JBoss standalone
                 web - Servidor Apache HTTPD
           BuildNumber - número de BUILD da imagem que será removida.

   run <ImageType> [BuildNumber]
        Executa imagem do tipo indicado por ImageType. Caso não seja informado o
        BuildNumber, será executada a imagem mais recente.
        Argumentos:
           ImageType - especifica que tipo de imagem sera executada.
              Tipo de imagem:
                 app - Servidor de aplicação JBoss standalone
                 web - Servidor Apache HTTPD
           BuildNumber - número de BUILD da imagem que será executada.
              Default: latest

   start
        Inicia o ambiente Siga Docker, iniciando automaticamente os contêineres
        de aplicação e servidor web na ordem correta.
        Se existir no sistema algum contêiner registrado para qualquer um dos
        ambientes válidos e, estando este contêiner parado, ele será iniciado.
        Caso contrário, um novo contêiner será criado.

   stop
        Para o ambiente Siga Docker, terminando automaticamente os contêineres
        de aplicação e servidor web na ordem correta.

   version
        Exibe somente a versão deste aplicativo.
```
