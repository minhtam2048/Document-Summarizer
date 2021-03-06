original paper-https://arxiv.org/pdf/1704.04368.pdf (2016) <br/>
new paper - https://web.stanford.edu/class/archive/cs/cs224n/cs224n.1194/reports/custom/15784595.pdf (2018) <br/>

summarizer.py - RNN implementation <br/>
summarizer-transformer.ipynb - Transformer implementation <br/>
```Prerequistes
* torch
* pickle
* gzip
```

```Data
Input and validation data can be downloaded from https://github.com/harvardnlp/sent-summary 
```

```Steps
* Change the file paths in the params class
* Run the summarizer.py to train the model 
```

RNN model explained:<br/>
![summarisation](https://user-images.githubusercontent.com/19767662/78631603-64a01e80-78cf-11ea-8375-6282c24e3bb5.jpg)
```
Pointer Generator Network in brief:
```
* The network has mostly copying capability with some generation capacity
* A history of encoder attention weights is maintained , to discourage new attention calculation to  
give much weight to already covered tokens, thus avoiding repetition
* Decoder attention history is maintained to calculate decoder context(weghts to already generated  words)  
* It decided at each token generation, how much weightage should be given to copying and how much  to generation from   vocabulary.
* This is done by learning pointer probability, which takes into account encoder-decoder context,  decoder context and   decoder hidden state at a particular generation step.
* The network also uses a coverage loss, which is minimum of the coverage vector and encoder-decoder  attention, to   punish the network for paying any attention to tokens where attention is already paid in previous steps.
* The network also uses an extra vocabulary, which is existing vocab + words that appear in the  training\test set.   These new words are not added to existing vocan, and are only used for copying, for input document. Thus it avoids having a huge vocabulary.


## Any questions 👨‍💻
<p> If you have any questions, feel free to ask me: </p>
<p>📧: nirmalendu@outlook.com<p>
