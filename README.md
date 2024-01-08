# aspnet-templates

Basic ASP.NET project templates

## Render Mode

### Auto

```

builder.Services.AddRazorComponents()
    .AddInteractiveServerComponents()
    .AddInteractiveWebAssemblyComponents();
...
app.MapRazorComponents<App>()
    .AddInteractiveServerRenderMode()
    .AddInteractiveWebAssemblyRenderMode()
    .AddAdditionalAssemblies(typeof(Counter).Assembly);

```

### Server

```
builder.Services.AddRazorComponents()
    .AddInteractiveServerComponents();
...
app.MapRazorComponents<App>()
    .AddInteractiveServerRenderMode();
```


### Wasm

```
builder.Services.AddRazorComponents()
    .AddInteractiveWebAssemblyComponents();
...
app.MapRazorComponents<App>()
    .AddInteractiveWebAssemblyRenderMode()
    .AddAdditionalAssemblies(typeof(Counter).Assembly);
```


## Global vs PerPage/Component

## Global

### App.razor Auto

```
<html>
...
<head>
    ...
    <HeadOutlet @rendermode="@InteractiveAuto" />
</head>

<body>
    <Routes @rendermode="@InteractiveAuto" />
    <script src="_framework/blazor.web.js"></script>
</body>

</html>

```

### App.razor Server

```
<html>
...
<head>
    ...
    <HeadOutlet @rendermode="@InteractiveServer" />
</head>

<body>
    <Routes @rendermode="@InteractiveServer" />
    <script src="_framework/blazor.web.js"></script>
</body>

</html>

```

### App.razor Wasm

```
<html>
...
<head>
    ...
    <HeadOutlet @rendermode="@InteractiveWebAssembly" />
</head>

<body>
    <Routes @rendermode="@InteractiveWebAssembly" />
    <script src="_framework/blazor.web.js"></script>
</body>

</html>

```

## Per Page/Component

### App.razor Auto, Server, Wasm

```
<html>
...
<head>
    ...
    <HeadOutlet />
</head>

<body>
    <Routes />
    <script src="_framework/blazor.web.js"></script>
</body>

</html>

```

### Counter.razor - Auto Client

```
@page "/counter"
@rendermode InteractiveAuto

<PageTitle>Counter</PageTitle>

```

### Counter.razor - Wasm Client

```
@page "/counter"
@rendermode InteractiveWebAssembly

<PageTitle>Counter</PageTitle>

```


