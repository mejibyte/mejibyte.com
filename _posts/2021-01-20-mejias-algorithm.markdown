---
layout: post
title:  "Mejía's Algorithm: Finding the Subarray of Maximum Sum"
subtitle: monkey
date:   2021-01-20 14:21:35 -0500
categories: thoughts
---

In this article I describe a very elegant algorithm I discovered to solve the problem of finding the subarray of maximum sum.


My algorithm uses O(n) time and O(1) memory, which is good as Kadane's Algorithm, a popular solution to this problem discovered in the 80's by [Jay Kadane](http://www.stat.cmu.edu/~kadane/). My solution doesn't improve the complexity but it uses a different idea that I found very pretty and satisfying and I thought it was worth sharing. I also think my solution is easier to understand than Kadane's, especially for beginner programmers who don't quite understand dynamic programming yet.


I discovered this algorithm on my own so I decided to name it after me, mostly because I thought it would be pretty funny if I'm able to make the name stick. However, it's possible that somebody else already described this algorithm elsewhere. If you are aware of that please let me know; I'm really curious to know!

# Problem Statement

# Naive Solution

# Divide-and-conquer Solution

# Kadane's Algorithm

# Mejía's Algorithm


To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
