---
layout: post
title: Introduction to Ruby language
categories: introduction
tags: hello-world
eye_catch: https://t4.ftcdn.net/jpg/01/34/41/35/240_F_134413529_K4TpMYLRsFeATEaGwVbScBOoDRLT0ysA.jpg
mathjax: "true"
---

<!--more-->

# What is the Ruby programming language?

Ruby is a dynamic programming language created by Yukihiro Matsumoto. Ruby was inspired by Lisp, Smalltalk, and Perl, but it uses the simple syntax of C and Java. Ruby is a object-oriented language, but it is also suitable for functional or procedural programming styles.

> Ruby is designed to make programmers happy.

{% highlight ruby %}
# Hello World
1.class		# => Integer
0.0.class	# => Float
true.class	# => TrueClass
false.class	# => FalseClass
nil.class	# => NilClass
{% endhighlight %}

In Ruby, parentheses are usually optional and they commonly ommited.

{% highlight ruby %}
3.times { print "Ruby!" }	# Ruby!Ruby!Ruby! => 3
1.upto(9) { |x| print x }	# 123456789 => 1
{% endhighlight %}

`times` and `upto` are methods implemented by integer objects. They are special kind of method known as an *iterator*, and they behave like loops. The coide within curly braces --known as a *block*--is a associated with the method invocation and serves as the body of the loop. The use of iterators and blocks is another notable feauture of Ruby; although the language does support an ordinary `while` loop, it is more common to perform loops with constructs that are actually method calls.

{% highlight ruby %}
a = [1,2,3,4]		# => [1, 2, 3, 4]
a[3] = a[2] - 1		# => 2
a.each do |elt|
	print elt+1
end			# 2343 => [1, 2, 3, 2]
{% endhighlight %}

Various other useful iterators are defined on top of `each`:

{% highlight ruby %}
a = [1,2,3,4]			# => [1, 2, 3, 4]
b = a.map {|x| x*x }		# => [1, 4, 9, 16]
c = a.select {|x| x%2==0 }
a.inject do |sum,x|
	sum + x
end				# => 10
{% endhighlight %}

Hashes, like arrays, are a fundamental data structure in Ruby. As their names implies, they are based on the hashtable data structure and serve to map arbitrary key objects to value objects. (To put this another way, we can say that a hash associates arbitrary value objects with key objects.) Hashes use square brackets, like arrays do, to query and set values in the hash. Instead of using an integer index, they expect key objects within the square brackets. Like the `Array` class, the `Hash` class also defines and `each` iterator method. This method invokes the associated block of code once for each key/value pair in the hash, and (this is where it differs from `Array`) passes both the key and the value as parameters to the block:

{% highlight ruby %}
h = {
	:one => 1,
	:two => 2
}
h[:one]
h[:three] = 3
h.each do |key,value|
	print "#{value}:#{key};"
end
{% endhighlight %}

See you soon!