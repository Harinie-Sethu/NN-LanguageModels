# NN-LanguageModels
Built Neural Language Model - RNN and LSTM trained on Auguste_Maquet corpus.  
Total number of sentences after cleaning was roughly 38 K.  



## NNLM
- 1_a.ipynb contain code for the NNLM model.
- The input to the Neural Network would be the pre-trained embbeddings of the previous 5-words
concatenated together(5-gram embedding).
- These embedding would pass into a Hidden Layer which would output a 100-dimension vector. The output of the first Hidden Layer would go into another Hidden Layer, which would output a vector of size vocabulary. This vector would be passed to a Softmax Layer, which would output the probabilities of entire vocabulary
occuring after the given 5-words.

- The model was > 20 MB so you can view it in this link instead: https://drive.google.com/file/d/1FHNg3aY_cBlWr7qUsa49Zx8nQrCuGVqq/view?usp=sharing

- 2021114008-LM1-test-perplexity and 2021114008-LM1-train-perplexity contain perplexity scores
- average perp for test = 680431334.1573
- average perp for train = 22508.5078

## LSTM
- 1_b.ipynb contain code for the LSTM model.
- The Neural Network would consist of repeating layers in an LSTM-structure.
- The input to each layer would consist of the hidden-layer and cell state output of the previous state, along
with the embedding of the current word.
- The 100-dimension output would be put into a Linear layer, which will transform it to vector of dimension
of size vocabulary. Then, that to SoftMax-layer, which would provide the probability distribution over the
entire vocabulary.

- The model was > 20 MB so you can view it in this link instead: https://drive.google.com/file/d/1ivOhLnMTDQV_zn8pI78LXZGOeG642hRc/view?usp=sharing

- 2021114008-LM2-test-perplexity and 2021114008-LM2-train-perplexity contain perplexity scores
- average perp for test = 42459179311748.9609
- average perp for train = 22424.7170
<br>
<br>

## ANALYSIS OF PERPLEXITY

- From the perplexity scores, we can observe that Model 2 has significantly lower perplexity values on both the train and test datasets compared to Model 1. 
  
- Lower perplexity indicates that Model 2 is better at predicting sequences of words and is likely a better language model.
  
- From THE FIRST perplexity figure in analysis.ipynb, the visualization will clearly demonstrate that Model 2 outperforms Model 1 by a significant margin in terms of test perplexity.
  
- In summary, Model 2 is the better-performing language model, as it achieves lower perplexity on both the train and test datasets. 
<br>
<br>


## ANALYSIS OF LOSS

### MODEL 1
Epoch 1/10, Train Loss: 5.4795, Val Loss: 5.2432  
Epoch 2/10, Train Loss: 4.9634, Val Loss: 5.2085  
Epoch 3/10, Train Loss: 4.8090, Val Loss: 5.2162  
Epoch 4/10, Train Loss: 4.6961, Val Loss: 5.2277  
Epoch 5/10, Train Loss: 4.6036, Val Loss: 5.2553  
Epoch 6/10, Train Loss: 4.5087, Val Loss: 5.2635  
Epoch 7/10, Train Loss: 4.4196, Val Loss: 5.2864  
Epoch 8/10, Train Loss: 4.3354, Val Loss: 5.3135  
Epoch 9/10, Train Loss: 4.2562, Val Loss: 5.3386  
Epoch 10/10, Train Loss: 4.1835, Val Loss: 5.3654  

### MODEL 2
Epoch [1/10] | Train Loss: 5.7433 | Val Loss: 5.2504   
Epoch [2/10] | Train Loss: 4.9438 | Val Loss: 5.0098  
Epoch [3/10] | Train Loss: 4.6128 | Val Loss: 4.9895  
Epoch [4/10] | Train Loss: 4.3506 | Val Loss: 5.0253  
Epoch [5/10] | Train Loss: 4.1098 | Val Loss: 5.0997  
Epoch [6/10] | Train Loss: 3.8805 | Val Loss: 5.2106  
Epoch [7/10] | Train Loss: 3.6602 | Val Loss: 5.3541  
Epoch [8/10] | Train Loss: 3.4569 | Val Loss: 5.4913  
Epoch [9/10] | Train Loss: 3.2669 | Val Loss: 5.5996  
Epoch [10/10] | Train Loss: 3.0906 | Val Loss: 5.7658  

<br>
<br>


### 
- From, the 2nd figure in analysis.ipynb, we see plotted two subplots side by side. 
- The left subplot shows the training and validation loss for Model 1, while the right subplot shows the same for Model 2.

- Model 1: The training loss decreases steadily, but the validation loss remains consistently higher, indicating overfitting.

- Model 2: The training loss decreases rapidly, and the validation loss also decreases, suggesting better generalization.

- Model 2 demonstrates superior performance in terms of both training and validation loss. It converges faster and achieves lower losses. In conclusion, Model 2 outperforms Model 1 in terms of training and validation loss. It converges faster and generalizes better, making it the preferred choice for language modeling tasks.


