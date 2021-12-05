# Save Model on Save

### 投稿フォームの値を保存する

Commit : `526c6f0`

app/views/questions/new.html.erb

```markup
<h1 class="display-1 my-4">QA Service / New</h1>

<div class="container"> 
	<div class="row">
	
		<div class="col-md-4 offset-md-4">
	
			<!-- formタグ @question モデル -->
			<%= form_with model: @question, local: true do |f| %>
			<div class="form-group">
				<label for="name">Name</label>
				<%= f.text_field :name, class: 'form-control', id: "name",
					placeholder: "Please input name" %>
			</div>

			<div class="form-group">
				<label for="title">Title</label>
				<%= f.text_field :title, class: 'form-control', id: "title",
					placeholder: "Please input title" %>
			</div>

			<div class="form-group">
				<label for="content">Content</label>
				<%= f.text_area :content, class: 'form-control', id: "content",
					placeholder: "Please input title" %>
			</div>

			<div class="text-center">
				<%= f.submit "Save", class: 'btn btn-primary' %>
			</div>
			<% end %>
		</div>
	</div>
</div>

<!-- 実際に書き出された HTML -->
<div class="col-md-4 offset-md-4">
	<form action="/questions" accept-charset="UTF-8" method="post">
			<!-- Tokenが一致したフォーム送信形式のみ受け入れる --> 
			<input type="hidden" name="authenticity_token" value="pra_XAA2D6i3ZJeEu0zkITxREhhaB9CLTPfklQNy8AYf34BURf8LL9z6beUifYm6TbuNLUuy4YT6MfUyZrGkcw">

			<div class="form-group">
				<label for="name">Name</label>
				<input class="form-control" id="name"
					placeholder="Please input name" type="text" name="question[name]">
			</div>

			<div class="form-group">
				<label for="title">Title</label>
				<input class="form-control" id="title"
					placeholder="Please input title" type="text" name="question[title]">
			</div>

			<div class="form-group">
				<label for="content">Content</label>
				<textarea class="form-control" id="content"
					placeholder="Please input title" name="question[content]"></textarea>
			</div>

			<div class="text-center">
				<input type="submit" name="commit" value="Save"
					class="btn btn-primary" data-disable-with="Save">
			</div>

	</form>
</div>

```

app/controllers/questions\_controller.rb

```ruby
...
  def new
    @question = Question.new #新規インスタンスの立ち上げ
  end
  
  def create #新しく値を作成するアクション
    @question = Question.new(question_params) #値のインスタンス作成 (引数)
    if @question.save #もし保存出来れば
      redirect_to root_path, notice: 'Success!' #rootにリダイレクト
    else
      flash[:alert] = 'Save error'　#エラー表示
    end
  end
  
  def edit
  end
  
  private #フォームで送る値を限定させる
    def question_params # Question.new(question_params) の中身
      params.require(:question).permit(:name, :title, :content) #限定した値の保存
    end
end

```

### Degugr    end

```ruby
private
  def question_params
    byebug #<- degug => paramの送信時の検証 
    params.require(:question).permit(:name, :title, :content)
  end


on terminal:

(byebug) params
#<ActionController::Parameters tokenに一致したキー/形式のみ通している確認
{"authenticity_token"=>"pra_XAA2D6i3ZJeEu0zkITxREhhaB9CLTPfklQNy8AYf34BURf8LL9z6beUifYm6TbuNLUuy4YT6MfUyZrGkcw", 

"question"=>{"name"=>"tes-na", "title"=>"tesiti", "content"=>"tes-comn"}, 
"commit"=>"Save", "controller"=>"questions", "action"=>"create"} 

permitted: false>

(byebug) exit;
```

###

### Validate

commit  `2a64c13`

app/models/question.rb

```ruby
class Question < ApplicationRecord
  validates :name, presence: true
  validates :title, presence: true
  validates :content, presence: true
end
```

app/assets/stylesheets/scaffolds.scss

```css
.field_with_errors {
  padding: 2px;

  > * {
    background-color: lighten(pink, 5%) !important;
  }
}
```

### flash message

app/views/layouts/application.html.erb

```markup
  <% if flash[:notice] %>
    <p class="text-success text-center alert alert-success" role="alert"><%= flash[:notice] %></p>
  <% else flash[:alert] %>
    <p class="text-danger text-center alert alert-danger" role="alert"><%= flash[:alert] %></p>
  <% end %>

```
