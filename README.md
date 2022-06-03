> <hr>
> 
> # **NOTICE:** This README is still in progress.
> 
> <hr>

# Introduction
Hi! My name is Immanuel Hise and I am a graduate of The Tech Academy's **C#
and .NET Framework Boot Camp.** During this boot camp I learned a plethora
of skills which are documented in this README. Succeeding this paragraph is
a section detailing a live project that I worked on and an assortment of
solutions that I developed during the project.

## Live Project
I participated in a two-week live project during my Tech Academy Boot Camp
during which I worked with other students to develop an ASP.NET MVC web
application.

### Technologies
While working on the project, I utilized many popular languages, libraries,
and frameworks listed below.

#### Languages
* [C#](c-razor-syntax-example>)
* [HTML]()
* [CSS]()
* [Javascript]()



#### Libraries
* [Bootstrap]()
* [JQuery]()

#### Frameworks
* [ASP.NET MVC]()
* [Entity Framework]()


### Examples
Below are some specific bits of code that I wrote while working on the project.

###### C# Razor Syntax Example
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
    <tr>
        <th>
            @Html.DisplayNameFor(model => model.Name)
        </th>
        <th>
            @Html.DisplayNameFor(model => model.YearJoined)
        </th>
        <th>
            @Html.DisplayNameFor(model => model.MainRole)
        </th>
        <th>
            @Html.DisplayNameFor(model => model.Bio)
        </th>
        <th>
            @Html.DisplayNameFor(model => model.Photo)
        </th>
        <th>
            @Html.DisplayNameFor(model => model.CurrentMember)
        </th>
        <th>
            @Html.DisplayNameFor(model => model.CastYearLeft)
        </th>
        <th>
            @Html.DisplayNameFor(model => model.DebutYearLeft)
        </th>
        <th></th>
    </tr>

@{ var index = 0; }
@foreach (var item in Model) {
    <tr>
        <td>
            @Html.DisplayFor(modelItem => item.Name)
        </td>
        <td>
            @Html.DisplayFor(modelItem => item.YearJoined)
        </td>
        <td>
            @Html.DisplayFor(modelItem => item.MainRole)
        </td>
        <td>
            @Html.DisplayFor(modelItem => item.Bio)
        </td>
        <td>
            <img src="@ViewBag.ImageDataUrls[index]" width="auto" height="75px" /> @{ index++; }
        </td>
        <td>
            @Html.DisplayFor(modelItem => item.CurrentMember)
        </td>
        <td>
            @Html.DisplayFor(modelItem => item.CastYearLeft)
        </td>
        <td>
            @Html.DisplayFor(modelItem => item.DebutYearLeft)
        </td>
        <td>
            @Html.ActionLink("Edit", "Edit", new { id=item.ProductionMemberId }) |
            @Html.ActionLink("Details", "Details", new { id=item.ProductionMemberId }) |
            @Html.ActionLink("Delete", "Delete", new { id=item.ProductionMemberId })
        </td>
    </tr>
}

</table>
```
