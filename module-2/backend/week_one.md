## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
  GET- retrieve resources
  POST- creates a new resources
  DELETE- destroy
  PATCH- updates a part of a resource
  PUT- updates a resource
2. What is Sinatra?
  Web application framework
4. What is MVC?
  Model, View, Control
5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
  We follow conventions to create our paths for readability purposes for both our team members and the user.
6. What types of variables are accessible in our view templates without explicitly passing them?
  local and instance variables
7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
    @count = Horses.find(params[:id])
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
  ```ruby
  get '/horses' do
    erb :index, :locals => { :name => 'Mr. Ed' }
  end
  ```
9. What's the purpose of ERB?
  encoded ruby to write to HTML
10. Why do I need a development AND test database?
  Time efficient to have to separate tests, and it's less expensive.
11. What is CRUD and why is it important?
  Create, Read, Update, Delete - it's a common list of operations
12. What does HTTP stand for?
  HyperText Transfer Protocol
13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
  <%= %> this allow you to see it on the page.
  <% %> this does not display on the page.
14. What's an ORM?
  Object Relational Mapping
15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
  ActiveRecord
16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.

  What does it do?	Verb	URI	Data Prep	Redirect or Render?	View
  directs to index of restaurants	GET	/restaurants
  directs to form to create new restaurant	GET	/restaurants/new
  creates new restaurant and redirects to homepage	POST	/restaurants
  directs to restaurant by ID 	GET	/restaurants/:id
  directs to restaurant with updates by ID 	GET	/tasks/:id/edit
  updates the task by ID in database, then redirects to restaurant page	PUT	/tasks/:id
  destroys by ID and redirects to restaurant index	DELETE	/tasks/:id
17. What's a migration?
  Maps data into tables.
18. When you create a migration, does it automatically modify your database?
  No, just your table.
19. How does a model relate to a database?
  Model connects/communicates with the database. Read and make changes.
20. What is the difference between `#new` and `#create`?
  #new has to #save and create does #new and #save together.
### Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  
  rake db:create_migration NAME=create_films (in terminal)
  ```ruby
  class CreateFilms < ActiveRecord::Migration[5.1]
    def change
      create_table :films do |t|
        t.text    :id
        t.integer :title
        t.integer :description

        t.timestamps null: false
      end
    end
  end
```
  rake db:migrate (in terminal)
22. Given the following hash:
```ruby
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores']}
}
```

How would I add 'granola bar' to things you should have when hiking?
  activies[:hiking][:supplies]<<'granola bar'
23. What are the 4 Principles of OOP? Give a one sentence explanation of each.
  Abstraction
  Encapsulation
  Inheritance
  Polymorphism

### Self Assessment:
Choose One:

* I was able to answer most questions independently, but utilized outside resources for a few


Choose One:

* I feel comfortable (and overwhelmed with the amount of information) with the content presented this week
