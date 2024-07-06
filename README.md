

# TCP ve UDP İstemcileri ve Sunucuları

Bu proje, basit TCP ve UDP istemcileri ve sunucuları içeren iki Python dosyasını içerir. Bu dosyalar, ağ programlama konularında temel bilgileri anlamak ve uygulamak isteyenler için örnek olarak kullanılabilir.

## Dosyalar

1. **TCPClient.py**
2. **TCPServer.py**

### TCPClient.py

Bu dosya, bir TCP istemcisi oluşturmayı ve çalıştırmayı gösterir. Temel işlevi, belirtilen bir sunucuya (bu örnekte Google) TCP üzerinden bir bağlantı kurmak ve veri göndermektir. İşlem adımları şunlardır:

- **Socket Nesnesi Oluşturma:** `socket.socket(socket.AF_INET, socket.SOCK_STREAM)` kullanılarak bir soket nesnesi oluşturulur. `AF_INET` IPv4 adreslerini kullanacağımızı belirtirken, `SOCK_STREAM` bu istemcinin TCP kullanacağını belirtir.
- **Bağlantı Kurma:** `client.connect((target_host, target_port))` ile belirtilen sunucuya ve bağlantı noktasına bağlanılır.
- **Veri Gönderme:** `client.send("GET / HTTP/1.1\r\nHost: google.com\r\n\r\n")` komutu ile belirli bir veri gönderilir.
- **Veri Alma:** `client.recv(4096)` komutu ile sunucudan gelen yanıt alınır ve ekrana yazdırılır.

### TCPServer.py

Bu dosya, bir TCP sunucusu oluşturmayı ve çalıştırmayı gösterir. Temel işlevi, belirtilen bir bağlantı noktasında gelen TCP bağlantılarını dinlemek ve veri alışverişi yapmaktır. İşlem adımları şunlardır:

- **Socket Nesnesi Oluşturma:** `socket.socket(socket.AF_INET, socket.SOCK_STREAM)` kullanılarak bir soket nesnesi oluşturulur.
- **Bağlantı Noktasına Bağlanma:** `server.bind((host, port))` ile belirtilen host ve port üzerinden bağlantı yapılır.
- **Dinleme:** `server.listen(5)` komutu ile sunucu bağlantı isteklerini dinlemeye başlar.
- **Bağlantı Kabul Etme:** `server.accept()` komutu ile gelen bağlantı istekleri kabul edilir ve istemci ile iletişim başlatılır.
- **Veri Alma ve Gönderme:** `client_socket.recv(1024)` komutu ile istemciden veri alınır ve `client_socket.send(response)` komutu ile istemciye yanıt gönderilir.

### Kullanım

Her iki dosya da Python 3.x ile çalışacak şekilde tasarlanmıştır. Çalıştırmak için terminal veya komut satırında aşağıdaki komutları kullanabilirsiniz:

#### TCPClient.py

```bash
python TCPClient.py
```

#### TCPServer.py

```bash
python TCPServer.py
```

### Gereksinimler

- Python 3.x
- İnternet bağlantısı (TCPClient.py dosyası için)

