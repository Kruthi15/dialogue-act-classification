Dialogue Act Classification
Project Overview
This project focuses on classifying dialogue acts using the DistilBERT transformer model. It categorizes dialogue utterances into predefined classes such as inform, question, directive, and more. The implementation involves fine-tuning DistilBERT using PyTorch and Hugging Face’s Trainer API, along with robust preprocessing and tokenization steps.

Directory Structure
bash
Copy code
.
├── train.csv              # Training dataset
├── test.csv               # Test dataset
├── validation.csv         # Validation dataset
├── results/               # Checkpoints and training logs
├── dialogue_model_hmtl/   # Trained model and tokenizer storage
├── main.py                # Script for training and evaluation
└── README.md              # Project documentation
Key Features
Preprocessing

Converts text to lowercase

Removes extra whitespace

Handles malformed dialogue act annotations

Tokenization

Utilizes DistilBERT tokenizer

Encodes input into token IDs and attention masks

Model

Uses DistilBERTForSequenceClassification

Fine-tuned for multi-class classification with 5 dialogue act categories

Trainer API

Leverages Hugging Face’s Trainer for:

Easy training configuration

Early stopping

Automatic checkpointing and evaluation

Evaluation

Evaluates on validation data after each epoch

Tracks validation accuracy and loss

Saves the best-performing model

Usage Instructions
1. Install Dependencies
bash
Copy code
pip install pandas transformers sklearn torch numpy
2. Prepare the Data
Ensure the following CSV files are available in the project directory:

train.csv

validation.csv

test.csv

The script includes data preprocessing during execution.

3. Train the Model
Run the main script:

bash
Copy code
python main.py
Adjust training parameters (e.g., batch size, epochs) via the TrainingArguments section.

4. Evaluate the Model
The model is evaluated automatically after each epoch. The version with the lowest validation loss is saved.

5. Save and Load the Model
The trained model and tokenizer are saved in:

bash
Copy code
./dialogue_model_hmtl/
You can load the saved model for inference or further fine-tuning.

Results
Validation Accuracy: Achieved approximately 71% accuracy after fine-tuning DistilBERT.
