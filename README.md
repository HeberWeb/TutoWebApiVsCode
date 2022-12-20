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

