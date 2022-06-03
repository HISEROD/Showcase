> ### **NOTICE:** This README is still in progress.

[this comment is to check for 80 character line lengths]:\\\\\\\\\\\\\\\\\\\\\\\

# Introduction
Hi! My name is Immanuel Hise and I am a graduate of The Tech Academy's **C# and
.NET Framework Boot Camp.** During this boot camp I learned a plethora of
skills which are documented in this README. Succeeding this paragraph is a
section detailing a live project that I worked on and an assortment of solutions
that I developed during the project.

## Live Project
I participated in a two-week live project during my Tech Academy Boot Camp
during which I worked with other students to develop an ASP.NET MVC web
application.

### Technologies
While working on the project, I utilized many popular languages, libraries, and
frameworks listed below.

#### Languages
* [C#](#c)
* [HTML (+C#/Razor syntax)](#razor-syntax)
* [CSS](#css)
* [Javascript](#javascript)

#### Libraries
* [Bootstrap](#bootstrap)
* [JQuery](#jquery)

#### Frameworks
* [ASP.NET MVC](#aspnet-mvc-controller)
* [Entity Framework](#c)

<hr>

### Examples
Below are some blocks of code that I wrote while working on the project. I've
inserted ellipses (`...`) wherever the snippets have been abbreviated.

###### C#
```cs
using System;
using System.Collections.Generic;
using System.ComponentModel.DataAnnotations.Schema;
using System.Linq;
using System.Web;

namespace TheatreCMS3.Areas.Prod.Models
{
    public class ProductionMember
    {
        public int ProductionMemberId { get; set; }
        public string Name { get; set; }
        public int? YearJoined { get; set; }
        public Position MainRole { get; set; }
        public string Bio { get; set; }
        public byte[] Photo { get; set; }
        public bool CurrentMember { get; set; }
        public int? CastYearLeft { get; set; }
        public int? DebutYearLeft { get; set; }
    }
    public enum Position
    {
        Actor,
        Director,
        Technician,
        StageManager,
        Other
    }
}
```
###### [*back to top*](#introduction)
<hr>

###### Razor Syntax
```razor
@model IEnumerable<TheatreCMS3.Areas.Prod.Models.ProductionMember>

@{
    ViewBag.Title = "Index";
    Layout = "~/Views/Shared/_Layout.cshtml";
}

<h2>Index</h2>

<p>
    @Html.ActionLink("Create New", "Create")
</p>
<table class="table">
    @* row for column headers *@
    <tr>
        
        ...
        
    </tr>

@{ var index = 0; }
@foreach (var item in Model) {
    <tr>
    
        ...
        
        <td>
            <img src="@ViewBag.ImageDataUrls[index]" width="auto" height="75px" />
            @{ index++; }
        </td>
        
        ...
        
        <td>
            @Html.ActionLink("Edit", "Edit", new { id=item.ProductionMemberId }) |
            @Html.ActionLink("Details", "Details", new { id=item.ProductionMemberId }) |
            @Html.ActionLink("Delete", "Delete", new { id=item.ProductionMemberId })
        </td>
    </tr>
}

</table>
```
###### [*back to top*](#introduction)
<hr>

###### CSS
```css
/* CREATE & EDIT PAGES */
/*form div*/
.ProductionMember-Create--formContainer {
    padding: 0 2rem 1rem;
    margin: 1rem;
    background-color: #111;
    border: solid var(--secondary-color) 3.5px;
    border-radius: 6px;
}

/*input fields*/
.ProductionMember-Create--inputField {
    width: 100%;
    height: 2.5rem;
    padding-left: .5rem;
    border: none;
    border-radius: 3px;
    transition: all .2s;
    outline: none;
    background-color: #ddd;
    color: var(--dark-color);
}

.ProductionMember-Create--inputField:focus {
    border: none;
    box-shadow: 0 0 2px 3px var(--secondary-color);
    background-color: var(--light-color);
}

/*create/save button*/
.ProductionMember-Create--input {
    width: 8rem;
    height: 3rem;
    position: relative;
    left: 50%;
    transform: translateX(-50%);
    background-color: var(--main-color);
    color: var(--dark-color);
    font-weight: 700;
    border: none;
    border-radius: 6px;
    transition: all .2s;
}

.ProductionMember-Create--input:hover {
    background-color: var(--main-color--light);
    color: var(--light-color);
}

/*back to list button*/
.ProductionMember-Create--button {
    width: 8rem;
    height: 3rem;
    position: relative;
    left: 50%;
    transform: translateX(-50%);
    background-color: var(--secondary-color--dark);
    border-radius: 6px;
    transition: all .2s;
    color: var(--dark-color);
    font-weight: 700;
    text-decoration: none;
}

.ProductionMember-Create--button a {
    color: var(--dark-color);
    font-weight: 700;
    text-decoration: none;
    transition: all .2s;
}

.ProductionMember-Create--button:hover {
    background-color: var(--secondary-color);
}

.ProductionMember-Create--button:hover a {
    color: var(--light-color);
}
/* END CREATE & EDIT PAGES */
```
###### [*back to top*](#introduction)
<hr>

###### JQuery
```js
//select and count developers on signin page
var total_developers = ($("#PersonList").children()).length;
$("#NumPersons").html(total_developers);
```
###### [*back to top*](#introduction)
<hr>

###### Bootstrap
```html
<h2 class="text-center mt-4 mb-4">Create Production Member</h2>


@using (Html.BeginForm("Create", "ProductionMembers", FormMethod.Post, new { enctype = "multipart/form-data" }))
{
    @Html.AntiForgeryToken()
    
    <div class="form-horizontal mx-auto col-sm-6 ProductionMember-Create--formContainer">
        <hr />
        @Html.ValidationSummary(true, "", new { @class = "text-danger" })
        <div class="form-group">
            <div>
                @Html.EditorFor(model => model.Name, new { htmlAttributes = new { @class = "form-control ProductionMember-Create--inputField", @placeholder = "Name" } })
                @Html.ValidationMessageFor(model => model.Name, "", new { @class = "text-danger" })
            </div>
        </div>

        ...

        <div class="form-group">
            <div>
                @Html.EditorFor(model => model.DebutYearLeft, new { htmlAttributes = new { @class = "form-control ProductionMember-Create--inputField", @placeholder = "Debut Year Left" } })
                @Html.ValidationMessageFor(model => model.DebutYearLeft, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.Photo, htmlAttributes: new { @class = "control-label" })
            <div>
                <input type="file" name="file" />
            </div>
        </div>

        <div class="form-group">
            <div>
                <input type="submit" value="Create" class="ProductionMember-Create--input" />
            </div>
        </div>
    </div>
}

<button class="ProductionMember-Create--button">
    @Html.ActionLink("Back to List", "Index")
</button>
```
###### [*back to top*](#introduction)
<hr>

###### ASP.NET MVC Controller
```cs
        ...
        
        // method for making files storable in DB
        public byte[] HttpPostedFileBaseToByteArr(HttpPostedFileBase file)
        {
            byte[] bytes = new byte[file.ContentLength];
            file.InputStream.Read(bytes, 0, file.ContentLength);
            return bytes;
        }

        // method for turning byte array from DB into a data URL
        public string GetPhotoDataUrl(int id)
        {
            ProductionMember productionMember = db.ProductionMembers.Find(id);
            if (productionMember.Photo == null)
                return "";
            string imgBase64Data = Convert.ToBase64String(productionMember.Photo);
            string imgDataURL = string.Format("data:image/png;base64,{0}", imgBase64Data);
            return imgDataURL;
        }
    }
}
```

###### [*back to top*](#introduction)
