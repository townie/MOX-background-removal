FROM ubuntu:20.04 as moxbackgroundremoverserver

WORKDIR /app

RUN apt-get update && apt-get install -y --no-install-recommends python3 python3-pip python3-dev llvm llvm-dev
RUN pip install torch==1.7.1+cpu torchvision==0.8.2+cpu -f https://download.pytorch.org/whl/torch_stable.html

COPY . .
RUN pip install -r requirements.cpu.txt
RUN pip3 install rembg

CMD ["rembg-server", "--port", "5001"]
