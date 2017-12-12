## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR.

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
  Active Record is an ORM framework. It allows a developer to interact with the tables in stored in their database. This interaction occurs through the use of active record methods and avoids the need for a developer to write SQL every time they interact with a database. 

2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?

team = Team.find(10) -> will return to you the team with a primary key ID of 10
team = Team.first -> will return the first team stored in the database to you 
team = Team.last -> will return the last team stored in the database to you
You have access to these methods becase Team inherits from Active record.


3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?

Team.find(4).name
Team.find(4).owner_id

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?

Owner.team.find(4)

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

Teachers has_many students 
students belong_to a teacher

6. Define foreign key, primary key, and schema.

Primary key = the ID that is unique to that table 
Foreign Key = an ID from another table that has been insterd into another table in order to define a realtionship 
Schema = The design of your database, will show what tables you have, what the relationships are and what data type the attributes have 

7. Describe the relationship between a foreign key on one table and a primary key on another table.

If a foreign key is found on a table, we know that table belongs to the other table 

8. What are the parts of an HTTP response?

Status Code 
HTTP Version 
Response Header
Response Body


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.

  Category.where(tile: "Finance") -> will retun an array all rows in the database that have a category title of finance
  Category.first -> will return the category in the database that has a primary key of 1 
  Category.find_by title: "Finance" -> will return a category object that has a title of Finance 
  Category.order(:title) -> will order the categories by title in alphabetical order 



2. Name your three favorite ActiveRecord rake tasks and describe what they do.

  rake/rails generate migration Students name:string rank:integer   -> This will create a migration file (blueprint) for a student table, student will have attributes name and rank 
  rake/rails db:migrate -> this will create the actual students table 
  rake/rails db:rollback -> if you migrated and made an error it will go back to a time before the migration 

3. What two columns does `t.timestamps null: false` create in our database?
   
   A column for created at and updated at 

4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?

  teachers belong_to a school 
  a school has_many teachers 

5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?

  You need to take the school_id and insert it in the teachers table 

6. Give an example of when you might want to store information besides ids on a join table.

    If you want to do statistical calculations on the joins table 

7. Describe and diagram the relationship between patients and doctors.

  A doctor has_many patients 
  A patient belongs_to a doctor 

8. Describe and diagram the relationship between museums and original_paintings.

  A museum has_many original paintings 
  original paintings belongs_to a museum 

9. What could you see in your code that would make you think you might want to create a partial?

  If you start to see repetition of the same code in multiple views. Particularly if you are showing the user a form
