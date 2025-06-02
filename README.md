# What is 1998-prompts
LLMs and other AI tools have become an indispensable part of our lives. That being said the transition from a world with no AI to a world that is tightly connected to these agents was rapid leaving us with little to no time to adapt ourselves to this new workflow. One aspect where we seriously lack is prompt engineering. There exists already a community of people investing time in finding the right format of prompts for each new AI model but their progress is slow in comparison to the outstanding growth of the field. Therefore the need for an automatic solution to prompt engineering was born. I started researching this topic when I found myself unable to express what I wanted to a video generation AI model. I found out that there are currently available solution that help you enhance your prompt. Some of them are really nice ones and I would invite the reader to check them out. However, all of them are wrappers of well known models with no customization whatsoever. So, while these solutions might be nice for personal use, they do not offer a feasible option for newly emerging AI models that are not yet under the radar of large LLMs. Hence the idea for '1998-prompts' a fine tuned model that can be tweaked to satisfy the prompt engineering needs of whoever is using it.

# How it works
For this project I have used meta-llama/Meta-Llama-3-8B-Instruct pretrained model provided by HuggingFace. To fine-tune this model I have used LoRA (Low-Rank Adaptation) since my resources where limited. I have also used pretrained tokenizers from HuggingFace. The method of training is that of gradient accumulation in which I use small batches but accumulate gradients over several steps before updating model weights. This simulates a larger batch size and helps training stability. The entire process is supervised and I have computed the loss between the model’s predicted output and the actual enhanced text.

# How to set it up for training
Setting it up for training is pretty easy. You just have to make sure you get your HuggingFace token and insert it in the proper place in the code (This is properly marked). After that run the first cell to install all the libraries that are needed. Make sure you have pointend your code to your dataset's (to see how the dataset should look like I have uploaded my own dataset here) path. And just like that you are ready to fine-tune this model!

# Quantization and Inference
The notebook named 'Quantization' has the code for both the quantized loading of the model and the inference (predictions) of the model. I opted for the quantization before the inference so that anyone can try the model on their own pc first and create an idea on how it works. It is very easy to set up. You just need your HuggingFace token again and point the code to where your LoRA config files are located. I will share the location of my LoRA configs at the end of this README file.

# Versions
This project is an ongoing work. I will be uploading new versions with broader range soon. Stay tuned (or should i say fine-tuned)!

# Resources
Download my LoRA configs here: https://drive.google.com/drive/folders/14SLqsQQf0TatOt1S7lQGJHcH7U5ThMx8?usp=sharing <br>
Learn basics here: https://aiml.com/what-do-you-mean-by-pretraining-finetuning-and-transfer-learning-in-the-context-of-machine-learning-or-language-modeling/

