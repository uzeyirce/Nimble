# <h1 align="center">![logo](https://github.com/uzeyirce/Nimble-kurulum/assets/85512132/888baff5-7679-4365-a4be-5fb385cc3a0c)</h1>

# <h1 align="center">Nimble</h1>

![spec](https://github.com/uzeyirce/Nimble/assets/85512132/995fb34b-6c85-418f-bde2-69f9a2e17d6d)

* [Twitter](https://twitter.com/Nimble_Network)
* [Discord](https://discord.gg/mFZKS5Ev)
* [Website](https://www.nimble.technology/tokenomics)
* [Docs](https://github.com/nimble-technology/nimble-wiki)
* [Github](https://github.com/nimble-technology)

## AŞAMA 1: CLORE.AI ÜZERİNDE HESAP OLUŞTURMA

Clore ai sitesine aşağıdaki bağlantıdan üye olun.

[LINK](https://clore.ai?ref_id=wrxtelh2)



### Account sayfasından deposite basarak clore adresimizi alıyoruz. Gate veya Mexc den bu hesaba Clore yüklüyoruz. 

![2](https://github.com/uzeyirce/Nimble-kurulum/assets/85512132/2f339cc8-cf9e-4136-8dc0-a87f900035a4)



### Hesabımıza clore geçtikten sonra artık gereksinimlere uygun makine kiralama aşamasına geçiyoruz. Aşağıda makine kiralarken dikkat etmeniz gereken yerleri  yeşil alan içinde görebilirsiniz.
### buna göre makine rent dediğmiz zaman o makine kiralama aşamasına geçmiş olur. 
![3](https://github.com/uzeyirce/Nimble-kurulum/assets/85512132/17c6524a-71c7-4f8c-bfc8-cc46a1885b99)


### Kiralama sayfasında lokasyon bilgisini not edin.
### Pytorch seçin
### Ve aşağıdaki WEBUI passwordı mutlaka not alın. önemli.

![4](https://github.com/uzeyirce/Nimble-kurulum/assets/85512132/7dd15751-4004-4e1f-a0bc-e836c048261c)

###  My orders kısmına tıklayalım. Deployed yazısını gördüğünüzde sunucunuz hazır demektir. Bağlantıya tıklayalım açılan sayfadan JyputerLABı seçelim.
Kullanıcı adı isterse : clore
şifre bir üstte kaydeetiğiniz şifre

![5](https://github.com/uzeyirce/Nimble-kurulum/assets/85512132/9629f050-0f50-4e2b-bd3a-0f2b3d1f62eb)


### Arayüze başarılı bir şekilde girdikten sonra terminal yazan girelim.

![6](https://github.com/uzeyirce/Nimble-kurulum/assets/85512132/fe8ffb27-8a52-4c19-90ec-59b237df5dcc)


## AŞAMA 2: NIMBLE KURULUM
KODLARI SIRASI İLE KOPYALAYIP TERMİNALE YAPIŞTIRALIM. 


güncellemeleri yapalım

```bash
sudo apt update
```

gerekli dosyaları indirelim

```bash
wget https://go.dev/dl/go1.22.1.linux-amd64.tar.gz
```

root dizinine geçelim.
```bash
sudo su
```
dosyaları silelim.
```bash
sudo rm -rf /usr/local/go && tar -C /usr/local -xzf go1.22.1.linux-amd64.tar.gz
```

roottan çıkalım.
```bash
exit
```

değişkenleri güncelleyelim.
```bash
export PATH=$PATH:/usr/local/go/bin
```

python3 kuralım.
```bash
sudo apt install python3-venv -y
```


### NIMBLE WALLET OLUŞTURMA


```bash
sudo apt install git
```

```bash
mkdir $HOME/nimble && cd $HOME/nimble
```

```bash
git clone https://github.com/nimble-technology/wallet-public.git
```

```bash
cd wallet-public
```

```bash
make install
```

```bash
cd
```

```bash
cd go/bin
```

!!!Aşağıdaki kodu girdikten sonra çıkan seedleri ve dosyaya verdiğiniz şifreyi kaydetmeyi unutmayın. Bu cüzdana bir ad vereceksiniz. Karşımaması açısından masterwallet verebilirsiniz. <  > bu işratleri kaldıracaksınız.

```bash
./nimble-networkd keys add <masterwalletname>
```

Yeniden cüzdan oluşturma kodu giriyoruz. Yine bu cüzdana verdiğiniz şifreyi kaydetmeyi unutmayınız. Karışmaması için buna subwallet adı verebilirsiniz.
```bash
./nimble-networkd keys add <subwalletname>
```

### NIMBLE MINER ÇALIŞTIRMA

```bash
cd
```

```bash
git clone https://github.com/nimble-technology/nimble-miner-public.git
```

```bash
cd nimble-miner-public
```

```bash
sudo rm requirements.txt
```


Aşağıdaki kodu tek seferde kopyalıp terminale yaptıştırın.

```bash
echo '
requests==2.31.0
torch==2.2.1
accelerate==0.27.0
transformers==4.38.1
datasets==2.17.1
numpy==1.24
gitpython==3.1.42' > requirements.txt
```

```bash
git pull
```

yükleme uzun sürebilir. Bitene kadar bekliyoruz.
```bash
make install
```
Bittikten sonra

```bash
pip uninstall fsspec -y
```

```bash
pip install 'fsspec==2023.10.0'
```

Minerı aktive ediyoruz.

```bash
source ./nimenv_localminers/bin/activate
```

Screen açıyoruz

```bash
screen  -S anasayfa
```

miner çalıştırma kodu var sırada. sub_nimble_address yazan yere aldığınız subwallet adresini yazıyorsunuz.

```bash
make run addr=sub_nimble_address
```

ERROR VEREN BİR LOG AKIŞI OLUR. MASTER WALLET KAYDEDİLMEDİ DİYE. MASTER WALLETI DISCORDDAN  KAYDETMEZSENİZ MINING BAŞLAMAZ.



## AŞAMA 3: MASTER WALLETI VE SUB WALLETI DISCORD AŞAMASI. 

Bunun için Nimble discordun #walletapplication kanalında bot etkileşime geçiyoruz. DM kutumuza gelen sorulara cevap vereceksiniz.
1-	MASTER CUZDAN ADRESİ
2-	SUB WALLET ADRESI,İŞLEMCİ
3-	LOKASYON YAZIP İŞLEM TAMAMLANIYOR.
4-  Son soruya beni yazabilirsiniz.

ÖRNEK 
nimble1a5wr7XXXXXXXXXXXXXXXXXXMASTER
nimbleXXXXXXXXXXXXXXDDDXXXXXXXXXXSUB,4090
RU
uxeyir (buraya beni yazabilirsiniz.)

Cüzdanınız onaylandıktan sonra size bottan bildirim gelir. Error veren loglar normale döner.

![7](https://github.com/uzeyirce/Nimble-kurulum/assets/85512132/aa5dbc19-74d7-4552-baac-dd4f138fe89a)

CTRL A D ile screeni kapatıp çıkıyoruz.

TEŞEKKÜRLER

* [Twitter](https://twitter.com/uzeyirce)



