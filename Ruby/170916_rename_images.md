```ruby
# rename all jpg files in current directory
file_names = Dir['*.jpg']
count = 0
file_names.each do |fn|
  system("mv #{fn} hiroshima-0-#{count}.jpg")
  count += 1
end
```
