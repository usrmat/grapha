
=======
Grapha
=======

Welcome to the Grapha project, a new graph based modelling package. 
Grapha allows you to analyse MIL (Multiple Instance Learning) problems 
without conforming to the MIL standard assumption. It also circumvents high dimensionality, 
incompatibility with null values, and instance irregularities.

Data format
-----------

The format of your graph data must be a list with vertex data in the form 
list[dict(node_type: node_value)] ,e.g. [{'systolic_bp': 120}, {'diastolic_bp': 80}]. If the 
data is time-bound then a 

It is a priority to support automatic transformation from a data table to the Grapha compatible
data format as described above in the near future. You will then be able to simply 
submit a dataframe or another table format and a discriminator that will be used to generate
the separate graphs.

How does Grapha work
--------------------

Grapha agnostically represents data and learns what graph properties mean in the context of 
the training data. It is currently limited to categorization tasks. The graphs are 
bi-directed to accomodate assymmetrical correlations.

Each instance is seen as a single node in the graph, with a numeric or categorical value. 
Grapha then trains on the provided data to categorize based on subnet similarities which 
uses the number of subnets, vertex value correlations, and weight per subnet similarity which 
is determined similarily as linear regression. Eventually Grapha consolidates a set of weights 
for possible subnets that can occur, the smallest being subnet of 1 vertex, which means there 
are at least V subnets where V are the number of features.

Grapha uses date-time values to decide connectivity between vertices.


