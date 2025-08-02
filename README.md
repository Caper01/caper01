## # 🔍 Flip Fair Checker

Cek keadilan hasil HEADS/TAILS di Flip.gg menggunakan sistem transparan. Masukkan `server_seed` dan `client_seed` untuk verifikasi hasil secara independen.

## 🚀 Demo Checker Online

🔗 [Coba langsung di sini](https://caper01.github.io/flip-fair-checker)

## 🛠️ Cara Pakai

1. Masukkan `server_seed` dari hasil Flip.gg
2. Masukkan `client_seed` kamu
3. Klik tombol Cek → hasil HEADS atau TAILS akan muncul

## 📦 Versi CLI/Docker
name: Build and Push Docker Image
on:
  push:
    branches: [ main ]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v3
      - name: Set up Docker Buildx
        uses: docker/setup-buildx-action@v3
      - name: Login to DockerHub
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_PASSWORD }}
      - name: Build and push Docker image
        uses: docker/build-push-action@v5
        with:
          context: .
          push: true
          tags: caper01/flip-fair-checker:latest

---
Untuk advanced user:
```bash
docker run -e SERVER_SEED=abc -e CLIENT_SEED=user123 caper01/flip-fair-checker
Hi there 👋
name: Build and Push Docker Image

on:
  push:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v3

      - name: Set up Docker Buildx
        uses: docker/setup-buildx-action@v3

      - name: Login to DockerHub
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_PASSWORD }}

      - name: Build and push Docker image
        uses: docker/build-push-action@v5
        with:
          context: .
          push: true
          tags: caper01/myapp:latest

<!--
**Caper01/caper01** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
