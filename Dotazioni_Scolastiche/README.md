# Quante scuole primarie statali hanno un locale mensa?

Un confronto tra le province italiane, anno scolastico 2024/25, con i dati aperti del Ministero dell'istruzione e del merito (MIM).

## La domanda

Quante scuole primarie statali hanno un locale mensa, e quanto cambia da provincia a provincia?

## Cosa emerge

- Su 14.513 primarie statali, 7.928 (54,6%) hanno un locale mensa, 6.556 (45,2%) no. Per 29 (0,2%) il dato non è definito.
- Tra le province, la quota di primarie senza locale mensa va dal 2% circa di Prato al 96,7% di Ragusa.
- Il notebook contiene anche i controlli fatti sul valore di Ragusa, il più alto.

Grafico: (https://public.flourish.studio/visualisation/30425283/)

**Attenzione:** i dati dicono se l'edificio ha un *locale* adibito a mensa, non se i bambini mangiano a scuola. Vedi i limiti in fondo.

## Contenuto del repository

```
[nome-cartella]/
├── README.md
├── [nome-notebook].ipynb
├── mensa_primarie_province.csv
└── data/
    ├── EDIANAGRAFESTA202120242520250806.csv
    └── EDIAMBFUNZSTA202120242520250806.csv
```

## Dati

Fonte: MIM, Portale Unico dei Dati della Scuola, area Edilizia scolastica, anno scolastico 2024/25, dati al 6 agosto 2025. Licenza dei dati: IODL 2.0.

- **Elenco e localizzazione degli edifici** (`EDIANAGRAFESTA...`): comune e provincia di ogni edificio.
- **Destinazione d'uso degli spazi** (`EDIAMBFUNZSTA...`): per ogni edificio, se ha aule, mensa, palestra, auditorium e altri spazi.

Catalogo: https://dati.istruzione.it/opendata/opendata/catalogo/elements1/?area=Edilizia+Scolastica

## Come riprodurre l'analisi

1. Scarica il repository (*Code* → *Download ZIP*) e decomprimilo.
2. Installa le librerie (testato con Python 3.11):

```
pip install pandas jupyter
```

3. Apri il notebook e lancia tutte le celle (*Kernel* → *Restart Kernel and Run All Cells*).

Alla fine devono risultare 104 province, 14.513 primarie e 6.556 senza locale mensa.

## Metodo in breve

- Nei dati una scuola è un plesso (`CODICESCUOLA`) e può occupare più edifici.
- La scuola risulta con mensa se almeno un suo edificio ce l'ha. È una scelta dell'analisi, non una regola dei dati.
- Il grado si ricava dal terzo e quarto carattere del codice scuola (`EE` = primaria).
- Le scuole con dato non definito restano nel conteggio.

## Limiti

- **Locale, non servizio.** Una scuola può servire i pasti senza un locale dedicato. Secondo l'Osservatorio sui conti pubblici il 39% delle primarie ha la mensa, mentre il 57% degli alunni usa il servizio.
- **Dati dichiarati dagli enti locali**, con possibili errori e omissioni.
- **Si contano scuole, non alunni.**
- **Perimetro.** Solo scuole statali. Esclusi la Valle d'Aosta (i suoi codici scuola hanno una struttura diversa) e le province di Trento e Bolzano, assenti dal dataset.
- **Province piccole.** Le primarie per provincia vanno da 34 (Enna) a 630 (Napoli): nelle più piccole un solo plesso sposta la percentuale di circa tre punti.
- **Una fotografia** dell'anno 2024/25.

## Fonti

- MIM, Portale Unico dei Dati della Scuola: https://dati.istruzione.it/opendata/opendata/
- Save the Children, mensa e tempo pieno: https://www.savethechildren.it/blog-notizie/scuola-poco-piu-di-1-bambino-su-2-ha-accesso-al-servizio-mensa
- Osservatorio sui conti pubblici (OCPI), PNRR, tempo pieno e mense: https://osservatoriocpi.unicatt.it/ocpi-pubblicazioni-il-pnrr-l-estensione-del-tempo-pieno-e-le-mense-scolastiche-nelle-scuole-primarie

## Licenza

Codice: [licenza che hai scelto, ad esempio MIT]. Dati: IODL 2.0, fonte MIM.
