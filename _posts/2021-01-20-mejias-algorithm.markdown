---
layout: post
title:  "Mejía's Algorithm: Finding the Subarray of Maximum Sum"
subtitle: monkey
date:   2021-01-20 14:21:35 -0500
categories: thoughts
---

In this article I describe an elegant algorithm I discovered to solve the problem of finding the subarray of maximum sum.

My algorithm uses O(n) time and O(1) memory, which is good as Kadane's Algorithm (a popular solution to this problem discovered in the 80's by [Jay Kadane](http://www.stat.cmu.edu/~kadane/)). My solution therefore doesn't improve the asymptotic complexity, but it uses a different idea that I found beautiful and satisfying, so I thought it was worth sharing. My solution is also a little easier to understand than Kadane's, especially for beginner programmers who don't quite understand dynamic programming yet.

I discovered this algorithm on my own so I decided to name it after me, mostly because I thought it would be pretty funny if I'm able to make the name stick. However, it's possible that somebody else already described this algorithm elsewhere. If you are aware of any paper, book or blog post that describes this algorithm please let me know since I'm really curious!

As part of this article I will also describe every other solution I know to this problem. We will start with the naive and slow solution and iterate from there. Specifically, these are the topics we are going to cover:

* Problem Statement
* The Naive Solution: `O(n^2)`
* The Divide-and-Conquer solution: `O(n log n)`
* Kadane's Algorithm: `O(n)`
* Mejía's Algorithm: `O(n)`


# Problem Statement

You are given an array `A` of `N` integers. A *subarray* is defined as a non-empty contiguous block of elements of `A`.

For example, let's say we have this array `A = [-3, 5, -1, 2]`:

![TODO: A sample array with elements [-3, 5, -1, 2]]()

Here are a few examples of subarrays of `A`:

* `[-3]`
* `[5, -1]`
* `[-3, 5, -1, 2]` (which happens to be the entire array, since the entire array is a valid subarray too).

On the other hand, `[-3, -1]` is not a subarray because these numbers do not appear contiguously in `A` (remember, a subarray must be a contiguous block).

We say that the *sum of a subarray* is the sum of all its elements. For example, here are the sums of the sample subarrays:

* The sum of `[-3]` is -3;
* The sum of `[5, -1]` is `5 - 1 = 4`;
* The sum of `[-3, 5, -1, 2]` is `-3 + 5 - 1 + 2 = 3`.


The problem is to **write a program that finds the subarray whose sum is as large as possible**.


In this particular example, the maximum possible sum is 6 and corresponds to `[5, -1, 2]`, as shown below:

![TODO: A sample array with elements [-3, 5, -1, 2]]()

In this case, any other subarray has sum less than 6 (try it!) but in the general case the solution is not guaranteed to be unique: there could be two or more different subarrays with maximum sum (as an example, consider the array `[5, 5, -100, 1, 9]` which has two different subarrays of sum 10, the maximum possible). If there are multiple solutions, we will assume it's OK to find *any* of them.

Obviously the problem is only interesting when the array contains both negative and positive elements, since if all elements are non-negative then the answer is to simply take the entire array (adding extra elements to the subarray will never make it smaller!).

In the case where all elements are negative, we are forced to pick at least one (because the problem explicitly asks for a **non-empty** subarray). So in this case the solution is two simply take a subarray of size 1 containing the least negative number (in other words, the maximum array element).

But how do we solve it when there are both positive and negative numbers in the array?

If you've never encountered this problem before, this is the part where I encourage you to think about it before you continue. Stop right now and try to find a solution on your own before proceeding!  If you are able to find any of the two `O(n)` solutions, congratulations! Otherwise, by thinking about it you'll gain some of insight about the problem that will make reading the solution more satisfying. Once you read Mejía's Algorithm at the end, I guarantee you will be thinking "how did I not think of that?!".

#### Rewriting the problem into something more useful

The goal is to find the subarray whose sum is maximum, but that's just words. Let's massage that a little bit to make it easier to work with.

Since a subarray is a contiguous block of `A`, it can be described by two indices `i` and `j`: the index where it starts and the index where it ends, respectively. Let's denote as `A[i..j]` the subarray of `A` that starts at index `i` and ends at index `j` (both inclusive). I will also use 0-based indexes. For example, if `A = [-3, 5, -1, 2]` then `A[0..1] = [-3, 5]`,  `A[2..2] = [-1]` and `A[0..3] = [-3, 5, -1, 2]`.

Let's also define `sum(i, j) = A[i] + A[i+1] + ... + A[j-1] + A[j]` to make the explanations easier (in words, `sum(i, j)` is the sum of the subarray `A[i..j]`).

So now we can restate the problem as follows: given an array `A` of size `N`, find a pair of indices `i, j` satisfying `0 ≤ i ≤ j < N` such that `sum(i, j)` is as large as possible.

The first part (`0 ≤ i ≤ j < N`) just says that both indices need to be valid (inside the bounds of the array) and that `i` needs to be to the left of `j` (or `i = j`). The second part just says that the sum of `A[i..j]` should be maximum.

In summary:

* **Input**: An array `A` of `N` integers.
* **Output**: Two valid indices `i`, `j` such that `sum(i, j)` is maximum, as well as the value of `sum(i, j)` itself.

Keep in mind that in my code snippets below I will actually only return `sum(i, j)`. I won't return `i` and `j` explicitly in order to keep things simple and tidy, but it's straightforward to adapt the the code to also return `i` and `j` if you actually need the indices.

# The Naive Solution

# The Divide-and-Conquer Solution

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
