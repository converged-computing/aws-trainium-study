FROM public.ecr.aws/neuron/pytorch-training-neuronx:2.9.0-neuronx-py312-sdk2.27.0-ubuntu24.04

# docker build -t ghcr.io/converged-computing/aws-tranium-study:pytorch-samples .
WORKDIR /code

RUN apt-get update && apt-get install -y \
    aws-neuronx-tools \
    aws-neuronx-collectives \
    && rm -rf /var/lib/apt/lists/*

# Clone a standard benchmark (AWS Neuron Samples)
# The BERT benchmark as it is highly optimized for Trainium
RUN git clone https://github.com/aws-neuron/aws-neuron-samples.git

# We will interactively find and install requirements.
# Install requirements for the BERT training script
# WORKDIR /code/aws-neuron-samples/torch-neuronx/training/bert
# RUN pip install -r requirements.txt

# Set environment variables for EFA and Neuron
ENV FI_EFA_USE_DEVICE_RDMA=1
ENV FI_PROVIDER=efa
ENV PATH="/opt/aws/neuron/bin:${PATH}"

# Default command: Start a bash shell so you can run the benchmark manually
CMD ["/bin/bash"]
