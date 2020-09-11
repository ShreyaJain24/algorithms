ALGORITHMS To find stickiness: 



1. Approximation of graph_density(D) using filters (like CNN - with one depth): 

a. Estimate D by hovering filters of a definite size with a definite stride all over the image. 
b. denisty of a filter  =  no of points(colored)/ area of square filters for each matrix. 
Example: a 2x2 1s on one side vs 4 points on corners in a matrix
c. Estimate k with approximation of the func by finding by best fit curve. Can use non-smooth functions like piecewise-splines if smooth standard functions like a polynomial function doesn't fit.

----------------------------------------------------------------------------------------------------------------------------------
    
2. Clustering Coefficient from Graph Theory

Steps: 
a. The goal is to calculate an average graph denisty. Then, find a function that best approximates k that takes input as the graph_density(D). Can find the function as a line of curve that best fits the observations of density, D against stickiness, k. Can use non-smooth functions like piecewise-splines if smooth standard functions like a polynomial function doesn't fit.

b. Global clustering coefficient = No of closed triangle points( when the triplets values are same)/ Total No of triangle points 

c. Local clustering algo = for each vertex: no of connections/ possible number of connections
example: a 2x2 1s on one side vs 4 points on corners in a matrix would have the same no of nodes but different density as their positioning varies.

----------------------------------------------------------------------------------------------------------------------------------

    
3. CNN:

a. Using a CNN architecture on the input image and capturing features at various layers. 
b. Loss function - RMSE of the target stickiness value with the predicted stickiness value.
c. Add a sigmoid function on the final CNN score to constrict the values between 0 to 1 as stickiness aslo lies in the same range.
c. Cons - need many training examples as it's a deep network.

----------------------------------------------------------------------------------------------------------------------------------

4. Findinig the network density in hops:

a. From each point, possible connections, in one, two, .. hops. This takes a wider field of view in account from just one level of layering. This is doing the job of a CNN but with defined iterative steps.
                        1' 
b. i)     1          1' 1  1'
        1 1 1      1' 1 1  1 1'    bars are the second level hops 
          1          1' 1  1' 
                        1'
                                                
c. Determining the overall average density of the network by first calculating density at each hop and averaging them.
d. Estimating stickiness using the same approaches as 2c. 
                        
----------------------------------------------------------------------------------------------------------------------------------

5. Calculating perimeter of the structure. 

a. The perimeter of the structure keeps shrinking in size as the density increases. 
b. Estimating stickiness as a function of this perimeter using multiple observations. 
c. Estimating stickiness using the same approaches as 2c.


----------------------------------------------------------------------------------------------------------------------------------

6. Building features for a Machine Learning equation: 

a. Func ( w1*(proportion of nodes with one connection) + w2*(proportion of nodes with two connections) + w3*(proportion of nodes with three connections) + w4*(proportion of nodes with four connection) ) = stickiness

b. The hypothesis is proportion of nodes with one, two, three and four connections would vary with stickiness

----------------------------------------------------------------------------------------------------------------------------------

7. Using all above as features and the target value as stickiness

a. Combining all above approaches as features for a Regression equation (with a scaling factor to normalise the outputs between 0 to 1)

----------------------------------------------------------------------------------------------------------------------------------

8. Find the prob directly? 

----------------------------------------------------------------------------------------------------------------------------------



