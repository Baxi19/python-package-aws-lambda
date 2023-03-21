# python-package-aws-lambda

### This script creates a ZIP archive called "request_layer.zip" that contains a Python virtual environment and all of its dependencies. This makes it easy to deploy the same environment to other systems and configurations of software. It package also can be used as AWS Layer for Lambda function.

```bash
# Create a new directory called "folder"
mkdir folder

# Change to the newly created directory
cd folder

# Create a new Python virtual environment named "v-env" in the current directory
virtualenv v-env

# Activate the virtual environment "v-env"
source ./v-env/bin/activate

# Install the Python library "requests" inside the virtual environment "v-env"
pip install requests

# Deactivate the virtual environment "v-env"
deactivate

# Create a new directory called "python"
mkdir python

# Change to the "python" directory
cd python

# Copy all files and folders from the "site-packages" directory inside the "v-env" virtual environment
cp -r ../v-env/lib/python3.9/site-packages/* .

# Change to the parent directory
cd ..

# Create a ZIP archive named "request_layer.zip" containing the "python" directory
zip -r request_layer.zip python
```
