### Week 5 Questions

Re-pull from this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 5 Questions
1. How do we make flash messages display on a page?

  The flash message type is added to the controller, and then added to the view.

2. Where is cart information/temporary information usually stored?

  PORO

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?

  We don't want to save any information to the DB until the user actually confirms this action.

4. What is the purpose of the asset pipeline?

  At a high level, the Rails Asset Pipeline is an attempt by Rails developers to decrease the time it takes for our pages to load. Specifically, the Asset Pipeline aims to speed up the process of serving our static assets.

5. Why do we precompile our assets?

  Precompiling: Allows us to write in languages related to CSS/JavaScript.

6. What do each of the following tags do?

```ruby
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```

  stylesheet_link_tag - spcefic to a css file
  javascript_include_tag - returns an HTML script tag for each of the sources provided.
  image_tag - displays an image from the image folder

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?

  Great elements for a readme is to include what the user experience is and to show the empathy intended for our users (having good user experience).

8. What are the top four accessibility issues that we as developers should be aware of?

  Navigation, site structure, forms, hyperlinks

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?

  updating an object

10. Given the following object, how would we create a scope for all users who are active?

```ruby
User.create(name: "Happy", active: true)
```

```
class User < ApplicationRecord
  scope :active, -> { where state: 'active' }
end
```

11. What is the difference between a scope and a class method?

  Class methods are methods that are called on a class and instance methods are methods that are called on an instance of a class.

### Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?  
        given[:cart]["48"] = 4
  12b. How would you increase the quantity of item 29?  
        given[:cart].keys[2].to_i + 1
  12c. How would you find out how many items your user is thinking about purchasing?   
        given.values.sum
13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?

    Polymorphism is the ability (in programming) to present the same interface for differing underlying forms (data types). It's related to duck-typing to invoke an existing method on an object.
    Polymorphic Associations - has_many & belongs_to

14. How would you clean the string "(630) 854-5483" to "630.854.5483"?  

    num.gsub(") ", ".").gsub("-", ".")


### Self Assessment:
Choose One:

* I was able to answer a few questions independently, but relied heavily on outside resources

Choose One:

* I feel comfortable/but a bit lost with the content presented this week
