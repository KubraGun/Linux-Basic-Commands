# **cat (concatenate)**

cat (concatenate) komutu, dosya içeriğini standart çıktıya (ekrana) tazdırmak için kullanılır.


## Normal Kullanım Senaryoları


### Konfigürasyon dosyası okuma

```bash
cat /etc/hosts
```

- Sistemin hosts dosyasını okur.
- IP adresi ve alan adı eşleşmelerini gösterir
- Linux sistemleri varsayılan olarak bir alan adı çözümlerken "etc/hosts" dosyasına bakar, eğer orada bulamazsa DNS sunucusuna gider. Bu örnek DNS çözümleme sorunlarında ilk kontrol noktasıdır. (Çünkü sistem DNS sunucusuna sormadan önce öncelikli olarak bu dosyaya bakar)
- [ÖNEMLİ NOT]: DNS sunucu IP'leri (nameserver) için bu dosyaya değil "cat /etc/resolv.conf" dosyasına bakılır.


### Küçük log dosyası inceleme

```bash
cat error.log
```

- Hata loglarını anında terminal ekranına döker
- 100 - 200 satırlık dosyalar bu komut için ideal boyuttatır. Bu dosyaları okumak için en pratik yöntemdir.
- Editör açmaya gerek kalmadan içeriye göz atmayı (anlık kontrolü) ve hızlı debug imkanı sağlar.


### Environment değişkenleri kontrolü

```bash
cat .env
```

- Uygulamaların DB bağlantıları veya API anahtarları... gibi kritik çalışma ayarlarını görüntüler. 
- Gizli dosya statüsünde olsa da, konfigürasyon doğrulaması yapmak için doğrudan içeriği okunabilir.
- Hassas şifreleri ve anahtarları açıkça döktüğü için, özellikler ekran paylaşımı sırasında veya kalabalık ortamlarda güvenlik açısından dikkatli olunmalıdır.

### README veya dokümantasyon okuma

```bash
cat README.md
```

-Bir geliştiricinin proje dizinine girdiğinde projeyi anlamak için yaptığı ilk iştir.
- Bu komut projenin dokümantasyon dosyasını, Markdown etiketlerini (#, * vb.) olduğu gibi yorumlamadan, ham metin olarak gösterir.
- Biçimlendirme gözrünmese de içerik tamamen okunabilir durumdadır.
- Proje indirildiğinde kod editörü açmaya gerek kalmadan talimatlara ve komutlara hızlıca göz atmayı sağlar.


### Birden fazla dosyayı birleştirme

```bash
cat file1.txt file2.txt > combined.txt
```

- Birden fazla dosyanın içeriğini sırayla okur ve tek dosyada birleştirir.
- ">" hedef dosyayı sıfırdan yazar. Eğer combined.txt varsa , içindeki eski verileri tamamen siler ve yeni içeriği yazar → overwrite
- ">>" hedef dosyayı silmez, Yeni gelen verileri mevcut dosyanın en sonuna ekler → append
- Özellikle parça parça duran log dosyalarını veya veri setlerini tek bir merkezde toplamak için kullanılır.
- [ÖNEMLİ NOT]: Okunan bir dosya ">" ile kendisine yönlendirilmemeli, aksi takdire dosya içeriği yazma başlamadan tamamen silinir.
- Birleştirilen dosyanın sonunda boş bir satır yoksa (enter ile alt satıra geçilmemişse) son karakter neredeyse hemen onun bitişiğine yapışık olarak yazılır.