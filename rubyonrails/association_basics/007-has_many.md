# has_many Association
~~~
A has_many association indicates a one-to-many(一对多) connection with another model. You'll often find this association on the "other side" of a belongs_to association. This association indicates that each instance of the model has zero or more instances（0或者多个实例） of another model. For example, in an application containing authors and books, the author model could be declared like this:

~~~

```rb
class Author < ApplicationRecord
  has_many :books
end
```

![](https://ws2.sinaimg.cn/large/0069RVTdgy1fu74lz61vgj30hm08r3za.jpg)