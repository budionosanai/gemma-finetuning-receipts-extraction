## 📘 Overview

This repository explains end-to-end fine-tuning Gemma 3-4B-Instruct model for receipt extraction use case that can extracting structured and accuracy information from receipt photo.

## 📁 Repository Structure

| File / Notebook | Description |
| :--- | :--- |
| `GemmaBeforeFineTuning.ipynb` | Notebook of deploy Gemma 3-4B-Instruct model and test upload several receipts to Gemma model before fine-tuning. |
| `GemmaFineTuning.ipynb` | Notebook of fine-tuning Gemma 3-4B-Instruct model using PEFT (Parameter-Efficient Fine-Tuning) technique, LoRA (Low-Rank Adaptation) technique and SFT (Supervised Fine-Tuning) technique then export result of this fine-tuning model to HuggingFace model repository. |
| `GemmaAfterFineTuning.ipynb` | Notebook of deploy fine-tuning model and test upload same receipts to fine-tuning model and see difference responses from receipts extraction before and after fine-tuning. |
| `gokbbq.jpg`, `ovenfc.jpg` and `strongflour.jpg` | Sample photo file used in the `GemmaBeforeFineTuning.ipynb` and `GemmaFineTuning.ipynb`. |

## ✅ Prerequisites

1.  **Amazon Web Services (AWS)**: Access to **Amazon SageMaker AI** features such as SageMaker Notebook Instance (Fine-tuning) and SageMaker Endpoint (Inference), you can sign up/sign in [here.](https://console.aws.amazon.com)

**NOTE :** Ensure your AWS region have quota for **ml.g6.2xlarge** instance type for both Notebook instance usage and Endpoint usage. If want to request quota of instance type, you can see this [link.](https://docs.aws.amazon.com/servicequotas/latest/userguide/request-quota-increase.html) but if you don't want to use Amazon SageMaker, use Google Colab.

2. **Hugging Face**: Access to create access token, Gemma model and [this receipt dataset](https://huggingface.co/datasets/cindyliang/receipts-v1), you can sign up/sign in [here.](https://huggingface.co)

## 🚀 Getting Started

1. Clone this repository
```bash
git clone https://github.com/budionosanai/gemma-finetuning-receipts-extraction.git
cd gemma-finetuning-receipts-extraction
```

2. Request access to [Gemma 3-4B-Instruct](https://huggingface.co/google/gemma-3-4b-it) model and wait approval from Google.

3. Open, run and following this notebooks :

| Notebook | Using |
| :--- | :--- |
| 1 - **[Gemma before fine-tuning](./GemmaBeforeFineTuning.ipynb)** | **SageMaker Endpoint (Inference)** or **Google Colab** and [Gemma 3-4B-Instruct](https://huggingface.co/google/gemma-3-4b-it) |
| 2 - **[Gemma fine-tuning process](./GemmaFineTuning.ipynb)** | **SageMaker Notebook Instance (Fine-tuning)** or **Google Colab** and [Gemma 3-4B-Instruct](https://huggingface.co/google/gemma-3-4b-it) |
| 3 - **[Gemma after fine-tuning](./GemmaAfterFineTuning.ipynb)** | **SageMaker Endpoint (Inference)** or **Google Colab** and [Gemma fine tuning model](https://huggingface.co/budionosan/gemma-finetuning-receipts-extraction) |

4. Create Python environment variable using python-dotenv, you can see this [link.](https://pypi.org/project/python-dotenv/) then write Hugging Face token (e.g.  `HUGGINGFACE_TOKEN=your_token_here`) in a Notepad file, then save the file with the name `....txt` (e.g. `env.txt`). You can see this [link.](https://huggingface.co/docs/hub/en/security-tokens) to create HuggingFace token.

## ⚠️ Warning

**Ensure securely API keys such as Hugging Face token — DO NOT HARDCORE them in notebooks.**

## 📚 Resources

* [Amazon SageMaker documentation](https://docs.aws.amazon.com/sagemaker/)
* [SFT for Gemma 3 Script](https://github.com/huggingface/trl/blob/main/examples/scripts/sft_vlm_gemma3.py)
* [PEFT documentation](https://huggingface.co/docs/peft/en/index)
* [LoRA documentation](https://huggingface.co/docs/peft/main/en/conceptual_guides/lora/)
* [SFT documentation 1](https://huggingface.co/docs/trl/sft_trainer#training-vision-language-models) and [SFT documentation 2](https://huggingface.co/docs/trl/main/en/training_vlm_sft)

## 🙏 Acknowledgments

**Amazon Web Services, Hugging Face, Google Gemma and Google Colab**
