## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?

  rails new ____ -T -d="postgresql" --skip-turbolinks --skip-spring

2. What do Models generally inherit from in rails?

  ApplicationController and ActiveRecord

3. What do Controllers generally inherit from in a rails project?

  ApplicationController

4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?

  resources :horses, only [:index]

5. What rake task is useful when looking at routes, and what information does it give you?

  rails routes or rake routes

6. What is an example of a route helper? When would you use them?

  article_path(id)

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?


  some_url: the full url of http://localhost:3000/somethings
  some_path: is just the URI Pattern of '/somethings'

8. What are strong params and why are they necessary?

  Strong params is the method to find an id dynamically. It's stored as a private
  method for security purposes so a user cannot manipulate the DB.

9. What role does `form_for` play in helping us create our forms?

  `form_for` is a Rails helper method that creates a specific field/forms for a new or edit view.

10. How does `form_for` know where to submit the user's input?

    the f in the block params

11. Create a form using a `form_for` helper to create a new `Horse`.
  ```
  <% form_for @horses do |f|
    f.label :name
    f.textfield :name

    f.label :breed
    f.textfield :breed

    f.submit

    <% end %>
  ```
12. Why do we want to validate our models?

  I have no clue, and not sure if I should continue doing it.

13. What are the steps of the DNS lookup?

  Client makes a request to the web server. Connection to the action pack
  (two parts: ActionDispatch/routing, and ActionController. ActionController
  connects to ApplicationController (your controller) connections to the models,
  then to the DB. The Action Controller also connects to the ActionView (your view),
  then back to the server, back to the client.

### Review Questions
14. How would you call the method `prance` from within the method `move` on a `Horse` instance?

  horse.moves.prance

15. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```
What is the different between how you would return true vs returning 3?  

  furniture[:purchased]

16. What is inheritance?

  Utilizing a method from another super class or module.

### Self Assessment:
Choose One:

* I was able to answer most questions independently, but utilized outside resources for a few


Choose One:

* I feel overwhelmed by the content presented this week
