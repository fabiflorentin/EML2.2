FROM public.ecr.aws/lambda/python:3.10

# Diretório onde o código e arquivos serão copiados
WORKDIR /var/task

# Dependências 
RUN yum install -y libGL libGL-devel
RUN pip install opencv-python-headless numpy torch torchvision Pillow boto3 ultralytics

# Copia o código da função Lambda
COPY lambda_function.py ${LAMBDA_TASK_ROOT}

# Copia o modelo treinado 
COPY yolov8_model.pt ${LAMBDA_TASK_ROOT}

# Comando para executar a função Lambda
CMD ["lambda_function.lambda_handler"]
