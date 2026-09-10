# Colorime3ka — podporná stránka (forensika.eu)

Podporná stránka a zásady ochrany súkromia aplikácie **Colorime3ka**, SK/EN.
Aktuálne pre verziu **2.8** (atlas 67 nálezov, kalibrácia terčom, merítko v mm,
klinický kontext, referenčné odtlačky, expertný režim, import/export `.ch3lab`).

Súbory: `index.html` (podpora + FAQ) a `privacy.html`. Sú samostatné, bez
externých závislostí — štýl je priamo v súbore, nič sa nesťahuje z internetu.

## Nasadenie pod forensika.eu

**Aktuálne živé** (a vložené v App Store Connect):

- Support URL: `https://dzanino.github.io/colorime3ka/`
- Privacy Policy URL: `https://dzanino.github.io/colorime3ka/privacy.html`

Obsah stránok je značkovo Forensika (hlavička „PROJEKT FORENSIKA.EU", kontakt
`forensika.eu@icloud.com`) — hostiteľ je len technická vec. Presun pod vlastnú
doménu je preto voliteľný; ak naň príde, cieľom je
`https://forensika.eu/colorime3ka/` a stačí zmeniť URL v ASC.

### A) Web forensika.eu (odporúčané)

Nahrajte oba súbory do adresára `colorime3ka/` v koreni webu. Nič viac —
stránky sú statické.

### B) GitHub Pages s vlastnou doménou

Ak web beží na GitHub Pages:

1. Súbory do repa (vetva `main`), do priečinka `colorime3ka/`.
2. Settings → Pages → Custom domain: `forensika.eu` → Save (vytvorí sa `CNAME`).
3. U registrátora domény nastaviť DNS podľa pokynov GitHubu (`A` záznamy
   na GitHub Pages, prípadne `CNAME` pre `www`).
4. Zapnúť **Enforce HTTPS**.

## Po nasadení skontrolovať

- [ ] Obe URL sa načítajú cez **https** a bez upozornenia na certifikát.
- [ ] Odkaz `privacy.html` z podpornej stránky funguje a naopak.
- [ ] E-mail je všade `forensika.eu@icloud.com`.
- [ ] Apple vyžaduje, aby Privacy Policy URL bola **verejne dostupná bez prihlásenia**.

## Prečo sa privacy prepisovala (2026-09)

Pôvodný text tvrdil, že „po zavretí aplikácie sa nič neuchováva". Od expertného
režimu to **neplatí**: naučené odtlačky zostávajú v zariadení. Nová verzia to
hovorí presne — dvanásť čísel a poznámka, nikdy fotografia — a popisuje aj
prenos `.ch3lab`. Privacy policy musí zodpovedať tomu, čo appka naozaj robí.

## Dokumentácia (PDF)

`Colorime3ka-prirucka-SK.pdf` a `Colorime3ka-Manual-EN.pdf` sa nasadzujú
spolu s `index.html` — odkazuje na ne karta „Dokumentácia / Documentation"
hneď pod úvodom aj obidve jazykové sekcie.

**Zdroj je v `docs/`** v koreni projektu: `manual-sk.html`, `manual-en.html`
a spoločný `manual.css`. Po úprave sa PDF vyrobí znova takto (macOS,
Chromium-based prehliadač; `wkhtmltopdf` ani `weasyprint` nie sú potrebné):

```
cd docs
"/Applications/Brave Browser.app/Contents/MacOS/Brave Browser" \
  --headless --disable-gpu --no-pdf-header-footer \
  --print-to-pdf="Colorime3ka-prirucka-SK.pdf" \
  "file://$PWD/manual-sk.html"
```

To isté pre `manual-en.html` → `Colorime3ka-Manual-EN.pdf`. Hotové súbory
sa potom skopírujú do `AppStoreConnect/support-page/`.

Pri zmene verzie aplikácie treba prepísať údaj „2.8" na titulnej strane,
v pätke dokumentu a v popiskách odkazov v `index.html`.
