So far with classes in Ruby, we’ve mostly dealt with **instance** methods and variables. For example, in:

```ruby
class Dog
 attr_accessor :name, :sound

 def bark
    "#{sound}, #{sound}, my name is #{name} and I’m a Dog."
 end

end
```

name and sound are **instance** variables, and bark is an **instance** method. In Ruby, we also have **class** methods and **class** variables. Where instance variables use the `@` symbol, as in `@name`.
**Class** variables use `@@`, as in `@@name`

**Class** methods have the keyword `self` before their name, a **class** method of `bark` would like this:    

```ruby
def self.bark
  “woof woof”
end
```



So in the following code:

```ruby
class Car
  @@amount = 0             # class variable

  def self.amount	        #  class method
     @@amount
   end
end


blue_car = Car.new
blue_car.amount            # won’t work, as amount is a class method
Car.amount                    #  will return @@amount

```

What does the following code print? Explain the result.

```ruby
class Computer
  def initialize
    @sound = "beep beep"
  end

  def self.about
    "Sometimes I go #{@sound}"
  end
end

p Computer.about
```



Explain the AirConditioner.about method and why the about() method definition uses the keyword self.
```ruby
class AirConditioner
  def self.about
    "my job is to keep people cool"
  end
end

p AirConditioner.about
```

Check out http://rubylearning.com/satishtalim/ruby_constants.html for this next question

What does the following code print? Explain.
```ruby
class Cup
  PURPOSE = "hold liquids"
  def main_use
    PURPOSE
  end
end

coffee_cup = Cup.new
p coffee_cup.main_use

```







Create a Robot class that has a **class** variable of `num_of_robots`, a **class** method that returns the number of robots, an **instance** variable of id, and an **instance** method that returns the id.
Instantiate (create) 3 robots with unique id’s, and then call the Robot’s **class** method to return the number of robots.


Let’s now go into inheritance. Inheritance is a relationship between two classes where a child class inherits, or receives, the properties of a parent class. Take a look at the example below:

```ruby
   class Animal
      attr_accessor :name, :sound

      def make_sound
      	 "I'm an animal;"
      end
    end


    class Dog < Animal
    end

    class Cat < Animal
    end


my_dog = Dog.new
puts my_dog.make_sound          # will output “I’m an animal”


```


What does the following code print?

```ruby
class Mammal
  def warm_blooded?
    true
  end
end

class Dog < Mammal; end

spike = Dog.new
p spike.warm_blooded?
```


What does the following code print?

```ruby
class Mammal
  def self.about
    "we are animals with warm blood and hair"
  end
end

class Dog < Mammal; end

p Dog.about

```



Refactor the following code to **not** use inheritance.

```ruby
class Person
  def full_name(first_name, last_name)
    "#{first_name} #{last_name}"
  end
end

class FootballPlayer < Person
end

player = FootballPlayer.new
p player.full_name("dan", "marino")

```



What does the following code print? Explain.
```ruby
class Building; end
class House < Building; end
p House.ancestors
```
