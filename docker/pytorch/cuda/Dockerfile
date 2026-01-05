FROM public.ecr.aws/deep-learning-containers/pytorch-training:2.9.0-cpu-py312-ubuntu22.04-ec2-v1.5
# https://github.com/aws/deep-learning-containers/releases/tag/v1.5-pt-ec2-2.9.0-tr-py312

# aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 633731392008.dkr.ecr.us-east-1.amazonaws.com
# docker build -t 633731392008.dkr.ecr.us-east-1.amazonaws.com/aws-trainium-study/pytorch-samples:cuda .
# docker push 633731392008.dkr.ecr.us-east-1.amazonaws.com/aws-trainium-study/pytorch-samples:cuda

WORKDIR /code
RUN git clone https://github.com/aws-neuron/aws-neuron-samples.git

# Install optimizations for NVIDIA
RUN pip install accelerate

# 5. Default command
CMD ["/bin/bash"]
