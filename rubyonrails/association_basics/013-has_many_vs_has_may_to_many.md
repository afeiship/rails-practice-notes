# 2.8 Choosing Between has_many :through and has_and_belongs_to_many
~~~
Rails offers two different ways to declare a many-to-many relationship between models. The simpler way is to use has_and_belongs_to_many, which allows you to make the association directly:
~~~

![](https://ws4.sinaimg.cn/large/0069RVTdgy1fu763vswo7j30zo0xu446.jpg)



## tips:
~~~
The simplest rule of thumb is that you should set up a has_many :through relationship if you need to work with the relationship model as an independent entity. If you don't need to do anything with the relationship model, it may be simpler to set up a has_and_belongs_to_many relationship (though you'll need to remember to create the joining table in the database).

You should use has_many :through if you need validations, callbacks or extra attributes on the join model.

你需要使用：has_many :through，如果 你需要 validates， callback 或者其它 的 extra attribute 当 join查询的时候

~~~