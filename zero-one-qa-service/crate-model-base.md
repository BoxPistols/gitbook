# Crate Model Base

### Model Base

app/controllers/questions\_controller.rb

```ruby
class QuestionsController < ApplicationController
  def index
    @questions = Question.all
  end
  ...
```

qustions/index.html.erb

```ruby
<h2>Questions</h2>

<div class="row">
  <div class="col-md-12">
    <table class="table-responsive striped">
      <thead class="thad-light">
        <tr>
          <th>ID</th>
          <th>Title</th>
          <th>Menu</th>
        </tr>
      </thead>
      <tbody>
      <% @questions.each do |question| %>
        <tr>
          <td><% question.id %></td>
          <td><% question.title %></td>
          <td>[Edit] [Delete]</td>
        </tr>
      <% end %>
      </tbody>
    </table>
  </div>
</div>
```

`rails db:seed`

`rails c`

`Question.all`

```sql
irb(main):001:0> Question.all
   (1.0ms)  SELECT sqlite_version(*)
  Question Load (0.4ms)  SELECT "questions".* FROM "questions" /* loading for inspect */ LIMIT ?  [["LIMIT", 11]]
=> #<ActiveRecord::Relation [#<Question id: 1, name: "Test Name 1", title: "Test Title 1", content: "Test content 1", created_at: "2021-04-09 06:25:13.084416000 +0000", updated_at: "2021-04-09 06:25:13.084416000 +0000">, #<Question id: 2, name: "Test Name 2", title: "Test Title 2", content: "Test content 2", created_at: "2021-04-09 06:25:13.093168000 +0000", updated_at: "2021-04-09 06:25:13.093168000 +0000">, #<Question id: 3, name: "Test Name 3", title: "Test Title 3", content: "Test content 3", created_at: "2021-04-09 06:25:13.097390000 +0000", updated_at: "2021-04-09 06:25:13.097390000 +0000">]>
```

