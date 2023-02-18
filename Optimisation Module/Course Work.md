**Introduction:**

The paper focuses on finding a better approach to define the characteristics of real world engineering optimisation problems which are often hard to understand and optimize. A new approach is introduced to characterize real-world Finite Element simulation based engineering optimization problems that are highyl non-linear in nature. Ten real-world representative automotive crashworthiness problem instances are chosen to carry out the research. Using Exploratory Landscape Analysis (ELA), the researchers found that, the classical optimization benchmark functions that are widely used, might not be the best way to characterize the problem instances chosen by them. They argue that the artifical functions generated with similar characteristics to the real world problem instances chosen by them, are better at defining the characterisitics of the problem instances. They propose to use these artificial functions for automated design of optimization algorithms for specific real-world problems. 

They also argue that, a proper understanding of problem characteristics is required before attempting to optimize these problem instances.
They built an automoated pipeline that can help them compare the problem instances with classic benchmark functions and also to generate artificial functions. 

They are tyring to understand the typical landscape characteristics of automotive crachworthiness optimization problems. Also, are there any similarities in landscape characteristics between automotive problem instances and academic benchmark function such as BBOB functions. And to which extent the BBOB functions can be used as reperesentatives of the crashworthiness optimization problems in terms of similarity in landscape characteristics, If none of them are sufficiently representing them, are there any other test functions which could serve as good approximation?

==Their main argument is not whether BBOB functions are good or bad or other artificial functions are better, it's about having extensive insights in defining the landscape characteristics which would help in designing an effective optimization algorithm that can be used for a particular problem class.==

In this paper, they are focusing on automotive side crash as a representative of this problem class where the battery cells installede jn a car must be additionally prpotected from crash impact.

They are considering only unconstrained single-objective optimization problems to minimize the complexity.

Upon doing clustering analysis, they come to a conclusion that the BBOB problem set seems to be inadequate in characterizing crashworthiness problem classes.

They designed a pipeline to characterise the automotive crashworthiness problem instances by computing ELA features on the chosen problem instances and comparing them with computations of ELA features done with classic benchmark functions such as BBOB. They then what to identify if there are any BBOB functions showing similar ELA features to the problem instances so that they can be used to characterize problem instances which will help with algorithm selection to carry out optimization.

In this experiment, they are focusing particulary on crashworthiness optimization of  a rocker panel design with respect to side crash against a pole. They acquired the required data from BMW, a German automobile manufacturer.
The data acquired consists of side crash test cases run with four different rocker panels with similar designs and three different pole positions which the car crashed into.

The design variables were the thickness of different components of the rocker panels.

During these development projects, the quality of a particular rocker panel design was evaluated by quantifying its structural crashworthiness through the following four objectives (Maximum force, Intrusion, Energy absorption and Rotation). ==reframe this==




~~while also explaining why the classical optimization benchmark functions might not be appropriate.~~

~~They develop an automated pipeline based on ten real world problem instances~~

~~understanding why the widely used Black-Box Optimization Problem sets might not be the appropriate way to characterize real-world Finite Element simulation based engineering optimization problems that are highyl non-linear in nature.~~
