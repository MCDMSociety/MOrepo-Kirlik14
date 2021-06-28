# Multiobjective Integer Linear Programming Problems -- Originals Taken from [moolibrary](http://home.ku.edu.tr/~moolibrary/)

Originals are taken from [moolibrary](http://home.ku.edu.tr/~moolibrary/) and converted to the fgt format specified below. Note that we do NOT claim to have created these instances, we have only converted them to another format.

## Test instances

Instances are named `Kirlik14_ILP_p-[p]_n-[n]_m-[m]_inst-[id].raw` where 

   - `p` is the number of objectives.
   - `n` is the size of the problem. 
   - `m` is the number of constraints.
   - `id`: Instance id running within the constraint id.

### Fgt format description 

All instance files are given in raw format (a text file). An example is:

```
10 5 4

maxsum maxsum maxsum maxsum 

-10 -100 36 -48 60 16 69 62 20 19
71 86 21 97 34 -8 88 -3 76 67
64 -36 5 6 67 85 76 1 -67 -95
87 -8 92 -3 40 3 48 37 94 80

31 2 66 59 2 64 0 71 64 45
81 36 26 79 55 72 35 41 73 31
94 7 32 45 68 57 21 87 0 19
90 100 99 35 30 -52 99 88 26 7
0 54 51 54 0 27 48 83 -17 44

1 394
1 419
1 341
1 492
1 295

0 0 0 0 0 0 0 0 0 0 
100 100 100 100 100 100 100 100 100 100 
```

The general format is defined as: 

```
n m p

objectiveTypes

objectiveCoefficientMatrix

constraintMatrix

rHSMatrix

lbVector
ubVector
```

where:

   - `n` is the number of variables.
   - `m` is the number of constrains.
   - `p` is the number of objectives.
   - `objectiveTypes` is the nature of the objectives to be optimized. An identifier should be 
   added for each objective, and it should be done in the same order as in the objective matrix. 
   Four types are supported:
      	* maxsum: maximise a sum objective function
      	* minsum: minimise a sum objective function
   - `objectiveCoefficientMatrix` is a p x n matrix defining the coefficients of the objective functions
   - `constraintMatrix` is a m x n matrix defining the coefficients of the constraints
   - `rHSMatrix` is a m x 2 matrix defining the right-hand side of the constraints. 
   For each constraint, two numbers are required:
      * The second number is the actual value of the right-hand side of the constraint
      * The first number is an identifier that is used to define the sign of the constraint. 
      Three identifiers can be used: 0 for >= constraints, 1 for <= constraints and 2 for = constraints.
   - `lbVector` is a vector of size n containing the lower bound of each variable.
   - `ubVector` is a vector of size n containing the upper bound of each variable.
