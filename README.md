# Tortuga — sürümler

Bu repo yalnız **Tortuga** terminalinin derlenmiş sürümlerini içerir (kaynak kod burada değildir).
Kurulu Tortuga güncellemeleri buradan denetler ve indirir.

## Kurulum

[Son sürüm](../../releases/latest) sayfasından sistemine uygun dosyayı indir:

| Sistem | Dosya |
|---|---|
| Windows 10/11 | `Tortuga_<sürüm>_x64-setup.exe` (önerilen) ya da `.msi` |
| Linux (Ubuntu 22.04+, Debian 12+) | `.deb` ya da `.AppImage` |
| macOS 11+ | `_aarch64.dmg` (Apple Silicon) ya da `_x64.dmg` (Intel) |

Windows'ta "Windows kişisel bilgisayarınızı korudu" uyarısı çıkarsa: **Ek bilgi → Yine de çalıştır**
(kurulum dosyası henüz kod imzalama sertifikasıyla imzalı değildir).

## Dosyayı doğrulama

Her sürümde `SHA256SUMS.txt` vardır. İndirdiğin dosyanın özeti oradakiyle aynı olmalı:

```
Windows:  certutil -hashfile Tortuga_<sürüm>_x64-setup.exe SHA256
Linux:    sha256sum -c SHA256SUMS.txt --ignore-missing
macOS:    shasum -a 256 <dosya>
```

## Güncellemeler nasıl güvenli?

- Her güncelleme paketi geliştiricinin bilgisayarında, çevrimdışı saklanan bir anahtarla imzalanır
  (`.sig` dosyaları). Anahtar GitHub'da ya da herhangi bir sunucuda bulunmaz.
- Tortuga indirdiği paketi kurmadan önce imzayı, uygulamanın içine gömülü açık anahtarla doğrular.
  İmza tutmazsa, paket başka bir sürüme aitse ya da daha eski bir sürümse kurulmaz.
- Güncelleme her zaman kullanıcının onayıyla kurulur.
