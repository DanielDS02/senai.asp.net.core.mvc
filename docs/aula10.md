# Aula 10

- Role
- Redirecionar p�ginas
- Layout
- partial view


# Materiais 


## Exemplo c�digo

```
// N�o usar layout 
@{
    Layout = null;
}

```

```
// Usar layout diferente
@{
    Layout = "_LayoutAdmin";
}

```

```
// Filtro com perfil no controller
[Authorize(Roles = "manager")]

```

```
// Configura��o para redirecionar quando n�o tem permiss�o
builder.Services.AddAuthentication(options =>
    ...

}).AddCookie(options =>
{
    ...
    options.AccessDeniedPath = "/Login/Denied";
});

```

```
//Exemplo de verificar perfil no inicio da autentica��o
[HttpGet]       
        public IActionResult Index()
        {

            // If user is already authenticated, redirect to another page
            if (User.Identity.IsAuthenticated)
            {
                var role = User.Claims.FirstOrDefault(c => c.Type == ClaimTypes.Role);

                if (role.Value == "simples")
                {
                    return RedirectToAction("Index", "Pizzas");
                }
                if (role.Value == "manager")
                {
                    return RedirectToAction("Index", "Admin");
                }
            }

            return View();
        }
```
## Exercicio

- 01 Criar no pro

 ## Pr�ximos

- [pr�ximo](aula2.md)