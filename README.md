# Colorime3ka — podporná stránka (forensika.eu)

Podporná stránka a zásady ochrany súkromia aplikácie **Colorime3ka**, SK/EN.
Aktuálne pre verziu **2.8** (atlas 67 nálezov, kalibrácia terčom, merítko v mm,
klinický kontext, referenčné odtlačky, expertný režim, import/export `.ch3lab`).

Súbory: `index.html` (podpora + FAQ) a `privacy.html`. Sú samostatné, bez
externých závislostí — štýl je priamo v súbore, nič sa nesťahuje z internetu.

## Nasadenie pod forensika.eu

Cieľové URL, ktoré patria do App Store Connect:

- Support URL: `https://forensika.eu/colorime3ka/`
- Privacy Policy URL: `https://forensika.eu/colorime3ka/privacy.html`

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
