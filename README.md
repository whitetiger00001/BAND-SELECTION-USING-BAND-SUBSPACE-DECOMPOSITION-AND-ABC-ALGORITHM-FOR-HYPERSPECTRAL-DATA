# BAND-SELECTION-USING-BAND-SUBSPACE-DECOMPOSITION-AND-ABC-ALGORITHM-FOR-HYPERSPECTRAL-DATA
Abstract
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
7
Chapter 1: Introduction
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
8
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
9
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
Figure 1.1 Indian Pines Data Cube
Chapter 2:- Literature Review
10
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
parameters are found and used for unsupervised intrusion detection. Experimental results show
11
that this method can solve the feature selection problem and algorithm parameter optimization
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
12
In this paper, we have first converted the data cube (3d data cube) of dimensions X, Y, and Z
denoting length, width, and height into 2D which have dimensions of ((X x Y) x Z). Here length
and width denote pixels of each band and height as bands. This helps us in further calculations
which eases out the process.
Fuding Xie et al.[23] presented this idea that we divide the bands into subspaces that have
similar characteristics. This similarity is calculated based on the correlation coefficient and
spectral reflectance.
Figure 3.1. Flow Diagram of the proposed methodology.
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
Here bi = band images and bi have n pixels. So, bik = kth pixel in the ith image represents the
mean of bi and bj respectively. Then we plot it and on the observation basis, we get to know
that just with this we cannot divide the whole band space into subspaces as we have got a lot
of local minima in between which further increases the subspace divisions.
For that, we are going to use spectral reflectance to remove this difficulty.
Spectral reflectance basically helps in subspace segmentation with the help of spectral
properties. This property considers only spectral characteristics and overlooks the local
characteristics of our dataset. Like Visible light, infrared, etc.
We get there are 7 breakpoints in the space and we get there are 6 subspaces in the 200 bands.
13
Figure 3.2. Graphs of Correlation Coefficient and Spectral Reflectance.
Ranges are like this :- 1~36, 37~61, 62~75, 76~103, 104~144, 145~200.
14
This is how we are doing subspace decomposition in the bands. Now we will move to take
some representative bands from each subspace. The criteria that we are going to use is
Maximum Entropy.
3.1.2 Maximum Entropy
In information theory, Shannon entropy is the basic unit of information contained in band bi.
The formula is as follows:-
 𝐸(𝑏𝑖) = − ∫𝑏𝑖
𝑝(𝑏𝑖) 𝑙𝑜𝑔 𝑝(𝑏𝑖) 𝑑𝑏𝑖
 (2)
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
with better fitness are retained. The fitness of a food source is calculated as the mean of
15
entropies of the bands in it.
𝑭𝒊 =
𝟏
𝑺
∑
𝑺
𝒋 = 𝟏 𝑬(𝒂𝒊𝒋) (4)

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
Scout Phase: The solutions (food sources) that haven’t been able to update since a long time
are thrown out and new food sources are generated in their place
Chapter 4:- Experimental Results
4.1 Data Set:
16
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
● Average Accuracy:
∑
𝑛
𝑖 = 1
𝐶𝐴 𝑖
𝑛
(8)
● Kappa Coefficient: A statistical measurement of agreement between the final
classification and the ground truth.
 𝑲 =
𝑷𝟎 − 𝑷𝒆
𝟏 − 𝑷𝒆
 (9)
 Comparison tables between
1. Normal ABC and with subspace decomposition before ABC
2. Using two types of fitness functions
● Maximum Entropy (f1)
● Classification Error (f2)
k here signifies the number of bands selected from each subspace and for without subspace, we
will take k*6 for easy understanding.
Table 1. Class-wise accuracies for k = 1
Without Decomposition With subspace decomposition
Classes F1 F1 F1 F2
0 0.901160093 0.898120214 90.58% 0.895799489
17
1 0.111111111 0.133333333 0.00% 0.2
2 0.322807018 0.518909411 23.86% 0.575197889
3 0.054216867 0.1015625 0 0.234375
4 0 0.113513514 0.021276596 0.12972973
5 0 0.008152174 0 0.108695652
6 0 0 0 0
7 0 0.380952381 0 0
8 0.864583333 0.799472296 0.791666667 0.627968338
9 0 0 0 0
10 0.118556701 0.202275601 0.164948454 0.127686473
11 0.771894094 0.609235353 0.82892057 0.646474677
12 0 0 0 0.033195021
13 0 0 0 0
14 0.181818182 0.312063809 0.098814229 0.273180459
15 0.025974026 0 0.012987013 0
16 0.684210526 0.697368421 0.736842105 0.776315789
Table 2. Class-wise accuracies for k = 2
Without Decomposition With subspace decomposition
Classes F1 F1 F1 F2
0 0.889108 0.88006 0.8876 0.894328
1 0.297297 0.243243 0.378378 0.378378
2 0.438704 0.394046 0.56042 0.581436
3 0.206325 0.245482 0.10994 0.111446
4 0.078947 0.157895 0.073684 0.005263
5 0.222798 0.007772 0.272021 0.165803
6 0.032534 0.119863 0.037671 0.078767
7 0.409091 0 0 0
8 0.856397 0.72846 0.83812 0.770235
9 0 0 0 0
10 0.494859 0.395887 0.394602 0.239075
11 0.748473 0.721996 0.707739 0.671079
12 0.059072 0.080169 0.175105 0.21097
13 0.04878 0 0.006098 0.115854
14 0.339921 0.374506 0.3083 0.201581
15 0.003236 0 0 0
16 0.905405 0.797297 0.837838 0.716216
Table 3. Class-wise accuracies for k = 3
18
Without Decomposition With subspace decomposition
Classes F1 F1 F1 F2
0 0.883062645 0.876421443 86.82% 0.872940357
1 0.555555556 0.2 44.44% 0.466666667
2 0.540350877 0.583992964 60.70% 0.571679859
3 0.295180723 0.3046875 0.331325301 0.365625
4 0.212765957 0.27027027 0.255319149 0.254054054
5 0.237113402 0.293478261 0.134020619 0.336956522
6 0.267123288 0.13973064 0.342465753 0.116161616
7 0.166666667 0.238095238 0.5 0.238095238
8 0.927083333 0.817941953 0.927083333 0.873350923
9 0 0 0 0
10 0.520618557 0.374209861 0.597938144 0.461441214
11 0.729124236 0.654915591 0.741344196 0.598311817
12 0.344537815 0.107883817 0.218487395 0.195020747
13 0.292682927 0.207317073 0.56097561 0.280487805
14 0.339920949 0.380857428 0.399209486 0.366899302
15 0 0.006557377 0 0.045901639
16 0.736842105 0.552631579 0.631578947 0.815789474
Table 4. Class-wise accuracies for k = 4
Without Decomposition With subspace decomposition
Classes F1 F1 F1 F2
0 0.874145 0.871245 0.863589 0.866721
1 0.540541 0.621622 0.486486 0.72973
2 0.612084 0.587566 0.591944 0.578809
3 0.35241 0.286145 0.406627 0.371988
4 0.221053 0.073684 0.421053 0.1
5 0.38601 0.331606 0.352332 0.411917
6 0.289384 0.383562 0.244863 0.357877
7 0.636364 0.454545 0.409091 0.772727
8 0.835509 0.877285 0.819843 0.765013
9 0.0625 0.0625 0.25 0.125
10 0.453728 0.501285 0.493573 0.482005
11 0.686354 0.697047 0.693992 0.710794
12 0.35865 0.312236 0.314346 0.261603
13 0.560976 0.170732 0.268293 0.603659
14 0.222332 0.405138 0.350791 0.349802
15 0 0.012945 0.067961 0.05178
16 0.783784 0.662162 0.662162 0.810811
Table 5. Class-wise accuracies for k = 5
Without Decomposition With subspace decomposition
19
Classes F1 F1 F1 F2
0 0.859860789 0.850661406 87.19% 0.865862149
1 0.888888889 0.733333333 77.78% 0.6
2 0.624561404 0.622691293 70.88% 0.671064204
3 0.421686747 0.371875 0.481927711 0.4
4 0.319148936 0.335135135 0.446808511 0.297297297
5 0.206185567 0.410326087 0.432989691 0.491847826
6 0.589041096 0.297979798 0.534246575 0.671717172
7 0.5 0.523809524 0.333333333 0.333333333
8 0.875 0.883905013 0.916666667 0.870712401
9 0.5 0 0.5 0.153846154
10 0.613402062 0.512010114 0.608247423 0.498103666
11 0.725050916 0.661866931 0.714867617 0.649453823
12 0.403361345 0.203319502 0.352941176 0.321576763
13 0.12195122 0.396341463 0.609756098 0.780487805
14 0.415019763 0.420737787 0.470355731 0.362911266
15 0.012987013 0.016393443 0.012987013 0.009836066
16 0.736842105 0.618421053 0.631578947 0.736842105
Table 6. Class-wise accuracies for k = 6
Without Decomposition With subspace decomposition
Classes F1 F1 F1 F2
0 0.864053 0.858021 0.860457 0.866257
1 0.810811 0.675676 0.702703 0.72973
2 0.644483 0.654991 0.645359 0.628722
3 0.402108 0.459337 0.379518 0.379518
4 0.268421 0.305263 0.336842 0.278947
5 0.432642 0.445596 0.406736 0.481865
6 0.52911 0.578767 0.683219 0.462329
7 0.318182 0.545455 0.5 0.636364
8 0.848564 0.801567 0.845953 0.853786
9 0.125 0.0625 0.125 0.25
10 0.512853 0.510283 0.550129 0.497429
11 0.64002 0.650713 0.657332 0.689409
12 0.462025 0.400844 0.449367 0.411392
13 0.579268 0.72561 0.713415 0.890244
14 0.417984 0.453557 0.459486 0.405138
15 0.009709 0.003236 0.042071 0.038835
16 0.783784 0.851351 0.72973 0.810811
Table 7. Class-wise accuracies for k = 7
Without Decomposition With subspace decomposition
Classes F1 F1 F1 F2
20
0 0.869605568 0.870155489 86.64% 0.851125551
1 0.666666667 0.666666667 66.67% 0.6
2 0.677192982 0.63060686 68.77% 0.63764292
3 0.548192771 0.4 0.572289157 0.4671875
4 0.446808511 0.410810811 0.468085106 0.308108108
5 0.422680412 0.5 0.402061856 0.581521739
6 0.445205479 0.434343434 0.684931507 0.488215488
7 0.666666667 0.333333333 0.5 0.476190476
8 0.822916667 0.73878628 0.927083333 0.833773087
9 0.25 0 0.25 0.615384615
10 0.572164948 0.493046776 0.525773196 0.451327434
11 0.716904277 0.631578947 0.737270876 0.605759682
12 0.546218487 0.392116183 0.462184874 0.360995851
13 0.634146341 0.652439024 0.658536585 0.81097561
14 0.438735178 0.389830508 0.47826087 0.49551346
15 0.012987013 0.062295082 0.012987013 0.08852459
16 0.789473684 0.5 0.947368421 0.552631579
Table -8
Without Decomposition With subspace decomposition
No of bands F1 F2 F1 F2
6 OA 0.615933413 0.623483948 0.612604043 0.629250892
AA 23.74% 28.09% 22.35% 27.23%
KC 0.3855 0.3916 0.3776 0.4076
18 OA 0.68608799 0.659988109 0.692508918 0.662960761
AA 41.46% 35.35% 44.47% 40.35%
KC 0.518 0.4693 0.5315 0.4788
30 OA 0.705588585 0.678359096 0.729845422 0.706361474
AA 51.84% 46.23% 55.32% 51.26%
KC 0.5576 0.5131 0.5964 0.5565
42 OA 0.726753864 0.695778835 0.738168847 0.696908442
AA 56.04% 47.68% 57.93% 54.26%
KC 0.5914 0.5384 0.6114 0.5477
Table 9
Taking k% of bands from each subspace
Objective Function
Percentage of bands F1 F2 F3
10% OA 0.673602854 0.674019025 0.681212842
AA 42.41% 43.64% 43.61%
21
KC 0.4927 0.4986 0.5063
20% OA 0.701902497 0.712306778 0.713020214
AA 53.83% 55.64% 54.09%
KC 0.5522 0.5690 0.5711
30% OA 0.710344828 0.71587396 0.712247325
AA 58.62% 58.37% 56.46%
KC 0.5756 0.5787 0.5744
40% OA 0.710463734 0.694411415 0.704340071
AA 57.87% 57.02% 55.72%
KC 0.576 0.5527 0.566
50% OA 0.703567182 0.706361474 0.7069560047562
AA 62.82% 60.16% 58.73%
KC 0.5678 0.573 0.5698
Table 10
Class Wise accuracies for k= 10%
Objective Function
Classes F1 F2 F3
0 88.67% 0.870084677 0.886324092
1 43.24% 0.702702703 0.540540541
2 60.60% 0.651488616 0.62084063
3 0.335843373 0.328313253 0.332831325
4 0.215789474 0.078947368 0.278947368
5 0.424870466 0.005181347 0.062176166
6 0.068493151 0.339041096 0.244863014
7 0.727272727 0.590909091 0.545454545
8 0.793733681 0.835509138 0.759791123
9 0.0625 0 0.1875
10 0.471722365 0.470437018 0.469151671
11 0.681771894 0.689409369 0.693482688
12 0.270042194 0.360759494 0.396624473
13 0.18902439 0.451219512 0.323170732
14 0.259881423 0.274703557 0.312252964
15 0.012944984 0 0.003236246
16 0.77027027 0.77027027 0.756756757
Table 11
Class Wise accuracies for k= 20%
Objective Function
Classes F1 F2 F3
0 86.50% 0.870084677 0.866836794
22
1 64.86% 0.702702703 0.72972973
2 60.51% 0.651488616 0.640105079
3 0.40813253 0.328313253 0.453313253
4 0.263157895 0.078947368 0.363157895
5 0.476683938 0.005181347 0.339378238
6 0.63869863 0.339041096 0.647260274
7 0.545454545 0.590909091 0.590909091
8 0.845953003 0.835509138 0.817232376
9 0.5 0 0.1875
10 0.489717224 0.470437018 0.501285347
11 0.682281059 0.689409369 0.706211813
12 0.392405063 0.360759494 0.544303797
13 0.768292683 0.451219512 0.725609756
14 0.320158103 0.274703557 0.336956522
15 0.012944984 0 0.01618123
16 0.689189189 0.77027027 0.72972973
Table 12
Class Wise accuracies for k= 30%
Objective Function
Classes F1 F2 F3
0 83.93% 0.853497274 0.851757337
1 72.97% 0.810810811 0.72972973
2 64.71% 0.678633975 0.65061296
3 0.420180723 0.46686747 0.471385542
4 0.415789474 0.510526316 0.484210526
5 0.595854922 0.406735751 0.502590674
6 0.554794521 0.582191781 0.678082192
7 0.772727273 0.681818182 0.590909091
8 0.882506527 0.869451697 0.864229765
9 0.1875 0.3125 0.1875
10 0.515424165 0.525706941 0.442159383
11 0.66089613 0.679735234 0.653258656
12 0.518987342 0.483122363 0.464135021
13 0.847560976 0.865853659 0.725609756
14 0.490118577 0.424901186 0.480237154
15 0.129449838 0.080906149 0.051779935
16 0.756756757 0.689189189 0.77027027
Table 13
Class Wise accuracies for k= 40%
Objective Function
Classes F1 F2 F3
0 83.92% 0.825194293 0.835749913
1 70.27% 0.702702703 0.783783784
2 69.26% 0.61821366 0.647110333
3 0.46686747 0.448795181 0.423192771
4 0.426315789 0.421052632 0.294736842
23
5 0.629533679 0.551813472 0.479274611
6 0.669520548 0.630136986 0.672945205
7 0.590909091 0.681818182 0.454545455
8 0.843342037 0.809399478 0.882506527
9 0.25 0.1875 0.3125
10 0.520565553 0.546272494 0.560411311
11 0.624745418 0.625763747 0.647148676
12 0.497890295 0.491561181 0.512658228
13 0.731707317 0.798780488 0.603658537
14 0.438735178 0.423913043 0.441699605
15 0.142394822 0.132686084 0.177993528
16 0.77027027 0.797297297 0.743243243
Table 14
Class Wise accuracies for k= 50%
Objective Function
Classes F1 F2 F3
0 82.42% 0.82832618 0.837257859
1 86.49% 0.864864865 0.810810811
2 62.00% 0.664623468 0.649737303
3 0.468373494 0.44126506 0.489457831
4 0.526315789 0.484210526 0.552631579
5 0.580310881 0.53626943 0.60880829
6 0.72260274 0.683219178 0.655821918
7 0.636363636 0.5 0.409090909
8 0.859007833 0.835509138 0.822454308
9 0.5625 0.375 0.375
10 0.51285347 0.517994859 0.484575835
11 0.599287169 0.624745418 0.602851324
12 0.52742616 0.537974684 0.516877637
13 0.87804878 0.920731707 0.792682927
14 0.485177866 0.455533597 0.4743083
15 0.187702265 0.226537217 0.171521036
16 0.824324324 0.72972973 0.72972973
Table 15
Measures from Genetic Algorithm
Performance metric Genetic Algorithm
OA 0.627407848
AA 27.34%
KC 0.4043
24
25
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
26
REFERENCES
[1] Q. Wang, Z. Yuan, Q. Du, and X. Li, “GETNET: A general end-to-end two-dimensional CNN
framework for hyperspectral image change detection,” IEEE Trans. Geosci. Remote Sens., vol. 57, no.
1, pp. 3–13, Jan. 2019.
[2] A. F. Goetz, “Three decades of hyperspectral remote sensing of the Earth: A personal view,” Remote
Sens. Environment, vol. 113, pp. S5–S16, Sept. 2009.
[3] K. S. He, D. Rocchini, M. Neteler, and H. Nagendra, “Benefits of hyperspectral remote sensing for
tracking plant invasions,” Diversity Distributions, vol. 17, pp. 381–392, Mar. 2011.
[4] P. S. Thenkabail, J. G. Lyon, and A. Huete, Hyperspectral Remote Sensing of Vegetation. Boca
Raton, FL: CRC, 2016.
[5] N. M. Nasrabadi, “Hyperspectral target detection: An overview of current and future challenges,”
IEEE Signal Process. Mag., vol. 31, no. 1, pp. 34–44, 2014.
[6] M. Fauvel, Y. Tarabalka, J. A. Benediktsson, J. Chanussot, and J. C. Tilton, “Advances in spectralspatial classification of hyperspectral images,” Proc. IEEE, vol. 101, no. 3, pp. 652–675, 2013.
[7] D. Landgrebe, “Hyperspectral image data analysis,” IEEE Signal Process. Mag., vol. 19, no. 1, pp.
17–28, 2002.
[8] M. Marshall and P. Thenkabail, “Advantage of hyperspectral EO-1 Hyperion over multispectral
IKONOS, GeoEye-1, WorldView-2, Landsat ETM+, and MODIS vegetation indices in crop biomass
estimation,” ISPRS J. Photogramm. Remote Sens., vol. 108, pp. 205–218, Oct. 2015.
[9] P. Bajcsy and P. Groves, “Methodology for hyperspectral band selection,” Photogramm. Eng.
Remote Sens., vol. 70, pp. 793–802, July 2004.
[10] X. Miao, P. Gong, S. Swope, R. Pu, R. Carruthers, and G. L. Anderson, “Detection of yellow star
thistle through band selection and feature extraction from hyperspectral imagery,” Photogramm. Eng.
Remote Sens., vol. 73, no. 9, pp. 1005–1015, 2007.
[11] W. Sun et al., “UL-Isomap based nonlinear dimensionality reduction for hyperspectral imagery
classification,” ISPRS J. Photogramm. Remote Sens., vol. 89, pp. 25–36, Mar. 2014
[12] I. Dópido, A. Villa, A. Plaza, and P. Gamba, “A quantitative and comparative assessment of
unmixing-based feature extraction techniques for hyperspectral image classification,” IEEE J. Select.
Topics Appl. Earth Observ. Remote Sens., vol. 5, no. 2, pp. 421–435, 2012.
[13] A. MartÍnez-UsÓMartinez-Uso, F. Pla, J. M. Sotoca, and P. García-Sevilla, “Clustering-based
hyperspectral band selection using information measures,” IEEE Trans. Geosci. Remote Sens., vol. 45,
no. 12, pp. 4158–4171, 2007.
[14] . Yang, Q. Du, and G. Chen, “Particle swarm optimization based hyperspectral dimensionality
reduction for urban land 136 IEEE GEOSCIENCE AND REMOTE SENSING MAGAZINE JUNE
27
2019 cover classification,” IEEE J. Select. Topics Appl. Earth Observ. Remote Sens., vol. 5, no. 2, pp.
544–554, 2012.
[15] A. Das, H.S. Das, H.S. Das Impact of cuckoo algorithm in speech processing , 2020 .
[16] M.N.A. Wahab, S. Nefti-Meziani, A. Atyabi A, comprehensive review of swarm optimization
algorithms, PLoS ONE, 10 (5) (2015), pp. 1-36
[17] D. Karaboga, B. Basturk, A powerful and efficient algorithm for numerical function
optimization: artificial bee colony (abc) algorithm, J. Glob. Optim., 39 (3) (2007), pp. 459-47
[18] S. Solorio-Fernández, J.A. Carrasco-Ochoa, J.F. Martínez-Trinidad, Hybrid feature selection
method for supervised classification based on Laplacian score ranking, in: Advances in Pattern
Recognition - Second Mexican Conference on Pattern, Puebla, Mexico, 2010.
[19] Q. Du, H. Yang, Similarity-based unsupervised band selection for hyperspectral image analysis,
IEEE Geosci. Remote Sens. Lett. 5 (4) (2008) 564–568.
[20] P. Mitra, C.A. Murthy, S.K. Pal, Unsupervised feature selection using feature similarity, IEEE
Trans. Pattern Anal. Mach. Intell. 24 (2002) 301–312, http: //dx.doi.org/10.1109/34.990133.
[21] R. Yang, L. Su, X. Zhao, H. Wan, J. Sun, Representative band selection for hyperspectral image
classification, J. Vis. Commun. Image Represent. 48 (2017) 396–403
[22] Y. Zhang, M.D. Desai, J. Zhang, M. Jin, Adaptive subspace decomposition for hyperspectral data
dimensionality reduction, in: Proceedings of the 1999 International Conference on Image Processing,
ICIP 99, Kobe, Japan, 1999, pp. 326–329.
[23] Fuding Xie a,b, Fangfei Li a,∗, Cunkuan Lei a, Jun Yang a, Yong Zhang
Unsupervised band selection based on artificial bee colony algorithm for
hyperspectral image classification.
[24]Qi Wang , Senior Member, IEEE, Qiang Li, and Xuelong Li, Fellow, IEEE Hyperspectral Band
Selection via Adaptive Subspace Partition Strategy (2019)
[25] J. Feng, L. Jiao, F. Liu, T. Sun, X. Zhang, Unsupervised feature selection based on maximum
information and minimum redundancy for hyperspectral images, Pattern Recognition. 51 (2016) 295–
309, http://dx.doi.org/10.1016/j. patcog.2015.08.018.
[26] J. Wu, Unsupervised intrusion feature selection based genetic algorithm and
FCM, Lect. Notes Electrical. Eng. 154 (2012) 1005–1012.
[27] WEIWEI SUN AND QIAN DU Hyperspectral Band Selection A review (2019)
[28] A modified version of the ABC algorithm and evaluation of its performance Kaylash Chand
Chaudhary
