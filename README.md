# Clustering credit card users

Clustering credit card clients with KMeans

## Data
https://www.kaggle.com/datasets/arjunbhasin2013/ccdata

## Notebook
The main objective was to use the unsupervised learning algorithm KMeans
to cluster the clients of a certain credit card, to define a marketing strategy.

This notebook is divided into sections:

### Preparing Data
missing data decisions

### Normalization
pre-processing with sklearn Normalizer

### Choosing number of clusters
chosing the number of clusters based on silhouette score, Davies Bouldin score and
Calinski Harabasz score. A solution to quantify the clustering with these metrics
is to make a relative validation, and ajust the model's parameters to maximize 
these scores.

### Cluster Validation
* Comparing cluster metrics when performing on a random dataset
* Comparing cluster metrics between subsets of the dataset, to ensure the clustering is stable

### Visualizing the Clusters
too many dimensions and clusters make visualization difficult.
instead it is preferable to understand each cluster's statistic properties to make assumptions.

### Understanding Cluster stats (+Marketing Strategy)
Conclusions:

CLUSTER 0:  Clients with lowest limit of Credit Card for user;
            Clients with bad full payment reputation;
            Lower number of clients.

            "SMALLEST CLUSTER, LOW LIMIT CREDIT CARD AND BAD PAYERS"

CLUSTER 1:  Clients with least balance amount left in their account to make purchases;
            Clients with least cash advance (withdraw) values;
            Clients with least amount of Payment done by user;
            Clients with highest limit of Credit Card for user;
            Clients with good full payment reputation;
            Higher number of clients.

            "LARGEST CLUSTER, GOOD PAYERS, HIGH LIMIT CREDIT CARD, BUT DOESN'T SPEND AND LOW BALANCE ON ACCOUNT"

CLUSTER 2:  Clients with most balance amount left in their account to make purchases;
            Clients with least amount of purchases made from account;
            Clients with bad full payment reputation.

            "BAD PAYERS, HIGH BALANCE ON ACCOUNT, BUT DON'T SPEND MUCH, MAINLY IN CASH"

CLUSTER 3:  Clients with most cash advance (withdraw) values;
            Clients with most amount of Payment done by user.

            "SPENDS THE MOST, AND WITH CASH, MEDIAN PAYMENT REPUTATION"

CLUSTER 4:  Clients with most amount of purchases made from account;
            Clients with good full payment reputation.
        
            "BUYERS WITH HIGH FULL PAYMENT PERCENT"
            
ACTIONLOG:

- Cluster 1 is the largest, its interesting to make a campaign so that these clients spend more.
- Cluster 4 is large and formed mainly by good buyers and payers, its interesting to raise credit limit for these clients.

Implement these actions with AB Testing to ensure cause/consequence of the results:

Example:
On Cluster 1, divide the cluster in two groups: Control and Campaign. In the end of the campaign compare the results.
