# Ruby

## Blocks

```ruby
def method_with_block_mandatory 
  puts 'reached the top'
  yield
  puts 'reached the bottom'
end

method_with_block_mandatory do
 puts 'reached yield'
end 

###############################
def method_with_block_optional
  puts 'reached the top'
  yield if block_given?
  puts 'reached the bottom'
end

method_with_block_optional

##############################
def block_with_parameters
 yield('Helio', 40)
end

block_with_parameters do |name, age|
  puts "#{name} is #{age} years old"
end

##############################
def yield_returns_the_last_line_of_block
  value = yield
  puts "The return the block is #{value}"
end

yield_returns_the_last_line_of_block do
  x = 1
  y = 2
  x
end

##############################
def my_map(array)
  new_array = []

  for element in array
    new_array.push yield(element)
  end
  
  new_array
end

numbers = my_map([1, 2, 3]) do |number|
  number * 2
end

numbers.each { |n| puts "#{n}" }

# Initialize objects with default values
class Car
  attr_accessor :color, :doors

  def initialize
    yield(self)
  end
end

car = Car.new do |c|
  c.color = 'Red'
  c.doors = 4
end

puts "My car's color is #{car.color} and it's got #{car.doors} doors."
```
