FROM drhippo/cuda:devel_base_cuda100

COPY ./requirements.txt ./
RUN python3 -mpip install --upgrade pip && \
    python3 -mpip install --no-cache-dir -r requirements.txt && \
    rm -rf requirements.txt