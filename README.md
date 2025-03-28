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
first element satisfying the inequality above, thus being a good pivot is:  
$\frac{\frac{3n}{4} - \frac{n}{4}}{n} = \frac{\frac{2n}{4}}{n} = \frac{\frac{n}{2}}{n} = 
\frac{n}{2} \cdot \frac{1}{n} = \frac{n}{2n} = \frac{1}{2}$  
or 50%. The probability of any individual element being among the values that exceed or fall
short of the range that is considered to qualify it as a good pivot is $\frac{1}{4}$ for
falling short, being too small of a value, and $\frac{1}{4}$ for exceeding, being to large
of a value.  

Using the information above, where we determined the probability of any individual element
being a good pivot, we can determine if Median-of-Three is better, worse, or equal to always
choosing the first element as our pivot.  

First we need to determine what scenarios would result in Median-of-Three producing a desirable
outcome, those in which our median value falls within the 1/2 middle region to be considered a
good pivot.  

First if all 3 elements fall within that middle region, our median value will be good. This has
a $\frac{1}{2} \cdot \frac{1}{2} \cdot \frac{1}{2} = (\frac{1}{2})^3 = \frac{1}{8}$ probability
of occuring.  

Next if 2 elements fall within that middle region, and 1 element is either high or low, our
median value will be good. This can occur in three different ways, low or high -> middle ->
middle, middle -> low or high -> middle, middle -> middle -> low or high. As low or high
occurances have a $\frac{1}{4}$ probability, and middle occurances have a $\frac{1}{4}$
probability, that gives us a $3 \cdot \frac{1}{2} \cdot \frac{1}{2} \cdot \frac{1}{4} =
3 \cdot \frac{1}{16} = \frac{3}{16}$ probability of occuring for either low or high, and a
futher \frac{3}{16} probabilty of occuring for the other, low or high, resulting in a total
of \frac{6}{16}.  

Finally if 1 element falls in the low region, 1 element falls in the middle region, and 1
element falls in the high region. This has 6 different ways this can occur, low -> medium ->
high, high -> low -> medium, medium -> high -> low, etc. Following the same pattern as above,
we can calculate the probability as $6 \cdot \frac{1}{4} \cdot \frac{1}{2} \cdot \frac{1}{4} =
\frac{6}{32}$ probability of occuring.  

Summing up these probabilities in which a good pivot is produced, we get $\frac{1}{8} +
\frac{6}{16} + \frac{6}{32} = \frac{2}{16} + \frac{6}{16} + \frac{3}{16} = \frac{11}{16}$
or 68.75%.  

Now, I'm no numbers scientist, but when it comes to being a bigger number, 68.75% does seem
a fair bit more impressive than 50%, thus, Median-of-Three is more likely to result in a good
pivot, and the winner.  

# Resources

I reviewed the following source, since I haven't done combinatorics in a while, and needed a
refresher to sort this out.
https://www.geeksforgeeks.org/combinatorics/

# Plagiarism Notice

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.
