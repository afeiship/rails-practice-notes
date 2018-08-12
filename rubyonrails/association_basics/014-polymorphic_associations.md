# 2.9 Polymorphic Associations
```
A slightly more advanced twist on associations is the polymorphic association. With polymorphic associations, a model can belong to more than one other model, on a single association. For example, you might have a picture model that belongs to either an employee model or a product model. Here's how this could be declared:

多态关联：

a model can belong to more than one other model, on a single association.
```

<!-- 
这种本质上是创建了一个 imageable 的中间表
-->


```rb
class Picture < ApplicationRecord
  belongs_to :imageable, polymorphic: true
end
 
class Employee < ApplicationRecord
  has_many :pictures, as: :imageable
end
 
class Product < ApplicationRecord
  has_many :pictures, as: :imageable
end
```

![](https://ws4.sinaimg.cn/large/0069RVTdgy1fu76ge0kz6j30ht0k9ac0.jpg)

## resouces:
+ https://ruby-china.org/topics/31672