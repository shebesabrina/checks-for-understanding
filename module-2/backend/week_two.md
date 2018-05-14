## Week Two - Module 2 Recap

Fork or re-pull this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.


### Week 2 Questions

1. At a high level, what is ActiveRecord? What does it do/allow you to do?

  ActiveRecord is the Model of the MVC. It allows the ORM to access the database.

2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?

  Team.all
  Team.find()
  Team.create
  Because you are inheriting ActiveRecord::Base.

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?

  Team.find(4).name
  team = Team.find(4)
  owner = team.owner_id

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?

  Team.find_by(owner_id: 4)

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

  It's a one to many relationship.Teachers will have_many students, and a student belongs_to teacher. Student will have a teachers_id.

create_table "teachers", force: :cascade do |t|
  t.string "title"
  t.datetime "created_at", null: false
  t.datetime "updated_at", null: false
end

create_table "students", force: :cascade do |t|
  t.string "name"
  t.datetime "created_at", null: false
  t.datetime "updated_at", null: false
  t.bigint "teacher_id"
  t.index ["teacher_id"], name: "index_students_on_teacher_id"
end

6. Define foreign key, primary key, and schema.

  foreign key: A column that references another column of a table that it's related to.
  primary key: id that's already created on a table.
  schema: blueprint or schematic structure of the table.

7. Describe the relationship between a foreign key on one table and a primary key on another table.

  foreign key: id that always on the belongs_to model
  primary key: id for the has_many model.

8. What are the parts of an HTTP response?

  Start line, headers, body, status code.

### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.

    find -  allows you to find attributes from the object.
    joins -

2. Name your three favorite ActiveRecord rake tasks and describe what they do.

    rake db:drop - drops the data from the DB.
    rake db:create - creates the DB.
    rake db:migrate - migrates the DB into the schema in a table.
    rake db:seed - loads the data

3. What two columns does `t.timestamps null: false` create in our database?

    updated_at and created_at

4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?

    One to many relationship: Schools has_many teachers. Teachers belongs_to schools

5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
    create_table "schools", force: :cascade do |t|
      t.string "title"
      t.string "description"
      t.string "address"
      t.datetime "created_at", null: false
      t.datetime "updated_at", null: false
    end

    create_table "teachers", force: :cascade do |t|
      t.string "name"
      t.datetime "created_at", null: false
      t.datetime "updated_at", null: false
      t.bigint "school_id"
      t.index ["school_id"], name: "index_teachers_on_school_id"
    end

6. Give an example of when you might want to store information besides ids on a join table.

    The relationships of which model the join table is joining.

7. Describe and diagram the relationship between patients and doctors.

    Doctor has_many patients, Patient has_many doctors, DoctorPatient belongs_to patient, belongs_to doctor

8. Describe and diagram the relationship between museums and original_paintings.

    museums has many original_paintings, original_paintings belongs_to museums

9. What could you see in your code that would make you think you might want to create a partial?

    I would use a partial if there was a navigation bar that's repeated on multiple views.

### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources
* I was able to answer most questions independently, but utilized outside resources for a few
* I was able to answer a few questions independently, but relied heavily on outside resources

Choose One:
* I feel confident about the content presented this week
* I feel comfortable with the content presented this week
* I feel overwhelmed by the content presented this week
* I feel quite lost by the content presented this week
