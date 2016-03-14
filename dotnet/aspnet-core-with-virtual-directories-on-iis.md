When using virtual directories with ASP.NET Core IIS will not properly render the application, using
rc1, as stated in the github issue: IIS virtual directories. Many suggestions are mentioned in the
issue, but [one comment](https://github.com/aspnet/IISIntegration/issues/14#issuecomment-190574696)
is fairly comprehensive containing the steps to take to resolve the issue.

The critical portion is to set the virtual directory the application will reside in and use that
location when the application is configured. A standard `Configure` looks like:

```csharp
public void Configure(IApplicationBuilder app)
{
    app.UseIISPlatformHandler();
    ...
}
```

The solution is to place the `Configuration` in another method and then in `Configuration` send the
virtual directory the application will reside in IIS.

```csharp
public void Configure(IApplicationBuilder app)
{
    // Use the virtual directory name in IIS
    app.Map("/MyWebSite" , (virtualApp) => ConfigureWithVirtualDirectory(virtualApp));
}

private void ConfigureWithVirtualDirectory(IApplicationBuilder app)
{
    app.UseIISPlatformHandler();
    ...
}
```

This issue should hopefully be resolved in the next release candidate.
