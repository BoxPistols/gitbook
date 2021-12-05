# Setting

### Create Controller

`rails g controller questions index show new edit`

```ruby
create app / controllers / questions_controller.rb

route get 'questions/index'
get 'questions/show'
get 'questions/new'
get 'questions/edit'

invoke erb

create app / views / questions
create app / views / questions / index.html.erb
create app / views / questions / show.html.erb
create app / views / questions / new.html.erb
create app / views / questions / edit.html.erb

invoke test_unit
create test / controllers / questions_controller_test.rb

invoke helper
create app / helpers / questions_helper.rb
invoke test_unit

invoke assets
invoke scss
create app / assets / stylesheets / questions.scss
```

routes.rb

```ruby
get 'questions/index'
get 'questions/show'
get 'questions/new'
get 'questions/edit'
```

### Create Model

`rails g model question name:string title:string content:text`

```ruby
invoke  active_record
create    db/migrate/20210408182548_create_questions.rb
create    app/models/question.rb

invoke    test_unit
create      test/models/question_test.rb
create      test/fixtures/questions.yml
```

db/migrate/20210408182548\_create\_questions.rb

```ruby
class CreateQuestions < ActiveRecord::Migration[6.1]
  def change
    create_table :questions do |t|
      t.string :name
      t.string :title
      t.text :content

      t.timestamps
    end
  end
end
```

```


rails db:migrate
```

`rails db`

`sqlite> .schema`

REATE TABLE sqlite\_sequence(name,seq); \
CREATE TABLE IF NOT EXISTS "questions" ("id" integer PRIMARY KEY AUTOINCREMENT NOT NULL, "name" varchar, "title" varchar, "content" text, "created\_at" datetime(6) NOT NULL, "updated\_at" datetime(6) NOT NULL);



routes

```
  # get 'questions/index'
  # get 'questions/show'
  # get 'questions/new'
  # get 'questions/edit'
 
  resources :questions
```

`rails routes`

```
                  questions GET    /questions(.:format)                                                                              questions#index
                            POST   /questions(.:format)                                                                              questions#create
               new_question GET    /questions/new(.:format)                                                                          questions#new
              edit_question GET    /questions/:id/edit(.:format)                                                                     questions#edit
                   question GET    /questions/:id(.:format)                                                                          questions#show
                            PATCH  /questions/:id(.:format)                                                                          questions#update
                            PUT    /questions/:id(.:format)                                                                          questions#update
                            DELETE /questions/:id(.:format)                                                                          questions#destroy
```

