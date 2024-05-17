# MA23M002 - ABHINAV T K
# Transliteration System using RNN, GRU & LSTM with Encoder-Decoder Seq2Seq Models (with and without Attention)

WANDB Report Link: 

## Project Description:
This project aims to build a transliteration system that converts text from one script to another while preserving its phonetic structure. The system leverages advanced neural network architectures, including Recurrent Neural Networks (RNNs), Gated Recurrent Units (GRUs), and Long Short-Term Memory networks (LSTMs). Using encoder-decoder sequence-to-sequence (Seq2Seq) models, the project explores both the conventional approach and enhanced versions incorporating attention mechanisms to improve accuracy. By comparing these different models, the project seeks to identify the most effective method for transliterating text between various languages from the [Aksharantar dataset](https://drive.google.com/file/d/1tGIO4-IPNtxJ6RQMmykvAfY_B0AaLY5A/view?usp=drive_link) released by [AI4Bharat](https://ai4bharat.org/). Hyperparameter tuning is done using wandb to find the best performing configurations.

## Files info 
1. [main.ipynb](link) - The main ipynb file containing the source code along with wandb sweeps for hyperparameter tuning
2. [train.py](link) - Python file to train and run the code
3. [prediction_vanilla.csv](predictions_vanilla/prediction_vanilla.csv) - Predicted data of the test set without attention
4. [attention_predictions.csv](predictions_attention/attention_predictions.csv) - Predictions of the test set with Attention

## Usage
The following steps will allow you to run this project and see the outputs.
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
Alternatively, <br>
** Download the *[main.ipynb](link)* file and run it on Google Colab or Kaggle using the provided *[Aksharantar dataset](aksharantar_sampled)*.** <br>
Note that the source file paths in the ipynb file is corresponding to Kaggle as the code has been trained and run in Kaggle environment.  

## Dependencies
- python
- numpy
- wandb 
- torch
- matplotlib
- pandas

## Project Roadmap
Q1. 
Q2. 
