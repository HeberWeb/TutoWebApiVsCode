# Tutorial em:
https://learn.microsoft.com/pt-br/aspnet/core/tutorials/first-web-api?view=aspnetcore-6.0&tabs=visual-studio-code

# Dificuldades para execução da api.
Ao pressionar Ctrl+F5, o VS Code mostra a opção para selecionar o .Net 6 no prompt, porém para criar os arquivos lanch.json e tasks.json, só foi possível ao aparecer a janela no canto inferior direito e clicando a opção sim. Isso no Windows

Diferente do Visual Studio, no VS Code é necessário incluir na url do browser /swagger para exibir a doc corretamente

# Problemas de versão que podem surgir na instalação de pacotes.
Os comandos abaixo podem ser incompatíveis com a versão atual do .Net core.

```
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet tool install -g dotnet-aspnet-codegenerator
dotnet-aspnet-codegenerator controller -name TodoItemsController -async -api -m TodoItem -dc TodoContext -outDir Controllers
```
OS comandos sempre baixam e instam a versão mais recente, caso isso aconteça, inclua no final de cada comando a versão compatível(Ex: --verion {version})
Para resgatar a versão mais adequada acesse o site https://www.nuget.org/packages e busque pelo package desejado.

**Obs:
No meu caso foi necessário add --version 6.0.11 na instalação onde houve erro de incompatibilidade com o .Net 6.**

# Notas
1. Neste tutorial não foi instalada a ferramenta httprepl, os testes foram feitos pelo swagger ou postman.
2. Também não foi feito a alteração para usar o DTO(Conceito para esconde algumas propriedades do retorno ou post).


# Executar o mesmo Projeto no Linux(Ubuntu) Com Wsl, exatamente como foi criado no windows.

# Erros ao clonar e abrir o projeto no Linux
1. Execute qualquer comando no git, e será exibido a configuração para executar e corrigir.
2. Nas notificações do VS Code Clique em Restore na notificação de resolução de dependencias da Extenção C#
3. Terá outra notificação com a opção reload e clique na mesma.

**Obs: As Referencias do EntityFrameworkCore serão corrigidas**

# Instalação dos sdks caso ainda não tenha sido instalado no ubuntu
1. Acesse https://learn.microsoft.com/pt-br/dotnet/core/install/linux-ubuntu.
2. Verifique a versão no ubuntu:
```
lsb_release -a
```
3. Identifique na doc qual versão e execute os comandos descritos para instalação dos sdks dotnet na versão desejada.
4. Digite os comandos para executar a api.
```
dotnet build
```
```
dotnet run
```

5. Será exibido a url configurada no arquivo /Properties/launchSettings.json onde é definido o profile do projeto.

**Obs: Pelo ubuntu a execução não obtem sucesso ao pressionar Ctrl+F5**
