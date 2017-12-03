## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

1. List the five common HTTP verbs and what the purpose is of each verb.

  GET - used to fetch a resource (page) from the server that a user has requested 
  POST - used when a user wants to add a resource to the database 
  PUT - used when a user wants to modify the entire resource in the database 
  PATCH - used when a user wants to modify part of a resource on the database 
  DELETE - used when the user wants to destroy a resource from the database 

2. What is Sinatra?

  A lightweight framework for building web applications around a rack and MVC model. Typically used when Rails would be 'overkill' for a basic project. 

4. What is MVC?

  Model - interacts with the database to perform logic when needed 
  View - shown to the user when needed. Will often invovle outputing data from the darabase in erb tags
  Controller - the product manager of the application, will control how requests and responses are managed throghout the user journey

5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?

  This folows REST-ful (Represenational state transfer) design, which has become a modern web convention. Alows another developer to easily understand your code base. 

6. What types of variables are accessible in our view templates without explicitly passing them?

  Those inside the params hash/method

7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
  ```ruby
  get '/horses' do
    @count =  1
    erb :index, :locals => {:name => 'Mr. Ed'}
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
9. What's the purpose of ERB?

  It stands for embeded ruby and allows us to render data from our database to the user when they are viewing a web page 

10. Why do I need a development AND test database?

  You do not want to make your development database dirty while you are building out CRUD functionality for your application 

11. What is CRUD and why is it important?
  
  C = create
  R = read
  U = update 
  D = destroy 

  It defines how a user will interact with a resource. It is an important part of REST-ful design

12. What does HTTP stand for? 

  Hyper Text Transfer Protocool 

13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?

  <%= %> will output the result of the ruby to the user to see 
  <% %> will not output the result for the user to see, but will instead run behind the page

14. What's an ORM?

  An Object Relational Mapper. In ruby the most used one is Active Record. It allows a developer to interact with a realtional database as if each table were an object and each row within that table, an instance of that object 


15. What's the most commonly used ORM in ruby (Sinatra & Rails)?

  Active Record 

16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.

  GET /restaurants -> will display all the restuarants to a user 
  GET /restaurants/new -> will display a form for a user to enter a new restaurant 
  POST /restaurants -> will allow a user to submit the form for a new restuarant and will create this in the database 
  GET /restaurants/:id -> allows a user to look at the inforamtion for a particular restaurant 
  GET /restauransts/:id/edit -> allows a user to edit the information for a particular restaurant 
  PUT /restaurants/:id -> allows a user to submit the form with the edits they have made to a particular restaurant 
  DELETE /restaurants/:id -> allows a user to delete a restaurant from the database 




17. What's a migration? 

 A way to update the database, in your migration you specify what columns a particular table will have. Every time you update the databse you want to run a new migration.

18. When you create a migration, does it automatically modify your database?

Yes in rails. 

19. How does a model relate to a database?

The model interacts with the database. In the model you define methods often with active record that are used to extract certain infomration from your database that you need within your application.

20. What is the difference between `#new` and `#create`?

With new you will not have saved anything to the databse, unless you follow it up with #save. With create you are effecitvely creating a  new instance and saving it to the database in one go

Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film? 

  require'CSV'

  films = CSV.open './db/csv/films.csv' headers:true header_converters: :symbol 
  films.each do |row|
    Film.create!(id: row[:id], title: row[:title], description: row[:description])
  end



22. Given the following hash:
```

activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone'],
  brunch: {cost: $35, supplies: ['mimosa flutes'],
  antiquing: {cost: $200, supplies: ['list of antique stores'] 
}

```
How would I add 'granola bar' to things you should have when hiking?

activities[:hiking][:supplies] << 'granola bar'
