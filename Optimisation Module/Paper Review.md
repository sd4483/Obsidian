#### What the paper is about
- In this paper, we introduce an approach for characterizing highly nonlinear and Finite Element (FE) simulation-based engineering optimization problems, focusing on ten representative problem instances from automotive crashworthiness optimization. 
> [!note] It's about introducing an approach to characterize optimisation problems (Highly non linear and finite element simulation based engineering problems) by using ten representation problems from automotive crashworthiness optimisation
- By computing characteristic Exploratory Landscape Analysis (ELA) features, we show that these ten crashworthiness problem instances exhibit landscape features different from classical optimization benchmark test suites, such as the widely-used Black-Box Optimization Benchmarking (BBOB) problem set. 
> [!note] Using something called as exploratory landscape analysis, they are trying to show that these 10 problems exhibit different features compared to the classical benchmarking test set such as BBOB
- Using clustering approaches, we demonstrate that these ten problem instances are clearly distinct from the BBOB test functions. 
> [!note] They use clustering approaches to show that these problems are different from the regular BBOB ones
- Further analysis of the crashworthiness problem instances reveal that, as far as ELA concerns, they are most similar to a class of artificially generated functions. 
> [!note] Here they say, after doing ELA, they found that these problems are similar to something called artificially generated functions.
- We identify such artificially generated functions and propose to use them as scalable and fast-to-evaluate representatives of the real-world problems. 
> [!note] Here basically they are saying that, identify those similar artifically generated functions and use those as the representatives of the real world problems. And I think they are trying to find scalable and fast to evaluate solutions for these artificial problems so that these solutions can be used for real world problems.
- Such artificially generated functions could be used for the automated design of an optimization algorithm for specific real-world problem classes. 
> [!note] And here they are saying those artificial functions can then be used to design an optimisation algorithm for specific real world cases.

>So far, I think the the artifical functions are just representatives, they are not a perfect representation of the real world problems so there could still be issues with using those optimisers.
>
>It's not the problem but more of the approach towards the way they want to characterize that problem is what I think needs to be critically evaluated.
>
>To consider: Are single objective optimisation problems good representive problem instances for real world ones?
>
>One thing that can be definitely said is that the sample is too low to chracterise landscape features problem istances. Although bootstrapping helps in creating sample sets that can give an hypothetical view, it doesn't help us understand ==edge cases== where something extreme could be happening. Due to this we don't excatly know how extensive the differences in characteristics could be between BBOB functions and crashwothiness problem instances. The experiment shows that the features are distinct, but how distinct are they, is that just a small margin or a significant one?
>
>It's a good approach that shows that there are differences in characteristics of crashworthiness problem instances compared to BBOB ones. But the sample size used and the methodologies used in the approach doesn't give an accurate representation, but gives an hypothetical overview of the differences. And since the sample size is small, there could be some extreme scenarios which would not be encountered in the analysis but could skew the results in a real world scenario. 
>
>What could be some issues that might arise with ==artifical test functions==? What could be the limitations of using them?
>
>==The way they are doing the characterisation is by comparing the landscape features of the problem instances with the landscape features of BBOB problems through hierarchial clustering.==
>
>Important thing to look into would be the references given for how they generated those artifical test functions. Limitations or challenges of those test fucntoins could also affect the comparision. How similar are the landscape properties of test functions to the original problem instances?
>

#### Terminologies & Keywords to note
- ##### Sampling with replacement
	- If you are randomly selecting value from a dataset to create a new dataset and you allow duplicates of the random values in the new dataset, that's known as sampling with replacement.
- ##### Bootstrapping:  ^ef71fe
	- The dataset created using sampling with replacement from values in the original dataset is called as bootstrapped dataset. 
	- And since the bootstrapped dataset is a little different from the original dataset, the mean differs a little bit as well.
	- If we take the mean of the bootstrapped dataset and keep track of it, and if we repeat this process for a number of times, this is known as bootstrapping.
		>[!INFO] Useful link: https://www.youtube.com/watch?v=Xz0x-8-cgaQ
	- To rephrase the above, the process of randomly creating a dataset using values from the original dataset  using sampling with replacement and calculating something from that new dataset and keeping track of that calculated value is known as bootstrapping.
	>[!question] What could be some of the downsides of doing bootstrapping?
- ##### BlackBox Optimisation:
	- BlackBox Optimisation problems (BBO) are optimisation problems in which ==we do not know what's happening inside them==. That's why it's called a blackbox. ==I think it can be thought of as a simulator==. ^f2ec9f
	- What we know is, the problem has upper bounds and lower bounds and there are some decision variables that can be passed into the problem and the objective function outputs some values. We do not exactly know how they are being calculated.
	- Till now in optimisation, we know what the objective function is, how it's defined and how we can use that to calculate outputs. In BBO problems, we do not know what this objective function is. We just pass values to the BBO problem and it returns an output for us.
	- So our goal with these problems could be to minimise or maximise the output we are getting out of the blackbox.
- ##### Exploratory Landscape Analysis (ELA)
	- The goal of ELA is to describe the objective function that is not known in BBO [[#^f2ec9f]] problems using landscape features.
	 >[!note] I think these landscape features are characterised in a particular way. There are approaches to characterise these fearures. Is this what they are trying to do in the paper? Characterize landscape features for automotive crashworthiness problems using ELA?
	- **Exploratory Landscape Analysis (ELA**) subsumes *(meaning includes)* a number of techniques employed to obtain knowledge about the properties of an unknown optimization problem, especially insofar as these properties are important for the performance of optimization algorithms.
	>[!note] In layman terms, ELA includes all the techniques used to understand the unknown optimisation problem more, as long as the properties discovered are important for the performance of the optimisation algortihm
- ##### Landscape Features
	- These quantify (measure) different landscape characterisitics of a given problem instance.
	- Once the characteristics are identified, the performace of an optimization algorithm on an unseen problem instance can be roughly estimated.
	- In other words, the landscape features can be used to predict the performance of an optimization algorithm on the problem instance.
	- 




#### Goals
- The general idea is to capture the landscape characteristics of a problem instance and use this information for selecting and configuring an optimal optimization algorithm.

#### Points to note
- Moreover, we neglect features concerning the computational costs of each feature class, as they do not provide useful information on the problem landscape. 
> [!note] Features related to computations costs are neglected
- In cases where a feature computation fails (e.g., when the sample size is too small for computing the level set features), it will be skipped. Consequently, less ELA features will be computed for such a problem instance. 
> [!note] Some features are skipped where computation fails due to low sample size. As a result less ELA features will be computed or analysed for that problem
-  To protect passengers and battery cells, the crash impact energy must be sufficiently absorbed through plastic deformation of different components, such as rocker panel. 
> [!note] This is what rocker panels are used for I guess!
-  depending on the purposes of each development project, not all four objectives were always considered and therefore not all of them are available for our study.
> [!note] The reason all 4 objectives regarding rocker panel design quality are not considered is because, simply the data is not available. And it's not so much as 'not considered', it's just not available to consider
- In our research, we separately analyze each of the objectives available and end up with a total of 30 single-objective optimization problem instances. 
> [!note] One argument could be made that, since it is a single objective optimisation problem what they chose, we don't know how good these chracteristics that they want to come up with are for real world problems cos real world problems are often multi objective
- In our experiments, we feed the data sets of the ten automotive crashworthiness optimization problem instances into our pipeline and independently compute the aforementioned 68 ELA features. 
> [!note] Each data set, (one data set for one problem instance) is sent into the pipeline and all the 68 ELA features are computed on that dataset.
- For each crashworthiness problem instance, we consider the mean ELA feature values computed based on a bootstrapping [[Paper Review#^ef71fe]] strategy to minimize the effects of random sampling in ELA, using a bootstrap size of 80% of the initial sample size and 30 repetitions 
> [!note] Why are only mean values considered? What is bootstrapping strategy? Why is random sampling used in ELA?
- Re-scaling is necessary to facilitate the comparison of ELA features between crashworthiness problem instances and the BBOB functions. Moreover, since ELA features are highly sensitive to sample size and sampling strategy, the identical sample points (and thus the identical dimensions) of the automotive crashworthiness problem instances are used to compute the ELA features of the BBOB functions for a fair comparison.
>[!question] Try to understand why re-scaling is used here and also the point about ELA features being highly sensitive to sampling size and sampling strategy
- Using clustering approaches, we demonstrate that these ten problem instances are clearly distinct from the BBOB test functions.
>[!question] Is clustering really the best approach here? What else could they have used to differentiate these problems from BBOB ones. Have they provided enough reasoning for using clustering analysis?
- Non-linear problems
>[!note] Non-linear problems are problems which do not increase linealy as we increase inputs, meaning increasing x doesn't necessarily increase y.
- Surrogate based optimization methods
>[!question] What are surrogate based optimization methods? Why is there still no proper understanding of the problem characteristics?
- Look into limitations of Tsne
- Look into the function generators and test functions mentioned in 5.2 Artificially generated functions
- Biases in ELA features?
- During these development projects, the quality of a particular rocker panel design was evaluated by quantifying its structural crashworthiness through the following four objectives (Maximum force, Intrusion, Energy absorption and Rotation) but not all four of them were always considered for every development project.
- 