---
title: Bygga kundresesegment
description: Lär dig skapa beteendebaserade kundsegment i Adobe Analytics och förbättra kundernas upplevelse med Adobe Experience Cloud genom att följa den här steg-för-steg-guiden.
feature: Segmentation
role: User
level: Experienced
doc-type: Article
last-substantial-update: 2023-05-02T00:00:00Z
jira: KT-13180
thumbnail: KT-13180.jpeg
exl-id: c06afc7b-e997-404d-82a4-e7ec5d5ba44d
source-git-commit: d95136a21c08312a81baba7673cb7135270af4bd
workflow-type: tm+mt
source-wordcount: '1243'
ht-degree: 0%

---

# Bygga kundresesegment

Lär dig skapa beteendebaserade kundsegment i Adobe Analytics och förbättra kundernas upplevelse med Adobe Experience Cloud genom att följa den här steg-för-steg-guiden.

Låt oss skapa bättre kundsegment! I den här serien använder vi Adobe Analytics för att definiera beteendebaserade segment, beräkna målgruppsstorlekar och spåra användarnas rörelser. Till slut kan ni personalisera media och förbättra kundernas upplevelse av Adobe Experience Cloud. Tänk på att dessa segment lever och bör uppdateras när ni lär er mer om era kunder. Även om rapportering kan medföra vissa utmaningar, oroa dig inte, jag hjälper dig igenom det! Vi börjar med att skapa vår första uppsättning kundresesegment, med början i segmentet&quot;One Hit Wonders&quot;.

Idag ska vi skapa platshållare för vår första uppsättning kundtjänstsegment, bygga en Adobe Analytics Workspace som hjälper oss att definiera våra segment och definiera vårt första segment,&quot;One Hit Wonders&quot;.

I slutet av den här serien kan ni skapa kundsegment i Adobe Analytics utifrån beteendesignaler. Ni kommer att kunna uppskatta storleken på varje målgrupp i varje skede av resan och förstå i vilken utsträckning användarna rör sig mellan dessa steg. Och ni kommer att kunna exportera dessa målgrupper inom kundresan till Adobe Experience Cloud för att möjliggöra personalisering och medieanpassning.

Varje företag är annorlunda, och det innebär att kundens kundfärdssegment ser annorlunda ut än mitt. I stället för att förskriva specifika formler för dina segment kan du föreslå några saker att titta på och en övergripande process för att skapa dem.

Det är också viktigt att komma ihåg att era kundsegment kommer att vara levande segment. Det här är inte en enda övning. När ni lär er mer om era kunder kommer ni att uppdatera dessa segment. Detta medför vissa problem när det gäller rapportering. Man vill ha enhetliga rapporter, och om segmentdefinitionerna ändras så ändras även siffrorna i rapporterna.

## Komma igång med besöksavsiktssegment

Det första steget för att skapa kundsegment är att sluta sig till varför en gäst finns på er webbplats med beteendesignaler och, om sådana finns, Voice of Customer data. Vi ska bygga en uppsättning besökssegment för att kategorisera alla besök på webbplatsen. I nuläget måste våra besöksavsiktssegment vara ömsesidigt uteslutande och fullständigt uttömmande. Varje besök ska tillhöra ett, och bara ett, besökssegment.

Segmenten Besöksmetod beskriver ett besök, så vi använder besöksbehållaren i segmentdefinitionen.

Min första uppsättning av besöksavsiktssegment inkluderade:

* One Hit Wonders
* Medvetenhet
* Villkor
* Bokning (inköp)
* Kvarhållning (hantera bokning/inköp)

För att göra mina besöksintent-segment enkla att använda lade jag till&quot;Intent:&quot; som prefix för mina segmentnamn, gav dem ett nummer för att möjliggöra sortering och taggade dem&quot;intent&quot;. Mina segment såg ut som bilden nedan.

![intent segments](assets/intent-segments.png)

**Skapa dina besöksåtergivningssegment med hjälp av besöksbehållaren med en platshållardefinition av sidvyer >= 1.**

Som vi kommer att se är byggandet av dessa segment en iterativ och sammankopplad process. Jag kommer att beskriva processen att bygga dessa segment i en framtida post.

## Workspace, Data Quality för besökssegment

![gå till arbetsytan Återgivning](assets/visit-intent-workspace.png)

Jag använde en enkel arbetsyta för att säkerställa att jag definierade mina besöksintent-segment väl. Kom ihåg att varje besök måste tillhöra ett, och bara ett, besökssegment. Den arbetsyta som jag konfigurerar ser till att alla besök tas med och att det inte finns någon överlappning mellan segmenten.

Jag gav den här arbetsytan namnet&quot;DATAKVALITET: Besök Intent Segments&quot; med taggarna&quot;datakvalitet&quot;,&quot;Besök avsikt&quot; och&quot;kundresa&quot;. Senare skapar vi en&quot;Besök instrumentpanel för återgivning&quot; så prefixet&quot;DATAKVALITET&quot; anger att den här arbetsytan används för att konfigurera och underhålla segment. Det är en administrativ kontrollpanel som har ganska lite affärsinsikter men som är viktig för att säkerställa att segmenten upprätthålls. Det är en god idé att regelbundet gå tillbaka till den här instrumentpanelen eller konfigurera aviseringar för att se till att era segment förblir korrekt definierade.

Den viktigaste visualiseringen på den här arbetsytan är segmentöverlappningsfriformsvisualiseringen i mitten till vänster. Använd mätvärdet för Besök för att skapa kolumnfilter för vart och ett av dina segment för Besöksmetod, plus segmentet Alla besök i den högra kolumnen. Skapa rader för varje besöksintent-segment till vänster. Nu kan du visualisera flera flikar. När era segment är korrekt konfigurerade finns det bara data i en kolumn och en rad, i skärningspunkten mellan varje besöksintent-segment och sig själv.

De näst viktigaste visualiseringarna är sammanfattningsmåtten längst upp till vänster. Sammanfattningen av segmenterade besök får sitt värde från kolumnen Alla besök i segmentöverlappningsvisualiseringen direkt nedanför. Sammanfattningen Alla besök har en egen dold tabell.

![alla besök](assets/all-visits.png)

I det övre högra hörnet har jag lagt till ytterligare mätvärden till vart och ett av segmenten för att ge lite &quot;smak&quot; åt hur segmenten formas. Eftersom de här segmenten utesluter varandra förväntar jag mig att bara se bokningar för bokningsmetoden (det är inte sant, vi får konverteringsgraden när vi gör besökssegmenten besöksbaserade.

Kom ihåg att vi just skapade platshållarsegment. Till att börja med ser arbetsytan fantastisk ut. Alla besöksavsiktssegment överlappar 100 % eftersom de har samma definition. Detta är korrekt och exakt vad du vill se nu i processen. När vi bygger upp segmentdefinitionerna börjar vi se hur dessa segment börjar få form.

![Besök segmentdefinitionerna för återgivning](assets/visit-intent-segment-defs.png)

## Bygger ditt första besökssegment

Att definiera segment för besöksåtergivning är en del av en process av eliminering, och det finns en hel del ömsesidigt beroende mellan dem. Så jag byggde inte upp dessa segment i turordning efter resan, utan skapade dem i ordning från den enklaste till den svåraste utmaningen. Det gav mig den här ordern:

1. Återgivning: 0 - One Hit Wonders
1. Återgivning: 3 - Bokning
1. Återgivning: 4 - Kvarhållning
1. Återgivning: 2 - övervägande
1. Återgivning: 1 - Medvetenhet

Ganska slumpmässigt, va? Att definiera dessa segment för besöksåtergivning var en iterativ process fram och tillbaka och ofta en justering av ett segment som krävde uppdateringar av andra segment. Detta blir tydligare när jag beskriver hur jag har definierat de olika segmenten.

Idag ska vi definiera vårt första och enklaste segment, One Hit Wonders

## Bygger segmentet One Hit Wonders

Mitt första segment,&quot;One Hit Wonders&quot;, var enkelt att definiera. Det är bara ett besök med bara en sidvy. Vi vet verkligen inte varför den användaren var på webbplatsen, eftersom de studsade. Jag antar att vi skulle kunna gissa oss till en metod som bygger på deras anmälningssida, men med bara en sidvy finns det inte tillräckligt med information för att kunna gissa sig till avsikten.

![Segmentdefinition](assets/segment-def.png)

När du har definierat det här segmentet börjar du se hur Workspace tar form på besökswebbplatsen.

![Fler segmentdefinitioner](assets/more-segment-defs.png)

Att bygga kundsegment med Adobe Analytics är en utmanande men givande process. Genom att skapa beteendebaserade segment, beräkna målgruppsstorlekar och spåra användarrörelser kan företag personalisera media och förbättra kundupplevelsen. Varje verksamhet är unik och det finns inga specifika formler för att skapa segment, utan riktlinjer och en process som ska följas. Segmenten bör uppdateras när företag lär sig mer om sina kunder, vilket medför rapporteringsproblem. Genom att följa processen med att bygga segment för besöksavsikt kan företag förbättra den övergripande kundupplevelsen.

## Upphovsman

Det här dokumentet har skrivits av:

![Aaron Fossum](assets/aaron-headshot.png)

**Aaron Fossum**, Director, Digital Analytics

Adobe Analytics Champion
