# BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA
ABSTRACT

Hyperspectral images provide a wealth of information by capturing a large number of spectral
bands for each pixel in an image. The richness of information captured by hyperspectral images
is not only a powerful tool for scientific researchers but also comes with its natural limitations
popularly called the Curse of Dimensionality.
This paper gives an improved version of band selection for this problem. For the removal of
redundancy, we first perform band subspace decomposition in a unique way using the two most
impactful features. For the optimization of band selection, the metaheuristics, and the swarmbased algorithms are found to be convenient so in this paper we use the Artificial Bee Colony
algorithm using entropy and classification to determine fitness.
With the obtained band set, we classify the data using, a support vector machine (SVM) with
five-fold cross-validation. It is performed on the Indian Pines dataset. Three performance
measures, namely, overall accuracy (OA), average accuracy (AA), and kappa coefficient (KC),
are used to assess the classification results. The results show better accuracy and classification
scores.

Chapter:- Introduction

Hyperspectral images capture information about objects of interest from broad, narrow
electromagnetic bands. Compared to RGB images, these bands can provide more spectral and
image information, better describe the properties of objects, and improve the search and
analysis ability [1.]
Technology has improved due to the advancement of imaging spectrometers With the
advancements, accurate hyperspectral sensors can now detect ground objects on the earth's
surface. It huge number of narrow bands to record its spectral reflectance [2]. Due to their high
spectral resolution, the resulting hyperspectral images (HSI) can use a slightly different spectral
difference to better distinguish the ground. Biophysical parameter retrieval [3], precise
classification of complex environments [4] small detection [5] etc. It is useful for many
practical applications such as but the amount of information generated by the Hang Seng Index
is huge. High accounting results aid in quick working.
Most HSI applications include:
● Detailed Information: HSI provides very detailed information about objects and
materials in images. It breaks down the colours of light into many narrow slices, like a
rainbow, allowing us to see unique features.
● Material Identification: With HSI, we can tell different materials apart, even if they
look similar to the naked eye. For example, it helps us distinguish between healthy and
unhealthy plants.
● Environmental Monitoring: HSI helps scientists keep an eye on the environment. They
can track changes in forests, oceans, and urban areas, helping to protect and manage
our planet better.
● Resource Exploration: It's used to find valuable resources like minerals and oil
underground. By looking at the colours of light reflected from the Earth's surface, we
can guess what's underneath.
● Agriculture: Farmers use HSI to check on their crops. It can spot problems early, like
diseases or pests, so farmers can take action to save their plants.
● Quality Control: Industries use HSI to make sure their products are good. For example,
in food production, it can find defects or contamination.
● Medical Imaging: In medicine, HSI can help doctors see more details in tissues and
organs, improving diagnosis and treatment.

1.1 Need for dimensionality reduction

Large datasets also enable image processing algorithms designed for a wide range of image
quality. Especially in the case of the high level of HSI data brought about by the "curse of
dimensionality" problem, that is, in a specific small set of training samples, the distribution of
HSI data decreases as the size of the HSI data increases. Writing multiple training models is
costly, time-consuming, or most other times, impossible. Therefore, dimensionality reduction
methods and methods for processing hyperspectral images need to be developed [6][7].
Adjacent bands have a very high correlation in the Hyperspectral dataset and some spectral
bands may not carry discrimination information in certain applications [8], [9]. Hyperspectral
reduction can be achieved through band selection or feature extraction [10]. Feature extraction
transforms the original data into another feature space in some models [11], [12]. Most linear
extraction methods provide all raw materials, which may affect the interpretation of results if
the resulting methods are not suitable [13]. Band selection selects the desired band group from
the original bands and effectively stores the content of the spectral channel [14].
Many types of algorithms can solve optimization problems [15]. These are heuristics and
metaheuristics, we will focus on metaheuristics. Metaheuristic algorithms; Evolutionary
algorithms are divided into group-based algorithms and trajectory-based algorithms. A groupbased algorithm was adopted in this study. Some examples of swarm-based algorithms include
Artificial Bee Colony Optimization (ABC), Ant Colony Optimization (ACO), Firefly
Algorithm (FA), and Particle Swarm Optimization (PSO) [16]. This article focuses on ABC
because it is a new development and is more effective than other methods [17]. Genetic
algorithms can search the world, but there is also the problem of population integration. The
DE algorithm was proposed to solve the local search incompleteness problem of GA. The PSO
method has the advantage of fast convergence and less communication, but this method easily
converges to the local minimum. Kabora proposed the ABC algorithm in 2005 [17]. The main
advantage of this algorithm is that both global and local searches are performed in each
iteration, thus increasing the chances of finding the optimal solution.
The bee swarm is based on the ABC algorithm: special bees (forager bees), spectator bees
(observer bees), and scout bees. There is only one special bee in each food. In other words, the
feeding area and the number of rented bees are the same. Bees recruit as guards from abandoned
foraging grounds, without searching for new food. Worker bees in the field exchange
information with observer bees so that observer bees can choose the food they will dig.
To increase optimization efficiency and speed up the process, we first group the similar bands.
Among unsupervised band selection techniques, band classification [18, 19], band grouping
[20,21], and band subspace decomposition [22] are often used to select the most common band
selection methods. band selection and correlation between frequency bands.
Unlike the integration method, in each subspace group, one or more groups are selected to
represent the spectral information of the subspace, and the continuous spectral features of the
HSI are unfortunately truncated. Bands in the same group are similar or related to each other,
while bands in different groups are similar or unrelated. Existing subspace decomposition
methods can be summarised as follows:
● General subspace decomposition
● Spectrum-based subspace decomposition
● Adaptive subspace decomposition (ASD) [23]

1.2 Overview of Artificial Bee Swarm (ABC ) Algorithm 

Natural bee colonies usually have three types of bees foraging; these are hired bees, onlooker
bees, and scout bees (onlooker bees and scout bees are also called putting bees out of work).
Bees forage around food recall while feeding food information to the monitor. Foragers tend
to choose the right food from those produced by hired bees and then forage around the selected
food. Scouts are a group of hired bees that leave food and find new ones. In short, finding food
for bees is done by worker bees, onlooker bees, and scout bees. Karaboğa [7] recently
developed an ABC algorithm for numerical optimization by simulating the foraging behaviour
of bees.

![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/8ba937ba-192f-4a3c-8e40-2eabc391e59e)

Chapter 2:- Literature Review

Representative Band Selection for Hyperspectral Image Classification[21].In the method
proposed in this study, we use the non-uniform data to measure the distance between two bands.
For band selection, all spectral bands are the first group and representative groups are selected
from this group. Unlike existing cluster selection methods that pick multiple rows from each
cluster separately, this method focuses on selecting multiple representatives simultaneously by
looking for the correlation between all frequency groups. Selecting the best representative
group is based on the process of reducing the distance within each group and increasing the
distance between different representatives. These bands selected can also be used for
segmentation of hyperspectral images.
Unsupervised band selection based on artificial bee colony algorithm for hyperspectral image
classification[23]. Based on improved subspace decomposition (ISD) and artificial bee colony
(ABC) developed to solve residual reduction problems in HSI classification, This article
introduces a cluster selection ISD -Method called ABC. Subspace decomposition is done by
calculating the correlation coefficient between adjacent bands and using the results found in
the HSI spectrum curve. The bee colony algorithm was first used to optimize the combination
of selected scores by ISD and maximum entropy (ME).
Band selection is a simple, clear and useful way to reduce redundancy by selecting some
expressions and different expressions from the actual HSI rectangle Square band. A lot of
frequency band selection methods have been proposed in recent years, but most of them only
consider the repetition of frequency bands and do not care about the information in the
frequency selection band. Additionally, these algorithms do not take into account the relevant
hyperspectral process. Based on this information , we propose a new method for selecting
hyperspectral scores via adaptive subspace segmentation (ASPS). Its main contributions are:
1) Using ASPS, the hyperspectral cube is divided into several subcubes by increasing the ratio
of individual classes to distant classes; 2) Unlike the previous method, we estimate the
frequency band. Noise and select each cube; the frequency band with the least noise in the cube
(high-frequency band) is used to represent all subcubes; 3) Adaptive subspace partitioning is
considered a general model, thus creating a gap . .
Unsupervised feature selection based on maximum information and minimum redundancy for
hyperspectral images[25]. Useful subset is a very difficult problem when class labels are not
available. MJMI (MJMI) is defined to select features that preserve the most important
information to the maximum extent. Since the high-order contribution in MJMI is difficult to
calculate, the maximum information and minimum redundancy (MIMR) technique is derived
from the low-order contribution of MJMI. From the perspective of the literature, many classical
unsupervised feature selection methods can also be considered a low-rank version of MJMI.
Compared to them, MIMR should have a loose estimate.
Unsupervised intrusion feature selection based on genetic algorithm and FCM[26].
Unsupervised intrusion detection feature selection based on genetic algorithm (GA) and fuzzy
C-means clustering (FCM) is proposed. This method uses genetic algorithms as a search
strategy and uses FCM to classify unique data. Then, the best feature subset and clustering
parameters are found and used for unsupervised intrusion detection. Experimental results show that this method can solve the feature selection problem and algorithm parameter optimization
problem in intrusion detection, and has better detection than traditional unsupervised intrusion
detection.
Band selection focuses on selecting a minimal number of bands so as to reduce redundancy but
also ensures to preserve the essential spectral information of the elements on the ground. In this
study, current hyperspectral band selection methods are discussed, which can fall into six main
types : ranking-based, searching-based, clustering-based, sparsity-based, embedding-learningbased, and hybrid-scheme-based. The two most popular hyperspectral data sets, the study
demonstrates the performances, comparisons , and also notes the challenges faced .
Some modifications of the ABC algorithm are general and can be applied to many problem
domains, while few of them can be application-dependent. This paper proposes a modified
version of the ABC algorithm named, MABC-SS (modified artificial bee colony algorithm
with selection strategy), which is general and not any application dependent thus can be used
in many areas . Based on the results of previous iterations, the algorithm gets updated based on
the initial population and bee location updates using old and new food sources.A new method
called convergence rate is used to evaluate options . In any optimization algorithm, global
optimality can be achieved well by proper way of population initialization. The algorithm
proposed in the paper uses stochastic and attack-based learning techniques to initialise the
population and update the position of bees after exceeding some parameters. The cost of the
change is calculated using the average cost of the previous two iterations and compared to the
model using the current iteration to achieve the best results[28].

Chapter 3:- Methodology

3.1 Working Principle:

In this paper, we have first converted the data cube (3d data cube) of dimensions X, Y, and Z
denoting length, width, and height into 2D which have dimensions of ((X x Y) x Z). Here length
and width denote pixels of each band and height as bands. This helps us in further calculations
which eases out the process.
Fuding Xie et al.[23] presented this idea that we divide the bands into subspaces that have
similar characteristics. This similarity is calculated based on the correlation coefficient and
spectral reflectance.

![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/cc3bdbe8-485c-4e31-b7e9-1558a3e86882)

3.1.1 Correlation Coefficient:-

Let there be N bands in the images so we calculate the correlation coefficient between adjacent
bands which represents the similarity of pixels of a band at certain special positions with
different bands. It is calculated as follows:-
 𝑅𝑖𝑗 =
∑
𝑛
𝑘 = 1
(𝑏𝑖𝑘 − 𝑏𝑖
)(𝑏𝑗𝑘 − 𝑏𝑗
)
√∑𝑛
𝑘=1
(𝑏𝑖𝑘 − 𝑏𝑖
)
2 ∑𝑛
𝑘=1
(𝑏𝑗𝑘 − 𝑏𝑗
)
2

(1)

![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/8b5a11ca-9858-427b-8cc2-fda5a6936f74)

Here bi = band images and bi have n pixels. So, bik = kth pixel in the ith image represents the
mean of bi and bj respectively. Then we plot it and on the observation basis, we get to know
that just with this we cannot divide the whole band space into subspaces as we have got a lot
of local minima in between which further increases the subspace divisions.
For that, we are going to use spectral reflectance to remove this difficulty.
Spectral reflectance basically helps in subspace segmentation with the help of spectral
properties. This property considers only spectral characteristics and overlooks the local
characteristics of our dataset. Like Visible light, infrared, etc.
We get there are 7 breakpoints in the space and we get there are 6 subspaces in the 200 bands. 

![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/2c42b6c4-78b9-4f82-88b5-e400fa1a38d8)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/5d13d809-938c-4ea7-b454-ccd287f487bc)

Ranges are like this :- 1~36, 37~61, 62~75, 76~103, 104~144, 145~200.

This is how we are doing subspace decomposition in the bands. Now we will move to take
some representative bands from each subspace. The criteria that we are going to use is
Maximum Entropy. 

3.1.2 Maximum Entropy

In information theory, Shannon entropy is the basic unit of information contained in band bi.
The formula is as follows:-
 𝐸(𝑏𝑖) = − ∫𝑏𝑖
𝑝(𝑏𝑖) 𝑙𝑜𝑔 𝑝(𝑏𝑖) 𝑑𝑏𝑖
 (2)
 ![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/7fafba3a-1bc1-4243-9516-a9649373d2f4)
𝐸(𝑏)Here p(bi) = probability density function(pdf) of band bi.
To increase the information gain, we select the bands with high information[19]. So we do
band selection and the information in band subset ‘B’ is calculated by taking the average of the
entropy of all the bands in B. The important thing is the better the value of this average the
better the classification ability of the bands in B[1].
All these pre-processing helps the ABC search algorithm to converge at a faster rate.

3.1.3 Artificial Bee Colony:

Population Initialization: The initial population A consisting of N food sources is generated.
A food source is formed by picking k bands at random from each subspace decomposed. This
is repeated N times to initialise the population. Each food source
𝑎𝑖
0 = 𝑎𝑖
𝑚𝑖𝑛 + 𝑐𝑒𝑖𝑙[ 𝑟𝑎𝑛𝑑 𝑥 (𝑎𝑖
𝑚𝑎𝑥 − 𝑎𝑖
𝑚𝑖𝑛)] (3) 
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/729c3336-35ef-4ab8-825f-fbf8ea2dd9bd)
Fitness calculation :- The fitness of a food source represents the quality of the food source as
a solution . The better the fitness, the better its classification ability. In this paper, three types
of fitness functions have been tested.
1. Based on Maximum Entropy
2. Based on Classification Error
3. Based of the combination of Maximum Entropy and Classification Accuracy
Population Updating: Every food source of the population is updated in an iteration.
Such updation is performed in every iteration. The population is sorted based on fitness
values in descending order and then it’s divided into two phases, The first half is sent
through the employed bee phase and the rest to the onlooker bee phase, and each goes
through its specific updation methods and based of their fitness values the food sources
with better fitness are retained. The fitness of a food source is calculated as the mean of entropies of the bands in it.
𝑭𝒊 =
𝟏
𝑺
∑
𝑺
𝒋 = 𝟏 𝑬(𝒂𝒊𝒋) (4)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/02f0b310-8602-4dcf-a50a-90ba17979515)
Employee Phase: In this phase, a(i) being our current food source, a neighboring food source
is selected a(t), and a new food source is generated randomly by replacing a random band j in
the original food source according to the formula below.
If the fitness of the newly generated is found to be greater than the original , the food source is
replaced with a new food source.
𝑉(𝑗) = 𝑎
𝑡
𝑖
(j) + ceil[(-1 + 2 rand) x (𝑎
𝑡
𝑖
(j) - 𝑎
𝑡
𝑘(j))] (5)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/74ab94cc-3510-4f05-a5a3-9da6e8597c53)
Onlooker Phase: The onlooker phase works the same as employee phase except that the
neighbour food source has to be from employee bee food sources and the selection of the
neighbour is done by using roulette wheel selection method , so as to ensure the food sources
with higher fitness have more probability of being picked.
The probability of a food source in roulette wheel selection is calculated as follows
 𝑷𝒊 =
𝑭𝒊
∑
𝑵/𝟐
𝒊=𝟏
𝑭𝒊

(6)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/b260fd75-4fb9-4781-bb09-6a7392065972)
Scout Phase: The solutions (food sources) that haven’t been able to update since a long time
are thrown out and new food sources are generated in their place

Chapter 4:- Experimental Results

4.1 Data Set:

We have Indian Pines as a data set[46]. The image was taken from an Airborne Visible/Infrared
Imaging Spectrometer sensor(AVIRIS). This data set is of dimension 145 x 145 (pixels of each
band) and 220 bands of which 200 are left after correction. There are 16 classes present in the
dataset. https://purr.purdue.edu/publications/1947/1.

4.2 Performance Evaluation:

In this section, we will analyse the performance of several experiments that we will get on our
data set of Indian pines. We are taking a SVM classifier with a test size of 0.2. We are using 3
performance evaluation metrics which are:
● Overall Accuracy: 𝐶𝑜𝑟𝑟𝑒𝑐𝑡𝑙𝑦 𝑐𝑙𝑎𝑠𝑠𝑖𝑓𝑖𝑒𝑑 𝑝𝑖𝑥𝑒𝑙𝑠
𝑡𝑜𝑡𝑎𝑙 𝑛𝑢𝑚𝑏𝑒𝑟 𝑜𝑓 𝑡𝑒𝑠𝑡𝑠
 (7)
 ![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/ea200481-8670-4d83-a161-73fb285630e2)
● Average Accuracy:
∑
𝑛
𝑖 = 1
𝐶𝐴 𝑖
𝑛
(8)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/d2d5680a-fa3e-4a38-b5ec-3e4df62c290a)
● Kappa Coefficient: A statistical measurement of agreement between the final
classification and the ground truth.
 𝑲 =
𝑷𝟎 − 𝑷𝒆
𝟏 − 𝑷𝒆
 (9)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/05f093ae-a669-4c82-b6e8-a1e1ad871ad5)
Comparison tables between
1. Normal ABC and with subspace decomposition before ABC
2. Using two types of fitness functions
● Maximum Entropy (f1)
● Classification Error (f2)
k here signifies the number of bands selected from each subspace and for without subspace, we
will take k*6 for easy understanding.
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/e4fb5ef8-7279-4e1f-b5ca-5692b2a33919)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/879ab50b-264f-4453-a9bb-415deee38231)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/27ac8077-a80e-4c26-b9c1-6fa8b9e19f4e)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/0d92fd4e-79b1-4419-a8b6-ebf285aacd0c)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/011b1c79-2f8f-407d-b774-da3e15537a39)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/64c35fe4-39cc-4879-b4ec-842fbad8547d)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/d6428d4b-779c-43aa-9117-ccfbc3ac24fa)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/2584e6d6-3068-494d-b8b6-ecfacef7dc4c)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/337e333f-78f3-423c-9bb6-3673ad78b301)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/c30f918a-92b7-43e8-9dc3-856d18ee0435)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/f3a46fcc-288f-46f6-8355-0ddd2af86d67)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/dbc53a5d-9bc2-460d-9954-410991d2725b)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/23609203-3f1f-4db7-b740-5b7b33903c84)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/eb81a7c5-2e79-4d2f-a7ec-756cc9bf73af)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/61a13abc-69ac-4863-80d2-705fdf988cdf)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/116cc4b0-c24b-4219-bb12-ca2be0e0c137)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/25b373ea-d694-4d5e-bc1f-acb8e43b3100)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/d27ae289-aed8-49a6-a6b1-b1f6c965fb93)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/113cc136-c943-4e00-b0e8-3b489162e165)
![image](https://github.com/whitetiger00001/BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA/assets/106367985/d1169e3b-9866-4a33-b406-9da18dfea25c)

Chapter 5 :- Conclusion

To face the trouble of the Hughes phenomenon, that is the decrease in classification ability as
the number of features increases, increasing the redundancy, we try to try out various numbers
of bands to decide the optimal range of bands we can choose. This is achieved by performing
a large number of experiments taking lots of time in computing.
In hyperspectral data, the band subspace decomposition further answers the redundancy by
clustering similar bands together, but with existing methods of decomposing yet are known to
have much redundancy.
The best way found out was to divide the regions not only by computational measure of
correlation coefficient alone but also using the characteristic measure of spectral reflectance.
This is called the improved subspace decomposition method. The improved decomposition is
followed by the Artificial bee colony algorithm to determine the most optimal and informative
band combination.
Classifications show significantly improved performances with subspace decomposition to
without decomposition. The results clearly depict the increase in classification ability as the
number of bands increases from 1 to 5 and tends to drop between 6 to 8 and in percentages, the
best round percentage is between 20 and 30. 

Future Scope

Further investigation of selecting the most optimal bands may be considered . Using other spatial
methods for information estimation, different band subspace decomposition methods can add to the
performance of ABC algorithm.
Using other optimization strategies instead of artificial bee colony algorithm might also be a possibility
for improvement. All these form the future scope for this study . 







