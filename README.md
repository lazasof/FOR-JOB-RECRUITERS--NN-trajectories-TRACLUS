# TRACLUS-for-NN-trajectories
implementing the traclus algorithm on maritime vessels in the sea of Aegean and a fully connected feed forward neural network<br>
Help with data wrangling was provided by user eva-chon and changed where needed<br>
##################################inputs########################################################<br>
given a timeseries of positions<br>
1. it's transformed to a supervised problem with lag 10 [MMSI, TRAJId, dlon(t-10), dlat(t-10), speed(t-10) ,dt(-9),........,dlon(t-1), dlat(t-1), speed(t-1) ,dt(t), dlon(t), dlat(t)]<br>
2. the representative trajectories is a dataframe of characteristic points [row,	tlon, tlat,	t+1lon, t+1lat, tags]<br>
3. thedistances mentioned in 1.1 are a table [pointAid, pointBid, distance, tag of pointA]<br>
4. the cluster representative trajectories are a timeseries [X0,Y0,X1,Y1,...,Xn,yn] there were 3 in total named rtr0, rtr1, rtr2 <br><br><br>
##################################STEPS########################################################<br>
0.0 Data wrangling.<br>
0.1 a simple fully connected feed forward NN.<br>
1.0 Partitioning the trajectories to their respective characteristic points using a line distance formula.<br>
1.1 using the same distance formula create a file that contains the distance between every point(ITS A BIIG FILE, in my study of 15000 lines it creates 224,985,000 rows with 4 columns). I didn`t upload it, its the same formula as in 1.0 but its applied to the characteristic line segments.<br>
1.2 calculate the hyperparameters epsilon and minlns for the algorithm using the partioned lines and the distances in 1.05 .<br>
1.3 cluster the data<br>
1.4 create the representative trajectories of the clusters, and assign to the rows of the raw timeseries a cluster based on their distance from the rtr closest to them.<br>
2.0 apply the same neural network but on clustered data<br>
#REFERENCES<br>
Jae-Gil Lee, Jiawei Han, and Kyu-Young Whang. Trajectory clustering: A partition-andgroup framework. SIGMOD ’07, page 593–604, New York, NY, USA, 2007. Association for
Computing Machinery. https://hanj.cs.illinois.edu/pdf/sigmod07_jglee.pdf
