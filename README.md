# TRACLUS-for-NN-trajectories
implementing the traclus algorithm on maritime vessels in the sea of Aegean and a fully connected feed forward neural network
##################################STEPS########################################################
0.1 Data wrangling.
0.2 a simple fully connected feed forward NN.
1.0 Partitioning the trajectories to their respective characteristic points using a line distance formula.
1.05 using the same distance formula create a file that contains the distance between every point(ITS A BIIG FILE, in my study of 15000 lines it creates 224,985,000 rows with 4 columns[pointA id, pointB id, distance, tag of pointA]).
1.1 calculate the hyperparameters epsilon and minlns for the algorithm using the partioned lines and the distances in 1.05 .
1.2 cluster the data
1.3 create the representative trajectories of the clusters, and assign to the rows of the raw timeseries a cluster based on their distance from the rtr closest to them.
2.0 apply the same neural network but on clustered data


