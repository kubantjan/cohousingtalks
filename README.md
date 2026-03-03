# Cohousing talks

Statický web pro [cohousingtalks.cz](https://cohousingtalks.cz) – platforma pro komunitní, participativní, cohousingové bydlení.

Postaveno na [Jekyll](https://jekyllrb.com/) a hostováno na [GitHub Pages](https://pages.github.com/).

## Lokální spuštění

```bash
bundle install
bundle exec jekyll serve
```

Poté otevřete http://localhost:4000

## Struktura

```
├── _config.yml              # Nastavení Jekyll
├── _data/
│   ├── communities.yml      # Seznam všech komunit (jednoduché přidávání!)
│   └── nav.yml              # Položky navigace
├── _layouts/                # HTML šablony
├── _includes/               # Sdílené komponenty (header, footer, gallery)
├── assets/
│   ├── css/style.css        # Styly
│   └── images/              # Obrázky (podsložky podle komunity)
├── index.md                 # Hlavní stránka
├── zapojene-cohousingy.md   # Přehled komunit (generuje se z _data/communities.yml)
├── kmen.md, vetev.md, …     # Stránky jednotlivých komunit
└── kontakt.md               # Kontakt
```

## Jak přidat novou komunitu

Stačí **2 kroky** (nebo 3, pokud chcete fotogalerii):

### 1. Přidejte záznam do `_data/communities.yml`

Otevřete soubor `_data/communities.yml` a přidejte nový řádek mezi aktivní komunity:

```yaml
- name: Název komunity
  slug: nazev-komunity        # URL-friendly název (bez diakritiky, malá písmena, pomlčky)
  location: Praha – Čtvrť
  status: active              # "active" nebo "memorial"
```

Pokud komunita nemá vlastní stránku (viz krok 2), nastavte `slug: null` – zobrazí se jen jako karta bez odkazu.

**Tím je hotovo!** Komunita se automaticky zobrazí na stránce [Zapojené cohousingy](/zapojene-cohousingy/).

### 2. (Volitelné) Vytvořte stránku komunity

Vytvořte nový soubor v kořenovém adresáři, např. `nazev-komunity.md`:

```markdown
---
layout: page
title: Název komunity
permalink: /nazev-komunity/
gallery:                                    # volitelné – seznam fotek do galerie
  - src: /assets/images/nazev-komunity/foto1.jpg
    alt: Popis fotky 1
  - src: /assets/images/nazev-komunity/foto2.jpg
    alt: Popis fotky 2
---

![Hlavní fotka]({{ site.baseurl }}/assets/images/nazev-komunity/hlavni.jpg)

*Praha – Čtvrť*

Popis komunity...

[Facebook](https://www.facebook.com/vase-komunita)

{% include gallery.html images=page.gallery %}
```

### 3. (Volitelné) Přidejte obrázky

Vytvořte složku `assets/images/nazev-komunity/` a nahrajte do ní obrázky.

### Shrnutí

| Co chcete udělat | Co je potřeba |
|---|---|
| Přidat komunitu jen jako kartu | Přidat řádek do `_data/communities.yml` |
| Přidat komunitu s vlastní stránkou | + vytvořit `nazev-komunity.md` |
| Přidat fotogalerii | + nahrát obrázky + přidat `gallery` do frontmatter |
