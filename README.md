# SkyCode

SkyCode是由奇点智源发布的多语言开源编程大模型，采用GPT3模型结构，使用海量的代码进行训练。支持Java, JavaScript, C, C++, Python, Go, shell等多种主流编程语言，并能理解中文注释。模型可以对代码进行补全，进行解题等操作，使您从编程中解放出来，专心于解决更大的问题。


## 项目亮点

1. 技术优势一 ：涵盖多种编程语言
   
   不同的编程语言着重于解决不同平台、环境下的问题，不同的编程语言都有自己存在的理由。奇点智源SkyCode能够生成的代码，不仅包括使用广泛的JavaScript、python、Java、C等，还涵盖了php、go、swift等共计十余种编程语言，使不同语言的使用者都能来体验SkyCode强大的代码生成能力。

2. 技术优势二：针对中文注释进行优化
   
   曾经在预训练大模型领域，一直是被英文社区主导着，依托于GPT3的代码生成模型有着同样的问题。奇点智源凭借深耕中文模型的经验，针对中文的特点，优化创新使用了独特的中文编码方式，更加符合中文的语言习惯，使得模型对中文注释的理解能力更为优秀。

3. 技术优势三：极其出色的解题能力
   
   在体现代码生成模型解题能力的HumanEval数据集上，奇点智源SkyCode的解题能力也远高出其他开源模型。
   
   | model          | pass@1 | pass@10 | pass@100 |
   |:-------------- | ------:|:-------:| -------- |
   | GPT-Neo 1.3B   | 4.79%  | 7.47%   | 16.30%   |
   | GPT-Neo 2.7B   | 6.41%  | 11.27%  | 21.37%   |
   | GPT-J 6B       | 11.62% | 15.74%  | 27.74%   |
   | SKY_code(2.6B) | 12.84% | 21.07%  | 35.97%   |
   
   可以看到，参数量2.6B的SkyCode在解题能力上不仅高出参数较少的GPT-Neo 1.3B许多，也远高于参数量相当的GPT-Neo 2.7B模型。即使对比参数量更高的GPT-J 6B模型，SkyCode的解题能力也更强。在更能体现解题能力上限的pass@100指标上，SkyCode超出GPT-J的净值为8.23%。


# 奇点新闻

- [2022.12.15] [昆仑天工AIGC发布会](https://live.vhall.com/v3/lives/subscribe/697547540)
  
  

## 依赖

```
推荐
transformers>=4.16.0
```

## 模型使用

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
print(text_generator(input_str, max_new_tokens=max_new_tokens, do_sample=True))
```

## huggingface模型主页

https://huggingface.co/SkyWork/SkyCode


# 版权许可

[MIT License](LICENSE)
