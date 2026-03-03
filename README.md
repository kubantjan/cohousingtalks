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
├── _config.yml          # Nastavení Jekyll
├── _layouts/            # HTML šablony
├── _includes/           # Sdílené komponenty (header, footer)
├── assets/css/          # Styly
├── index.md             # Hlavní stránka
├── o-platforme.md       # O platformě
├── cohousing-fest.md    # Cohousing fest
├── cohousing-talks.md   # Cohousing talks
├── zapojene-cohousingy.md  # Zapojené cohousingy
├── hledas.md            # Hledáš?
└── kontakt.md           # Kontakt
```
