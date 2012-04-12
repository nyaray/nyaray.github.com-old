---
layout: default
title: Distributed erlang, part 1.
published: true
---
<h2>"What is this?! I don't even..."</h2>

I'm mainly writing this as a note to myself for future reference, the purpose of this post is to aid the reader (probably just me :P) in setting up two erlang nodes on one computer so that they can communicate with each other and to test the setup by sending a message with the help of erlangs awesome message passing.

The steps described are just some things I've put together from a few resources on the web, I am by no means taking any credit for anything other than organising the information below into its current format and using quirky names and messages.

<h2>Putting It Together</h2>

Firstly, we need to bring up two terminal windows and write some stuff in them (don't worry, it should be pretty self-explanatory, but there will be some clarifications further down).


Terminal 1,

{% highlight sh %}$ erl -name mario@127.0.0.1{% endhighlight %}
{% highlight erlang %}(mario@127.0.0.1)1> erlang:set_cookie('luigi@127.0.0.1', shrooms).
true
{% endhighlight %}

Terminal 2,

{% highlight sh %}
$ erl -name luigi@127.0.0.1
{% endhighlight %}
{% highlight erlang %}
(luigi@127.0.0.1)1> erlang:set_cookie('mario@127.0.0.1', shrooms).
true
(luigi@127.0.0.1)2> register(sink, self()).
true
{% endhighlight %}

So far, we've started two erlang nodes, one called 'mario' and one called 'luigi'. They are both set up to use the atom shrooms as a magic cookie (which is used to keep traffic between the nodes safe).


We have also registered the shell process in 'luigi' under the atom sink, this allows us to send messages directly to the shell at 'luigi' by sending them to the process 'sink' on the node 'luigi@127.0.0.1'.


Let's send (and receive, of course) some messages!


Terminal 1,

{% highlight erlang %}
(mario@127.0.0.1)2> {sink, 'luigi@127.0.0.1'} ! "It's-a-me!".
"It's-a-me!"
{% endhighlight %}


Terminal 2,

{% highlight erlang %}
(luigi@127.0.0.1)3> receive Term -> io:format("Received: ~p\n", [Term]) end.
Received: "It's-a-me!"
ok
{% endhighlight %}

It should be noted that the use of the -name flag makes it impossible for the erlang nodes to communicate with erlang nodes started with the -sname flag. See <a title="documentation" href="http://www.erlang.org/doc/reference_manual/distributed.html" target="_blank">http://www.erlang.org/doc/reference_manual/distributed.html</a> for more information regarding distributed erlang.

That's all there is to it, hopefully this will help you in setting up your own awesomely tasty distributed system built with erlang :).


Happy hacking!
