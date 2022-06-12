FROM openvino/ubuntu20_dev:latest
USER root
RUN apt update -y
RUN apt install -y curl vim
RUN update-alternatives --install /usr/bin/python python /usr/bin/python3 10
WORKDIR /root
RUN omz_downloader --name mobilenet-v3-small-1.0-224-tf
RUN omz_downloader --name person-reidentification-retail-0288
RUN pip install jupyter opencv-python matplotlib pytube monai yaspin
RUN pip install torch==1.9.1 nncf[torch]
RUN pip install protobuf==3.9.2
RUN pip install paddlepaddle paddlehub
RUN pip install jupyterlab

#remember mount notebooks at launch time
#COPY openvino_notebooks/notebooks /root/notebooks
RUN mkdir /root/.jupyter
COPY jupyter_configs/nopassword.json /root/.jupyter/jupyter_notebook_config.json 
COPY start_notebook.sh /root
CMD ["./start_notebook.sh"]
EXPOSE 8888
