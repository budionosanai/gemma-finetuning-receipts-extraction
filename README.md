## Gemma 3 4B Instruct before Fine-tuning

**[Gemma before fine-tuning](./GemmaBeforeFineTuning.ipynb)** : deploy [Gemma 3 4B Instruct](https://huggingface.co/google/gemma-3-4b-it) to **Amazon SageMaker** then test prompt engineering with instruction of receipts extraction.

**NOTE :** Choose **ml.g6.2xlarge** for Notebook instance type.

## Gemma 3 4B Instruct Fine-tuning process

**[Gemma fine-tuning process](./GemmaFineTuning.ipynb)** : fine tuning [Gemma 3 4B Instruct](https://huggingface.co/google/gemma-3-4b-it) based [receipts extraction dataset](https://huggingface.co/datasets/cindyliang/receipts-v1) using PEFT and SFT (Supervised Fine-Tuning) technique then push fine-tuning model to HuggingFace model.

**NOTE :** Choose **ml.g6.2xlarge** for Notebook instance type.

## Gemma 3 4B Instruct after Fine-tuning

**[Gemma after fine-tuning](./GemmaAfterFineTuning.ipynb)** : after fine tuning process is done, deploy [my Gemma fine tuning model](https://huggingface.co/budionosan/gemma-finetuning-receipts-extraction) to **Amazon SageMaker** then test prompt engineering with same instruction of receipts extraction.

**NOTE :** Choose **ml.g6.2xlarge** for Notebook instance type.

**NOTE :** Before try this repository, get Hugging Face token to can access Gemma 3 4B Instruct model and my fine-tuning model, then write Hugging Face token in Notepad such as **HUGGINGFACE_TOKEN = your_Hugging_Face_token** and save the token with format file name "env.txt".

**NOTE :** See different result of answer of receipt extraction between before fine-tuning and after fine-tuning then compare now.

**Reference :**

1. https://huggingface.co/docs/trl/sft_trainer#extending-sfttrainer-for-vision-language-models

2. https://github.com/huggingface/trl/blob/main/examples/scripts/sft_vlm_gemma3.py

3. https://huggingface.co/docs/trl/training_vlm_sft