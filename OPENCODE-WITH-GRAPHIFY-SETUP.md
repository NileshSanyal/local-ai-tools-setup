# **Welcome** 👋

Below guide will help you to setup AI tools locally. If you feel you don't want to share your private data while using online AI tools, then you are at right place!

You will find enough information such that you can setup your environment to use AI locally.

# **A Quick Note**
By following below steps you will be able to set up local AI powered development environment using Graphify inside Opencode agent.

# **Prerequisites**
- ✅ A laptop or desktop with proper internet connection.
- ✅ Visual Studio Code Editor
- ✅ Desire to learn new and emerging Generative AI technologies.
- ✅ You need to have Opencode installed in your system, if not please visit [Setup Opencode with Openrouter](OPENCODE-WITH-OPENROUTER-SETUP.md)

If you are looking for other tutorials, feel free to refer to below guides...

- 🧑‍💻 [Setup LM Studio with Roo Code Extension](LM-STUDIO-WITH-ROO-SETUP.md)
- 🧑‍💻 [Setup Ollama with Continue Extension](OLLAMA-WITH-CONTINUE-SETUP.md)
- 🧑‍💻 [Setup Opencode with Gitnexus](OPENCODE-WITH-GITNEXUS-SETUP.md)

# **System Requirements**

| Software & Hardware | Specification |
|---|---|
| OS | Windows 11 |
| RAM | 8GB or more |
| GPU | Not mandatory |
| Processor | Intel i5 latest generation or AMD Ryzen 5 |

# **Prerequisites Before Installing Graphify**

| Software | Specification |
|---|---|
| Python | 3.10+ |
| uv | any |

## **Install Graphify**

- Visit [this link](https://github.com/safishamsi/graphify) to get documentation on installing Graphify.

Open your terminal, and run 

```bash
uv tool install graphifyy
``` 
You will see something similar as below, if Graphify installed properly.

![graphify-setup-1](images/graphify-setup-1.png "Graphify Setup 1")

## **Register Graphify with Opencode**

Run below command in terminal...

```bash
graphify install --platform opencode
```
You will see something similar as below,

![graphify-setup-2](images/graphify-setup-2.png "Graphify Setup 2")

## **Running Graphify to Generate Knowledge Graph in Opencode**

- Make sure to run opencode agent inside a project folder.

- Navigate to project folder and type **opencode** in that location.

- Then in the terminal, type below as shown in the screenshot.

![graphify-setup-3](images/graphify-setup-3.png "Graphify Setup 3")

- Wait for some time. After it is finished, you will see something as shown below.

![graphify-setup-4](images/graphify-setup-4.png "Graphify Setup 4")

- Also, you will notice a HTML file is generated and after opening that you will see the graph of your project.

![graphify-setup-5](images/graphify-setup-5.png "Graphify Setup 5")

__Note__ : The project for which I generated graph was pretty small project.

## **Making Sure Graphify is Used By Opencode Everytime**

- Run **graphify opencode install** in the terminal outside of opencode.

![graphify-setup-6](images/graphify-setup-6.png "Graphify Setup 6")

- After running above command, it will create an AGENTS.md file in your project and it will also register graphify plugin for your project.

## 🧪Testing

### Test 1
![graphify-setup-7](images/graphify-setup-7.png "Graphify Setup 7")

### Test 2
![graphify-setup-8](images/graphify-setup-7.png "Graphify Setup 8")

