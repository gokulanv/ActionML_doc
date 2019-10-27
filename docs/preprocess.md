# Preprocessing

## Data Shuffling
> Shuffling data serves the purpose of reducing variance and making sure that models remain generic and do not overfit.

> The obvious case where you'd shuffle your data is if your data is sorted by their class/target. Here, you will want to shuffle to make sure that your training/test/validation sets are representative of the overall distribution of the data.

## What did we do?
> As you can see, the data is organized in some places and is stochastic in other places. We want the data to be shuffled in all places
so that we do not bias the model with the order of True/False data.

> We created batches of data such that each batch consisted of equal number of True Positives and True Negatives. That way, each batch serves as a perfect mix of data so that the model improves consistently and reaches the best validation that it can.

## Next steps

> We want to shuffle your data after each epoch because we will always have the risk to create batches that are not representative of the overall dataset, and therefore, our estimate of the gradient will be off. Shuffling the data after each epoch ensures that we will not be "stuck" with too many bad batches.
