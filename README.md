# SkyCode

SkyCode is a multi-language open source programming model released by Singularity-AI. It adopts the GPT3 model structure and uses a large amount of code for training. Support Java, JavaScript, C, C++, Python, Go, shell and other mainstream programming languages, and can understand Chinese comments. The model can complete the code, solve problems and other operations, freeing you from programming and focusing on solving larger problems.

#### Hugging Face home page: https://huggingface.co/SkyWork/SkyCode

## Project Highlights

1. Technical advantage 1: covering multiple programming languages
   
   Different programming languages focus on solving problems in different platforms and environments, and different programming languages have their own reasons for existence. The codes that Singularity SkyCode can generate not only include widely used JavaScript, python, Java, C, etc., but also cover more than ten programming languages such as php, go, and swift, so that users of different languages can experience SkyCode has powerful code generation capabilities.


2. Technical advantage 2: optimize for Chinese annotations
   
   In the field of pre-training large models, it has always been dominated by the English community. The code generation model based on GPT3 has the same problem. Relying on the experience of deeply cultivating Chinese models, Singularity-AI optimized and innovated a unique Chinese encoding method according to the characteristics of Chinese, which is more in line with Chinese language habits, making the model's ability to understand Chinese annotations better.

3. Technical advantage 3: excellent problem-solving ability
   
   On the HumanEval data set that reflects the problem-solving ability of the code generation model, the problem-solving ability of SkyCode is also much higher than that of other open source models.
   
   | model          | pass@1 | pass@10 | pass@100 |
   |:-------------- | ------:|:-------:| -------- |
   | GPT-Neo 1.3B   | 4.79%  | 7.47%   | 16.30%   |
   | GPT-Neo 2.7B   | 6.41%  | 11.27%  | 21.37%   |
   | GPT-J 6B       | 11.62% | 15.74%  | 27.74%   |
   | SKY_code(2.6B) | 12.84% | 21.07%  | 35.97%   |
   
   It can be seen that SkyCode with a parameter quantity of 2.6B is not only much higher than the GPT-Neo 1.3B model with fewer parameters, but also much higher than the GPT-Neo 2.7B model with a comparable parameter quantity. Even compared to the GPT-J 6B model with a higher number of parameters, SkyCode's problem-solving ability is stronger. In the pass@100 indicator that better reflects the upper limit of problem-solving ability, SkyCode's net value exceeds GPT-J by 8.23%.


# News of Singularity-AI

- [2022.12.15] [AIGC Press Conference of Singularity-AI](https://live.vhall.com/v3/lives/subscribe/697547540)
  
  

## Installation

```
Recommand
transformers>=4.18.0
```

## Model Usage

```python
# -*- coding: utf-8 -*-
from transformers import GPT2LMHeadModel
from transformers import AutoTokenizer
from transformers import TextGenerationPipeline

model = GPT2LMHeadModel.from_pretrained("SkyWork/SkyCode")
tokenizer = AutoTokenizer.from_pretrained("SkyWork/SkyCode", trust_remote_code=True)
text_generator = TextGenerationPipeline(model, tokenizer, device=0)
input_str = "if __name__"
max_new_tokens = 40
print(text_generator(input_str, max_new_tokens=max_new_tokens, do_sample=True))### 
```

# License

[MIT License](LICENSE)

# Developer Group
#### Scan the QR Code below to join in the developer group of SkyCode
<img width="160" alt="img_v2_40e89a4f-5ec2-4184-b88d-f07a8dbd42dg" src="https://user-images.githubusercontent.com/120169448/209295979-ddae008c-f7d3-4e8c-bd96-b7d9b0d64150.png">
