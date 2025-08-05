
# Java code analysis tool

The Java Code Analyzer is a Python-based tool that scans through a directory of Java files, parses their syntax trees using ollama with Mistral LLM, and generates a consolidated analysis report. The report includes class structures, method definitions, field declarations, and optionally their access modifiers and inheritance relationships.
This tool is helpful for:
- Understanding large Java codebases
- Generating lightweight documentation
- Performing static analysis for refactoring or auditing

There are certain prerequisities for installing this tool on your device. Following are the necessary environment setups required to run the tool on your local machine: 
1. Jupyter Notebook
2.	Ollama Desktop 
3.	Downloading mistral model via Ollama 
4.	Download necessary python packages 
The detailed environment setup steps are as follows:



# Step 1: Install Python (Required for Jupyter)
1.	Download the latest Python installer from:
 https://www.python.org/downloads/windows/

2.	Run the installer
- 	Check “Add Python to PATH” before clicking "Install Now".
3.	Verify installation by running the following commands on your windows terminal


```
python --version
pip –version
```
Successful installation will show you the following result: 
<img width="940" height="128" alt="image" src="https://github.com/user-attachments/assets/db9cf30f-5ce3-4199-ab72-7ac3252f1d25" />



# Step 2: Install Jupyter Notebook
1.	Open Command Prompt or PowerShell.
2.	Install Jupyter using pip:

	```
	pip install notebook
	```

3.	Launch Jupyter via Powershell/Command prompt:
jupyter notebook
It will open in your default browser at: `http://localhost:8888`

<img width="940" height="376" alt="image" src="https://github.com/user-attachments/assets/bd694678-efcf-482f-b495-35e93c56f1c1" />


# Step 3: Install Ollama
1.	Visit:  https://ollama.com/download
2.	Download the Windows installer and run it.
3.	After installation, verify by running on your command prompt/Powershell:
```
ollama --version
```
<img width="940" height="157" alt="image" src="https://github.com/user-attachments/assets/cae4845f-f470-4992-b273-c2ad592dce39" />

# Step 4: Run Mistral on Ollama
Ollama hosts and runs models locally. To install and run Mistral:
1.	Pull the model:
```
ollama pull mistral
```
2.	Start a chat with it:
```
ollama run mistral
```

You can now type prompts and interact with the Mistral model locally via Command prompt. 
For our particular use case we shall be using Jupyter notebook. 

# Step 5: Required Python packages
Install the packages via your command prompt/Powershell before opening the jupyter notebook:
```
pip install requests os

```

# Step 6: Upload Jupyter notebook 
-	In the Jupyter web interface, click the Upload button at the top-right.
-	Select your .ipynb file from your system.
-	Click the blue "Upload" button next to the filename once it's added to the list.
-	Once upload is finished navigate to the filename and double click to open and run it.

<img width="954" height="237" alt="image" src="https://github.com/user-attachments/assets/b93829de-455b-4b56-af5b-5afd68ac0954" />


# Step 7: Change folder path on Jupyter
-	In the Jupyter notebook travel to the second code cell.
-	Change the mentioned folder path to the folder path of the java code file on your system.
<img width="940" height="347" alt="image" src="https://github.com/user-attachments/assets/fa5d7d88-ca01-4456-9e45-76bc0623d645" />

-	To find your java project’s local file path simply navigate to the project folder double click and select Copy as path.
<img width="940" height="547" alt="image" src="https://github.com/user-attachments/assets/a2567634-84e1-4354-9f36-7f7958b19259" />

```
    import os
    
    # Path to your main Java project folder
    root_dir = r"<your folder path here>"
    
    # Step 1: Find all .java files recursively
    java_files = []
    for dirpath, _, filenames in os.walk(root_dir):
        for file in filenames:
            if file.endswith(".java"):
                java_files.append(os.path.join(dirpath, file))
    
    
    all_code_lines = []
    
    for file_path in java_files:
        with open(file_path, "r", encoding="utf-8") as f:
            all_code_lines.append(f.read())
    
    # Step 3: Join everything into one string variable
    java_code_sample_1 = '"""\n' + "\n\n".join(all_code_lines) + '\n"""'
    
    # Optional: Print or confirm the size
    print("Total lines of Java code:", java_code_sample.count("\n"))
```

<img width="940" height="347" alt="image" src="https://github.com/user-attachments/assets/a559e277-88f8-400d-977c-208f1dea7a45" />


# Execution
-	Once the path is changed click on run button and select run all cells.
  
<img width="940" height="420" alt="image" src="https://github.com/user-attachments/assets/ed10c418-e3cd-4b6a-89df-7441be34b06a" />

- You should be able to see a generated documentation on your jupyter notebook.
  
<img width="940" height="409" alt="image" src="https://github.com/user-attachments/assets/3f71c67b-e64d-4247-b683-ded3896f2ac3" />


- The text is already formatted as a markdown document. This block of text can be directly copied and pasted onto a markdown generator and read as a comprehensive documentation of the code. 
- Additionally the code also automatically writes this text into a markdown file which is directly saved in your system's downloads folder when run the jupyter notebook.
  
<img width="940" height="355" alt="image" src="https://github.com/user-attachments/assets/50e8dc77-5dd1-4b22-b98b-ff48a068f4b7" />

- The downloads folder on your system, will have the saved file.
<img width="940" height="250" alt="image" src="https://github.com/user-attachments/assets/768427d9-f0ac-4481-8818-663d4f3f533f" />








