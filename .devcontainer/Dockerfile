FROM jupyter/scipy-notebook

# 必要なパッケージをインストール
COPY requirements.txt /home/jovyan/work/requirements.txt
RUN pip install --no-cache-dir -r /home/jovyan/work/requirements.txt
