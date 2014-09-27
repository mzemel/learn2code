# Learn To Code
*By Michael Zemel*

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

**Example 1**:
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
    File.open("output.txt", "wb") do |file|
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

## Functions: puttin' the pedal to the metal

In the above code, we also saw the word `def`.  What does `def` really do?  Well, to understand that, we need to understand what a function is.

A function is a black box which will take in one thing and give out another.  The simplest explanation could be a black box which turns any words it gets into all capital letters, like so:

```ruby
def upper_case(word)
  return word.upcase
end
```

The `def` keyword means "turn this into a function" - specifically, one called *upper_case*.  The word `word` is a stand-in for what we'll give to the black box, and what we get back comes from that `return` command.  So if we give it `"hello, world"`, we should expect to get back `"HELLO, WORLD"` like so:

```ruby
upper_case("hello, world!")
# => HELLO, WORLD
```

Remember, just think of functions as black boxes that can take one, several, or zero things as *input* and return transformed versions of them as *output*.  Armed with **objects** and **functions**, we can bring any program to life.


## Bash: talking to the kernel since 1989

Before we start, make sure that you've copy and pasted the code in **example 1** into a text editor (like TextEdit on a Mac) and saved it to your Home folder (e.g. the folder named after your user name on your Mac.)  Already did?  Groovy!

**We can use Bash to bring our program to life!**

Open up the Terminal program ( Applications > Utilities > Terminal on your Mac ) to bring up a screen that looks like this:

![Image of Terminal]
(http://i.imgur.com/ITPBSqH.png)

When you start typing in, you're typing into the **command line** - this is how we will interact with the operating system and all of its useful tools.  Fun fact: most programs you're using on your computer will be using the same tools!

##### ls

`ls` is one of the most commonly used tools.  Try it out, type `ls` in command line and press `enter` on your keyboard.  You should see something that looks like this:

```bash
Applications        Movies				Sites
Applications        Music				VirtualBox VMs
Desktop				Nitrous				bin
Documents			Pictures			cc_gatherer.rb
Downloads			Projects
Library				Public
```

What you're seeing is a *listing* of the files in that folder.  That's because `ls` is a tool to list things!  Let's try another.

##### ruby

The ruby command line tool will use the Ruby interpreter to go through a program written in the Ruby programming language.  As luck would have it, we've already made one!

We can play with our new program by writing:

```bash
ruby cc_gatherer.rb
```

And we get to interact with the program we wrote, alternating between collecting info (make sure it's accurate!) and printing out a response.  Imagine that writing your own text-based adventure game isn't far around the corner (see below).

![Image of Terminal]
(http://i.imgur.com/7lmW3Cj.png)

Well isn't that fancy!  Let's look at one last super cool tool, `mail`

##### mail

The `mail` command lets us send emails to anyone, anywhere using nothing but our own computer.  Imagine if you didn't have to go through the hassle of signing up for GMail or Yahoo account because your computer already comes with one.  That's actually the case!

We can send mail to anyone: to your parents, to your pastor, to your best friends.  Simply type the following:

```bash
cat output.txt | mail -s "Hi, Michael!" michael.zemel@gmail.com
```

This'll send me a friendly email saying hi!

Well, hi yourself.





That's all for now folks, I hope you've enjoyed this tutorial as much as I've enjoyed making it for you.  Stay tuned for

**Part 2: Making Fractals with Your Social Security Number**.
