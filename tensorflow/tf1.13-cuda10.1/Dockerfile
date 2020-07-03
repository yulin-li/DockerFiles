FROM drhippo/cuda:devel_base

COPY ./requirements.txt ./
RUN python3 -mpip install --upgrade pip && \
    python3 -mpip install --no-cache-dir -r requirements.txt && \
    rm -rf requirements.txt

RUN pip install --no-cache-dir pandas tqdm librosa matplotlib>=3.0 tensorflow_datasets==1.0.2 tensorflow_gpu==1.13.1 absl_py soundfile pysptk