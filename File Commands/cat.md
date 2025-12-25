# **cat (concatenate)**

cat (concatenate) komutu, dosya içeriðini standart çýktýya (ekrana) tazdýrmak için kullanýlýr.


## Normal Kullaným Senaryolarý


### Konfigürasyon dosyasý okuma

```bash
cat /etc/hosts
```

- Sistemin hosts dosyasýný okur.
- IP adresi ve alan adý eþleþmelerini gösterir
- Linux sistemleri varsayýlan olarak bir alan adý çözümlerken "etc/hosts" dosyasýna bakar, eðer orada bulamazsa DNS sunucusuna gider. Bu örnek DNS çözümleme sorunlarýnda ilk kontrol noktasýdýr. (Çünkü sistem DNS sunucusuna sormadan önce öncelikli olarak bu dosyaya bakar)
- [ÖNEMLÝ NOT]: DNS sunucu IP'leri (nameserver) için bu dosyaya deðil "cat /etc/resolv.conf" dosyasýna bakýlýr.


### Küçük log dosyasý inceleme

```bash
cat error.log
```

- Hata loglarýný anýnda terminal ekranýna döker
- 100 - 200 satýrlýk dosyalar bu komut için ideal boyuttatýr. Bu dosyalarý okumak için en pratik yöntemdir.
- Editör açmaya gerek kalmadan içeriye göz atmayý (anlýk kontrolü) ve hýzlý debug imkaný saðlar.


### Environment deðiþkenleri kontrolü

```bash
cat .env
```

- Uygulamalarýn DB baðlantýlarý veya API anahtarlarý... gibi kritik çalýþma ayarlarýný görüntüler. 
- Gizli dosya statüsünde olsa da, konfigürasyon doðrulamasý yapmak için doðrudan içeriði okunabilir.
- Hassas þifreleri ve anahtarlarý açýkça döktüðü için, özellikler ekran paylaþýmý sýrasýnda veya kalabalýk ortamlarda güvenlik açýsýndan dikkatli olunmalýdýr.

