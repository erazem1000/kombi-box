# Kombi Box — Spletna stran

Predstavitvena spletna stran za Kombi Box, zgrajena z Jekyll in gostovana na GitHub Pages.

---

## Struktura projekta

```
kombi_box_spletna/
├── _config.yml          ← Nastavitve strani (naslov, domena, e-pošta, Formspree ID)
├── Gemfile              ← Ruby odvisnosti za Jekyll
├── index.html           ← Slovenska različica (/)
├── en/index.html        ← Angleška različica (/en/)
├── _layouts/
│   └── default.html     ← Glavni HTML layout (header, footer, scripts)
├── _includes/
│   ├── header.html      ← Navigacija
│   ├── footer.html      ← Noga
│   ├── hero.html        ← Hero sekcija
│   ├── features.html    ← Zakaj Kombi Box
│   ├── gallery.html     ← Galerija
│   └── contact.html     ← Kontaktni obrazec
├── _data/
│   ├── sl.yml           ← VSA slovenska besedila (uredi tukaj!)
│   └── en.yml           ← VSA angleška besedila (uredi tukaj!)
├── _sass/
│   ├── _variables.scss  ← Barve, fonti, razmiki
│   ├── _base.scss       ← Reset in osnovni stili
│   └── _layout.scss     ← Stili za vse sekcije
└── assets/
    ├── css/main.scss    ← Vstopna točka za CSS
    └── images/          ← TUKAJ dodaj svoje fotografije
```

---

## Namestitev in lokalni razvoj

### Zahteve
- Ruby ≥ 2.7
- Bundler (`gem install bundler`)

### Koraki

```bash
# 1. Kloniraj repozitorij
git clone https://github.com/tvoj-username/kombi-box.git
cd kombi-box

# 2. Namesti odvisnosti
bundle install

# 3. Zaženi lokalni strežnik
bundle exec jekyll serve --livereload

# Stran je dostopna na: http://localhost:4000
```

---

## Objava na GitHub Pages

### 1. Ustvari GitHub repozitorij
1. Pojdi na [github.com/new](https://github.com/new)
2. Poimenuj repozitorij (npr. `kombi-box`)
3. Nastavi ga na **Public**

### 2. Poveži lokalni projekt z GitHubom
```bash
cd pot/do/kombi_box_spletna

git init
git add .
git commit -m "Začetna postavitev spletne strani"
git branch -M main
git remote add origin https://github.com/tvoj-username/kombi-box.git
git push -u origin main
```

### 3. Vklopi GitHub Pages
1. Pojdi v repozitorij → **Settings** → **Pages**
2. Pod "Source" izberi **Deploy from a branch**
3. Izberi vejo **main** in mapo **/ (root)**
4. Klikni **Save**

Stran bo v 1–2 minutah dostopna na: `https://tvoj-username.github.io/kombi-box`

### 4. Poveži lastno domeno
1. V GitHub Pages nastavitvah vnesi svojo domeno (npr. `www.kombi-box.si`)
2. Pri svojem registratorju domene dodaj DNS zapise:
   - **CNAME** zapis: `www` → `tvoj-username.github.io`
   - Za apex domeno (`kombi-box.si`) dodaj **A** zapise:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
3. Počakaj do 48 ur na propagacijo DNS

---

## Prilagoditev vsebine

### Besedila
Vsa besedila uredi v datotekah `_data/sl.yml` (slovenščina) in `_data/en.yml` (angleščina).

### Fotografije
Dodaj fotografije v mapo `assets/images/` z naslednjimi imeni:
- `hero-bg.jpg` — Glavna slika v heroju (priporočeno: 1920×1080px)
- `gallery-1.jpg` do `gallery-6.jpg` — Slike galerije (priporočeno: 800×600px)
- `og-image.jpg` — Slika za socialna omrežja (1200×630px)
- `favicon.png` — Ikona zavihka (32×32px ali 64×64px)

### Kontaktni obrazec (Formspree)
1. Registriraj se na [formspree.io](https://formspree.io) (brezplačni plan: 50 sporočil/mesec)
2. Ustvari nov obrazec in kopiraj ID (oblika: `xyzabcde`)
3. V `_config.yml` nastavi: `formspree_id: "xyzabcde"`

### Barve in stili
Uredi `_sass/_variables.scss` za spremembo barvne sheme:
- `$color-primary` — Temno modra (trenutno `#1a2332`)
- `$color-accent` — Oranžno zlata (trenutno `#f0a500`)

### Kontaktni podatki
V `_config.yml` nastavi:
```yaml
url: "https://www.tvoja-domena.si"
email: "info@tvoja-domena.si"
phone: "+386 XX XXX XXX"
```

---

## Tehnologije
- [Jekyll](https://jekyllrb.com/) — Statični generator strani
- [GitHub Pages](https://pages.github.com/) — Brezplačno gostovanje
- [Formspree](https://formspree.io/) — Kontaktni obrazec brez strežnika
- [Google Fonts](https://fonts.google.com/) — Inter pisava
