# **Welcome** 👋

Below guide will help you to setup AI tools locally. If you feel you don't want to share your private data while using online AI tools, then you are at right place!

You will find enough information such that you can setup your environment to use AI locally.

# **A Quick Note**
By following below steps you will be able to set up local AI powered development environment using Ollama inside Visual Studio Code Editor. 

If you are looking for other tutorials, feel free to refer to below guides...

- 🧑‍💻 [Setup LM Studio with Roo Code Extension](LM-STUDIO-WITH-ROO-SETUP.md)
- 🧑‍💻 [Setup Ollama with Continue Extension](OLLAMA-WITH-CONTINUE-SETUP.md)
- 🧑‍💻 [Setup Opencode with Openrouter](OPENCODE-WITH-OPENROUTER-SETUP.md)
- 🧑‍💻 [Setup Opencode with Graphify](OPENCODE-WITH-GRAPHIFY-SETUP.md)

# **Prerequisites**
- ✅ A laptop or desktop with proper internet connection.
- ✅ Visual Studio Code Editor
- ✅ Desire to learn new and emerging Generative AI technologies.


# **System Requirements**

| Software & Hardware | Specification |
|---|---|
| OS | Windows 11 |
| RAM | 8GB or more |
| GPU | Not mandatory |
| Processor | Intel i5 latest generation or AMD Ryzen 5 |

## **Install Ollama**
Install Ollama by visiting [this link](https://ollama.com/). Then click Download button. It's pretty straight-forward process.

## **Check whether Ollama is installed properly**

Open your terminal, and run 

```bash
ollama --help
``` 
You will see something similar as below, if Ollama installed properly.

![ollama-installed-check](images/ollama-install-check.png "Ollama Installed")
---

## **Download local model in Ollama for Local Use**

Here, the below command we will download Qwen2.5 coder 7B variant. If you have 16 GB RAM, it's more than enough for you. Otherwise, if you have 8GB RAM then you can choose any other variant which is less than 7B. 

```bash
ollama pull qwen2.5-coder:7b
``` 

## **Check whether local model is properly downloaded**

```bash
ollama list
```

You will see something similar as below.

![ollama-model-downloaded](images/ollama-list.png "Ollama list")
---

## **Configure Ollama to Act as Local Inference Server**

 ❇️ Open Ollama and then click on Settings option.

![ollama-settings-image](images/ollama-settings.png "Ollama Settings")

 ❇️ Click Expose Ollama to the Network toggle button. Also, increase context length as per your requirement.

![ollama-expose-image](images/ollama-expose-to-network.png "Ollama Expose")

 ❇️ Run Locally Downloaded Model inside Ollama

First, we need to know the model id to run, issue below command to do that.

```bash
ollama list
``` 
![ollama-model-downloaded](images/ollama-list.png "Ollama list")

Next, run below command to run downloaded model. 

```bash
ollama run qwen2.5-coder:7b
``` 
When it's running type "Hi". You will see something similar as below.

![ollama-active-model](images/model-running.png "Ollama active model")

Type **/bye** to close the interaction session with the local llm.

Double check to ensure you're running the model currently, by issuing below command.

```bash
ollama ps
``` 
You will something as below.

![ollama-running-model](images/active-ai-model.png "Ollama running model")

 ❇️ Set Environment Variables 

```bash
setx OLLAMA_DEBUG 1
setx OLLAMA_LOG_LEVEL debug
setx OLLAMA_CONTEXT_LENGTH 128000
``` 
You will something similar as below.

![ollama-env-setup](images/ollama-env-before-serve.png "Ollama env setup")

 ❇️ Run Ollama as local inference server

```bash
ollama serve
```
---

## **Install Visual Studio Code Extension**

Open Visual Studio Code and goto Extensions tab, search Roo code. Click Install button.

![vs-code-extension](images/roo-code-extension.png "Roo Code Extension")

## **Configure Roo Code to Use Ollama's Local Inference Server**

- Click Roo Code Icon inside VS Code, click it's Settings icon.

You will something similar as below.

![roo-code-settings1](images/roo-code-settings-1.png "Roo Code Settings 1")

- Type Ollama and click Create Profile button.

![roo-code-settings2](images/roo-code-settings-2.png "Roo Code Settings 2")

- In API Provider section, type Ollama in search text box and select Ollama option.

![roo-code-settings3](images/roo-code-settings-3.png "Roo Code Settings 3")

- Don't edit base URL, if you didn't modify default one.

- In Model drop-down, the model will be visible once you click the drop down. Otherwise check if you have enabled Ollama to expose to network in Ollama Settings.

![roo-code-settings4](images/roo-code-settings-4.png "Roo Code Settings 4")

- Click **Save** button.

- Also, increase context length inside Roo Code as per your Ollama setup.

![roo-code-settings8](images/roo-code-settings-8.png "Roo Code Settings 8")

All done so far! Just make sure newly created **Ollama** profile is active in Roo code extension.

![roo-code-settings5](images/roo-code-settings-5.png "Roo Code Settings 5")

Change the mode of interaction to **Ask** if it's anything othar than **Ask**.

![roo-code-settings6](images/roo-code-settings-6.png "Roo Code Settings 6")

## 🧪Testing The Setup

Type a simple prompt in Roo code and hit the Return key on keyboard or click plane icon.

```text
Hi, can you write javascript code to add two numbers.
```

![roo-code-settings7](images/roo-code-settings-7.png "Roo Code Settings 7")

Wait for some time. After waiting you will see response in visual studio code.

## **Important Note**

While using Qwen2.5 Coder 7B in this setup, I got memory exhausted error from Roo. So, I tried with different variant of same model i.e, 1.5B variant's Q8 precision.

I did that using below ollama command

```bash
ollama pull qwen2.5-coder:1.5b-instruct-q8_0
```
But, it resuled errors similar to one shown below.

![roo-code-output2](images/ollama-roo-code-output2.png "Roo Code Output 2")

Then I tried a different model Qwen3.5 2B variant.

```bash
ollama pull qwen3.5:2b
```

Then I got good response, as shown below.

![roo-code-output1](images/ollama-roo-code-output1.png "Roo Code Output 1")

## 📒Lesson Learnt After This Experiment

Not every local AI model with smaller variant (2B, 1.5B) is capable of running tool calls. It depends on the model architecture and model features mostly. That's why Qwen2.5 Coder's 1.5B variant was unable to perform the prompt instructions. Although, Qwen3.5 2B variant was able to follow the instructions clearly.

