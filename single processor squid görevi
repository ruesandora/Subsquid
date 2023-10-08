

# Deploy a single processor squid görevi

### I. Bağımlılıkları yükleyin: Node.js, Docker, Git.
Not: Daha önce Subsquid kurulumu yaptıysanız 1. adımı geçin.
</details>
<details>
<summary>On Linux</summary>

```bash
sudo apt update -y && sudo apt upgrade -y
apt install Node.js
apt install npm
npm i @npmcli/fs
```
DOCKER kurulumu
```bash
sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo docker run hello-world
```


</details>

### II. Subsquid CLI'yi yükleyin


```bash
npm install --global @subsquid/cli@latest
```
```bash
sqd --version
```
Böyle çıktı verecek. Node versiyon farklı olabilir takılmayın devam edin.
```
@subsquid/cli/2.5.0 linux-x64 node-v20.5.1
```

### III. Squid çalıştırma.

1. Squid klasörü oluşturup içine girmek için aşağıdaki kodları girin.
   ```bash
   sqd init my-single-proc-squid -t https://github.com/subsquid-quests/single-chain-squid
   ```
   ```bash
   cd my-single-proc-squid
   ```
  

2. Sitede Get key tuşuna bastığınızda size `singleProc.key` dosyasını verecek. Bunu `single-chain-squid/query-gateway/keys` dizinine atın. Sonra aşağıdaki kodlar ile devam edin.

3. ```bash
   sqd up
   ```
  Biraz bekliyoruz ve devam ediyoruz.
   ```bash
   npm ci
   sqd build
   sqd migration:apply
   ```
4. Squidi başlatın
   ```bash
   sqd run .
   ```
  Böyle çıktı verdikten sonra siteden sync durumunu kontrol edin. Sync olduğunda verify ile puanınızı alın.
   ```
   [api] 09:56:02 WARN  sqd:graphql-server enabling dumb in-memory cache (size: 100mb, ttl: 1000ms, max-age: 1000ms)
   [api] 09:56:02 INFO  sqd:graphql-server listening on port 4350
   [processor] 09:56:04 INFO  sqd:processor processing blocks from 6000000
   [processor] 09:56:05 INFO  sqd:processor using archive data source
   [processor] 09:56:05 INFO  sqd:processor prometheus metrics are served at port 33097
   [processor] 09:56:08 INFO  sqd:processor:mapping Burned 59865654 Gwei from 6000000 to 6016939
   [processor] 09:56:08 INFO  sqd:processor 6016939 / 17743832, rate: 5506 blocks/sec, mapping: 304 blocks/sec, 182 items/sec, eta: 36m
   ```
  Daha sonra CTRL+C ile çıkın ve squidi durdurup diğer göreve geçin. Bütün görevler birbirinin aynısı sadece key dosyası ve klasör dizini değişiyor ona dikkat edin.
   ```bash
   sqd down
   ```


