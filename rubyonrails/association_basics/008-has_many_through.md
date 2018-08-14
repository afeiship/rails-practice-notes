# 2.4 The has_many :through Association

~~~
A has_many :through association is often used to set up a many-to-many connection with another model(多对多模型). This association indicates that the declaring model can be matched with zero or more instances of another model by proceeding through a third model. For example, consider a medical practice where patients make appointments to see physicians. The relevant association declarations could look like this:
~~~

```rb
class Physician < ApplicationRecord
  has_many :appointments
  has_many :patients, through: :appointments
end

## 关联表
class Appointment < ApplicationRecord
  belongs_to :physician
  belongs_to :patient
end
 
class Patient < ApplicationRecord
  has_many :appointments
  has_many :physicians, through: :appointments
end
```

## 解释
~~~
这里的情况其实是，正好 appiontments 这个与 phy pat 都是一对多的关系
phy 和 pat 正好也是多对多的关系

正好借一张表，作为中间表的情况
~~~

![](https://ws1.sinaimg.cn/large/0069RVTdgy1fu74om022fj30i90lmace.jpg)


## 最终的数据 结构如下：
```rb

class CreateAppointments < ActiveRecord::Migration[5.0]
  def change
    create_table :physicians do |t|
      t.string :name
      t.timestamps
    end
 
    create_table :patients do |t|
      t.string :name
      t.timestamps
    end
 
    create_table :appointments do |t|
      t.belongs_to :physician, index: true
      t.belongs_to :patient, index: true
      t.datetime :appointment_date
      t.timestamps
    end
  end
end
```