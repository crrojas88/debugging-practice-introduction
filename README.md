# Debugging

> The terms "bug" and "debugging" are popularly 
> attributed to Admiral Grace Hopper in the 1940s. 
> While she was working on a Mark II computer at 
> Harvard University, her associates discovered a 
> moth stuck in a relay and thereby impeding operation, 
> whereupon she remarked that they were "debugging" 
> the system. - Wikipedia

Debugging is the process of finding and fixing problems
in our code. The keyword being _process_ - part of the journey
of learning how to program is learning how to deal with
obstacles like errors in your code.

"Debugging" is the process a mechanic does when you bring your
car in. "When I start it, it sounds fine. But when I hit the
brakes I hear squee-squee-squee." "Debugging" is the process
a repair person does when your washing machine does something
"strange."

Both cars and washing machines are 
complex machines with many interacting parts. But if
your car won't start you might "isolate" the battery and hook it up to a
battery tester. If the battery tester shows the battery is good, then you know
that the problem is somewhere else; if the battery is dead, then you have
_verified_ that the battery is the problem with your car.

That process is known as _debugging_ when applied to computers or
_troubleshooting_ when applied to pretty much everything else. At the risk of
sounding mystical, debugging is a skill shared by all makers: guitarists to
brewers, to chefs, to programmers. From Neal Stephenson's _Cryptonomicon_:

> Randy counts four men in addition to Amy and the pilot...  All of them are
> fiddling around with engines or diving gear in a way Randy recognizes,
> through many cultural and technological barriers, as debugging.

## Debugging and Programming

To quote Brian Kernighan (who invented the C programming language and the
Unix operating system; so, someone who made a bug or two):

> The most effective debugging tool is still careful thought, coupled with judiciously placed print statements.

We might not have battery testers, but if we have small methods we can
put `puts` and `print`s and `p` and even `pp` throughout our code so
that we can understand the flow of the code. At this point, we can
print out the contents of variables or leave a message to ourselves
in the console output like:

```ruby
puts "please, i want to go home, please print this out!"
```

## "Stop the World" Debuggers

Sometimes we have a _really hard_ bug. We write `puts` statements and
we look at our code and we're still stuck. Or (even worse!) we're
debugging SOMEONE ELSE'S code and we "just don't get it." Sometimes in
these cases, we want to use a tool called a "stop the world" debugger.

When we run our code these debuggers will stop the execution of our program
and let us interact with our code. After we quit the debugger, the program
will continue execution.

Ruby's main "stop the world" debuggers are called Pry and Byebug. We'll be
exploring Pry in the rest of this section.

## WHY DIDN'T YOU GIVE THIS TO ME SOONER?

We know it's hard to realize that stop the world debuggers exist AFTER
you've gained some muscle strength debugging with careful thought and
print statements. Here are some key reasons to **not** learn about them
first.

### Interviews

Programmers are usually hired during a "whiteboard" interview where they
have to handle complexity, correct code, and achieving a goal by writing
with a pen on a whiteboard. If you can't structure
code in digestible chunks, or to debug it by reading code, you will not
pass the interview. We speak from bitter experience here.

### Debugging Production

Most of the time, on a production system, it's not OK to stop the site
to use a "stop the world" debugger. Can you imagine someone
freezing Facebook or Amazon to debug something? No.

The way those engineers debug those sites is they look at a log file with
data about what the world looked like, they look at the code, and then
they think **really** hard about how those two would interact. They build
little mock experiments and figure out what went wrong. You can't neglect
"thinking clearly."

### Debugger-Driven Developers

"Stop the world" debuggers have given rise to a certain negative pattern
in developers. They write a method like:

```ruby
def thing_that_needs_to_happen(param1, param2, param3)
  # code to stop the world
end
```

Once they reach the "stop the world" point, or "breakpoint," they then work out
the code that needs to go there. In pairing interviews, this will usually be a 
disqualifying behavior. Programmers expect other programmers to have a model of
what to write _before_ they start writing. Leaning on a debugger to debug, within
limits, is fine, but ***requiring it*** to do your basic tasks is a "No Hire" red
flag. Don't lose your chance at employment by becoming dependent on the 
"stop the world" debuggers.

### Conclusion

In this module, we'll discuss how to debug methodically before giving you
[Excalibur][], the stop-the-world debugger known as "Pry." We've held it
back from you so that you could be sure to learn "small methods" and
"clear variable names" as the core technique for preventing bugs. At the
end of this section, you'll be shown Pry.

[Excalibur]: https://en.wikipedia.org/wiki/Excalibur
