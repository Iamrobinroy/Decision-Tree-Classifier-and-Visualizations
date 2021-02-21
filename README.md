# Decision-Tree-Classifier-and-Visualizations-
Internship task as part of The Sparks Foundation

# Prediction using Decision Tree Algorithm
Create the Decision Tree classifier and visualize it graphically, The purpose is if we feed any new data to this classifier, it would be able to
predict the right class accordingly.
Dataset : https://bit.ly/3kXTdox

A decision tree is a flowchart-like tree structure where an internal node represents feature(or attribute), the branch represents a decision rule, and each leaf node represents the outcome. The topmost node in a decision tree is known as the root node. It learns to partition on the basis of the attribute value. It partitions the tree in recursively manner call recursive partitioning. 


## Information Gain
Shannon invented the concept of entropy, which measures the impurity of the input set. In physics and mathematics, entropy referred as the randomness or the impurity in the system. In information theory, it refers to the impurity in a group of examples. Information gain is the decrease in entropy. Information gain computes the difference between entropy before split and average entropy after split of the dataset based on given attribute values. ID3 (Iterative Dichotomiser) decision tree algorithm uses information gain.
Image : https://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1545934190/3_tvqfga.png

Where, Pi is the probability that an arbitrary tuple in D belongs to class Ci.
https://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1545934190/4_vvrzww.png
https://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1545934190/5_trlrj8.png

Where,

Info(D) is the average amount of information needed to identify the class label of a tuple in D.
|Dj|/|D| acts as the weight of the jth partition.
InfoA(D) is the expected informa-tion required to classify a tuple from D based on the partitioning by A.
The attribute A with the highest information gain, Gain(A), is chosen as the splitting attribute at node N().

Gain Ratio
Information gain is biased for the attribute with many outcomes. It means it prefers the attribute with a large number of distinct values. For instance, consider an attribute with a unique identifier such as customer_ID has zero info(D) because of pure partition. This maximizes the information gain and creates useless partitioning.

C4.5, an improvement of ID3, uses an extension to information gain known as the gain ratio. Gain ratio handles the issue of bias by normalizing the information gain using Split Info. Java implementation of the C4.5 algorithm is known as J48, which is available in WEKA data mining tool.

https://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1545934190/6_zub2e8.png

Where,

|Dj|/|D| acts as the weight of the jth partition.
v is the number of discrete values in attribute A.
The gain ratio can be defined as

https://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1545934190/7_xnqpo8.png

The attribute with the highest gain ratio is chosen as the splitting attribute (http://www.enggjournals.com/ijcse/doc/IJCSE10-02-09-092.pdf)

Gini index
Another decision tree algorithm CART (Classification and Regression Tree) uses the Gini method to create split points.
https://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1545934190/8_k4ia8r.png

Where, pi is the probability that a tuple in D belongs to class Ci.

The Gini Index considers a binary split for each attribute. You can compute a weighted sum of the impurity of each partition. If a binary split on attribute A partitions data D into D1 and D2, the Gini index of D is:
https://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1545934191/9_atnmbc.png

In case of a discrete-valued attribute, the subset that gives the minimum gini index for that chosen is selected as a splitting attribute. In the case of continuous-valued attributes, the strategy is to select each pair of adjacent values as a possible split-point and point with smaller gini index chosen as the splitting point.
https://res.cloudinary.com/dyd911kmh/image/upload/f_auto,q_auto:best/v1545934191/10_oqzzp6.png

The attribute with minimum Gini index is chosen as the splitting attribute.




