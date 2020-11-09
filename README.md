# A Multi-Tenant, SaaS, Web Hosting Service with the Orchard Core CMS Framework

## A Web Hosting Service with Orchard Core

# [YouTube Video](https://youtu.be/tFuuVHkhX0c)

[![OrchardSkillsYouTubeThumbNailSaaS](https://user-images.githubusercontent.com/59172485/91002906-07aab980-e58d-11ea-9315-56111a33a0e9.png)](https://youtu.be/tFuuVHkhX0c)

# Introduction

A web hosting service is a type of Internet hosting service that allows individuals and organizations to make their website accessible via the World Wide Web. We will be creating a Multi-Tenant, SaaS, Web Hosting Service with the Orchard Core CMS Framework.




![SaaS-001](https://user-images.githubusercontent.com/59172485/91002775-daf6a200-e58c-11ea-8690-01374ed6bda3.png)

Launch Visual Studio and then "Create a new Project".



![SaaS-002](https://user-images.githubusercontent.com/59172485/91002779-dcc06580-e58c-11ea-8f71-e1170fdc2a9e.png)

Select the "ASP.NET Core Web Application" and then press the "Next" button.



![SaaS-003](https://user-images.githubusercontent.com/59172485/91002781-ddf19280-e58c-11ea-81fa-3603f3d24d6b.png)

Enter in a project name.



![SaaS-004](https://user-images.githubusercontent.com/59172485/91002784-df22bf80-e58c-11ea-8088-1ceccfe37dbc.png)

Select "Empty" and then press the "Create" button.



![SaaS-005](https://user-images.githubusercontent.com/59172485/91002786-e053ec80-e58c-11ea-8dd8-83b468c6b4ed.png)

Right click on the solution, select "Add" and then "New Item...".



![SaaS-006](https://user-images.githubusercontent.com/59172485/91002788-e053ec80-e58c-11ea-8836-9adacb03e5b2.png)

Select "Text File" and safe the file as "NuGet.config".



![SaaS-007](https://user-images.githubusercontent.com/59172485/91002791-e0ec8300-e58c-11ea-8d5c-9d118f2f80e9.png)

Enter the NuGet feed. Note: this is the RC2 configuration.

```
<?xml version="1.0" encoding="utf-8"?>
<configuration>
	<packageSources>
		<clear />
		<add key="NuGet" value="https://api.nuget.org/v3/index.json" />
		<!-- add key="OrchardCorePreview" value="https://nuget.cloudsmith.io/orchardcore/preview/v3/index.json" / -->
	</packageSources>
	<disabledPackageSources />
</configuration>
```

Restart Visual Studio so that the NuGet configuration is used.

 

![SaaS-008](https://user-images.githubusercontent.com/59172485/91002792-e1851980-e58c-11ea-95f8-99a6c9313d48.png)

Open the Web Application project. Add the "CMS Targets". Note this is RC2.



```
  <ItemGroup>
    <PackageReference Include="OrchardCore.Application.Cms.Targets" Version="1.0.0-rc2-13450" />
  </ItemGroup>
```



![SaaS-009](https://user-images.githubusercontent.com/59172485/91002794-e21db000-e58c-11ea-91bb-456bfe15b54e.png)

Modify the "Startup.cs" file. 

```
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Hosting;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.Extensions.Hosting;

namespace OrchardSkills.OrchardCore.OrchardCMS
{
    public class Startup
    {
        // This method gets called by the runtime. Use this method to add services to the container.
        // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
        public void ConfigureServices(IServiceCollection services)
        {
            services.AddOrchardCms();
        }

        // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
        public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
        {
            if (env.IsDevelopment())
            {
                app.UseDeveloperExceptionPage();
            }

            app.UseOrchardCore();

        }
    }
}

```

Run the application by clicking on the green play button.



![SaaS-010](https://user-images.githubusercontent.com/59172485/91002797-e2b64680-e58c-11ea-8c54-cb9fee831633.png)

Enter in the site name and your credentials and then press the "Finish Setup" button.



![SaaS-011](https://user-images.githubusercontent.com/59172485/91002799-e34edd00-e58c-11ea-92d4-7a193b390f72.png)

Click on the "Log in" menu link.

![SaaS-012](https://user-images.githubusercontent.com/59172485/91002800-e34edd00-e58c-11ea-9f1c-d4f782a57a20.png)

Enter your credentials and then press the "Log in" button.



![SaaS-013](https://user-images.githubusercontent.com/59172485/91002801-e3e77380-e58c-11ea-9285-0a5b29e180c8.png)

Select the Dashboard.



![SaaS-014](https://user-images.githubusercontent.com/59172485/91002802-e3e77380-e58c-11ea-841a-a1d1f668feaa.png)

Everything seems to we working.



![SaaS-015](https://user-images.githubusercontent.com/59172485/91002803-e4800a00-e58c-11ea-9235-436b634eb332.png)

Right click on the solution, select "Add" and then "New Project...".

 

![SaaS-016](https://user-images.githubusercontent.com/59172485/91002805-e518a080-e58c-11ea-8b19-e6011dfde323.png)

Click on "Class Library (.NET Core)" and then press the "Next" button.



![SaaS-017](https://user-images.githubusercontent.com/59172485/91002809-e5b13700-e58c-11ea-92c2-66f6fd7f7faf.png)

Enter in a "Project name" and then press the "Create" button.



![SaaS-018](https://user-images.githubusercontent.com/59172485/91002810-e649cd80-e58c-11ea-99cb-278cc06e4e09.png)

Right click on "Class1" and select "Rename...".



![SaaS-019](https://user-images.githubusercontent.com/59172485/91002813-e6e26400-e58c-11ea-9356-b223acd2928d.png)

Click the check boxes and then press the "Apply" button.



![SaaS-020](https://user-images.githubusercontent.com/59172485/91002815-e6e26400-e58c-11ea-9823-cbe4a7c2c2ba.png)

Click the "Apply" button.



![SaaS-021](https://user-images.githubusercontent.com/59172485/91002816-e77afa80-e58c-11ea-9c7f-da269fb9ef0a.png)

Click on the "SaaS" project and modify it to the following: Node this configuration is for RC2.

```
<Project Sdk="Microsoft.NET.Sdk.Razor">

  <ItemGroup>
    <FrameworkReference Include="Microsoft.AspNetCore.App" />
  </ItemGroup>

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <AddRazorSupportForMvc>true</AddRazorSupportForMvc>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="OrchardCore.Admin.Abstractions" Version="1.0.0-rc2-13450" />
    <PackageReference Include="OrchardCore.Email.Abstractions" Version="1.0.0-rc2-13450" />
    <PackageReference Include="OrchardCore.DisplayManagement" Version="1.0.0-rc2-13450" />
    <PackageReference Include="OrchardCore.Data.Abstractions" Version="1.0.0-rc2-13450" />
    <PackageReference Include="OrchardCore.Module.Targets" Version="1.0.0-rc2-13450" />
    <PackageReference Include="OrchardCore.Recipes.Abstractions" Version="1.0.0-rc2-13450" />
    <PackageReference Include="OrchardCore.ResourceManagement" Version="1.0.0-rc2-13450" />
    <PackageReference Include="OrchardCore.Setup.Abstractions" Version="1.0.0-rc2-13450" />
    <PackageReference Include="OrchardCore.Setup" Version="1.0.0-rc2-13450" />
  </ItemGroup>  
  
</Project>

```





![SaaS-023](https://user-images.githubusercontent.com/59172485/91002821-e944be00-e58c-11ea-8f5d-1ac25ff73e88.png)

Right click on the "Saas" project and then "Add New Item..."

![SaaS-024](https://user-images.githubusercontent.com/59172485/91002824-ea75eb00-e58c-11ea-90e3-0c2fcdcabbaf.png)

Add the file "Manifest.cs".



![SaaS-025](https://user-images.githubusercontent.com/59172485/91002825-eba71800-e58c-11ea-955d-160024d2283c.png)

Modify  the manifest to the following:

```
using OrchardCore.Modules.Manifest;

[assembly: Module(
    Name = "SaaS",
    Author = "Orchard Skills",
    Website = "http://OrchardSkills.com",
    Version = "1.0.0-rc2",
    Description = "A SaaS Multi-Tenant website."
)]
```



 

![SaaS-026](https://user-images.githubusercontent.com/59172485/91002828-ec3fae80-e58c-11ea-9b1c-db45e8596445.png)

Right click on the "Recipe" folder and the "Add New Item..."

 

![SaaS-027](https://user-images.githubusercontent.com/59172485/91002829-ecd84500-e58c-11ea-8721-15d5f32656d2.png)

Add the file "sass.recipe.json".



![SaaS-028](https://user-images.githubusercontent.com/59172485/91002831-ed70db80-e58c-11ea-8176-5cb1d4092622.png)

Modify the recipe to as follows:

```
{
  "name": "SaaS",
  "displayName": "SaaS",
  "description": "A SaaS Multi-Tenant website.",
  "author": "Orchard Skills",
  "website": "http://orchardskills.net",
  "version": "1.0.0-rc2",
  "issetuprecipe": true,
  "categories": [ "default" ],
  "tags": [ "developer", "default" ],
  "steps": [
    {
      "name": "feature",
      "disable": [],
      "enable": [
        "OrchardCore.Admin",
        "OrchardCore.Diagnostics",
        "OrchardCore.Email",
        "OrchardCore.HomeRoute",
        "OrchardCore.Localization",
        "OrchardCore.Features",
        "OrchardCore.Navigation",
        "OrchardCore.Recipes",
        "OrchardCore.Resources",
        "OrchardCore.Roles",
        "OrchardCore.Settings",
        "OrchardCore.Tenants",
        "OrchardCore.Themes",
        "SaaS",
        "OrchardCore.Users",

        // Themes
        "TheTheme",
        "TheAdmin",
        "SafeMode"
      ]
    },
    {
      "name": "themes",
      "admin": "TheAdmin",
      "site": "TheTheme"
    },
    {
      "name": "settings",
      "HomeRoute": {
        "Action": "Index",
        "Controller": "Home",
        "Area": "SaaS"
      }
    }
  ]
}

```



![SaaS-029](https://user-images.githubusercontent.com/59172485/91002834-ee097200-e58c-11ea-8b0b-399fab42c480.png)

Add the asset files to the "wwwroot" folder.

![SaaS-030](https://user-images.githubusercontent.com/59172485/91002835-eea20880-e58c-11ea-89f3-b6675dded556.png)

Requirements for the Web Hosting Service.



![SaaS-031](https://user-images.githubusercontent.com/59172485/91002839-ef3a9f00-e58c-11ea-96e3-ee0998d8d186.png)

Right click on the "Controllers" folder and then select "Add New Item...".



![SaaS-032](https://user-images.githubusercontent.com/59172485/91002842-efd33580-e58c-11ea-93a2-246ef90c13e5.png)

Add a "HomeController.cs" file.



![SaaS-033](https://user-images.githubusercontent.com/59172485/91002845-f06bcc00-e58c-11ea-8139-62de6dc1662b.png)

Right click on the "ViewModels" folder and then select "Add New Item...".



![SaaS-034](https://user-images.githubusercontent.com/59172485/91002846-f06bcc00-e58c-11ea-9608-fae9e7e4d21a.png)

Add the file "RegisterUserViewModel.cs".



![SaaS-035](https://user-images.githubusercontent.com/59172485/91002849-f1046280-e58c-11ea-8516-3f266affc346.png)

Right click on the "Home" folder.

![SaaS-036](https://user-images.githubusercontent.com/59172485/91002850-f19cf900-e58c-11ea-9024-b4efe492391e.png)

Select "Add New Items...".



![SaaS-037](https://user-images.githubusercontent.com/59172485/91002851-f19cf900-e58c-11ea-91ec-10e460abffcf.png)

Add the file "index.cshtml".



![SaaS-038](https://user-images.githubusercontent.com/59172485/91002854-f2358f80-e58c-11ea-9ab5-b03e37d382b4.png)

Right click on the "Views" folder and then "Add New Item...".



![SaaS-039](https://user-images.githubusercontent.com/59172485/91002856-f2ce2600-e58c-11ea-9855-355978adf3c0.png)

Add the the file "_ViewImports.cshtml".



![SaaS-040](https://user-images.githubusercontent.com/59172485/91002859-f366bc80-e58c-11ea-8bfb-ed0973292ff6.png)

Add the following to the file "RegisterUserViewModel.cs".

```
namespace SaaS.ViewModels
{
    public class RegisterUserViewModel
    {
        public string SiteName { get; set; }
        public string Handle { get; set; }
        public string Email { get; set; }
        public string RecipeName { get; set; }
        public bool AcceptTerms { get; set; }
    }
}

```



![SaaS-041](https://user-images.githubusercontent.com/59172485/91002861-f3ff5300-e58c-11ea-9823-704a75c7c138.png)

Add the following to the file "_ViewImports.cshtml".

```
@inherits OrchardCore.DisplayManagement.Razor.RazorPage<TModel>
@using SaaS
@using SaaS.ViewModels
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers
@addTagHelper *, OrchardCore.DisplayManagement
@addTagHelper *, OrchardCore.ResourceManagement
```



![SaaS-042](https://user-images.githubusercontent.com/59172485/91002862-f497e980-e58c-11ea-93a8-2bb2eaf4e6d6.png)

Add the following to the "Success.cshtml" file.

```
<div class="jumbotron">
  <h1 class="display-4">@T["Site created successfully."]</h1>
  <p class="lead">@T["An email has been sent to the provided address. Please check your inbox (or spam folder) and follow the instructions."]</p>
  <hr class="my-4">
  <p>@T["This email contains a link to setup your site and the credentials to access the admin."]</p>
</div>
```



![SaaS-043](https://user-images.githubusercontent.com/59172485/91002865-f5308000-e58c-11ea-809b-899673cf1902.png)

Add the following to the "Index.cshtml" file.

```
@model RegisterUserViewModel
<style>
    .hidden {
        display: none;
    }

    .jumbotron {
        background: url("/SaaS/images/OrchardCore-2560x1440.png") no-repeat center center;
        background-size: cover;
        width: 100%;
        padding-top: 20%;
        padding-bottom: 20%;
    }


    input[type=radio]:checked + label > img {
        border: 1px solid #fff;
        box-shadow: 0 0 3px 3px #090;
    }
</style>

<div class="jumbotron">
</div>

<div>
<h2>Web Hosting, A SaaS Muti-Tenant Website</h2>
</div>
<form asp-action="Index" method="post">
    <input asp-for="Handle" type="hidden" />
    <div class="form-group">
        <label asp-for="Email">@T["Email"]</label>
        <small class="text-muted">- Please provide a valid email address to send you a link that will activate the site.</small>
        <input class="form-control" asp-for="Email" type="email" required />
    </div>

    <div class="form-group">
        <label asp-for="SiteName">@T["Site Name"]</label>
        <small class="text-muted">- The name of the site that will be created.</small>
        <input class="form-control" asp-for="SiteName" required />
    </div>

    <div class="form-group">
        <label asp-for="RecipeName">@T["Recipe"]</label>
        <small class="text-muted">- Orchard Core websites can be preconfigured with custom content and templates. The following examples will give you an idea of what you can build with it.</small>
        <div class="row">
            <div class="col-md-4 box">
                <input id="agency" type="radio" name="RecipeName" value="Agency" class="hidden" autocomplete="off" checked>
                <label class="btn btn-light" for="agency">
                    <img src="/SaaS/themes/agency.jpg" title="Agency" class="img-thumbnail img-check">
                </label>
            </div>
            <div class="col-md-4 box">
                <input id="blog" type="radio" name="RecipeName" value="Blog" class="hidden" autocomplete="off">
                <label class="btn btn-light" for="blog">
                    <img src="/SaaS/themes/blog.jpg" title="Blog" class="img-thumbnail img-check">
                </label>
            </div>
            <div class="col-md-4 box">
                <input id="comingsoon" type="radio" name="RecipeName" value="ComingSoon" class="hidden" autocomplete="off">
                <label class="btn btn-light" for="comingsoon">
                    <img src="/SaaS/themes/comingsoon.jpg" title="Coming soon" class="img-thumbnail img-check">
                </label>
            </div>
            <div class="clearfix"></div>
        </div>
    </div>

    <div class="form-group form-check">
        <input type="checkbox" class=" form-check-input" asp-for="AcceptTerms" required />
        <label class="form-check-label" asp-for="AcceptTerms">@T["I agree with the"] <a href="/terms">@T["Terms and Conditions"]</a></label>
        <small class="text-muted">We use the email address to create a demo site. Here is our <a href="/privacy">Privacy Policy</a>.</small>
    </div>
    <div class="form-group">
        <button type="submit" class="btn btn-primary">@T["Submit"]</button>
    </div>

    @Html.ValidationSummary(false, "", new { @class = "alert-danger" })
</form>
<script at="Foot">$("#navbar").remove();</script>
```



![SaaS-044](https://user-images.githubusercontent.com/59172485/91002866-f5c91680-e58c-11ea-973b-3cf14fc63802.png)

Add the following to the "HomeController.cs" file.

```
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text.RegularExpressions;
using System.Threading.Tasks;
using Microsoft.AspNetCore.DataProtection;
using Microsoft.AspNetCore.Identity;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Extensions.Localization;
using Microsoft.Extensions.Logging;
using Microsoft.Extensions.Options;
using OrchardCore.Email;
using OrchardCore.Environment.Shell;
using OrchardCore.Environment.Shell.Models;
using OrchardCore.Modules;
using OrchardCore.Setup.Services;
using SaaS.ViewModels;

namespace SaaS.Controllers
{
    public class HomeController : Controller
    {
        private const string defaultAdminName = "admin";
        private const string dataProtectionPurpose = "Password";
        private const string emailSubject = "SaaS Registration";
        private const bool emailToBcc = true;

        private readonly IShellSettingsManager _shellSettingsManager;
        private readonly IShellHost _shellHost;
        private readonly ISmtpService _smtpService;
        private readonly ISetupService _setupService;
        private readonly IOptions<SmtpSettings> _smtpSettingsOptions;
        private readonly IClock _clock;
        private readonly IDataProtectionProvider _dataProtectionProvider;
        private readonly ILogger<HomeController> _logger;

        public HomeController(
            IShellSettingsManager shellSettingsManager,
            IShellHost shellHost,
            ISmtpService smtpService,
            ISetupService setupService,
            IOptions<SmtpSettings> smtpSettingsOptions,
            IClock clock,
            IDataProtectionProvider dataProtectionProvider,
            ILogger<HomeController> logger,
            IStringLocalizer<HomeController> stringLocalizer)
        {
            _shellSettingsManager = shellSettingsManager;
            _shellHost = shellHost;
            _smtpService = smtpService;
            _setupService = setupService;
            _smtpSettingsOptions = smtpSettingsOptions;
            _clock = clock;
            _dataProtectionProvider = dataProtectionProvider;
            _logger = logger;

            S = stringLocalizer;
        }

        public IStringLocalizer S { get; set; }

        public IActionResult Index(RegisterUserViewModel model)
        {
            // Generate random site prefix
            model.Handle = GenerateRandomName();

            return View(model);
        }

        [HttpPost]
        [ActionName(nameof(Index))]
        public async Task<IActionResult> IndexPost(RegisterUserViewModel model)
        {
            if (!model.AcceptTerms)
            {
                ModelState.AddModelError(nameof(RegisterUserViewModel.AcceptTerms), S["Please, accept the terms and conditions."]);
            }

            if (!string.IsNullOrEmpty(model.Handle) && !Regex.IsMatch(model.Handle, @"^\w+$"))
            {
                ModelState.AddModelError(nameof(RegisterUserViewModel.Handle), S["Invalid tenant name. Must contain characters only and no spaces."]);
            }

            if (ModelState.IsValid)
            {
                if (_shellHost.TryGetSettings(model.Handle, out var shellSettings))
                {
                    ModelState.AddModelError(nameof(RegisterUserViewModel.Handle), S["This site name already exists."]);
                }
                else
                {
                    shellSettings = new ShellSettings
                    {
                        Name = model.Handle,
                        RequestUrlPrefix = model.Handle.ToLower(),
                        RequestUrlHost = null,
                        State = TenantState.Uninitialized
                    };
                    shellSettings["RecipeName"] = model.RecipeName;
                    shellSettings["DatabaseProvider"] = "Sqlite";

                    await _shellSettingsManager.SaveSettingsAsync(shellSettings);
                    var shellContext = await _shellHost.GetOrCreateShellContextAsync(shellSettings);

                    var recipes = await _setupService.GetSetupRecipesAsync();
                    var recipe = recipes.FirstOrDefault(x => x.Name == model.RecipeName);

                    if (recipe == null)
                    {
                        ModelState.AddModelError(nameof(RegisterUserViewModel.RecipeName), S["Invalid recipe name."]);
                    }

                    var adminName = defaultAdminName;
                    var adminPassword = GenerateRandomPassword();
                    var siteName = model.SiteName;
                    var siteUrl = GetTenantUrl(shellSettings);

                    var dataProtector = _dataProtectionProvider.CreateProtector(dataProtectionPurpose).ToTimeLimitedDataProtector();
                    var encryptedPassword = dataProtector.Protect(adminPassword, _clock.UtcNow.Add(new TimeSpan(24, 0, 0)));
                    var confirmationLink = Url.Action(nameof(Confirm), "Home", new { email = model.Email, handle = model.Handle, siteName = model.SiteName, ep = encryptedPassword }, Request.Scheme);

                    var message = new MailMessage();
                    if (emailToBcc)
                    {
                        message.Bcc = _smtpSettingsOptions.Value.DefaultSender;
                    }
                    message.To = model.Email;
                    message.IsBodyHtml = true;
                    message.Subject = emailSubject;
                    message.Body = S[$"Hello,<br><br>Your demo site '{siteName}' has been created.<br><br>1) Setup your site by opening <a href=\"{confirmationLink}\">this link</a>.<br><br>2) Log into the <a href=\"{siteUrl}/admin\">admin</a> with these credentials:<br>Username: {adminName}<br>Password: {adminPassword}"];

                    await _smtpService.SendAsync(message);

                    return RedirectToAction(nameof(Success));
                }
            }

            return View(nameof(Index), model);
        }

        public IActionResult Success()
        {
            return View();
        }

        public async Task<IActionResult> Confirm(string email, string handle, string siteName, string ep)
        {
            if (!_shellHost.TryGetSettings(handle, out var shellSettings))
            {
                return NotFound();
            }

            if (shellSettings.State == TenantState.Uninitialized)
            {
                var recipes = await _setupService.GetSetupRecipesAsync();
                var recipe = recipes.FirstOrDefault(x => x.Name == shellSettings["RecipeName"]);

                if (recipe == null)
                {
                    return NotFound();
                }

                var password = Decrypt(ep);

                var setupContext = new SetupContext
                {
                    ShellSettings = shellSettings,
                    SiteName = siteName,
                    EnabledFeatures = null,
                    AdminUsername = defaultAdminName,
                    AdminEmail = email,
                    AdminPassword = password,
                    Errors = new Dictionary<string, string>(),
                    Recipe = recipe,
                    SiteTimeZone = _clock.GetSystemTimeZone().TimeZoneId,
                    DatabaseProvider = shellSettings["DatabaseProvider"],
                    //DatabaseConnectionString = shellSettings["ConnectionString"],
                    //DatabaseTablePrefix = shellSettings["TablePrefix"]
                };

                var executionId = await _setupService.SetupAsync(setupContext);

                // Check if a component in the Setup failed
                if (setupContext.Errors.Any())
                {
                    foreach (var error in setupContext.Errors)
                    {
                        ModelState.AddModelError(error.Key, error.Value);
                    }

                    return Redirect("Error");
                }
            }

            return Redirect("~/" + handle);
        }

        private string Decrypt(string encryptedString)
        {
            try
            {
                var dataProtector = _dataProtectionProvider.CreateProtector(dataProtectionPurpose).ToTimeLimitedDataProtector();

                return dataProtector.Unprotect(encryptedString, out var expiration);
            }
            catch (Exception ex)
            {
                _logger.LogError(ex, "Error decrypting the string");
            }

            return null;
        }

        public string GetTenantUrl(ShellSettings shellSettings)
        {
            var requestHostInfo = Request.Host;

            var tenantUrlHost = shellSettings.RequestUrlHost?.Split(new[] { "," }, StringSplitOptions.RemoveEmptyEntries).First() ?? requestHostInfo.Host;
            if (requestHostInfo.Port.HasValue)
            {
                tenantUrlHost += ":" + requestHostInfo.Port;
            }

            var result = $"{Request.Scheme}://{tenantUrlHost}";

            if (!string.IsNullOrEmpty(shellSettings.RequestUrlPrefix))
            {
                result += "/" + shellSettings.RequestUrlPrefix;
            }

            return result;
        }

        public string GenerateRandomName()
        {
            return Path.GetRandomFileName().Replace(".", "").Substring(0, 8);
        }

        public string GenerateRandomPassword(PasswordOptions opts = null)
        {
            if (opts == null) opts = new PasswordOptions()
            {
                RequiredLength = 8,
                RequiredUniqueChars = 4,
                RequireDigit = true,
                RequireLowercase = true,
                RequireNonAlphanumeric = true,
                RequireUppercase = true
            };

            string[] randomChars = new[] {
            "ABCDEFGHJKLMNOPQRSTUVWXYZ",    // uppercase 
            "abcdefghijkmnopqrstuvwxyz",    // lowercase
            "0123456789",                   // digits
            "!@$?_-"                        // non-alphanumeric
            };

            Random rand = new Random(System.Environment.TickCount);
            List<char> chars = new List<char>();

            if (opts.RequireUppercase)
            {
                chars.Insert(rand.Next(0, chars.Count), randomChars[0][rand.Next(0, randomChars[0].Length)]);
            }

            if (opts.RequireLowercase)
            {
                chars.Insert(rand.Next(0, chars.Count), randomChars[1][rand.Next(0, randomChars[1].Length)]);
            }

            if (opts.RequireDigit)
            {
                chars.Insert(rand.Next(0, chars.Count), randomChars[2][rand.Next(0, randomChars[2].Length)]);
            }

            if (opts.RequireNonAlphanumeric)
            {
                chars.Insert(rand.Next(0, chars.Count), randomChars[3][rand.Next(0, randomChars[3].Length)]);
            }

            for (int i = chars.Count; i < opts.RequiredLength || chars.Distinct().Count() < opts.RequiredUniqueChars; i++)
            {
                string rcs = randomChars[rand.Next(0, randomChars.Length)];
                chars.Insert(rand.Next(0, chars.Count), rcs[rand.Next(0, rcs.Length)]);
            }

            return new string(chars.ToArray());
        }
    }
}

```



![SaaS-045](https://user-images.githubusercontent.com/59172485/91002867-f661ad00-e58c-11ea-899e-d212f233acde.png)

Click on the green play button to run the application.



![SaaS-046](https://user-images.githubusercontent.com/59172485/91002870-f792da00-e58c-11ea-8565-677ed83353c9.png)

Enter the the site name, select the Saas recipe, enter your credentials and then press the "Finish Setup" button.



![SaaS-047](https://user-images.githubusercontent.com/59172485/91002871-f792da00-e58c-11ea-928e-3f65c89c6e26.png)

Login to the Admin Dashboard.



![SaaS-048](https://user-images.githubusercontent.com/59172485/91002873-f8c40700-e58c-11ea-8f0f-305632d32bd4.png)

![SaaS-049](https://user-images.githubusercontent.com/59172485/91002874-f8c40700-e58c-11ea-8a1a-45245af837cc.png)

Select Configuration and then Smtp. Enter in the setup configuration.



![SaaS-050](https://user-images.githubusercontent.com/59172485/91002875-f95c9d80-e58c-11ea-957b-7507a8137ebf.png)

Press the "Test settings" button.



![SaaS-051](https://user-images.githubusercontent.com/59172485/91002877-f9f53400-e58c-11ea-92f4-4cfe91ec5741.png)

Send a test message.



![SaaS-052](https://user-images.githubusercontent.com/59172485/91002878-f9f53400-e58c-11ea-83cf-b9290c3dd65c.png)

Message sent successfully.



![SaaS-053](https://user-images.githubusercontent.com/59172485/91002881-fa8dca80-e58c-11ea-9ae3-6c0500de3db5.png)

Go back to the website and signup for a hosting site.



![SaaS-054](https://user-images.githubusercontent.com/59172485/91002883-fb266100-e58c-11ea-9769-c6bebdc6ba23.png)

Congratulations! Site created successfully.



![SaaS-055](https://user-images.githubusercontent.com/59172485/91002884-fbbef780-e58c-11ea-92f8-3bfc9455298c.png)

Go to your email and click on the "Setup your by opening this link".



![SaaS-056](https://user-images.githubusercontent.com/59172485/91002887-fc578e00-e58c-11ea-96aa-b7e2c7a2d272.png)

Your site is now activated.



# Conclusion

With the powerful features of the Orchard Core framework, we were able to create a Multi-Tenant, SaaS, Web Hosting Service with just a single Web Application.

# GitHub

The complete source code is located [here](https://github.com/OrchardSkills/OrchardSkills.OrchardCore.SaaS).


