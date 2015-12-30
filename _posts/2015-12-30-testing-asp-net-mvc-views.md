---
layout:post
title: Testing an ASP.NET MVC View
redirect_from: "/2015/12/30/testing-asp-net-mvc-view"
permalink: testing-asp-net-mvc-view
---

It can be frustrating to test an MVC view when there is logic around the rendering of the view.
	
I am going to show you an effective way to test your MVC views that are bound to a view model. Hopefully this will better help you test your views in scenarios where the view is dynamic.

##Why would this ever be useful?
This web app I was working on had a component which sent a PDF in the customer email - this was the end of our application flow. To generate the PDF we relied on an HTML to PDF conversion. The HTML displayed different content based on certain properties of the view model. Certain sections of the HTML page were not styled right when given certain conditions. To debug this I needed a fast and repeatable method to change HTML and styling, convert HTML to PDF, and see what the final PDF would look like. I didn't find a quick and easy way to write a unit test for it, also a unit test probably would not make sense here since I am testing out how things visually look.

###My approach
The approach I used was to create a dummy controller action that would generate the view model and pass it into the view with the conditions I needed it to have. This allowed me to quickly change the properties in the view model and render different HTML.

Controller Action

```
[GET("RenderHtml")]
public ActionResult RenderHtml()
{
	var viewModel = new DummyViewModel();
	viewModel.SomeBooleanProperty = true;
	viewModel.SomeIntegerProperty = 123;
	viewModel.SomeStringProperty = "Dummy";
	
	return View("TestView", viewModel);
}
```
Html View

```
@if(viewModel.SomeBooleanProperty)
{
	<span>Boolean is true!</span>
}
else
{
	<span>Boolean is false!</span>
}
```

Now you can hit this controller action and render your view. Need to render it under another condition? Change the property, build, re-deploy, and your new view should load.