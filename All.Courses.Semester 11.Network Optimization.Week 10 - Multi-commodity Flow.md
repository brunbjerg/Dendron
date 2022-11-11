---
id: rc8qgny3fmoxgas6hdn5bfr
title: Week 10 - Multi-commodity Flow
desc: ''
updated: 1668155375234
created: 1668151872827
---
Each edge has a capacity $u_e$ and a unit transpotation cost $c_e$. K mommodities are given. 

Applications: 
* Communication neyworks
* Computer networks
* Transportation network
* Foodgrain export-import


Warehousing: 

![](/assets/images/2022-11-11-08-40-57.png)

There are k commodities, which are sent from the sources s to the time periods 1 to 4. Since we are using time periods node 1 can send its commodities on to node 2. 

MIP formulation of the Multi-commodity flow problem.

![](/assets/images/2022-11-11-08-45-12.png)

We have demand constraints for the starting node and for the terminal. Flow conservation constraints and capacity constraints.

MCF: Multi-commodity flow
* Congestion objective function: non-linear
* Splitable: A group of commodities 
* Unsplitable: A container should be send at one unit if it is larger than one TEU. K-splitable

## Structure of LP model

![](/assets/images/2022-11-11-08-53-29.png)

Multi-commodity flow problem cannot use the same structure. There are not one upper bound associated with each edge. 

## Fractional solutions

![](/assets/images/2022-11-11-08-55-47.png)

We can somehow send fractional commodities through the network. Sending a half through the network will be a better solution. 

MCF: Each commodity can only have one source and terminal. We can make a supersource with cost zero on each edge and a corresponding capacity equal to the demand for each subsource that the supersource is connected to. If we solve the MCF problem, we can solve all network flow problems, since they are simply deriviations of the MCF problem. 

## Decomposition
Making a two-stage problem. Master stage


![](/assets/images/2022-11-11-09-04-50.png)

Stage 1: 
* Writing down all the different paths for each commodity together with the cost for each path. Path formulation.
* The formulation have the cost for each edge 
* The sum of the decision variables should be equal to the demands of the terminals.
* There is a coeffecient for each edge that is used in a path. 

![](/assets/images/2022-11-11-09-11-03.png)

Danzig-wolf decomposition. This problem has much fewer constraints, one constraint for each edge. We set the flow greater or equal to the demands this is done so that the dual variable can only be positive instead of laying in the reals. To many paths, generate them iteratively. Master problem that takes care of the capacities and subproblem for each path. 


## Example
All possible paths:


![](/assets/images/2022-11-11-09-15-24.png)


First iteration: We get a solution, together with the dual variables. Duals are important since they tell us how we can save cost in the objective function. 

Reduced cost $c_p = \sum_{i,j \in p} (c_{i,j} - y_{i,j}) - y^*_k$

Start with an initial solution.

Dual variables tell how expensive an edge is

Subtract dual variable from path cost. Path costs are found using dijkstras algorithm. 

In general:
* Interaction between master problem and subproblem
* Add all paths with negative reduced cost to master problem
* Stavilization: Dual variables may fluctuate in the beginning, add soft sonstraints to dual variables.



We just want the dual solution. 
