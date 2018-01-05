1. How do we make flash messages display on a page?

  You want to go into application.html.erb and itterate over all the messages and ouput the result out 

  <% flash.each do |type,message| %>
    <%= content_tag :div, message, class: type >
  <% end %>

2. Where is cart information/temporary information usually stored?

In a session. 

3. What might be some reasons not to store cart in our database? Are there any reasons why we would want to persist that information?

A cart will constantly be in a state of change. Users will add to it and remove from it over the entire lifecyle of their jounrey through our application. To constantly be handling these changes and writing to them to the database would put unecessary strain on our application.

4. What is the purpose of the asset pipeline?

It has three main purposes
  It will compress your style assets so you dont have to make multiple requests during an HTML cycle 
  It allows you to fingerprint your files so you dont have to make constant version updates when you change something 
  Lets you precompile css assets into another languague such as sass

5. Why do we precompile our assets?
  Allows us to have more power within our assets i.e. if we precompile to sass we will be able to use variables and nest styles. 

6. What do each of the following tags do?

```ruby 
<%= stylesheet_link_tag "application" %> 
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```
The first will use the application stylesheet when the page is rendered to the browser
The second will use the application javascript when the page is rendered to the browser 
The last will add an image to the browser

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?

  The version
  User stories 
  How to run your test suite
  The contributors to the project
  Info about the project
  An image of your schema 

8. What are the top four accessibility issues that we as developers should be aware of?

Visual 
Mobility 
Cognition 

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?

A callback. We would find it in the application controller. 

10. Given the following object, how would we create a scope for all users who are active?

```ruby 
User.create(name: "Happy", active: true)
```


11. What is the difference between a scope and a class method?

They are very similar and can be used to search your databse for something. Scopes are easier to chain together. 