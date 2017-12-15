## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app?

    rails new notarealapp -T -d="postgresql' --skip-turbolinks --skip-spring 

2. What do Models generally inherit from in rails?

    ApplicationRecord 

3. What do Controllers generally inherit from in a rails project?

  ApplicationController

4. How would I create a route if I wanted to see a specific horse in my routes fitle assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?

  resources :horses, only: [:show]


5. What rake task is useful when looking at routes, and what information does it give you?

  rake routes
  It gives you the path helper to get to the route, the HTTP verb, the path URI, the controller and index that handles the request 


6. What is an example of a route helper? When would you use them?

  pets_path
  you use them when you want to redirect the user somewhere 
  also when you are in a test and you want to test a certain page has links on it 


7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?

  _url will give you the whole url 
  _path will give you the uri 


8. What are strong params and why are the necessary?

  strong params are how rails ensures the security of your application when users fill in forms. String params mean only the params you permit will be passed into your appliaction. This can stop a malicious user from submitting something to your application that could do harm.

9. What role does `form_for` play in helping us create our forms?

  it is a rails helper method that lets you build a form, for a particualr resource. It lets you create a form for a new resource and updating a resource. The importnat thing to remember is that if you have nested routes/a belongs to relationship. You need to pass form_for instance variables for both things in the relationship.


10. How does `form_for` know where to submit the user's input?

  it defaults to the create/update action in the controller for the specific reseource depending on what the path is


11. Create a form using a `form_for` helper to create a new `Horse`. 

  <%= form_fo(@horse) do |f| >
    <%= f.label :name %>
    <%= f.text_field :name>

    <%= f.submit %>
  <% end > 

12. Why do we want to validate our models?

To make sure a user can only save something to the database if they provide the necessary attributes needed to create the record. 
