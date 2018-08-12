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

## simple:
```rb
belongs_to  # 一对多，与 has_many,has_one 套用        
has_one      # 一对一          
has_many   # 一对多的另外一方            
has_and_belongs_to_many # 多对多
```

## resources:
+ https://guides.rubyonrails.org/association_basics.html