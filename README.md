# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

# First vs. Median-of-Three

From lecture slide 34 we define a good pivot as a pivot from the middle $\frac{n}{2}$ elements.
That is to say if our chosen pivot, $x$, satisfies $\frac{n}{4} \leq x \leq \frac{3n}{4}$, it
qualifies as a good pivot.  

In a randomly ordered array, every individual element, including the first element, is equally
likely to be te $i$th smallest element for any $i = 1, 2, ..., n$, thus the probability of the
first being a good pivot is:  
$\frac{\frac{3n}{4} - \frac{n}{4}}{n} = \frac{\frac{2n}{4}}{n}$
