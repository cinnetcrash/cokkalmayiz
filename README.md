# Çok Kalmayız — Web Sitesi

Ankara'dan alternative rock üçlüsü Çok Kalmayız'ın resmi tek-sayfa web sitesi.
Statik: yalnızca `index.html` + `style.css` + `img/`. Hiçbir build adımı yok.

## GitHub Pages'de yayına alma

### Seçenek A — Repo `main` dalından (en kolay)

1. GitHub'da yeni bir repo oluştur. Önerilen adlar:
   - `cokkalmayiz.github.io` → site `https://cokkalmayiz.github.io/` adresinde yayınlanır
   - veya `cok-kalmayiz-site` → `https://<kullanıcı-adı>.github.io/cok-kalmayiz-site/` olur
2. Bu `site/` klasörünün **içeriğini** (index.html, style.css, img/, README.md) reponun köküne koy.
3. Push:
   ```bash
   git init
   git add .
   git commit -m "İlk yayın"
   git branch -M main
   git remote add origin git@github.com:<kullanıcı-adı>/<repo-adı>.git
   git push -u origin main
   ```
4. Repo → **Settings → Pages**:
   - **Source:** Deploy from a branch
   - **Branch:** `main` / `/ (root)` → **Save**
5. 1–2 dakika sonra site yayında.

### Seçenek B — `/docs` klasöründen

Aynı repoda başka şeyler de tutmak istiyorsan: klasör adını `docs/` yap ve
Pages ayarında **Branch:** `main` / `/docs` seç.

### Özel domain (isteğe bağlı)

`CNAME` adlı bir dosya oluştur, içine `cokkalmayiz.com` (ya da neyse) yaz.
DNS tarafında A kayıtlarını GitHub Pages IP'lerine, ya da `CNAME` ile
`<kullanıcı-adı>.github.io`'a yönlendir.

## Yerelde önizleme

Sıfır kurulumla:
```bash
cd site
python3 -m http.server 8000
```
→ `http://localhost:8000`

## İçeriği güncellemek

- **Single ekle/değiştir:** `index.html` içinde `#sarkilar` bölümündeki
  `<article class="single">` blokunu kopyala, kapak görselini `img/` altına ekle.
- **Üye bilgisi:** `#uyeler` bölümünde figcaption'ları düzenle.
- **Sosyal linkler:** `#iletisim` bölümündeki `<a href="#">`'leri Instagram/Spotify/
  YouTube URL'leriyle değiştir.
- **Renkler:** `style.css` üstündeki `:root` değişkenleri (`--ember`, `--bg`, …).

## Görseller

`img/` altındaki dosyalar yalnızca grubun gönderdiği görsellerden türetildi:

| Dosya | Kaynak / Kullanım |
| --- | --- |
| `logo-wide.png` | Hero arka plan (eclipse logo) |
| `cover-ne-farkeder.png` | "Ne Farkeder" gerçek kapak |
| `cover-1.png` | Eclipse kare; favicon olarak kullanılıyor |
| `cover-bir-problem-var.png` | "Bir Problem Var" gerçek kapak |
| `cover-bana-bi-yalan-soyle.jpg` | "Bana Bi' Yalan Söyle" gerçek kapak |
| `tarot-gultekin.png`, `tarot-ahmet.png`, `tarot-yunus.png` | Üye tarot kartları |
| `band-table.png` | Hakkımızda bölümü grup fotoğrafı |
