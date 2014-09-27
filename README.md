This is an interactive program which will teach you everything you need to start coding!  In this tutorial, we'll be using the *Ruby* programming language and the *Bash* scripting language.

##### Ruby

Ruby is an imperative, object-oriented language.  *Imperative*, meaning you give a set of step-based instructions (`"first do this", "next do this"`), and *object-oriented* meaning that you can create complex objects that interact with each other (such as a `Person` starting a `Car`).

##### Bash

Bash is a shell scripting language, meaning it talks to the core of the operating system -- in our case UNIX and UNIX-based systems, such as your Mac.  We'll be using tools like `mkdir` (make a directory), `cp` (copy) and `rm` (remove) to come up with some cool tricks!

## Objects: a representation of real-world items

**Objects** are the object-oriented (or OO for short) way of collecting code into meaningful structures.  For example, let's say we have a Person object.

We can say "person should say their name"

```ruby
alice = Person.new
alice.speak!
```

and we will see in the console `Alice says, "Hello, my name is Alice."`

In the above, we've created an object (Alice) who is of a particular *class* (`Person`).  We can apply the same logic to other structures.  For example, let's write a program to create one of our most useful tools - a credit card!

First, open up a text editor and paste this, then save it as `cc_gatherer.rb`.  Don't worry about understanding it all now, we'll go through it step by step!


```ruby
# All of this goes in a file called 'cc_gatherer.rb'
class CreditCard

  def initialize
    STDOUT.puts "Please enter the following.\n"
    set_object_attributes!
    write_to_disk
  end

  def set_object_attributes!
    STDOUT.puts "Credit card number (#):"
    @cc_number = gets.chomp
    STDOUT.puts "Expiration date (mm/yyyy):"
    @exp_date = gets.chomp
    STDOUT.puts "CVV number (#):"
    @cvv_number = gets.chomp
  end
  
  def write_to_disk
    File.open("credit_info.txt", "wb") do |file|
      file.puts "\
        Credit card number: #{@cc_number}\
        Expiration date: #{@exp_date}\
        CVV number: #{@cvv_number}"
    end
  end
end

cc = CreditCard.new
```
  
#### What's going on above, anyway?

In the above example, the `class` method creates a *class* called CreditCard.  A *class* is an abstract representation of an object: it may be called "Dog" but it doesn't refer to any particular dog, just the attributes which represent doggy-ness.  When we say:

```ruby
class CreditCard
  # stuff
end

cc = CreditCard.new
```

we're creating a particular *instance* of that class, much like how Fido is an instance of class Dog.  This instance is also called an *object*.
