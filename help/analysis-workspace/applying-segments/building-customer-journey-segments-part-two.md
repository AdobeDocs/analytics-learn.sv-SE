---
title: Bygga kundresesegment - del två
description: I del två, lär du dig hur ni bygger segment för köp och lojalitet för att förstå kundernas köpresa och personalisera innehåll. Med hjälp av signaler som"Book Now"-klick eller inloggningar kan vi identifiera inköpsmetoder och kundlojalitet för effektiv analys och riktad marknadsföring.
feature: Segmentation
role: User
level: Experienced
last-substantial-update: 2023-07-21T00:00:00Z
jira: KT-13476
thumbnail: KT-13476.jpeg
exl-id: 2db73010-5cd0-4454-a4ba-fc1667a50cba
source-git-commit: d95136a21c08312a81baba7673cb7135270af4bd
workflow-type: tm+mt
source-wordcount: '1997'
ht-degree: 0%

---

# Bygga kundresesegment - del två

I del två, lär du dig hur ni bygger segment för köp och lojalitet för att förstå kundernas köpresa och personalisera innehåll. Med hjälp av signaler som&quot;Book Now&quot;-klick eller inloggningar kan vi identifiera inköpsmetoder och kundlojalitet för effektiv analys och riktad marknadsföring.

## Bygger segment för köp och lagring av återgivningsmetod

I vårt sista inlägg beskrev vi processen att skapa besökssegment och byggde vårt första besökssegment, One Hit Wonders. Idag ska vi bygga upp våra inköp och kvarhållningssegment. Vi hade segmenterat cirka 23 % av våra besök och vi byggde våra platshållare för de återstående besökssegmenten.

![Bild 1](assets/Image-1.png)

De besökssegment som vi bygger nu är grunden för att bygga kundsegment baserade på besökare. Vi kommer att bygga dessa besöksbaserade resesegment efter att vi har byggt upp våra besöksavsiktssegment.

Kom ihåg att segment för att bygga besök är en elimineringsprocess. Vi bygger alltså inte upp dessa segment i kronologisk ordning. Vi bygger upp våra besöksavsiktssegment för att enklare definiera för hårdare definition:

1. Återgivning: 0 - One Hit Wonders
1. Återgivning: 3 - Inköp
1. Återgivning: 4 - Kvarhållning
1. Återgivning: 2 - övervägande
1. Återgivning: 1 - Medvetenhet

I vårt sista inlägg kallade jag&quot;Inköp&quot;-segmentet&quot;Bokning&quot; eftersom jag är med i resebranschen. Men i framtiden kallar vi det köpsegmentet för att göra det enklare att tillämpa det på flera branscher.

Ju tydligare signalen är, desto enklare är det att bygga segmentet. I vårt sista inlägg har vi byggt vårt One Hit Wonders-segment, som var det enklaste att definiera eftersom det bara är trafik som studsar. Du kommer att märka att segmenten Inköp och Kvarhållning också är mycket enkla att definiera, eftersom de baseras på mycket tydliga signaler.

## Kundresan är annorlunda än köpbenägenheten

När vi ser på hur vi bygger upp vårt segment för köpmetod är det viktigt att komma ihåg att det är skillnad från benägenhet att identifiera var kunden befinner sig på sin resa. Du kanske har modeller för köpbenägenhet som gör att webbbesökare får poäng för att förutse hur sannolikt det är att de gör ett köp. Dessa modeller är mycket användbara, men de skiljer sig från segmentet Inköpsmetod som vi bygger idag.

Medan en benägenhetsmodell försöker förutsäga om en besökare kommer att köpa, försöker våra segment för besöksavsikt att förstå var en person befinner sig på sin köpresa. Genom att använda intent-segment för att förstå en kunds sinnestillstånd kan vi personalisera innehåll och skräddarsy marknadsföring för att driva rätt trafik till vår säljpipeline. Därför letar vårt segment för köpmetod efter explicita beteendesignaler som indikerar att en besökare vill göra ett köp.

## Bygger segmentet för inköpsbesöksmetod

Det är enkelt att definiera segmentet Inköpsbesöksmetod. I mitt fall är det någon som klickar på knappen &quot;Bok nu&quot; som indikerar någon form av avsikt att boka en kryssning. Det liknar att klicka på&quot;Checka ut&quot; för en webbutik eller en&quot;Prenumerera&quot;-länk i ett mediekontext.

Du måste göra en bedömning när du bestämmer vilken signal som ska användas för att härleda inköpsmetoden. Vi vill att vårt segment för Inköpsmetod ska innehålla alla inköp, men konverteringsgraden ska inte vara 100 %. Vi vill alltså inte använda sidan Inköpsbekräftelse eller Tack för det här segmentet.

På samma sätt är sidan Granska köp (eller det som står omedelbart före inköpsbekräftelsen) antagligen för långt ner för att vara användbar för analys och målinriktning.

När ni går vidare kan det bli mindre tydligt om signalen är användbar för att ange att en kund tänker göra ett köp eller inte. I mitt fall liknar &quot;Bok nu&quot; en länk till en utcheckning i detaljhandeln, och det är signalen jag använde. Men i detaljhandelskontext kan kassan fortfarande vara för långt ned i tratten och View Cart (Visa kundvagn) eller Add to Cart (Lägg i kundvagn) kan vara bättre.

Vi kan se det som något som en mataffär. Om någon plockar upp en produkt som inte betyder att de tänker köpa den. Även om de lägger den i kundvagnen kan de omedelbart lägga den på hyllan igen. Men om de lägger produkten i kundvagnen och börjar gå runt med den, finns det en ganska bra chans att de tänker köpa den. Och om de går in i kassan med den produkten är det ett bra val att de kommer att köpa.

Jag föreslår att man använder besökta sidor eller andra explicita signaler för inköpsavsikt och undviker andra, mindre direkta signaler för att identifiera inköpsavsikt. Jag använder till exempel inte antal sessioner eller antal sidor i en session eller liknande. Dessa indirekta signaler indikerar övervägande, inte avsikt att köpa. Tänk på att syftet med det här segmentet är att sluta sig till besökarens avsikter, inte deras benägenhet.

### Använda Analytics Workspace för att identifiera skyltar för inköpsavsikt

Utfallsrapporten är mycket användbar för att identifiera en bra signal som indikerar inköpsavsikt. Leta efter en plats som logiskt anger återgivning. Du kan bekräfta att steget anger avsikten när du ser ett markerat utfall som går till det steget, ofta följt av ett mindre utfall för steget direkt efter.

![Bild 2](assets/Image-2.png)

Det är också användbart att titta på konverteringsgrader som är kopplade till de olika sidorna på webbplatsen. Detta är särskilt användbart när du ska identifiera sidor som anger inköpsavsikt men som kanske inte behöver göra ett köp (t.ex. finansieringssidor, konfigurationssidor för inköp).

![Bild 3](assets/Image-3.png)

Slutligen är det viktigt att inkludera alla sidor mellan inköpsstart och inköpsbekräftelse i segmentet. Besökarna kan studsa runt och återgå till inköpsflödet vid olika tidpunkter.

### Utesluta andra segment

Från vår första post vill vi påminna om att besöksavsiktssegmenten måste vara ömsesidigt uteslutande och fullständigt uttömmande. Det här är att du kommer att höra mycket i den här serien.

Se till att segmentet Inköpsmetod inte omfattar segmentet One och Done. Du behöver bara exkludera segmentet One och Done eftersom de signaler vi använder för Inköpsmetod är mycket specifika.

Observera att om du exkluderar segmentet One och Done kan du utesluta någon som kommer in på webbplatsen igen på en utcheckningssida. Det här är okej. Själva definitionen av One och Done är en sida, vilket innebär att även om en besökare kommer in eller uppdaterar på en utcheckningssida så gick besöket inte vidare, vilket innebär att det inte finns något uttryck för inköpsavsikt.

### Inköpsåtergivningssegmentet i segmentbyggaren

Segmentdefinitionen för Inköpsmetod är mycket enkel.

Använd besöksbehållaren för att inkludera de sidor eller andra åtgärder som uttryckligen anger en avsikt att göra ett köp. Om du har flera inkluderingsvillkor måste du placera dem i en behållare som förenas med villkoret &quot;And&quot;.

Lägg till en Exkludera-behållare i segmentet som förenas med villkoret&quot;And&quot;. Lägg till segmentdefinitionen för One Hit Wonders (sidvyer är lika med 1) i behållaren Exclude.

![Bild 4](assets/Image-4.png)

Det bästa sättet är att märka behållarna. Du kommer att bli glad att du gjorde det, särskilt som våra segmentdefinitioner blir mer komplexa.

Nu när vi har skapat segmentet Inköpsmetod kan vi använda Workspace Visit Intent Data Quality för att se att segmentet Inköpsmetod är ömsesidigt uteslutande för vårt One and Done-segment.

![Bild 5](assets/Image-5.png)

## Bygga segmentet för återgivningsbesöket

Inom kryssningsbranschen kommer många gäster till vår webbplats för att hantera en bokning, men inte nödvändigtvis för att göra ett köp. De kan komma till webbplatsen för att lägga in reseinformation, granska sin färdväg, göra middagsbokningar eller något annat, utan att handla på en kryssning. Våra gäster kan också köpa utflykter från landskapet eller andra förbättringar av upplevelsen. Vi anser att dessa förbättringar är en del av lojaliteten, så vi håller dem åtskilda från bokningssegmentet (som vi kallar&quot;Inköp&quot; i den här bloggserien).

Butikskunder kan kanske göra returer eller hantera sina lojalitetsprogram. Medie- eller teknikprenumeranter kanske använder produkten. Om din gäst finns på din webbplats för att hantera sin relation med dig är det ett kvarhållningsbesök, och vi bör titta på dessa signaler. Och om ni tillhandahåller en produkt online, som Media, Tech, Online Banking eller andra, finns det troligen många andra typer av besökssegment som vi inte kommer att diskutera i den här serien.

Precis som med segmentet Inköpsmetod söker vi efter mycket tydliga indikationer på avsikt. För mig har vi en hel del på webbplatsen som är dedikerad till att hantera en kryssning så att det är enkelt att identifiera de sidorna. Detta kan vara mer komplicerat för andra företag. Håll utkik efter signaler som inloggningar, kontohantering, besök på supportsidor och liknande.

Jag bör notera att &quot;Kvarhållning&quot; är lite av ett pinsamt namn för besöksavsikten, eftersom besökaren inte finns på vår webbplats &quot;så jag kan behållas som kund.&quot; Vi tänker behålla besöket. Kom bara ihåg att vara empatisk för våra kunder och behålla kundfokus!

### Använda Analytics Workspace för att identifiera signaler för lagringsmetod

Återigen kan Analytics Workspace hjälpa oss att identifiera bevarandemetod. Du kan kategorisera sidorna med hjälp av sidorna, webbplatsavsnittet eller de anpassade segmentdimensionerna. Leta efter sidor med låga inköpskonverteringsgrader. I det här fallet ser vi att sidorna Online Check-In och Shore Excursion (Shorex) har relativt lägre konverteringsgrader än andra sidor som är mer logiskt kopplade till köp och köp.

![Bild 6](assets/Image-6.png)

Det är också en bra idé att titta i Workspace efter sidor med mycket trafik. Skanna listan över sidor med hög trafik och bestäm om de visar på en bevarandesats.

## Utesluta andra segment

Återigen måste våra besöksavsiktssegment vara ömsesidigt uteslutande och fullständigt uttömmande. Om du inte är trött på att läsa detta ännu, kommer du att bli det! För vårt segment för kvarhållningsmetod är det mycket viktigt att utesluta beteenden för inköpsmetod.

För de flesta av oss är inköpsmetod och kvarhållningsmetod inte ömsesidigt uteslutande beteenden. Vi har gäster som kommer till webbplatsen för att hantera sin kommande kryssning, men som också bokar sin nästa resa (tack!). Om du är restaurang kan en besökare kontrollera sina förmånspoäng och sedan göra en onlinebeställning.

Även om beteendet inte utesluter varandra måste våra segment vara till för kundreseanalys. Vi kan bygga andra mycket intressanta segment för att analysera överlappningen mellan köp- och lojalitetsbeteenden. Men för våra nuvarande syften måste dessa segment vara ömsesidigt uteslutande.

Eftersom efterfrågegenerering är ett av de viktigaste målen för marknadsföringen kommer vårt segment med bevarandesats att exkludera Inköpsmetod. Med andra ord, om någon kommer till vår webbplats för att hantera en kryssning, men också anger att man tänker boka en ny kryssning, kommer besöket att gå till segmentet Inköpsmetod.

### Segmentet för kvarhållningsmetod i segmentverktyget

Våra segmentdefinitioner håller på att bli lite mer unika. Inkludera besök i ditt segment. Lägg till dina signaler för bevarandeåtergivning. För mig var det okomplicerat. Om sidnamnet börjar med &quot;bge:&quot; (våra bokade gästsidor) är du i segmentet. Jag har lagt till sidvyer som är större än ett för extra mått (men vi kommer fortfarande att utesluta en av träffarna nedan).

Lägg sedan till exkluderingsbehållare för dina One Hit Wonders- och Purchase Intent-besök. Kontrollera att behållarna är kopplade till villkoret&quot;And&quot;.

![Bild 7](assets/Image-7.png)

Återigen kan du titta på Workspace Intent Data Quality för att försäkra dig om att era segment är ömsesidigt uteslutande. Våra besöksintent-segment är perfekta!

![Bild 8](assets/Image-8.png)

Nu har vi konfigurerat tre av våra fem besöksintent-segment. Vi ser att dessa segment utesluter varandra. I vårt nästa inlägg kommer vi att skapa de sista besöksavsiktssegmenten, överväganden och medvetenhet, och alla våra segment kommer att vara helt uttömmande. När våra besöksintent-segment väl har skapats kan vi sammanföra dem i besöksbaserade segment som ni tycker är mycket användbara för analys och personalisering.

## Upphovsman

Det här dokumentet har skrivits av:

![Aaron Fossum](assets/aaron-headshot.png)

**Aaron Fossum**, Director, Digital Analytics

Adobe Analytics Champion
