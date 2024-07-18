---
title: Hej då Excel, hej till beräknade mätvärden
description: Lär dig fördelarna med beräknade värden i Adobe Analytics och hur de kan ge dig en kontinuerlig, dynamisk vy av dina data i den här artikeln.
feature: Calculated Metrics
role: User
level: Experienced
doc-type: Article
last-substantial-update: 2023-05-02T00:00:00Z
jira: KT-13178
thumbnail: KT-13178.jpeg
exl-id: d4f69244-6614-41f3-ac48-70adabb8a8e7
source-git-commit: d95136a21c08312a81baba7673cb7135270af4bd
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 0%

---

# Hej då Excel, hej till beräknade mätvärden

Lär dig fördelarna med beräknade värden i Adobe Analytics och hur de kan ge dig en kontinuerlig, dynamisk vy av dina data i den här artikeln.

Hej! Varför är du i Excel just nu? Jag vet varför. Du har rapporter för att komma till rätt personer. Du är upptagen med att mata in data från Adobe Analytics och beräkna konverteringsgraden, kartlägga dem och förbereda dig för att lägga in dem i en PowerPoint som leder vidare till beslutsfattare. Jag hoppas verkligen att du åtminstone använder Report Builder för att göra det, men jag vet att vissa av er kopierar och klistrar in data manuellt från en Workspace till Excel.

Varför?

Varför gå igenom en manuell process varje månad? Varför visas en statisk vy en gång i månaden i stället för en kontinuerlig, dynamisk vy? Varför kopiera det till PowerPoint? Varför inte skapa Beräknade mått direkt i Adobe Analytics?

## Beräknade värden är kraftfulla

Beräknade mått är kraftfulla, men även de grundläggande matematiska funktionerna är mycket användbara och ger en avsevärd förbättring jämfört med att göra matematiska beräkningar i Excel. Låt oss titta på några av fördelarna och några exempel:

1. **Beräknade värden är Aktuella och dynamiska**

   När du exporterar nummer från Adobe Analytics låses de vid en viss tidpunkt. Du behöver veta hur er webbplats eller app fungerade månaden innan, men hur håller beslutsfattarna reda på hur saker och ting går i mitten av månaden? Om din konverteringsgrad sväller i en dag och sedan återgår till medelvärdet i slutet av månaden, vet du? Det blocket kan vara värdefull information som avslöjar ett viktigt telemetriproblem, eller ännu viktigare, en förändring av besökarnas beteende. Med ett beräknat mätresultat kan du diagramma detta och se det samma dag det inträffar, så att du kan börja svara.

1. **Beräknade mått sparar tid**

   Jag har varit där. Kopiera/klistra in. Ange formeln eller dra cellen ovanför den nedåt. Klicka på diagrammet och ändra intervallet så att du har de senaste tolv eller tretton månaderna. Kopiera diagrammet. Gör det nu igen. Och igen. Och igen. Skicka ut PowerPoint. Det är tidsödande och tidsödande och det känns som om du måste göra det varje månad för alltid.

   I stället kan du skapa en Workspace som använder dina beräknade värden, ha de tolv eller tretton senaste helmånaderna som datumintervall och automatiskt uppdatera data och diagram vid midnatt den första dagen i varje månad. Mottagarna kan ha direktåtkomst till Workspace. De kan få en PDF-kopia automatiskt via e-post den första dagen i månaden eller efter att du har använt textvisualiseringar för att lägga till kommentarer om data (du vet, den roliga delen av rapporteringen).

1. **Beräknade mått kan användas för stora datamängder**

   Du kan exportera alla produktnamn till Excel och börja beräkna konverteringsgrader och intäkter per besökare, men det blir ett problem om du har 100 000 eller så. Inte ett problem med beräknade värden. Släpp dimensionen i en tabell som vanligt och använd sedan dina beräknade värden som mått. Nu har du en dynamisk sorterbar tabell som uppdateras automatiskt när produkter eller någon dimension som du använder läggs till i katalogen.

1. **Beräknade mått förhindrar fel**

   Excel-fel inträffar. Vi har alla varit där. Hela Greklands ekonomi och anseendet för två högt värderade akademiker förstördes på grund av ett fel i Excel-formeln. Du har förmodligen ingen europeisk ekonomi som använder dina Excel-kunskaper, men det finns definitivt ett beslut om budgetar som kommer att ändras baserat på dina siffror. Med Beräknade mått kan du skapa ett mätvärde, ha det QAd och sedan inte oroa dig för det igen.

### Nu när vi har gått igenom fördelarna med beräknade värden ska vi titta på hur vi kan omsätta dem i praktiken

**Användningsfall 1: Konverteringsgrader**

De flesta konverteringsgrader är bara en enkel uppdelning. Dela upp antalet konverteringar med antalet besökare eller besök. Dela upp antalet sidvyer för den sista sidan i en tratt med antalet sidor som visas för den första sidan i tratten. Dela upp antalet interna kampanjklickningar med antalet visningar. Allt detta kan enkelt göras som beräknade mätvärden och placeras i en kontrollpanel som har låg datalatens, uppdaterar visualiseringar och större delningsbarhet.

**Användningsfall 2: Intern sökning**

Intern sökning är ett av de viktigaste verktygen för att förstå webbplatsen. Sökresultaten för webbplatsen talar om för dig vad besökarna är intresserade av och om de enkelt kan hitta det via navigering eller inte. Du måste kunna se om din webbplatssökning fungerar bra och om du använder lite grundläggande tillägg och division kan du få det svaret.

Låt oss börja med sökresultat. Du vill veta om en sökterm ger resultat eller inte ger något. Det är vanligtvis separata händelser. Vill du gå igenom problemet med att få en tredje händelse för alla interna webbplatssökningar tillagda? Ge i stället dina utvecklare en paus och använd Beräknade värden för att lägga till intern sökning: Resultat och intern sökning: Inga resultat tillsammans för att få interna sökningar totalt.

Hur stor procent av sökningarna returnerar inga resultat? Dela upp intern sökning: Inga resultat med det nya beräknade totalantalet interna sökningar. Nu vet ni om det är viktigt att skapa nytt innehåll som matchar söktermerna, eller om ert innehållsteam kanske kan ta itu med högre prioriteringar.

Vi vill veta hur många av sökningarna med resultat som får klickningar och har vanligtvis en separat mätmetod för det också. Använd Beräknade värden om du vill dividera antalet klick med antalet gånger som termen leder till sökresultat och visar det som en procentandel. Nu har du klickfrekvensen för varje intern sökterm på webbplatsen. Du kan isolera söktermerna som ger oanvändbara resultat. Ni har tillgång till alla historiska data så att ni kan diagram över dem, och när ni gör förbättringar kan ni enkelt se om de fungerar genom att titta på den frekvensen eller inte.

Dela upp antalet interna sökningar med antalet sökande besökare. Du har sökningar per besökare för varje term. Om talet är högt (ju närmare 1,0 desto bättre) har du ett av två möjliga problem. Antingen är resultatet som klickas på dåligt och besökarna gör flera sökningar för att hitta det bästa resultatet, eller så kan de inte hitta de sidor de letar efter via nav.

Hur kan du mäta om dessa nyckelsidor går att hitta via din navigering? Skapa ett beräknat mått för sidvyer som följdes av en sidvy med sökresultat. Dela upp det med den totala sidvisningen för den sidan. Nu vet du hur stor procentandel av sidvyerna som kom från sökresultaten. Om du har en hög procentandel har du antagligen en del att göra när det gäller navigering.

### Beräknade värden är kraftfulla

Jag hoppas att detta har visat dig några av möjligheterna att använda grundläggande matematiska funktioner i Beräknade mått och att du kommer att börja bygga lite själv. Detta börjar bara beskriva möjligheterna med matematiska beräkningar, även med fyra enkla funktioner. Beräknade mätvärden kan hjälpa er att förstå besökarnas beteende på en helt ny nivå, och när ni väl har använt det har ni öppnat dörren för mer komplexa funktioner som också är tillgängliga för er.

## Upphovsman

Det här dokumentet har skrivits av:

![Gittai-huvudbild](assets/gittai.png)

**Gitai Ben-Ammi**, rektor på Concentrix Catalyst

Adobe Analytics Champion
