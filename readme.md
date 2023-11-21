# Visual Question Answering (VQA)
## Introduction
<p>is a task in computer vision that involves answering questions about an image. The goal of VQA is to teach machines to understand the content of an image and answer questions about it in natural language.</p>

## VQADataset
VQA is a new dataset containing open-ended questions about images. These questions require an understanding of vision, language and commonsense knowledge to answer.
- 265,016 images (COCO and abstract scenes)
- At least 3 questions (5.4 questions on average) per image
- 10 ground truth answers per question
- 3 plausible (but likely incorrect) answers per question
- Automatic evaluation metric
#### 2. Download and unzip the dataset from the official URL of VQA: 
- https://visualqa.org/download.html.

## Model Architecture
We introduced a new model architecture based on attention is all you need ( Transformers ), and Inception model architecture for the visual side of inputs
 ## How does our model work?
 ### The VQA Model has two inputs
 - The first input is the question that fed into the encoder of the transformer
 - The second input is the image
### How do we add the encoded image into the transformer decoder
- We pass the incoded image that was proceced by the Inception model into the decoder as the `v` of the cross attention layer
- Then we pass the incoder output into the decoder cross attention layer as `k`

## Challenges
1. The VQA datset is very big around 30 GB so we coud not train in local machine
2. We decrease the model complixity as possiple to allow us train in Colab free acount
## Future work and updates
1. Use an updated decoder with two cross atention layers 
> - The first one allows the output to pay attention to the question
> - The second one allows the output to pay attention to the encoded image

3. Add more realible datasets
> -  Most of VQA answers is yes or no and dicimal numbers
> - We aim to add more samples were the answer is an sentance not just word or dicimal
2. Deployment Phase
> - We already deployed a tiny version that was traind in random 20% of the dataset samples
