- Step1: Run "pip3 install transformers==4.6.1"
- step2: RUN "pip3 install torch==1.9.0"
- Step3: RUN "python3 summarization.py"
- Step4: docker build -t summarization .
- Step5: docker run -p 80:80 --gpus all summarization



If you want to run the API indefinitely, use console applications like "Screen" 

GPU used: g4dn.4xlarge
<br>
AMI: Deep Learning AMI GPU PyTorch 1.13.0 (Ubuntu 20.04) 20221110
