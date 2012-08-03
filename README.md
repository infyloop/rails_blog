=======
rails_blog
==========
1. rails new blog
2. rails generate controller home index
3. root :to => 'home#index' (uncomment in config/routes.rb this tells to go to
controller home and function index)
4. rails server
5. rails generate scaffold Post name:string title:string content:text  (The scaffold generates a crud *.html.erb corresponding to * function in
controllers. Eg. Creating new post: posts_controller.rb and new.html.erb
)
6. rake db:migrate

The above 6 steps will help you get started. 

Url Mapping:
`<%= link_to "My Blog", posts_path %>`
To notice here post was the model we created was *Post*


Minimal Validation:

validates :name,  :presence => true
validates :title, :presence => true,
                  :length => { :minimum => 5 }

This would ensure that the name and title are reqd. and that length of
the title should be min. of 5 chars. 

To configure the html styling open
app/views/layouts/application.html.erb

Adding another model with references: rails generate model Comment commenter:string body:text post:references
