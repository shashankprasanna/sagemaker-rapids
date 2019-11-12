FROM rapidsai/rapidsai:cuda10.0-runtime-ubuntu16.04

RUN apt-get update && apt-get install -y --no-install-recommends \
    software-properties-common \
    build-essential \
    gcc-4.9 \
    g++-4.9 \
    gcc-4.9-base

RUN pip install sagemaker-containers

# Copies the training code inside the container
COPY rapids-higgs.py /opt/ml/code/rapids-higgs.py

# Defines train.py as script entry point
ENTRYPOINT ["/opt/conda/envs/rapids/bin/python", "/opt/ml/code/rapids-higgs.py"]