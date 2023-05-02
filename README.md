# TRACLUS-for-NN-trajectories
implementing the traclus algorithm on maritime vessels in the sea of Aegean and a fully connected feed forward neural network<br>
##################################STEPS########################################################<br>
0.0 Data wrangling.<br>
0.1 a simple fully connected feed forward NN.<br>
1.0 Partitioning the trajectories to their respective characteristic points using a line distance formula.<br>
1.1 using the same distance formula create a file that contains the distance between every point(ITS A BIIG FILE, in my study of 15000 lines it creates 224,985,000 rows with 4 columns[pointA id, pointB id, distance, tag of pointA]). I didn`t upload it, its the same formula as in 1.0 but its applied to the line segments.<br>
1.2 calculate the hyperparameters epsilon and minlns for the algorithm using the partioned lines and the distances in 1.05 .<br>
1.3 cluster the data<br>
1.4 create the representative trajectories of the clusters, and assign to the rows of the raw timeseries a cluster based on their distance from the rtr closest to them.<br>
2.0 apply the same neural network but on clustered data<br>
