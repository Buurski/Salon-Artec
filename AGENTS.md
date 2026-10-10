# Salon Artec, Skive — demo-site (prospekt, pause)
Enkeltside-HTML i `Salon Artec.html` (al CSS i `<style>`, al JS i `<script>`, intet framework/build). `index.html` er kun en meta-refresh dertil; `vercel.json` omskriver `/` til `/Salon Artec.html`. Live https://salon-artec.vercel.app · GitHub `Buurski/Salon-Artec` (default-gren `master`) · Vercel-projekt `salon-artec`.
Kunde: Julie Ellebæk (ejer, "Artec by Julie Ellebæk"). Sagde ja til at se demoen, svarede aldrig på demo-mailen; status `ingen-svar-pause` (2026-07-31: ingen opfølgning planlagt, beholdt som reference).
Hårde regler: `C:\Users\Buur\Documents\KnowledgeOS\context\hard-rules.md` (læs først). Router: `C:\Users\Buur\Documents\Websites\AGENTS.md`.

## Opgave | læs | læs IKKE
KB = `C:\Users\Buur\Documents\KnowledgeOS`. Gæt aldrig et faktum; står det ikke her eller i filen, skriv "ved ikke".

| Opgave | læs | læs IKKE |
|---|---|---|
| Tekst/indhold på siden | `Salon Artec.html`, `KB\wiki\kunder\salon-artec.md`, `KB\context\brand-og-tone.md` | `C:\Users\Buur\_Arkiv`, andre kunders sites |
| Design/CSS | `Salon Artec.html` (tokens i `:root`), `design.md` (løs reference, ikke lov; untracked) | nye farver/skrifter udenfor tokens; `Salon Artec-handoff\`, `references\`, `research\` (gitignoreret) |
| SEO | `Salon Artec.html` (title, meta, schema), `KB\wiki\kunder\salon-artec.md` | generiske SEO-skabeloner uden at tjekke siden |
| Deploy | `C:\Users\Buur\Documents\Websites\AGENTS.md`, `KB\wiki\os\agents-detaljer.md` (afsnit "Deploy-disciplin") | `.vercel\` (projekt-id, rør ikke) |
| Kinly-priser, startpris, tilbud | `KB\context\priser.md` (kanon; hjemmeside fra 3.997 kr) | gamle tilbud i wiki; individuelle aftaler afviger |
| Kundefakta, kontakt, status, log | `KB\wiki\kunder\salon-artec.md` | `C:\Users\Buur\Documents\Kunder\`, `.send_queue\` |
| Adresser (kunder, bl.a. Ikast Autoservice), tværgående fakta (Planuko-wordmark, HQ-gates, modelvalg) | `KB\context\fakta.md` | Lucas' privatadresse må aldrig stå nogen steder |
| Selskab, CVR, adresseregel | `KB\context\selskab.md` | |
| Mails/udgående tekst til kunden | `KB\context\brand-og-tone.md`, `KB\context\forbidden-phrases.md` | |
| Alle repos og sites | `C:\Users\Buur\Documents\REPOS.md`, `C:\Users\Buur\Documents\Websites\SITES.md` | |

## Kommandoer
Ingen `package.json`, ingen build, ingen `verify`-script.
- Dev: `python -m http.server 8080` i repo-roden → http://localhost:8080/Salon%20Artec.html
- Deploy: kun Lucas merger til `master`. `vercel deploy --prod` kun efter Lucas' ja.

## Arkitektur (kort)
- Tokens i `:root`: `--teal-900…600`, `--gold` (#c9a35e, spares), `--cream`/`--cream-2`/`--cream-3`, `--ink`, `--rose`, `--serif` (Cormorant Garamond), `--sans` (DM Sans). Retning: roligt, redaktionelt, "Aesop-agtigt". Afvig aldrig.
- Sektioner (id): `site` → `hero` → `velkomst` → `behandlinger` → `priser` → `galleri` → `produkter` → `anmeldelser` → `findos`. Booking linker til salonbook.one.
- `images/` (tracked): logo, `hero.mp4`, salon-/portfolio-fotos og en gemt Instagram-side (`(2) Instagram.html` + `_files`, ikke brugt af siden).
- Dirty, rør ikke: `.gitignore` (ændret), `design.md` (untracked). Lokalt-only (gitignoreret): `PROMPT-TIL-CLAUDE-DESIGN.md`, `billeder\`, `research\salon-info.md`.

## Regler
1. Aldrig `master` uden Lucas: ny gren + Vercel-preview, Lucas merger. Samler ændringer; maks 2-3 prod-deploys/dag; `[skip vercel]` ved docs.
2. "Done" = live-check: åbn preview/prod og print HTTP-status eller screenshot; ikke kun "ser rigtigt ud i koden".
3. Udgående (mails, opslag til Julie) er KLADDER; Lucas sender selv. Intet sendes, ingen konti, køb eller DNS. Ingen opfølgning før Lucas siger til.
4. Dansk. Ingen AI-slop (ingen gradient-blobs, emoji-ikoner, fyldtekst). Få farver pr. sektion; guld sparsomt, aldrig ren hvid eller `#000`.
5. Én kode-agent pr. worktree; commit med eksplicit `git add <sti>`, aldrig `git commit -a`; ingen stash/reset/clean.
