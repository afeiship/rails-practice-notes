# The belongs_to Association
~~~
A belongs_to association sets up a one-to-one(一对一) connection with another model, 
such that each instance of the declaring model "belongs to" one instance of the other model. 
For example, if your application includes authors and books, and each book can be assigned to exactly one author, you'd declare the book model this way:
~~~

```rb
class Book < ApplicationRecord
  belongs_to :author
end
```

![](https://ws1.sinaimg.cn/large/0069RVTdgy1fu73xaoe9cj30hs096wf9.jpg)
## tips:
~~~
belongs_to associations must use the singular term. If you used the pluralized form in the above example for the author association in the Book model, you would be told that there was an "uninitialized constant Book::Authors". This is because Rails automatically infers the class name from the association name. If the association name is wrongly pluralized, then the inferred class will be wrongly pluralized too.

belongs_to: 这个后面必须跟的是单数形式
belongs_to ：声明应该出现在包含外键(author_id)定义的表model中
~~~