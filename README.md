# Music-Store-App-ASP.NET MVC

SIMPLE MUSIC STORE<br/>
|____SHOPPING<br/>
|____CHECKOUT<br/>
|____ADMIN<br/>

### Features 
- Visitors can browse album by Genre
- They Can View A Single Album and Add it to their Cart
- They Can Review Their Cart, Removing any things they no longer want
- Processing to Checkout will prompt them to log in or Register For A User Account
- After creating/logging account they can complete the order by filling out shopping and payment info
- After ordering they see simple confirmation screen
- In Admin Pannel ADministrator can Create Read Update and Delete The Albums in A GUI

### Some MECHANISMS used in this project
- DBAccess
- Form Posting Scenario
- Data Validation
- Using Master Pages 
- AJAX For Page Updates
- Validation in Login

### Controllers

Web based MVC framework Map urls to server code in a slightly different way, 

Instead of Mapping URL to file it maps URL to methods of classes

these are responsible for processing input

- HTTP Req
- Handling user input
- Retrieving and saving data
- Determining the response to sned back to client

#### Types of Responses
- display of HTML
- download a file
- redirect to a different URL

### Adding a Home Controller
- HomeController[Home]

### Adding A Store Controller
- Listing Page
- Browser Page
- Details Page
  
```cs
    public string Browse(string genre)
    {
      string message = HttpUtility.HtmlEncode("store.Browse,Genre="+genre);
      return message;
    }

    public string Details(int id)
    {
      string message = "store.Details.Id="+id;
      return message;
    }
```

### Views

VIEWS <br/>
|____ HOME <br/>
|_________Index.cshtml<br/>

```cs
@
{
  ViewBag.Title = "Index";
}
<h2>Index</h2>
```

#### Using A Layout for Common Site Elements

VIEWS <br/>
|____ Shared<br/>
|_______ _Layout.cshtml<br/>

```asp 
  <!DOCTYPE html>
  <html>
  <head>  
    <meta charset = "UTF-8"/>
    <title>@ViewBag.Title</title>
    <link href = "@Url.Content("~/Content/Site.css")" rel = "stylesheet" type="text/css"/>
  </head>
  <body>
    @RenderBody()
  </body>
  </html>
```
