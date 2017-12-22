## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

* What is a cookie?

A cookie is a small piece of data stored either on the clent or server side to make HTTP stateful as opposed to stateless. 

* What’s the difference between a session and a cookie?

The data stored in a cookie is stored on the vistiros browser. The data in a sesison is stored on the server side. 

* What’s a flash and when do you want to use flashes?

  Its a type of session that lasts for a single instance. You want to use one when the user engages in some sort of CRUD operation on your site to let them know they have been succesful. 

* Why do people say “HTTP is stateless”?

 Every time you engage with the request response cycle it assumes you are a new person every time and does not know anything about you. 

* What’s authentication? Explain.

  Is the user coming to your site who they say they are. We use authentication to check that the person logging in is actually the person we have on reccord who frequently visits our application. 

* What’s the difference between authentication and authorization?

  Authentication = are you who you say you are 
  Authorization = do you belong in this part of my applicaiton 


* What’s a before filter?

  Its a method you define at the top of your controller, it will check that a condition is met before it allows any of the actions within that controller to dispatch a resource 


* How do we keep track of a user once they’ve logged in?

  We store them in a session 


* When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?

You would namesapce if you dont have a resource for the thing you are creating the namespace for in your database. It is common to create one if you will have a route like admin/cats, where we have a cat resource but do not have an admin one. Nesting a resource is useful when you want to convey a relationship i.e. books have many authors so the URI would want to look soemthing like author/1/books.


* At a high level, what tools can you use to implement authorization? How would you use them?

I would use becrypt to make sure that password data was not stored as a string on my database but was instead stored as a password digest. I  would also have a users controller to deal with the initial log in and I would storet the user ID in a session. Within the application controller I would create a helper method for the current_user.


* What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?

You want to use an enum when you have an attribute that can have only one of a few differnt values. For example a user can either be a default user or an admin. Enums let you map the attributes of an Active Record object to integers as opposed to string values. They are much faster to use but provide the same flexibility as usign a string. 

* What are some strategies you can use to keep your views DRY?

Make sure you only iterate through things in the view. You dont want to be building out complex logic in the views, this should be reserved for the model. You then call out the methods in the view. 

