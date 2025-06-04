# Project I

Members: Bui Cong Minh, Tran Hoang Thai
Supervisor: Tong Van Van

## Watermark removal using LLMs
Check out our work
Removing watermarks: **[Google Colab](https://colab.research.google.com/drive/1O0ELetnGKWsIZrSZFcD2huVQBWjW3BTY#scrollTo=B_pe-hG6SW6H)**.
## Notebook structure
1. Set up: Contains cells for importing and installing libraries, choosing models, configuring devices, and initializing
2. Removing watermark by using LLMs to paraphrase the texts: Contains functions to generate watermarked texts, paraphrasing texts via LLMs API and calculating mean scores of the paraphrased text

## Running the notebook
Set up the program by running all the cells in "Set up" section. To run the paraphraser tool, GPUs is required, then input the text and desired size of the model needs paraphrasing. Wait for a moment and the paraphrased text will be returned with a result showing that if it bypasses the watermark detector (You may need to run again since the program does not guarantee successful watermark removal in the first run)

## Finding threshold
SynthID provides a scoring function to detect whether a text is watermarked or not. The score value ranges between 0 and 1. To determine the threshold for watermark detection, we run the program to generate non-watermarked responses and watermarked responses. Then we evaluate the distribution of the scores from both type of responses. Noticing that they nearly represented normal distribution, we plot the probability distribution function (p.d.f) and find the intersection of the 2 p.d.f to determine the threshold

## Evaluation of the watermark removal
After running a dataset of prompts to our paraphraser tool, translation tool show relatively low success rate with around 50%. However, watermark removing via LLMs shows promising results with above 90% success rate.
