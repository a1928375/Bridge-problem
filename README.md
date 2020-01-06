# Bridge-problem

1. Bridge problem:

(1) Original version: doesn't find the lowest cost
=> 因為是先以最lowest cost來排序，然後繼續run
=> 但有可能 其他次小cost的path 的最終結果(total cost)會更小
=> 如下圖的 (i): (a)14 + (b)5 = 19 & (ii): (c)15 + (d)2 = 17

(2) Intermediate version: find the correct answer, but it's not efficient
=> 因為就算是繞圈 => loop => 但是t不同，所以都會被判定成不同states
=> person 1 來來回回 來往here & there，但是t不同，所以都被探定不同states
=> 但實際上就是一個loop，但每個state都要探索 => inefficient，且浪費resources

(3) Refactoring version: efficient
=> 所以把t提出來成額外parameter
=> 讓t & action成為一個tuple

(4) Gerneralized version: 此類problems較tricky，容易有bugs
=> 但是解題strategy大部分相同
=> 所以將可以共用的部分，分離出來，讓其他problems皆可直接套用
=> reduce bugs
=> 稱"Generalization"

2. Refactoring Bsuccessors: In this problem you will be refactoring the bsuccessors function. Your new function, bsuccessors3, will take a state as an input and return a dict of {state:action} pairs. A state is a (here, there, light) tuple. Here and there are frozensets of people (each person is represented by an integer which corresponds to their travel time), and light is 0 if it is on the `here` side and 1 if it is on the `there` side. An action is a tuple of (travelers, arrow), where the arrow is '->' or '<-'. See the test() function below for some examples of what your function's input and output should look like.
      
      Return a dict of {state:action} pairs. State is (here, there, light) where here and there are frozen sets of people, light is 0 if         the light is on the here side and 1 if it is on the there side. Action is a tuple (travelers, arrow) where arrow is '->' or '<-'"""
