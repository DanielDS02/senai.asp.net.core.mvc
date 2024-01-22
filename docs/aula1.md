# Aula 01 

- Introdu��o
- Conteudo
	� Configura��o do ambiente de desenvolvimento
	� Conhecendo o Padr�o MVC
	� Entity Framework
	� Caching
	� Roteamento
	� Model binding
	� Valida��o de modelos
	� Inje��o de depend�ncia
	� Utiliza��o do sistema de templates Razor
	� Filtros
	� Autentica��o e autoriza��o
	� Identity Framework
	� Testes
	� Publicando a aplica��o	
- Sobre
- Tutorial

# Materiais 

	-  https://learn.microsoft.com/pt-br/aspnet/core/mvc/overview?view=aspnetcore-8.0
	-  https://learn.microsoft.com/pt-br/aspnet/core/tutorials/first-mvc-app/start-mvc?view=aspnetcore-8.0&tabs=visual-studio

## Exemplo c�digo

```
-  https://learn.microsoft.com/pt-br/aspnet/core/tutorials/first-mvc-app/start-mvc?view=aspnetcore-8.0&tabs=visual-studio
Add-Migration InitialCreate
Update-Database

builder.Services.AddDbContext<MvcMovieContext>(options =>
    options.UseSqlServer(builder.Configuration.GetConnectionString("MvcMovieContext")));

@model MvcMovie.Models.Movie

if (context.Movie.Any())
{
    return;  // DB has been seeded.
}

 <a asp-action="Details" asp-route-id="@item.Id">Details</a>
 @Html.ActionLink("Details", "Details", new { id = item.Id })

```
## Exercicio

- 01 Finalizar tutorial https://learn.microsoft.com/pt-br/aspnet/core/tutorials/first-mvc-app/start-mvc?view=aspnetcore-8.0&tabs=visual-studio

 ## Pr�ximos

- [voltar](../README.md)
- [pr�ximo](aula2.md)