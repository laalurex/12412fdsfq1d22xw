# LASPOS Public Delivery

Acest repository public contine doar fisierele necesare pentru verificarea licentei si publicarea update-urilor LASPOS.

Structura:
- `deployment/licenses/` licente publice pentru clienti
- `deployment/update/manifest.json` manifestul public de update

Codul aplicatiei LASPOS ramane in repository-ul privat.

## Status licenta

In fisierul de licenta al clientului, campul principal este `status`.

Valorile recomandate:

- `active` - clientul are acces complet
- `inactive` - programul se blocheaza la pornire
- `grace` - clientul mai are o perioada scurta de folosire pana la data din `grace_until`

Exemplu fisier:

- `deployment/licenses/nami-sushi-srl.github-license.json`

Ce schimbi de obicei:

- `status`
- `expires_at`
- `grace_until`
- `message`

Exemple rapide:

- `status: "active"` pentru client achitat
- `status: "inactive"` daca vrei sa opresti accesul
- `status: "grace"` daca vrei 7 zile pana la dezactivare

## Update public

Fisierul verificat de aplicatie este:

- `deployment/update/manifest.json`

Campuri importante:

- `version`
- `download_url`
- `url`
- `sha256`
- `notes`

Important:

- GitHub repository normal nu accepta usor fisiere foarte mari peste aproximativ 100 MB
- installerul LASPOS si arhiva de update sunt mai mari decat aceasta limita
- pentru download real al update-ului trebuie folosita o sursa separata pentru fisierul mare, de exemplu GitHub Releases sau alt hosting controlat de tine
- in `manifest.json` pui linkul public real catre fisierul descarcabil
