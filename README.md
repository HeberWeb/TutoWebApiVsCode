# Tutorial em:
https://learn.microsoft.com/pt-br/aspnet/core/tutorials/first-web-api?view=aspnetcore-6.0&tabs=visual-studio-code

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

