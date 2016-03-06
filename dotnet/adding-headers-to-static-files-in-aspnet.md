When serving static files in ASP.Net Core headers can be added to the served files by specifying
them in the static file middleware in the startup of the application. Therefore to prevent static files
from being cached headers can be added like:

```c#
// Add static files to the request pipeline.
app.UseStaticFiles(new StaticFileOptions()
{
    OnPrepareResponse = (context) =>
    {
        // Disable caching of all static files.
        context.Context.Response.Headers["Cache-Control"] = "no-cache, no-store";
        context.Context.Response.Headers["Pragma"] = "no-cache";
        context.Context.Response.Headers["Expires"] = "-1";
    }
});
```

(Stack Overflow Reference](http://stackoverflow.com/a/34725559/16973)
