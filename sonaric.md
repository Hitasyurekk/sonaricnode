

**Minimum Sistem Gereksinimleri**

- **2 CPU**
- **2GB RAM**
- **Ubuntu 22++**

```
sudo apt-get update && sudo apt-get upgrade -y
```
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
nvm install 20
nvm use 20
npm install -g npm@latest
```
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/monk-io/sonaric-install/main/linux-install-sonaric.sh)"
```

sonaric node-info ile node çıktısını görebilirsiniz.

![alt text](https://i.hizliresim.com/d1aq2w8.png)

**Yedek almak için**

**1. Seçenek**

Aşağıdaki kodda user@sunucu-ipsi olan yerde eğer root olarak kullanıyorsanız root@sunucu-ipsi

Bu kodu kendi local pcnizdeki terminal yada powershellde yazmanız ve sunucunuzun şifresini girmeniz gerekiyor.


```
ssh -L 127.0.0.1:44003:127.0.0.1:44003 -L 127.0.0.1:44004:127.0.0.1:44004 -L 127.0.0.1:44005:127.0.0.1:44005 -L 127.0.0.1:44006:127.0.0.1:44006 user@sunucu-ipsi
```


Bu işlemi yaptıktan sonra http://localhost:44004/ linkine tıklayarak kendi nodeunuz hakkındaki bilgilere ulaşabilirsiniz.

![alt text](https://i.hizliresim.com/da2ca9u.png)

Ok ile gösterilen yerden Export Key diyerek ve bir şifre belirliyerek bilgilerinizi alabilirsiniz.

![alt text](https://i.hizliresim.com/gv0tld0.png)

**2. Seçenek**

Sunucu üzerinden identity bilgilerinizi almak için aşağıdaki kodu girip bir şifre belirleyin. SFTP bağlantısı ile sunucunuza bağlandıktan sonra root dizinindeki identity dosyanızı da localinize kaydedin.

```
sonaric identity-export -o my.identity
```

Sunucu üzerinden puanlarınızı görmek isterseniz

```
sonaric points
```

![alt text](https://i.hizliresim.com/8mpx7zo.png)

Node isminizi değiştirmek isterseniz aşağıdaki kodu girin ve isminizi belirleyin.

```
sonaric node-rename
```
