Observations: 
1. Low stickiness, Higher density. 
2. Density approximation measures
3. More breadth than depth
4. stickiness - dependent or independent of N, mostly independent of N
5. Density of a graph generally defined as: (density) = (the number of edges) / (the number of nodes)



Algorithms: 


1. Clustering Coefficient from Graph Theory
a. graph traversal to find density of each node -> average density of the graph
b. func(D)
c. Estimate k with approximation of the func
d. Algo to find global clustering coefficient = No of closed triangle points( when the triplets values are same)/ Total No of triangle points 
e. Local clustering algo = for each vertex: no of connections/ possible number of connections
example: a 2x2 1s on one side vs 4 points on corners in a matrix


2. Approximation of D using filters --DONE
a. Estimate D = sampling circles = d =  no of points/ area of square filters for each matrix  - verified with an example
example: a 2x2 1s on one side vs 4 points on corners in a matrix

b. func(D)
c. Estimate k with approximation of the func

    
3. CNN 
a. While applying the 2. algo, figured that we're relaying a square filter with overlap, a stride of negative
b. Loss function - RMSE of stickiness value using a sigmoid function as values between 0 to 1
c. Cons - need many training examples - and generation is a slow process here.



4. Findinig the network density in hops. 
a. From each point, possible connections, in one, two, .. hops. This takes a wider field of view in account from just one level of layering.
                        1' 
b. i)     1          1' 1  1'
        1 1 1      1' 1 1  1 1'    bars are the second level hops 
          1          1' 1  1' 
                        1'
                        
                        
c. Determining the density at each hop. 
                        


5. Calculating perimeter of the structure. 

a. The perimeter keeps shrinking in size as the density increases. 
b. that as a func to calculate stickiness



6.

Func ( w1*(proportion of nodes with one connection) + w2*(proportion of nodes with two connections) + w3*(proportion of nodes with three connections) + w4*(proportion of nodes with four connection) ) = stickiness


7. Using all above as features and the target value as stickiness


8. Find the prob directly 


Data for stickiness estimation: 
Logging N, stickiness and average_density:


500, 0.05, 4.993070427933126e-05
500, 0.1, 7.781992648940816e-05
500, 0.5, 5.667809674951114e-05
500, 1, 4.318331180915135e-05
