# Landing brief

Business facts for this page. Claude reads it before writing anything and never invents what is missing.

Short, reusable values (brand, colours, URL, title, headline, CTA, form endpoint, author, verification codes)
live in `site.config.json`, not here: the build puts them into every page. This file holds everything else.

## Identity
- LOGO: brak (favicon = litera S na fiolecie)
- Social profiles (become schema.org `sameAs`):
  - https://www.facebook.com/profile.php?id=100091447430165
  - https://www.instagram.com/smoksport/
  - https://maps.google.com/?cid=8363382794408190962 (wizytówka Google, 5,0 / 5 opinii, 2026-11)

## Hosting
- REPO_NAME: smoksport
- REPO_OWNER: GKunc
- CUSTOM_DOMAIN: www.smoksport.pl (DNS w OVH; smoksport.pl bez www przekierowuje na www)

## Business
- What is offered: zajęcia ogólnorozwojowe i lekkoatletyczne dla dzieci (biegi, skoki, rzuty, starty z bloków); damskie wyjazdy biegowe (rozbieganekobiety.pl)
- Target audience: rodzice dzieci 4–6 lat i uczniów klas 1–3 z Krakowa (Płaszów)
- Main problem solved: wszechstronny rozwój ruchowy dziecka przez zabawę i elementy lekkiej atletyki
- Unique selling points: trenerzy to byli lekkoatleci (AZS AWF Kraków, medale MP); współpraca z KS AZS AWF Kraków (zaangażowane dzieci zapraszane na trening próbny); pierwsze zajęcia gratis
- Price / offer: sezon 2026/2027, I semestr: 600 zł semestralnie lub 160 zł miesięcznie (4 płatności); rodzeństwo −50 zł od dziecka w opłacie semestralnej; płatność po pierwszych zajęciach
- Location / service area: SP nr 47, ul. Myśliwska 64, 30-718 Kraków-Płaszów (duża sala gimnastyczna, bieżnia); CKP Płaszów
- Grafik: grupa przedszkolna 4–6 lat środa 18:15 (brak wolnych miejsc); grupa szkolna kl. 1–3 piątek 16:45; CKP Płaszów „Motoryka smyka” wtorek 18:00 (zapisy przez CKP)
- Trenerzy: Magdalena Kunc, Sara Drwal, Grzegorz Kunc (bio z obecnej strony smoksport.pl)
- Kontakt: +48 570 080 490, smoksportkrakow@gmail.com

## Proof (real only)
- Testimonials (quote, name, role, permission to publish):
  -
- Numbers / results (with source):
  -
- Client logos (with permission):
  -

## FAQ (real questions customers ask; becomes the FAQ section + FAQPage schema)
- Q:
  A:

## Author (for blog posts and E-E-A-T; name and URL go into site.config.json)
- AUTHOR_BIO: Magdalena Kunc — trenerka PZLA, Akademicka Mistrzyni Polski, wykształcenie pedagogiczne; biegała w barwach KS AZS AWF Kraków.

## Voice
- Tone: ciepły, energiczny, konkretny; mówimy do rodzica
- Words to use / avoid:

## SEO
- Primary keyword: lekkoatletyka dla dzieci Kraków
- Secondary keywords: zajęcia sportowe dla dzieci Płaszów, zajęcia ogólnorozwojowe dla przedszkolaków
- Competitors / reference sites:

## Forms, analytics, compliance
- Contact form: na razie zapisy przez istniejący Google Form (ten sam co na starej stronie); formularz na stronie z autoodpowiedzią (form worker) po założeniu kont Cloudflare + Resend
- Who receives enquiries: (email address; FORM_NOTIFY_TO in site.config.json, empty = CONTACT_EMAIL)
- Reply promise for the autoreply: (e.g. "within one business day"; leave empty to promise no time)
- Named person to sign the autoreply: (optional)
- Analytics wanted: none
- AI_CRAWLERS: allow-all

## Facts Claude must not invent
- „AZS AKF Kraków” we wpisie o zawodach (Krakowska Rodzinna Olimpiada Sportowa) jest poprawne — nie zmieniać na AWF.
- Opinie rodziców: są na wizytówce Smok Sport w Google; cytować tylko za zgodą autorów.

## site.config.json cheat sheet
| Key | What to put |
| --- | --- |
| BRAND, BRAND_INITIAL | name; one letter for the generated favicon |
| THEME_COLOR | brand accent as 6-digit #hex |
| LANG, LOCALE | e.g. `pl` and `pl_PL` |
| LEGAL_ENTITY, CONTACT_EMAIL | who is responsible for the site (privacy policy) |
| SITE_URL | (auto, publish skill) https URL without trailing slash |
| INDEXNOW_KEY | (auto) `openssl rand -hex 16` |
| PAGE_TITLE | 30-60 chars incl. brand, primary keyword first |
| H1_HEADLINE, SUBHEADLINE, CTA_LABEL | hero copy and button label |
| META_DESCRIPTION | 120-155 chars, with a reason to click |
| LLMS_SUMMARY | 2-4 plain sentences: what the business is, for whom, where |
| BLOG_TITLE, BLOG_DESCRIPTION | needed from the first post on |
| AUTHOR_NAME, AUTHOR_URL | blog author (LinkedIn or about page) |
| FORM_ENDPOINT | (auto with the form worker: `node tools/form-worker.mjs deploy`) or the external form service URL |
| FORM_PROVIDER | who processes the form, for the privacy policy ("Cloudflare and Resend" with the worker) |
| EMAIL_FROM | sender of the autoreply; domain verified in Resend |
| FORM_NOTIFY_TO | who gets enquiries (empty = CONTACT_EMAIL) |
| TURNSTILE_SITE_KEY | Cloudflare Turnstile site key (anti-bot check, needed for the autoreply) |
| FORM_ACCESS_KEY | only for services that need a key in the form (e.g. Web3Forms) |
| ANALYTICS, ANALYTICS_ID | `none`, `plausible` (id = domain, may stay empty), `goatcounter` (site code), `cloudflare` (token), `ga4` (G-…) |
| PRIVACY_UPDATED | YYYY-MM-DD |
| GOOGLE_SITE_VERIFICATION, BING_SITE_VERIFICATION | filled after launch (`node tools/google.mjs verification-token`) |
