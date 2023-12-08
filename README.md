# TRACLUS-for-NN-trajectories
read the pdf Vessel_Future_Location_Prediction_using_Neural_Networks_and_TRACLUS_algorithm.pdf for a full walkthrough<br>
implementing the traclus algorithm on maritime vessels in the sea of Aegean and a fully connected feed forward neural network<br>
Help with data wrangling was provided by user eva-chon and changed where needed<br>  


**##################################inputs########################################################** <br>
given a timeseries of positions<br>
1. it's transformed to a supervised problem with lag 10 [MMSI, TRAJId, dlon(t-10), dlat(t-10), speed(t-10) ,dt(-9),........,dlon(t-1), dlat(t-1), speed(t-1) ,dt(t), dlon(t), dlat(t)]<br>
2. the representative trajectories is a dataframe of characteristic points [row,	tlon, tlat,	t+1lon, t+1lat, tags]<br>
3. thedistances mentioned in 1.1 are a table [pointAid, pointBid, distance, tag of pointA]<br>
4. the cluster representative trajectories are a timeseries [X0,Y0,X1,Y1,...,Xn,yn] there were 3 in total named rtr0, rtr1, rtr2 <br><br><br>

5.   
**##################################STEPS#########################################################** <br>

**0.0 Data wrangling.** <br>
**0.1 a simple fully connected feed forward NN.** <br>
**1.0 Partitioning the trajectories to their respective characteristic points using a line distance formula.** <br>
**1.1 using the same distance formula create a file that contains the distance between every point(ITS A BIIG FILE, in my study of 15000 lines it creates 224,985,000 rows with 4 columns). I didn`t upload it, its the same formula as in 1.0 but its applied to the characteristic line segments.** <br>
**1.2 calculate the hyperparameters epsilon and minlns for the algorithm using the partioned lines and the distances in 1.05.** <br>
**1.3 cluster the data** <br>
**1.4 create the representative trajectories of the clusters, and assign to the rows of the raw timeseries a cluster based on their distance from the rtr closest to them.** <br>
**2.0 apply the same neural network but on clustered data** <br>

     
**REFERENCES** <br>
[1] Punit Rathore, Dheeraj Kumar, Sutharshan Rajasegarar, Marimuthu Palaniswami, and
James C. Bezdek. A scalable framework for trajectory prediction. IEEE Transactions on
Intelligent Transportation Systems, 20(10):3860–3874, 2019.  
[2] Alexandros TroupiotisKapeliaris, Nicolas Zygouras, Manolis Kaliorakis, Spiros Mouzakitis,
Giannis Tsapelas, Alexander Artikis, Eva Chondrodima, Yannis Theodoridis, and Dimitris
Zissis. volume 1, pages 744–751. 1st edition, 2022.  
[3] Eva Chondrodima, Nikos Pelekis, Aggelos Pikrakis, and Yannis Theodoridis. An efficient
lstm neural network-based framework for vessel location forecasting. IEEE Transactions on
Intelligent Transportation Systems, pages 1–17, 2023.  
[4] Panagiotis Tampakis, Eva Chondrodima, Aggelos Pikrakis, Yannis Theodoridis, Kostis
Pristouris, Harry Nakos, Eleni Petra, Theodore Dalamagas, Andreas Kandiros, Georgios
Markakis, Irida Maina, and Stefanos Kavadas. Sea area monitoring and analysis of fishing
vessels activity: The i4sea big data platform. In 2020 21st IEEE International Conference
on Mobile Data Management (MDM), pages 275–280, 2020.  
[5] Eva Chondrodima, Petros Mandalis, Nikos Pelekis, and Yannis Theodoridis. Machine learning models for vessel route forecasting: An experimental comparison. In 2022 23rd IEEE
International Conference on Mobile Data Management (MDM), pages 262–269, 2022.  
[6] Petros Mandalis, Eva Chondrodima, Yannis Kontoulis, Nikos Pelekis, and Yannis Theodoridis. Machine learning models for vessel traffic flow forecasting: An experimental comparison. In 2022 23rd IEEE International Conference on Mobile Data Management (MDM),
pages 431–436, 2022.  
[7] Jae-Gil Lee, Jiawei Han, and Kyu-Young Whang. Trajectory clustering: A partition-andgroup framework. SIGMOD ’07, page 593–604, New York, NY, USA, 2007. Association for
Computing Machinery.  
[8] Angelos Valsamis, Konstantinos Tserpes, Dimitrios Zissis, Dimosthenis Anagnostopoulos,
and Theodora Varvarigou. Employing traditional machine learning algorithms for big data
streams analysis: The case of object trajectory prediction. Journal of Systems and Software,
127:249–257, 2017.  
[9] Simon Haykin. Neural networks: a comprehensive foundation. Prentice Hall PTR, 1998.
42  
[10] Yuan Wang, Dongxiang Zhang, Ying Liu, and Kian-Lee Tan. Trajectory forecasting with
neural networks: An empirical evaluation and a new hybrid model. IEEE Transactions on
Intelligent Transportation Systems, 21(10):4400–4409, 2020.  
