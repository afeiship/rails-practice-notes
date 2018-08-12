# 2.5 The has_one :through Association(暂时不太理解)
~~~
A has_one :through association sets up a one-to-one connection with another model. This association indicates that the declaring model can be matched with one instance of another model by proceeding through a third model. For example, if each supplier has one account, and each account is associated with one account history, then the supplier model could look like this

暂时理解就是：可以自动 join 联表查询
~~~

```rb
class Supplier < ApplicationRecord
  has_one :account
  has_one :account_history, through: :account
end
 
class Account < ApplicationRecord
  belongs_to :supplier
  has_one :account_history
end
 
class AccountHistory < ApplicationRecord
  belongs_to :account
end
```


![](https://ws2.sinaimg.cn/large/0069RVTdgy1fu7559z5krj30hl0lkwgq.jpg)
