## Week Four Recap

### Instructions
Fork or re-pull this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 4 Questions

1. What is a cookie?

  Identification that the client always carries.

2. What’s the difference between a session and a cookie?

  The session stores the data on the server for the cookie. The cookie only
  stores data for the client.

3. What’s a flash and when do you want to use flashes?

  Flash is a message that you want to have as a confirmation for the client.

4. Why do people say “HTTP is stateless”?

  HTTP is a stateless protocol, which means that the connection between the
  browser and the server is lost once the transaction ends.

5. What’s authentication? Explain.

  Authentication is the process of verifying a registered user.

6. What’s the difference between authentication and authorization?

  Authentication is who are you when you log in. Authorization is what you have
  access to once you log in.

7. What’s a before filter?

  before_filters is an action that calls a method before any other method can be
  initiated. It's used to protect admin controllers.

8. How do we keep track of a user once they’ve logged in?

  cookies

9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?

  It's helpful to namespace a resource for authorization in resources. It's
  helpful to nest resources to hide the user_id path for security protocols.

10. At a high level, what tools can you use to implement authorization? How would you use them?

  Namespace and roles for users. Namespace is used when setting up routes. Roles
  are used when setting up user specification on a user table.

11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?

  Enums are used to specify the role of a user. We must first create a migration
  to add a user role column to the user table.

12. What are some strategies you can use to keep your views DRY?
  You can add namespace to your routes and a bit of logic to your view templates
  so determine if a user is an admin or not.

### Reviews Questions
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}
]
```  

  Given.order(holiday: :desc)

14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300?

  rails g migration CreateTable price:integer

### Self Assessment:
Choose One:

* I was able to answer most questions independently, but utilized outside resources for a few


Choose One:

* I feel comfortable, but a bit overwhelmed with the content presented this week
