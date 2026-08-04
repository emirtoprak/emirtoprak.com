# emirtoprak.com

Kişisel web sitesi. Tek dosyalık statik site (`index.html`), GitHub Pages üzerinden yayınlanır.

## Yayınlama (GitHub Pages + GoDaddy)

### 1. GitHub'a yükle

```bash
cd ~/emirtoprak.com
git init
git add .
git commit -m "Personal website"
gh repo create emirtoprak.com --public --source=. --push
```

### 2. GitHub Pages'i aç

GitHub → repo → **Settings → Pages**:
- Source: **Deploy from a branch**
- Branch: **main** / root → Save
- Custom domain: **emirtoprak.com** → Save (CNAME dosyası zaten repoda)

### 3. GoDaddy DNS ayarları

GoDaddy → My Products → emirtoprak.com → **DNS**:

| Tip   | Ad  | Değer                  |
|-------|-----|------------------------|
| A     | @   | 185.199.108.153        |
| A     | @   | 185.199.109.153        |
| A     | @   | 185.199.110.153        |
| A     | @   | 185.199.111.153        |
| CNAME | www | emirtoprak.github.io   |

Varsa GoDaddy'nin eklediği "Parked" A kaydını ve varsayılan Forwarding'i sil.

### 4. HTTPS

DNS yayılınca (5 dk – 1 saat) GitHub → Settings → Pages → **Enforce HTTPS** işaretle.

Site sonrasında https://emirtoprak.com adresinde yayında olur. Güncelleme = dosyayı değiştir, commit'le, push'la.
