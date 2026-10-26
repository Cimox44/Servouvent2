# Servo-U Vent ICU — v2.2 (26/10/2026)

PWA di supporto alla ventilazione meccanica con Servo-U in Terapia Intensiva Cardiochirurgica: meccanica respiratoria, ossigenazione, CO₂ e spazio morto, drive e weaning, pressione transpolmonare, range, troubleshooting. I dati restano sul dispositivo.

> Strumento di supporto decisionale, non dispositivo medico certificato. Non sostituisce il manuale d'uso Getinge né i protocolli di reparto.

## File
| File | Ruolo |
|---|---|
| index.html | app completa |
| svu-manifest.json | installazione come app |
| svu-sw.js | funzionamento offline (cache `servou-vent-v2.2.0`) |
| svu-icon-192.png, svu-icon-512.png, svu-icon-maskable.png | icone |

## Novità v2.2
- **Telefono**: la scheda Paziente si allargava a circa 590 px e la pagina scorreva di lato; corretto.
- **Potenza meccanica**: in VC senza Pplat veniva usata la formula per la ventilazione a pressione controllata (Becher); ora si usa la formula surrogata di Giosa (VE × (Ppeak + PEEP + F/6)/20). In PS/VS/NAVA/Bi-Vent il valore è marcato come solo indicativo.
- **Compliance dinamica**: calcolata su PEEP totale, come da formula.
- **Interazioni cuore-polmone**: corretto il criterio di validità di PPV/SVV («FC/FR > 3,6», non «FR/FC»).
- **ROX**: soglie di fallimento in base all'ora (2,85 a 2 h · 3,47 a 6 h · 3,85 a 12 h) con nuovo campo «Ore di HFNO».
- **Dati inseriti**: saturazioni inserite come frazione (0,96) e Hb in g/L vengono convertite.
- **Pressione transpolmonare**: aggiunta la verifica del catetere (occlusion test, ΔPes/ΔPaw 0,8–1,2).
- **Fonti**: DOI del consensus italiano sul fast-track (Silvetti 2024), De Backer 2009, Giosa 2019, guida Getinge sulla pressione transpolmonare.

## Aggiornare
1. Caricare `index.html` e `svu-sw.js` (gli altri file non cambiano) con Add file → Upload files → Commit changes.
2. A ogni modifica aumentare `CACHE` in `svu-sw.js` e la versione nel piè di pagina.
3. Sul telefono: aprire l'app online, chiuderla e riaprirla.
