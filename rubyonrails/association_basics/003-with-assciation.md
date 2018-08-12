# with assciation:
```rb
class Author < ApplicationRecord
  has_many :books, dependent: :destroy
end
 
class Book < ApplicationRecord
  belongs_to :author
end
```


## basic operations:

## create:
```rb
@book = @author.books.create(published_at: Time.now)
@book.save
```

## destroy:
```rb
@author.destroy
```