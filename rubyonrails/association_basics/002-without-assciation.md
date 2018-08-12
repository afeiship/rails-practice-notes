# without assciation:
```rb
class Author < ApplicationRecord
end
 
class Book < ApplicationRecord
end
```


## basic operations:

## create:
```rb
@book = Book.create(published_at: Time.now, author_id: @author.id)
@book.save
```

## destroy:
```rb
# 得先把挂在作者下面的 books 删除，再删除作者
@books = Book.where(author_id: @author.id)
@books.each do |book|
  book.destroy
end
@author.destroy
```