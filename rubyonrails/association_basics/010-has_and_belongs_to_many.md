# 2.6 The has_and_belongs_to_many Association
~~~
A has_and_belongs_to_many association creates a direct many-to-many connection with another model, with no intervening model. For example, if your application includes assemblies and parts, with each assembly having many parts and each part appearing in many assemblies, you could declare the models this way:
~~~

```rb
class Assembly < ApplicationRecord
  has_and_belongs_to_many :parts
end
 
class Part < ApplicationRecord
  has_and_belongs_to_many :assemblies
end
```


![](https://ws3.sinaimg.cn/large/0069RVTdgy1fu758akdxuj30h40hmwfx.jpg)


```rb

class CreateAssembliesAndParts < ActiveRecord::Migration[5.0]
  def change
    create_table :assemblies do |t|
      t.string :name
      t.timestamps
    end
 
    create_table :parts do |t|
      t.string :part_number
      t.timestamps
    end
 
    create_table :assemblies_parts, id: false do |t|
      t.belongs_to :assembly, index: true
      t.belongs_to :part, index: true
    end
  end
end
```