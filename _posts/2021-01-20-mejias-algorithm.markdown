---
layout: post
title:  "Mejía's Algorithm: Finding the Subarray of Maximum Sum"
subtitle: monkey
date:   2021-01-20 14:21:35 -0500
categories: thoughts
---

In this article I describe an elegant algorithm I discovered to solve the problem of finding the subarray of maximum sum.

My algorithm uses O(n) time and O(1) memory, which is good as Kadane's Algorithm (a popular solution to this problem discovered in the 80's by [Jay Kadane](http://www.stat.cmu.edu/~kadane/)). My solution therefore doesn't improve the asymptotic complexity, but it uses a different idea that I found pretty and satisfying, so I thought it was worth sharing. My solution is also a little easier to understand than Kadane's, especially for beginner programmers who don't quite understand dynamic programming yet.

I discovered this algorithm on my own so I decided to name it after me, mostly because I thought it would be pretty funny if I'm able to make the name stick. However, it's possible that somebody else already described this algorithm elsewhere. If you are aware of any paper, book or blog post that describes this algorithm please let me know. I'm really curious!

# Problem Statement

You are given an array `A` of `N` integers. A *subarray* is defined as a non-empty contiguous block of elements of `A`. We say that the *sum of a subarray* is the sum of all its elements. Write a program that finds the subarray whose sum is as large as possible.

For example, let's say we have this array `A`:

![TODO: A sample array with elements [-3, 5, -1, 2]](https://codeo.app/public/problems/0x94/1.png)

Here are a few sample subarrays:

* `[-3]`, whose sum is -3;
* `[5, -1]`, whose sum is -1;
* `[-3, 5, -1, 2]`, whose sum is 3.

On the other hand, `[-3, -1]` is not a subarray because it's not a contiguous block of some elements of the array.

In this particular example, the maximum sum

Obviously the problem is only interesting when the array contains both negative and positive elements, since if all elements are non-negative then the answer is to simply take the entire array.


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
