## Using Docker

Install

```bash
docker pull sagemath/sagemath
```

Run

```bash
docker run -it --mount type=bind,source="$(pwd)",target=/app  sagemath/sagemath:latest sage /app/run.py
```

## Using Apt packages (Ubuntu 23.10)

Install

```bash
sudo apt install sagemath

curl \
-O https://mirror.enzu.com/ubuntu/pool/universe/s/singular/libsingular4-dev-common_4.3.1-p3+ds-1_all.deb \
-O https://mirror.enzu.com/ubuntu/pool/universe/s/singular/libsingular4-dev_4.3.1-p3+ds-1_amd64.deb \
-O https://mirror.enzu.com/ubuntu/pool/universe/s/singular/libsingular4m3n0_4.3.1-p3+ds-1_amd64.deb \
-O https://mirror.enzu.com/ubuntu/pool/universe/s/singular/singular-data_4.3.1-p3+ds-1_all.deb \
-O https://mirror.enzu.com/ubuntu/pool/universe/s/singular/singular-modules_4.3.1-p3+ds-1_amd64.deb \
-O https://mirror.enzu.com/ubuntu/pool/universe/s/singular/singular-ui_4.3.1-p3+ds-1_amd64.deb \
-O https://mirror.enzu.com/ubuntu/pool/universe/s/singular/singular_4.3.1-p3+ds-1_amd64.deb \


sudo dpkg -i libsingular4-dev-common_4.3.1-p3+ds-1_all.deb \
libsingular4-dev_4.3.1-p3+ds-1_amd64.deb \
libsingular4m3n0_4.3.1-p3+ds-1_amd64.deb \
singular-data_4.3.1-p3+ds-1_all.deb \
singular-modules_4.3.1-p3+ds-1_amd64.deb \
singular-ui_4.3.1-p3+ds-1_amd64.deb \
singular_4.3.1-p3+ds-1_amd64.deb

sudo apt-mark hold \
libsingular4-dev-common \
libsingular4-dev \
libsingular4m3n0 \
singular-data \
singular-modules \
singular-ui \
singular

rm -f libsingular4-dev-common_4.3.1-p3+ds-1_all.deb \
libsingular4-dev_4.3.1-p3+ds-1_amd64.deb \
libsingular4m3n0_4.3.1-p3+ds-1_amd64.deb \
singular-data_4.3.1-p3+ds-1_all.deb \
singular-modules_4.3.1-p3+ds-1_amd64.deb \
singular-ui_4.3.1-p3+ds-1_amd64.deb \
singular_4.3.1-p3+ds-1_amd64.deb
```

Run

```bash
sage run.py
```
