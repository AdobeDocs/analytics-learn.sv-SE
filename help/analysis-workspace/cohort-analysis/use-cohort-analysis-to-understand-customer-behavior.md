---
title: Använd kohortanalys för att förstå kundbeteende
description: För att förbättra kundupplevelsen och intäkterna måste företagen förstå kundbeteendet. Kohortanalyser kan hjälpa er att förstå engagemang och lojalitet, vilket kan leda till åtgärder som att förbättra kontoskapande och skapa kampanjer för stora månadsvolymer.
feature: Cohort Analysis
role: User
level: Experienced
doc-type: Article
last-substantial-update: 2023-05-16T00:00:00Z
jira: KT-13213
thumbnail: KT-13213.jpeg
source-git-commit: 1b82bc495f72b099c44a1118145a63c255dcc62a
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 0%

---


# Använd kohortanalys för att förstå kundbeteende

För att förbättra kundupplevelsen och intäkterna måste företagen förstå kundbeteendet. Kohortanalyser kan hjälpa er att förstå engagemang och lojalitet, vilket kan leda till åtgärder som att förbättra kontoskapande och skapa kampanjer för stora månadsvolymer.

Att analysera digitala prestanda är avgörande för att förstå hur kunderna interagerar med ett företag och vilka åtgärder som kan vidtas för att förbättra deras upplevelse. I det här blogginlägget ska vi titta närmare på hur man använder kohortanalyser för att bättre förstå kundbeteenden.

## Del 1: Jämföra digitala prestanda mellan första och andra besök

### Ställa in scenen

En kund vill förstå digitala prestanda under de senaste två åren och funderar på att utveckla ett lojalitetsprogram för att höja det digitala resultatet. Till att börja med kan vi titta på den aktuella webbplatsmixen mellan nya och återkommande användare för att förstå hur de två besökarna uppför sig idag.

Aktuella digitala prestanda

1. 2022 kom 62 % av beställningarna från förstagångsbesök jämfört med 38 % av beställningarna från återbesök (som var föremål för cookies, flera enheter).
1. Första besöket konverterar något högre än antalet besök för båda, 11,6 % jämfört med 11,4 %.
1. Jämfört med 2021 minskade konverteringsgraden i båda segmenten.

![Besökstabell](assets/cohort1.png)

## Del 2: Kohortanalys - Besök Edible Arrangements Global Prod

För att förstå hur krånglig den digitala kanalen är och möjligheten att driva fler återkommande köpare är nästa fråga att svara på: Hur många besökare återvänder till webbplatsen varje månad under 2022?

### Vi presenterar kohortanalys

Kohortanalys är ett användbart verktyg för att förstå hur kohorter interagerar med ett varumärke över tid. Till att börja med har vi bestämt vilka frågor vi ska besvara:

1. Hur lång är den genomsnittliga kvarhållningsperioden per månad under ett givet år?
1. Hur många besökare återvänder till webbplatsen varje månad under ett visst år?
1. Hur påverkar inloggningar lojaliteten?
1. Finns det specifika produkter som har ökat lojaliteten?

Konfigurera kohorttabellen

1. Ange datumintervall till jan till dec 2022
1. **Inkluderingskriterier:** Besök
1. **Returkriterier:** Besök
1. **Kornighet:** Månad
1. **Inställningar:** Rullande beräkning \*\*Gör att du kan beräkna kvarhållningen baserat på föregående kolumn, inte den inkluderade kolumnen. Detta innebär att en användare ingår i var och en av månaderna\*\*
1. **Segment:** kan du välja specifika segment för att ytterligare utveckla analysen
   1. Särskilda landningssidor
   1. Enhetstyp
   1. Marknadsföringskanaler
   1. osv.

### Tolka resultaten

**År 2022:**

1) Månader med högsta lojalitetsgrad +1 månad omfattar januari, april och november
1) Månader med störst volym är februari och maj
1) Det finns cirka 1 000 besökare som återvänder till webbplatsen varje månad

![2022 kvarhållningstabell](assets/cohort2.png)

**År 2021:**

1) Månader med högsta lojalitetsgrad +1 månad omfattar april, januari och mars
1) Månader med störst volym är februari och maj

![2021 Retention table](assets/cohort3.png)

**Åtgärdsobjekt:**

Skapa ett segment baserat på ~1 000 besökare och läs mer om dem:

- Var ligger de?
- Vilka produkter köper de under året?
- Vilka butiker köper de av?

Viktiga månader visar på möjligheten att öka kundlojaliteten baserat på volym:

- Finns det någon särskild taktik som kan leda till ökad krånglighet under februari och maj för att dra nytta av volymen?

Upprepa analys för beställningar för att förstå repetera inköp

- Är de högsta +1-månadersräntorna för kvarhållande samma månad?
- Är den högsta månaden av besöken densamma för beställningar?

## Del 3: Lägga till två mätvärden i inkluderingsvillkor

### Förstå påverkan av inloggning

Eftersom den här klienten vill förstå värdet av ett lojalitetsprogram inkluderade nästa steg i analysen att lägga till i händelsen Login success som ett Inclusion-mått till kohorten.

Caveat: Kohortanalys kan inte användas för beräknade värden (t.ex. konverteringsgrad) eller icke-heltalsvärden (t.ex. Intäkter). Endast mätvärden som kan användas i segment kan användas i kohortanalyser, och de kan bara ökas med >1 åt gången.

Är det troligare att webbplatsen behåller användare som loggar in?

Vilken skulle påverkas om vi kunde få fler användare att logga in? Är det en mer klibbig upplevelse?

### Konfigurera kohorttabellen

1. **Ange datumintervall:** till jan till dec 2022
1. **Inkluderingskriterier:** Besök + händelse om att inloggningen lyckades
1. **Returkriterier:** Besök
1. **Kornighet:** Månad
1. **Inställningar:** Rullande beräkning \*\*Gör att du kan beräkna kvarhållningen baserat på föregående kolumn, inte den inkluderade kolumnen. Detta innebär att en användare ingår i var och en av månaderna\*\*

### Tolka resultaten

**År 2022:**

1) Månader med de högsta kvarhållningsfrekvenserna +1 månad omfattar januari, april och november (samma månader som första kohorttabellen)
1) Månader med störst volym är februari, maj och december
1) Det finns cirka 2 500 besökare som återvänder varje månad \*\*mer än dubbelt\*\*

**Åtgärdsobjekt:**

Undersök webbplatsens användarupplevelse för att få användare att skapa ett konto under utcheckning

![Kohorttabell 4](assets/cohort4.png)

## Del 4: Custom Dimension Cohort

Custom Dimension Cohort: Skapa kohorter baserat på den valda dimensionen i stället för tidsbaserade kohorter (standard). Många kunder vill analysera sina kohorter med något annat än tid, och med den nya funktionen Custom Dimension Cohort kan du skapa kohorter baserat på de mått de själva väljer. Använd dimensioner som marknadsföringskanal, kampanj, produkt, sida, region eller någon annan dimension i Adobe Analytics för att visa hur kvarhållandet ändras baserat på de olika värdena för dessa dimensioner. The

Segmentdefinitionen för Custom Dimension Cohort tillämpar bara dimensionsobjektet som en del av inkluderingsperioden, inte som en del av returdefinitionen.

När du har valt alternativet Egen Dimension-kohort kan du dra och släppa vilken dimension du vill i släppzonen. På så sätt kan du jämföra liknande dimensionsobjekt under samma tidsperiod. Du kan till exempel jämföra prestanda för städer sida vid sida

sida, produkter, kampanjer osv. Den returnerar de 14 viktigaste artiklarna. Du kan emellertid använda ett filter (öppna det genom att hålla muspekaren åt höger om dimensionen som dragits på) för att endast visa önskade dimensionsobjekt. Det går inte att använda en anpassad Dimension-kohort med funktionen Latency Table.

### Vilka produkter driver webbplatsens kantighet?

Tabellen Custom Dimension Cohort visar produkter som ger högre retentionstakt än genomsnittet.  Tabellen hjälper er att identifiera era främsta produkter för att driva interna och externa marknadsföringskampanjer med de bästa, intressanta produkterna.

**I februari:** 3 produkter som sticker ut med högre retentionshastighet

1) Produkt 1
1) Produkt 2
1) Produkt 3

**I mars:**

1) Produkt 1
1) Produkt 2
1) Produkt 3 - presterar ofta bättre än den genomsnittliga retentionshastigheten jämfört med den genomsnittliga retentionshastigheten.

![Kohorttabell 5](assets/cohort5.png)

## Slutsats

Kohortanalyser och Custom Dimension Cohort är kraftfulla verktyg för att förstå kundbeteende och förbättra digitala prestanda. Genom att analysera kundlojalitet, inloggningsfrekvens och påverkan av specifika produkter kan företag fatta datadrivna beslut för att förbättra kundupplevelsen och öka tillväxten.

## Upphovsman

Det här dokumentet har skrivits av:

![Jennifer Yacenda](assets/jennifer-yacenda.png)

**Jennifer Yacenda**, Senior Director på Marriott

Adobe Analytics Champion