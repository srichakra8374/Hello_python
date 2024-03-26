## Created a docker image with new hello world python program
1. Created a new python project test.
2. Created a application      
```     
hello.py"
```
Written python code to print 

print('hello,this is a test to my python and docker knowledge')
3. Created a Docker file to run image.
   
    FROM python:3.9-slim
WORKDIR /app
RUN apt-get update \
    && apt-get upgrade -y \
    && apt-get install -y gcc default-libmysqlclient-dev pkg-config \
    && rm -rf /var/lib/apt/lists/*
COPY . .

CMD ["python", "hello.py"]
4. Build image 
     docker build -t python_hello_image .
5. Runned image 
     docker run -p 8000:8000 --name python_hello_container python_hello_image
