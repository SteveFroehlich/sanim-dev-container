FROM python:3.8-slim

# Update the package repositories and install Git
RUN apt-get -y update && apt-get -y install git

RUN apt-get update -qq \
    && apt-get install --no-install-recommends -y \
        ffmpeg \
        build-essential \
        gcc \
        cmake \
        libcairo2-dev \
        libffi-dev \
        libpango1.0-dev \
        freeglut3-dev \
        pkg-config \
        make \
        wget \
        ghostscript \

    # development resources
        git
        
RUN pip install jupyterlab

# start of test code, below is blow away
RUN pip install pandas

# Create a directory for your Jupyter notebooks
RUN mkdir /notebooks

# Set the working directory
WORKDIR /notebooks

# Expose the default Jupyter Notebook port (8888)
EXPOSE 8888

# Start Jupyter Notebook when the container runs
CMD ["jupyter", "notebook", "--ip=0.0.0.0"]
