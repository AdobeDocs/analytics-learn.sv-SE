---
title: Ta dataanalysen till nästa nivå med Beräknade värden
description: Läs om hur en peer-expert använder beräknade värden för att skapa nya mätvärden utan att ändra implementeringen och använda de data som redan samlats in för att besvara komplexa affärsfrågor.
feature: Calculated Metrics
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2023-05-16T00:00:00Z
jira: KT-13266
thumbnail: KT-13266.jpeg
exl-id: 74793149-9967-4765-832c-c65e578ee34b
source-git-commit: d95136a21c08312a81baba7673cb7135270af4bd
workflow-type: tm+mt
source-wordcount: '1583'
ht-degree: 0%

---

# Ta dataanalysen till nästa nivå med Beräknade värden

De flesta nya användare av Adobe Analytics känner till segment som ett sätt att segmentera och tona ned data. Idag vill jag presentera er för beräknade mätvärden, det näst bästa verktyget i er verktygslåda för analytiker.

Med beräknade mätvärden i Adobe Analytics kan ni skapa nya mätvärden utan att ändra implementeringen med de data ni redan har samlat in. Med Calculated Metrics Builder kan du använda många olika matematiska och statistiska funktioner, så att du kan skapa mätvärden som besvarar även de mest komplexa affärsfrågorna.

## Komma igång med beräknade värden

För att komma igång med beräknade mätvärden ska vi titta på ett enkelt exempel. Tänk dig att du vill förstå om självbetjäningsanvändare online har ett högre genomsnittligt ordervärde (AOV) än samtalsassisterade användare. Så här skapar du ett beräknat mätvärde för att besvara den här frågan:

Om du vill öppna verktyget Beräknade mått använder du den övre navigeringen och klickar på → **Komponenter** → **Beräknade mått** → **+ Lägg till.** Du kan också klicka på **+-tecknet** ovanför **Metrisk** på panelen Komponenter.


![Calc 01](assets/calc01.png) ![Calc 02](assets/calc03.png) ![Calc 03](assets/calc02.png)

![Beräkna 04](assets/calc04.png)

*Beskrivningar nedan för gränssnittsobjekt*

När verktyget för beräkning av mått öppnas lägger du till och/eller gör följande:

**A.** Ett namn för det beräknade måttet. Det här namnet visas i komponentlistan för mätvärden, så gör det något som är tydligt för dig själv och andra, som *Call Center AOV*.

**B.** En beskrivning av det beräknade måttet. Den här beskrivningen visas när användare klickar på **i** bredvid måttet i komponentlistan, så kontrollera att det är informativt. För AOV på Call Center kan vi till exempel lägga till *Beräknar AOV för beställningar som stöds av Call Center*.

**C.** Måttformatet: Välj decimal, tid, procent eller valuta och lägg till decimaler och polaritet. Här väljer vi *Valuta för Format, 0 för antal decimaler och* ⬆ *Bra (grön) för polaritet.*

**D**. Om du använder taggar, som gör att du kan använda ämnen och snabbt hitta beräknade värden, lägger du till de taggar som gäller här. Vi har lagt till taggarna *AOV* och *Call Center*.

**E.** Det här avsnittet är till för visning - när du bygger dina beräknade värden i avsnitt F visas formeln här.

**F.** Här drar och släpper du dimensionerna (H), måtten (I) eller segmenten (J) för att skapa det beräknade måttet samt operatorerna för formeln. För varje mätvärde kan du ändra måtttyp (standard/summa) och attribueringsmodell om du klickar på cog-hjulet. *Vi drar och släpper Call Center Revenue. Under det kommer vi* ￼*. Vi godkänner standardmåtttypen och attribueringsmodellen.*

**G**. Använd det här alternativet, **+Lägg till**, om du vill lägga till ytterligare villkor eller statiska nummer, som vi inte behöver här.

**K.** Och slutligen, när du bygger din beräkning, kan du förhandsgranska de senaste 90 dagarnas data här.

Nu när vi har byggt Call Center AOV behöver vi också ett beräknat mått för AOV online. Vi skulle göra detta i enlighet med de steg som beskrivs ovan.

Sedan kan vi bygga ett tredje beräknat mätresultat, antingen med Calculated Metrics Builder eller direkt från frihandsregistret, för att jämföra Call Center och AOV online, så vi får något sådant:

![Beräkna 05](assets/calc05.png)

I vårt exempel ser vi en avsevärd förbättring när kunderna använder callcenter för att hjälpa dem att göra ett köp. Dessa data kan sedan informera våra beslut om hur kunderna kan få hjälp med sina inköp genom exempelvis popup-erbjudanden eller andra guidade upplevelser.

## Använda segment i beräknade värden

Nu ska vi titta på hur vi kan använda segment i beräknade mätvärden för att få mer kunskap om kundbeteende, preferenser och motiv. Med segment och beräknade värden kan vi lära oss tillräckligt mycket om kunderna för att förbättra deras upplevelse, öka intäkterna och förbättra kundnöjdheten och kundlojaliteten.

Vi vet redan från AOV-exemplen att inköp hos kundtjänst vanligtvis har ett högre AOV. Andra mätvärden talar dock om för oss att de flesta användare inte använder callcenter för inköp.

Vilka kategorier av återförsäljare - och användarsökvägar genom dessa kategorier - ger det högsta AOV?  Vi kan ta reda på det genom att kombinera segment med beräknade värden.

För att göra det måste vi först skapa segment på besöksnivå *include* och *exclude* för varje produktkategori. Inkludera eller exkludera bestäms genom att klicka på **alternativknappen** i behållarens högra hörn. Standardvärdet är Inkludera.

![Calc 06](assets/calc06.png) ![Calc 07](assets/calc07.png)

När vi väl har skapat dessa segment kan vi skapa en beräknad mätmetod som ger dig svaret på din fråga. Vi öppnar Calculated Metrics Builder och gör följande:

1. Sök efter de nyligen skapade segmenten och dra och släpp dem som du vill använda i det grå området högst upp i rutan **Definition**. Om vi t.ex. vill skapa ett AOV för användare som besökte både Kvinna och Män, men inte Kid, kan vi dra och släppa dessa tre segment i det området: *Inkludera Kvinna*, *Inkludera Mans* och *Uteslut Kid*. Vi kallar det här *stacksegmentet*.

   ![Calc 09](assets/calc09.png) ![Calc 08](assets/calc08.png)

1. Sedan drar och släpper vi mätvärdet **Online Revenue** i samma behållare och sedan **Online Orders**. Eftersom behållare fungerar som matematiska uttryck för att bestämma ordningen på operationer, bearbetas objekt i behållare före efterföljande processer, även om det inte finns flera behållare eller processer i den här beräkningen.
1. Vi ändrar operatorn mellan de två mätvärdena till division ( max).
1. Vi väljer **Valuta** som format, **** decimaler och **UP** för polaritet.
1. Namnge det beräknade måttet och ange en beskrivning.
1. Spara.

När vi är klara ser våra beräknade mätvärden ut så här:

![Beräkna 10](assets/calc10.png)

När vi har skapat beräknade mätvärden med skiktade segment för varje kombination av besökarens kategoriresa och tagit en titt på data, titta på vad vi lär oss! Användare som besöker både kvinnor och män under besöket har det högsta AOV-värdet, och jämfört med besökare i en enda kategori är lyften betydande:

![Calc 11](assets/calc11.png) ![Calc 12](assets/calc12.png)

Vi vet att vi kan optimera sidlayout, produktplaceringar och kampanjmeddelanden för att få in fler personer i dessa kategorier innan vi checkar ut dem.

## Värdefull, men inte tillgänglig överallt

**Därför är beräknade värden, både enkla och komplexa, mycket värdefulla för analytiker!**

Dessa mått är dock inte tillgängliga i alla delar av Adobe Analytics. Du kan inte använda beräknade värden i:

- Utfall i Analysis Workspace
- Kohortanalys i Analysis Workspace
- Data Warehouse
- Realtidsrapporter
- Aktuella datarapporter
- Analyser för Target
- Report Builder

## Beräknade mätvärden - bästa praxis

Nu när du vet hur värdefull beräknad statistik kan vara, ska vi titta på några av de bästa sätten att skapa dem.

1. **Kontrollera formelsyntaxen.** Kontrollera att formelsyntaxen är korrekt och att den följer Adobe Analytics-syntaxen så att du får meningsfull information.
1. **Verifiera åtgärdsordningen.** Se till att använda behållare noggrant och placera saker i rätt matematisk ordning för åtgärder.
1. **Dubbelräkna inte data**. Du kan undvika dubbelräkning genom att se till att formeln som används i det beräknade måttet inte räknar samma data flera gånger. Detta uppnås ofta genom att kombinera villkoren *Inkludera* och *Uteslut* i det beräknade måttet eller genom användning av segment.
1. **Kontrollera tidsåterstämmighet.** Kontrollera att det beräknade måttet har samma tidshalaritet som källmåtten som används i formeln.
1. **Använd korrekta data:** Du får bara värdefulla resultat om du använder korrekta och tillförlitliga data i beräkningen.

## Metodtips för anpassade segment

När du skapar segment i Adobe Analytics bör du tänka på följande:

1. **Gör det enkelt.** Undvik att komplicera segmentet för mycket. Förvara det så enkelt som möjligt och använd endast de villkor som är nödvändiga för att säkerställa noggrannheten.
1. **Använd rätt behållartyper**. Använd rätt behållartyp - besökare, besök eller tryck - i segmentdefinitionen för att undvika felaktiga resultat.
1. **Dubbelräkna inte data**. Precis som med beräknade värden kan du se till att segmentet inte räknar samma data flera gånger. Det kan vara till hjälp att inkludera och exkludera behållare.
   1. När en inkluderingsbehållare används, *inkluderar* *allt innehåll i besöket* om någon träff matchar villkoret i besöket.
   1. När en exkluderingsbehållare används, *utelämnar den allt innehåll i besöket* om någon träff matchar villkoret i besöket.
1. **Kapsla behållare korrekt**. Bestäm vilka data som ska inkluderas med den yttersta behållaren och tillämpa sedan kapslade regler på återstående data. När kapslade regler tillämpas fungerar segmentflödet som en tratt, och efterföljande regler gäller inte för träffar som den första regeln har exkluderat.
1. **Kontrollera att dina data är aktuella.** Se till att använda korrekta och aktuella data i segmentdefinitionen för att få korrekta resultat.
1. **Testa segmentet.** Testa alltid segmentet för att kontrollera att det fungerar som det ska innan du släpper det till andra.
1. **Fundera på prestanda.** segment kan göra rapportbearbetningen långsammare, så tänk på den effekten när du skapar dem.

## Viktiga uppgifter

Genom att kombinera segment och beräknade värden i Adobe Analytics kan ni få en mer robust och effektiv dataanalys. Genom att segmentera och dela upp era data och bygga upp beräkningar för jämförelse kan ni få djupare insikter i kundbeteenden som ni kan använda för att optimera era marknadsföringskampanjer och skapa skräddarsydda instrumentpaneler och rapporter. Tänk dock på att beräknade värden inte är tillgängliga inom alla områden av Adobe Analytics, och glöm inte att följa bästa praxis för att säkerställa att ni får korrekta och användbara data.


## Upphovsman

Det här dokumentet har skrivits av:

![Debbie Kern](assets/calc13.jpeg)

**Debbie Kern**, Senior Adobe Analytics Manager på Adswerve

![Adswerve](assets/calc14.png)
