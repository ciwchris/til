In ASP.NET Core dependency injection is not limited to constructors. One convenient method is in
razor views using the `@inject` directive. Therefore, if appSettings need to be exposed in the view
one approach this can be accomplished is to setup Startup.cs like:

```c#
public static IConfiguration Configuration { get; set; }

public Startup(IHostingEnvironment env)
{
    var builder = new ConfigurationBuilder()
        .AddJsonFile("appsettings.json")
    Configuration = builder.Build();
}

public void Configure(IApplicationEnvironment appEnv)
{
      appEnv.SetData("MyValue", Configuration["MyValue"]);
```

And then IApplicationEnvironment can be injected into the view and used:

```c#
@using Microsoft.Extensions.PlatformAbstractions

@inject IApplicationEnvironment appEnv

@appEnv.GetData("MyValue")
@appEnv.ApplicationVersion
```

Thanks for the tips [K. Scott
Allen](http://odetocode.com/blogs/scott/archive/2016/02/18/avoiding-the-service-locator-pattern-in-asp-net-core.aspx)
