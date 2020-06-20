# Use an official Python runtime as a parent image
FROM python:3.7-alpine

WORKDIR /notebook

# Install any needed packages specified in requirements.txt
RUN apk update && \
    apk add --no-cache make gcc g++ libgcc libstdc++ libsodium musl libzmq zeromq-dev linux-headers python3-dev && \
    pip install --upgrade pip && \
    pip install jupyter requests bs4 boto3 PyMySQL && \
    jupyter notebook -y --no-browser --generate-config --allow-root

# Make port 8888 available to the world outside this container
EXPOSE 8888

# Run app.py when the container launches
CMD ["jupyter", "notebook", "-y", "--no-browser", "--ip", "0.0.0.0", "--allow-root", "--NotebookApp.token=''", "--NotebookApp.password=''"]
