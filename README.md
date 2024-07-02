# Berachain-Node-Build

1. bir vps kiralayın, evde boşta duran bilgisayar / sunucu da olabilir, 16G bellek, 200G sabit disk, 6 çekirdekli cpu gereksinimleri
Ubuntu 22.04 sunucu veya masaüstü kurulabilir, openssh servisi açılabilir, yapının donanım kısmı tamamlandı!
2. FinalShell ile sunucuya giriş yapın (başka herhangi bir ssh aracı işinizi görür)
3. Go 1.20+ veya üstünü yükleyin, ben 1.21.6 kullanıyorum：
```
cd ~
wget https://go.dev/dl/go1.21.6.linux-amd64.tar.gz
sudo tar -xzf go1.21.6.linux-amd64.tar.gz -C /usr/local/
echo 'export PATH=$PATH:/usr/local/go/bin' | tee -a ~/.bashrc
source ~/.bashrc
go install github.com/onsi/ginkgo/v2/ginkgo@v2.14.0
echo 'export PATH=$PATH:$(go env GOPATH)/bin' | tee -a ~/.bashrc
source ~/.bashrc
```
   
5. Aşağıdaki yazılımı yükleyin：
```
sudo apt-get install jq -y
```
   
6. Dökümhane：
```
curl -L https://foundry.paradigm.xyz | bash
source ~/.bashrc
foundryup
```

8. Kaynak kodunu klonlayın ve çalıştırın：
```
cd ~
git clone https://github.com/berachain/polaris
cd polaris
git checkout main
make test-unit
```
9. Test ağının başlatılması：
```
screen -S polaris
cd ~/polaris
make start
```

Başarılı olduktan sonra aşağıdaki ekran görüntülenir：

![image](https://github.com/tujj99/Berachain-Node-Build/assets/53027340/4ae8869b-225e-4ede-9750-a87b761d16a3)

