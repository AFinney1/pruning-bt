# Neural Network Pruning Challenge README

- Running the notebook:
    - I included an environment file (pruning_env.yml) that can be used to recreate the environment variables for the notebook if you are using conda.
    - With the appropriate environment, the notebook can be run with:
    - The notebook can be run with the following command:
        ```
        jupyter network_pruning.ipynb
        ```
    - I also ran the notebook in Google Colab without having set up the environment.



 ## Results, Analysis, Discussion

1. I attempted to build the neural network architecture stipulated in the original assigment and prune two networks with weight and unit pruning. *I ended up forgoing the unit pruning and only used bias 
2. Overall, the pruned models performed better than the original network, as noted by the general increase in performance above 94% accuracy in each plot. 
3. The weight pruning performed better than the bias pruning.
4. No pruning method was stipulated for the weight pruning, so I used L1 unstructured pruning.
5. Pruning should have resulted in faster models, but my timer implementation needs further developement.

   * #### Austin's Known Knowledge Gaps and Conpromises

    1. I wasn't sure how to implement the unit pruning method with the global pruning method, at least not without including the last layer. If I had, I believe I would have seen the degradation in accuracy suggested in the assigment. This led me to implement bias pruning as a second method, so I kept the biases in all models.
    2. I may have used an unfavorable batch size (1) for the training and validation loaders to make the architecture implementation easier(I started with 64). With additional time, I'm sure I could configure the architecture to use a larger batch size.
    3. This was my first time using Pytorch's benchmarking tool. I'm not sure if importing it from __main__ gave me the actual trained 99% pruned models. I think additional setup is needed.
