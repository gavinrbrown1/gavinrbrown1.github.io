---
layout: post
title: Information and Algorithms
date: 2016-08-01
---

## Preface

I do not know much about what follows. This is an exploratory post where I can get my thoughts written out and maybe learn something interesting based off of it. For all I know, this post could only ask totally trivial and closed questions, or it could be totally nonsensical. A few minutes on Google Scholar haven't cleared anything up.

It will all be pretty philosophical, although I think there are mathematical questions at the core.

Certainly, I abuse and conflate a variety of terms throughout. I do not have hard definitions for any of these things so my word use is bound to be fluid.

## Initial Thoughts

While hiking in Vermont, I had lots of time to ponder things. There were lots of mosquitoes. I spent some time pondering mosquitoes. I wondered how much a mosquito knows: enough to find and bite me! A mosquito knows *something*, and it seems like we should be able to talk about it in the language of bits even if exact quantification escapes us.

Furthermore, I believe that the mosquito is running off of some  algorithm. And so it  seems to me that we should be able to talk about how much any algorithm in general knows, how much information it contains. The more natural connection is with machine learning algorithms and that's where my thoughts originated. I have an inkling, though, that whatever framework answers questions about a neural network should answer questions about quicksort.

So my goal is to address the question: is there a way talk about how much an algorithm "knows"?

## Examples

There are a few algorithms and situations that I feel might be illustrative for starting a discussion.

#### Testing for Primality

I know how to correctly check if any number is a prime. There are an infinite number of primes, but clearly my knowledge of `is_prime(n)` does not grant me infinite knowledge. So I believe any definition of the information of an algorithm should be, in some way, divorced from the domain over which it operates.

#### Incorrect Information

Consider the following algorithm for identifying if a number is even:

    def is_even(x):
        if x % 2 == 0:
            return(True)
        else:
            return(False)

and this companion algorithm:

    def is_even_redux(x):
        if x % 2 == 0:
            return(False)
        else:
            return(True)

I'm reasonably confident that any measure of information in an algorithm should treat these two as exactly the same, even though one is incorrect.

As an extension, I don't think it should matter how accurate a neural network is. I imagine that ACCURACY -> INFORMATION, but not the converse.

#### Regularization and Overfitting

Along those lines, I think we can address overfitting. Initially I thought I had a paradox on my hands: with regularization we can generate a "more knowledgeable" algorithm by taking *less* information from each training example! But the mistake lies in confused definitions of "knowledge" and "information." In everyday usage, we might refer to "knowledge" as correct information, but I haven't necessarily been doing so here.

#### Two Sorting Algorithms

Does Merge Sort contain more information than Insertion Sort? What about two different implementations of the same fundamental algorithm? The inputs and outputs are exactly the same, although the resources required are different.

This appears to be a tough one. I have no idea.

#### Randomly Initialized Neural Networks

Another thought is that the information in an algorithm is simply the minimum number of bits needed to encode the algorithm. This certainly seems reasonable! But it leads us to an interesting point: for a given configuration, a network with its weights randomly initialized requires as much information to encode as it ever could. (I think that is true.)

So there are three options:
1. The information-to-encode definition is incorrect.
2. I need to learn more about information theory.
3. When we talk about a network "learning," we are not describing an increase in information content.

The last option is the most tantalizing to me. I feel we may have co-opted the language of information to describe the narrowing down of our generic model onto a specific function.

#### Constant Output, Identity Function

Let's look at two limit cases of regression: constant output and identity output.

Is it safe to say that a function with constant output contains no information? Is that obvious?

What about an identity function? It seems to be a simple algorithm, but perhaps that simplicity is misleading. I have the feeling that there is some set of informationally-equivalent functions.

## Additional Questions

* Does this relate in any way to Akaike Information Criterion? It's not clear to me.
* Can the problem be attacked by some evaluation of the input and output entropy?
    * Maybe it is just a matter of taking the entropy of the output, perhaps over the entire input space (whatever that means)?
* Is there a limit to the information that can be contained by a certain machine learning algorithm specification?
* Does an algorithm's confidence of its output (when defined) come into play?
* Might I just be talking about the *complexity* of a function?

## Final Thoughts

I have strong reasons to believe this is not a world-as-we-know-it-changing blog post. I'll say it even though I have exactly zero readers: please let me know if you know how to solve this problem or if you think it is worth talking about. I'd like to talk more about it.
