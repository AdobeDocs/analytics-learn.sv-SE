---
title: Skapa standardiserade namnkonventioner
description: Standardiserade namnkonventioner gäller både för själva variabelnamnet när det är aktiverat i användargränssnittet i AA Admin och värdena som skickas till dimensionen.
feature: Implementation Basics
topic: Administration
role: Admin
level: Beginner
doc-type: article
thumbnail: 10531.jpg
kt: 10531
source-git-commit: 160df6c23acb67f1b07f2fcd25f1eca96eb6dee7
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---


# Skapa standardiserade namnkonventioner

**VAD:** Standardiserade namnkonventioner gäller för både variabelnamnet när det är aktiverat i Adobe Analytics (AA) Admin UI och värdena som skickas till dimensionen. (d.v.s. sidnamn skulle vara &quot;sidnamn (v1)&quot; som ett variabelnamn och de värden för sidnamn som skickas ska vara enhetliga och följa en specifik struktur/hierarki som &quot;sitename|homepage&quot; eller &quot;sitename|search|searchresults&quot;).

**VARFÖR:** Namngivningskonventioner är ett bra sätt att hålla allting enhetligt och att hålla gränssnittet lätt att förstå för användarna. Om du skapar dessa från början och använder dem i plattformen och i koden blir de enklare att skala.

**HUR:** Gränssnittet och taggningsdokumentet ska matcha både Namn och Beskrivning. På så sätt kan användarna inte längre behöva öppna ett Excel-dokument och förstå informationen direkt i gränssnittet. Vi rekommenderar också att du håller allting i gemener för att det ska bli konsekvent.

Det är alltid bäst att ha samma sidnamn på plattformen även (eller skärmnamn för program). Du kan till exempel ställa in &quot;property&quot;:section:underavsnitt:underavsnitt:unikt sidnamn till en variabel/dimension. Om alla dessa fält är separata i datalagret kan du till och med skapa sidnamnet direkt i JS-filen/Launch. Att ha alla dessa element i sina egna dimensioner kan också hjälpa dig att enklare bryta ned specifika egenskaper eller områden på din webbplats/app och få en bättre förståelse för trafik och flöden.

Allt som gör det enklare för användarna att hitta och förstå data, inklusive något så enkelt som namnkonventioner, ökar användningen av Adobe Analytics och ger bättre insikter för företaget.

## Författare

Det här dokumentet skrevs tillsammans av:

![Christel Guidon](assets/Christel-Headshot-150.png)

Christel Guidon, Digital Analytics Platform Manager på NortonLifeLock Adobe Analytics Champion

![Rachel Fenwick](assets/Rachel-Fenwick-150.png)

Rachel Fenwick, Senior Consultant på Adobe
