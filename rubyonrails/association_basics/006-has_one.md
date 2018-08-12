2.2 The has_one Association

~~~
A has_one association also sets up a one-to-one(一对一) connection with another model, but with somewhat different semantics (and consequences). This association indicates that each instance of a model contains or possesses one instance of another model. For example, if each supplier in your application has only one account, you'd declare the supplier model like this:
~~~

```rb
class Supplier < ApplicationRecord
  has_one :account
end
```

![](https://ws3.sinaimg.cn/large/0069RVTdgy1fu73xv78uyj30he08rmxy.jpg)
