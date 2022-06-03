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
* [Entity Framework](#)

<hr>

### Examples
Below are some blocks of code that I wrote while working on the project. I've
inserted ellipses (`...`) wherever the snippets have been abbreviated.

###### C#
```cs

```

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

###### CSS
```css

```

###### JQuery
```js

```

###### Bootstrap
```html

```

###### ASP.NET MVC Controller
```css

```
