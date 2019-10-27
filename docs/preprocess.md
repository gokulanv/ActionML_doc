# Preprocessing

## Data Shuffling
> Shuffling data serves the purpose of reducing variance and making sure that models remain generic and do not overfit.

> The obvious case where you'd shuffle your data is if your data is sorted by their class/target. Here, you will want to shuffle to make sure that your training/test/validation sets are representative of the overall distribution of the data.

## Data Sampling 
> The data has one true for every ten False(1:10). To make the data to have 1:1 ratio, we do Data Sampling. For this process we take a set of True occurrences until we get a False occurrence . Then we divide the True occurrences by two. Lets say n is the number of occurrence of the True and s is half of n (s=n/2). We then traverse to the First occurrence of the True of the current set and get s number of False before the  occurrence of True and we have to get the same number of False after the last occurrence of True of the current set. We continue to do the same for the whole Dataset in order to make the occurrence of True or False equal (1:1)

## What did we do?
> As you can see, the data is organized in some places and is stochastic in other places. We want the data to be shuffled in all places
so that we do not bias the model with the order of True/False data.

> We created batches of data such that each batch consisted of equal number of True Positives and True Negatives. That way, each batch serves as a perfect mix of data so that the model improves consistently and reaches the best validation that it can.

> Data Sampling as mentioned above

## Next steps

> We want to shuffle your data after each epoch because we will always have the risk to create batches that are not representative of the overall dataset, and therefore, our estimate of the gradient will be off. Shuffling the data after each epoch ensures that we will not be "stuck" with too many bad batches.
