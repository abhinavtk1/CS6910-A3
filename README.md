# MA23M002 - ABHINAV T K
# Transliteration System using RNN, GRU & LSTM with Encoder-Decoder Seq2Seq Models (with and without Attention)

WANDB Report Link: https://api.wandb.ai/links/abhinavtk/g63f5a80

## Project Description:
This project aims to build a transliteration system that converts text from one script to another while preserving its phonetic structure. The system leverages advanced neural network architectures, including Recurrent Neural Networks (RNNs), Gated Recurrent Units (GRUs), and Long Short-Term Memory networks (LSTMs). Using encoder-decoder sequence-to-sequence (Seq2Seq) models, the project explores both the conventional approach and enhanced versions incorporating attention mechanisms to improve accuracy. By comparing these different models, the project seeks to identify the most effective method for transliterating text between various languages from the [Aksharantar dataset](https://drive.google.com/file/d/1tGIO4-IPNtxJ6RQMmykvAfY_B0AaLY5A/view?usp=drive_link) released by [AI4Bharat](https://ai4bharat.org/). Hyperparameter tuning is done using wandb to find the best performing configurations.

## Files info 
1. [main.ipynb](main.ipynb) - The main ipynb file containing the source code along with wandb sweeps for hyperparameter tuning
2. [train.py](train.py) - Python file to train and run the code
3. [prediction_vanilla.csv](predictions_vanilla/prediction_vanilla.csv) - Predicted data of the test set without attention
4. [attention_predictions.csv](predictions_attention/attention_predictions.csv) - Predictions of the test set with Attention

## Usage
You can run and train the model by two ways. <br>
- Using main.ipynb file.
- Using train.py

**Download the *[main.ipynb](main.ipynb)* file and run it on Google Colab or Kaggle using the provided *[Aksharantar dataset](aksharantar_sampled)*.** <br>
Note that the source file paths in the ipynb file is corresponding to Kaggle as the code has been trained and run in Kaggle environment. 

Alternatively, <br>
1. Clone the repository to your local machine:  
```
git clone https://github.com/abhinavtk1/CS6910-A3.git
```
2. Navigate to the project directory: 
```
cd CS6910-A3
```
3. Compile and run the project:
```
python train.py
```
 

## Dependencies
- python
- numpy
- wandb 
- torch
- matplotlib
- pandas

## Project Roadmap

### Sweep configuration:
```
# sweep config file
sweep_config = {
    'method': 'bayes',
    'name' : 'sweep - no attention',
    'metric': {
      'goal': 'maximize',
      'name': 'validation_accuracy'
    },
    'parameters':{
        'input_embedding_size': {
            'values': [16,32,64, 128]
        },
        'enc_layers': {
            'values': [1,2,3]
        },
        'dec_layers': {
            'values': [1,2,3]
        },
        'hidden_size': {
            'values': [16, 32, 64, 128, 256]
        },
        'cell_type': {
            'values': ['lstm','rnn','gru']
        },
        'bidirectional' : {
            'values' : [True]
        },
        'dropout': {
            'values': [0.1, 0.2, 0.3]
        },
        'beam_size' : {
            'values' : [1,3,5]
        }
     }
}
```
**Note: To run the wandb sweeps you have to provide your unique wandb API key.**

### Attention heatmap:
Plotted using Matplotlib. Used AnjaliOldLipi-Regular for plotting. Plot uploaded to report using wandb. 
