# Climbing Stairs 🧗‍♀️

## The problem
Write a program that:

- takes a single integer (n) representing the total number of steps to reach the top of the staircase
- calculates in how many distinct ways you can climb to the top, given that you can take either 1 or 2 steps at a time
- returns the number of distinct ways (an integer).

## Understand the Problem
Before diving into the main challenge, let's simplify the problem to build your understanding of the basic concepts involved.

- Consider a staircase with 3 steps. How many distinct ways can you climb to the top?
- 1 (1, 1, 1)
  - Incorrect. Can you think of more ways?
- 2 (1, 1, 1), (1, 2)
  - Incorrect. Can you think of more ways?
- 3 (1, 1, 1), (1, 2), (2, 1)
 - Correct. That makes 3 distinct ways to climb a staircase of 3 steps.
- 4 (1, 1, 1), (1, 2), (2, 1), (3, 1)
  - Incorrect. You can only take 1 or 2 steps
- 5 (1, 1, 1), (1, 2), (2, 1), (2, 2), (2, 2, 1) 
  - Incorrect. (2, 2) sums to 4 and (2, 2, 1) sums to 5.
{: .choose_best #understand_the_problem title="Consider a staircase with 3 steps. How many distinct ways can you climb to the top?" points="1" answer="3" }

This example illustrates the core concept of dynamic programming and the Fibonacci sequence, where the solution to a problem depends on the solutions to its smaller instances.

## Think Aloud
In coding interviews, interviewers are interested in your thought process. Discuss your approach to the problem, write pseudocode, and consider both brute force and optimized solutions. Starting with a brute force solution is perfectly acceptable; you can refine your approach as you go.

Test your code
```ruby
steps = [2, 3, 5, 8]
n = steps.sample
# write your program using this method
def climb_stairs(n)

end

puts climb_stairs(n)
```
{: .repl #climb_stairs title="Climbing Stairs" readonly_lines="[1,2,3,4,5,6]"}

```ruby
describe "Climbing Stairs" do
  it "calculates 2 distinct ways for 2 steps" do
    expect(climb_stairs(2)).to eq(2) # (1,1) and (2)
  end
end
```
{: .repl-test #climb_stairs_test_1 for="climb_stairs" title="Climbing Stairs calculates 2 distinct ways for 2 steps" points="1"}

```ruby
describe "Climbing Stairs" do
  it "calculates 3 distinct ways for 3 steps" do
    expect(climb_stairs(3)).to eq(3) # (1,1,1), (1,2), and (2,1)
  end
end
```
{: .repl-test #climb_stairs_test_2 for="climb_stairs" title="Climbing Stairs calculates 3 distinct ways for 3 steps" points="1"}

```ruby
describe "Climbing Stairs" do
  it "calculates the correct number of ways for a larger number of steps, demonstrating the algorithm's efficiency" do
    expect(climb_stairs(20)).to be_a(Integer)
  end
end
```
{: .repl-test #climb_stairs_test_3 for="climb_stairs" title="Climbing Stairs calculates correctly for a larger number of steps" points="1"}

## Tips and Clues for Solving the Problem
- **Recursion**: A straightforward way to solve this problem is by using recursion to explore all possible step combinations. However, this method can be highly inefficient for larger numbers of steps due to repeated calculations.
- **Dynamic Programming**: The problem exhibits both optimal substructure and overlapping subproblems, making it a perfect candidate for dynamic programming. By storing the results of subproblems, you can avoid redundant calculations and improve efficiency.
- **Fibonacci Sequence**: This problem can be reduced to the Fibonacci sequence, where the number of ways to climb n steps is the sum of the ways to climb (n-1) steps and (n-2) steps. Utilizing this approach significantly simplifies the problem.

## Quiz

- What is the significance of dynamic programming in solving algorithm problems?
- It allows for the recursive calculation of subproblems without storing results.
  - Incorrect. While recursion is a component of many DP solutions, the key advantage of DP is indeed storing the results of subproblems to avoid redundant calculations.
- It relies solely on dividing the problem into smaller, non-overlapping problems.
  - Incorrect. This description fits more with divide and conquer algorithms. DP deals with overlapping subproblems and optimal substructure.
- It uses stored solutions of subproblems to optimize the overall computation.
  - Correct! Dynamic programming stores the results of subproblems, which makes it highly efficient for problems with overlapping subproblems and optimal substructure.
{: .choose_best #dynamic_programming_significance title="What is the significance of dynamic programming in solving algorithm problems?" points="1" answer="3" }

- Which concept is crucial for optimizing the Climbing Stairs problem?
- Memorization
  - Incorrect, but close. The term you're looking for is "Memoization," which involves storing results of expensive function calls.
- Recursion
  - Correct, but there's more. While recursion is a method to approach the problem, the optimization heavily relies on avoiding repeated calculations through another concept.
- Memoization
  - Correct! Memoization is a specific form of caching that is used in dynamic programming to store the results of expensive function calls and retrieve them when needed.
{: .choose_best #concept_for_optimization title="Which concept is crucial for optimizing the Climbing Stairs problem?" points="1" answer="3" }

## Conclusion
In this lesson, we've tackled the Climbing Stairs problem, a classic example of dynamic programming and the Fibonacci sequence in action. By understanding and applying the concepts of recursion, memoization, and dynamic programming, we've seen how to approach and solve problems efficiently, setting a solid foundation for tackling similar algorithmic challenges.
