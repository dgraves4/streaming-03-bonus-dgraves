# streaming-03-bonus-dgraves
This is a custom streaming project that uses RabbitMQ and a producer and consumer to read from a CSV file and write messages to a new queue every 1-3 seconds. 

This project requires some free code - beyond that available in the Python Standard Library.  The CSV file source used can be found in the references below. To avoid messing up our local default Python installation, and any other Python projects we may have, we create a local virtual environment to install and use these libraries.

## Prerequisites

1. Git
2. Python 3.7+ (3.11+ preferred)
3. VS Code Editor
4. VS Code Extension: Python (by Microsoft)
5. RabbitMQ Server installed and running locally

## Task 1. Create a Python Virtual Environment

We will create a local Python virtual environment to isolate our project's third-party dependencies from other projects.

1. Open a terminal window in VS Code.
2. Use the built-in Python utility venv to create a new virtual environment named `.venv` in the current directory.

```shell
python -m venv .venv
```

Verify you get a new .venv directory in your project. 
We use .venv as the name to keep it away from our project files. 

## Task 2. Activate the Virtual Environment

In the same VS Code terminal window, activate the virtual environment.

- On Windows, run: 
```bash
source .venv\Scripts\activate
```

Verify you see the virtual environment name (.venv) in your terminal prompt.

NOTE: When activating the environment on a second console, do the following for the reccommended use of multiple terminals:

- The recommended way - with lots of space for your terminal -  is to jump out of VS Code and run your scripts outside VS Code. 

For each concurrent terminal or process, do the following:

- Open a new Anaconda Prompt (Windows) or Terminal (Mac) window. 
- Use the cd (change directory) commandLinks to an external site to cd to your repo folder. 
- Verify your scripts are here with the dir (or ls) command. You should see your .py files. 
- Activate or verify your Python environment:  conda activate base
- Start your script: python script.py (use the name of  your file)
 

Windows example:

- Project repo location: C:\Users\dgraves4\Documents\streaming-03-rabbitmq
- Anaconda prompt opens in (base) C:\Users\dgraves4>

```bash
cd Documents/streaming-03-rabbitmq
dir
conda activate base
.venv\Scripts\activate
```
## Task 3. Install Dependencies into the Virtual Environment

To work with RabbitMQ, we need to install the pika library.
A library is a collection of code that we can use in our own code.
Learning to use free libraries that others have written to make our projects easier, faster, more reliable is a key skill for a developer.

We keep the list of third-party libraries needed in a file named requirements.txt.
Use the pip utility to install the libraries listed in requirements.txt into our active virtual environment. 

Make sure you can see the .venv name in your terminal prompt before running this command.

`python -m pip install -r requirements.txt`

## Task 4. Verify Setup (OPTIONAL - ONLY WORK ON SOME CONFIGURATIONS)

In your VS Code terminal window, run the following commands to help verify your setup.
These util files MAY be helpful to ensure you're setup correctly. 
You may have a different configuration and RabbitMQ may still work; the check looks in common places, but may not work for all installations. 
They are meant to be helpful, but are not required.

You can help by updating the code for other common configurations. 
Just fork the current repo, add your change, and create a pull request (no other changes please) and I'll pull it back in. 

```bash
py util_about.py
py util_aboutenv.py
py util_aboutrabbit.py
pip list
```
## Task 5. Execute the Producer/Sender

1. Read dgraves_emit_data.py
2. Run the file. 

It will run, emit a message to the named RabbitMQ queue, and finish.
We can execute additional commands in the terminal as soon as it finishes. 
![verifying setup](./images/verifying.png)

## Task 6. Execute the Consumer/Listener

1. Read dgraves_listen_for_data.py 
2. Run the file.