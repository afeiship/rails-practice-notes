# 1 Why Associations?
定义： In Rails, an association is a connection between two Active Record models. （Assocaition 是两个 Model 的 connection）

# 2. Why do we need associations between models? 
Because they make common operations simpler and easier in your code.(更加 simpler/easier 完成我们的代码)

# 3. example: [Each author can have many books.]
```rb
class Author < ApplicationRecord
end
 
class Book < ApplicationRecord
end
```

## resources:
+ https://guides.rubyonrails.org/association_basics.html