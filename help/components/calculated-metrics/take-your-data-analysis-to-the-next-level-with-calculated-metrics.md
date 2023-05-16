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
source-git-commit: c64f2fde1b91edd9f3d6c0f87aa889ed2c613d9b
workflow-type: tm+mt
source-wordcount: '1566'
ht-degree: 0%

---


# Ta dataanalysen till nästa nivå med Beräknade värden

De flesta nya användare av Adobe Analytics känner till segment som ett sätt att segmentera och tona ned data. Idag vill jag presentera er för beräknade mätvärden, det näst bästa verktyget i er verktygslåda för analytiker.

Med beräknade mätvärden i Adobe Analytics kan ni skapa nya mätvärden utan att ändra implementeringen med de data ni redan har samlat in. Med Calculated Metrics Builder kan du använda många olika matematiska och statistiska funktioner, så att du kan skapa mätvärden som besvarar även de mest komplexa affärsfrågorna.

## Komma igång med beräknade värden

För att komma igång med beräknade värden ska vi titta på ett enkelt exempel. Tänk dig att du vill förstå om självbetjäningsanvändare online har ett högre genomsnittligt ordervärde (AOV) än samtalsassisterade användare. Så här skapar du ett beräknat mätvärde för att besvara den här frågan:

Om du vill öppna verktyget för beräkning av mått använder du den översta navigeringen och klickar på → **Komponenter** → **Beräknade mått** → **+ Lägg till.** Du kan också klicka på **+-tecken** ovan **Mått** i panelen Komponenter.


![Beräkning 01](assets/calc01.png) ![Beräkning 02](assets/calc03.png) ![Beräkning 03](assets/calc02.png)

![Beräkning 04](assets/calc04.png)

*Beskrivningar nedan för UI-objekt*

När verktyget för beräkning av mått öppnas lägger du till och/eller gör följande:

**S.** Ett namn för det beräknade måttet. Det här namnet visas i listan med metriska komponenter, så skapa något som kommer att vara tydligt för dig själv och andra, som *Call Center AOV*.

**B.** En beskrivning av det beräknade måttet. Beskrivningen visas när användaren klickar på&#x200B;**i**&#39; bredvid mätvärdena i komponentlistan, så se till att det är informativt. För Call Center AOV kan vi till exempel lägga till *Beräknar AOV för beställningar via Call Center*.

**C.** Måttformatet: Välj decimal, tid, procent eller valuta och lägg till decimaler och polaritet. Här väljer vi *Valuta för Format, 0 för antal decimaler och* ⬆ *Bra (grönt) för polaritet.*

**D**. Om du använder taggar, som gör att du kan använda ämnen och snabbt hitta beräknade värden, lägger du till de taggar som gäller här. Vi har lagt till *AOV* och *Call Center* -taggar.

**E.** Det här avsnittet är till för visning - när du bygger upp det beräknade måttet i avsnitt F visas formeln här.

**F.** Här drar och släpper du dimensionerna (H), måtten (I) eller segmenten (J) för att skapa det beräknade mätvärdet samt operatorerna för formeln. För varje mätvärde kan du ändra måtttyp (standard/summa) och attribueringsmodell om du klickar på kodhjulet. *Vi drar och släpper Call Center Revenue, och därefter drar vi*‡ ￼*. Vi godkänner standardmåtttypen och attribueringsmodellen.*

**G**. Använd den här **+Lägg till** möjlighet att lägga till ytterligare villkor eller statiska tal, som vi inte behöver här.

**K.** Och slutligen, när du bygger din beräkning, kan du förhandsgranska de senaste 90 dagarnas data här.

Nu när vi har byggt Call Center AOV behöver vi också ett beräknat mått för AOV online. Vi skulle göra detta enligt samma steg som beskrivs ovan.

Sedan kan vi bygga ett tredje beräknat mätresultat, antingen med Calculated Metrics Builder eller direkt från frihandsregistret, för att jämföra Call Center och AOV online, så vi får något sådant:

![Beräkning 05](assets/calc05.png)

I vårt exempel ser vi en avsevärd förbättring när kunderna använder callcenter för att hjälpa dem att göra ett köp. Dessa data kan sedan informera våra beslut om hur kunderna kan få hjälp med sina inköp genom exempelvis popup-erbjudanden eller andra guidade upplevelser.

## Använda segment i beräknade värden

Nu ska vi titta på hur vi kan använda segment i beräknade mätvärden för att få mer kunskap om kundbeteende, preferenser och motiv. Med segment och beräknade värden kan vi lära oss tillräckligt mycket om kunderna för att förbättra deras upplevelse, öka intäkterna och förbättra kundnöjdheten och kundlojaliteten.

Vi vet redan från AOV-exemplen att inköp hos kundtjänst vanligtvis har ett högre AOV. Andra mätvärden talar dock om för oss att de flesta användare inte använder callcenter för inköp.

Vilka kategorier av återförsäljare - och användarsökvägar genom dessa kategorier - ger det högsta AOV?  Vi kan ta reda på det genom att kombinera segment med beräknade värden.

För att göra det måste vi först skapa en besöksnivå *include* och *exclude* segment för varje produktkategori. Inkludera eller exkludera bestäms genom att klicka på **Alternativ** i behållarens högra hörn. Standardvärdet är Inkludera.

![Beräkning 06](assets/calc06.png) ![Beräkning 07](assets/calc07.png)

När vi väl har skapat dessa segment kan vi skapa en beräknad mätmetod som ger dig svaret på din fråga. Vi öppnar Calculated Metrics Builder och gör följande:

1. Sök efter de nya segmenten och dra och släpp dem som du vill använda i det grå området högst upp i **Definition** box. Om vi t.ex. vill skapa ett AOV för användare som besökte både Kvinna- och Män-kategorierna, men inte Kid:n, kan vi dra och släppa dessa tre segment till det området: *Inkludera kvinnors*, *Inkludera mäns* och *Exkludera barnens*. Vi kallar det *stapla segment*.

   ![Beräkning 09](assets/calc09.png) ![Beräkning 08](assets/calc08.png)

1. Sedan drar och släpper vi **Online-intäkt** mätvärden i samma behållare, och sedan **Onlinebeställningar**. Eftersom behållare fungerar som matematiska uttryck för att bestämma ordningen på operationer, bearbetas objekt i behållare före efterföljande processer, även om det inte finns flera behållare eller processer i den här beräkningen.
1. Vi ändrar operatorn mellan de två mätvärdena till division ( max).
1. Vi väljer **Valuta** som formatet, **0** decimaler, och **UPP** för polaritet.
1. Namnge det beräknade måttet och ange en beskrivning.
1. Spara.

När vi är klara ser våra beräknade mätvärden ut så här:

![Beräkning 10](assets/calc10.png)

När vi har skapat beräknade mätvärden med skiktade segment för varje kombination av besökarens kategoriresa och tagit en titt på data, titta på vad vi lär oss! Användare som besöker både kvinnor och män under besöket har det högsta AOV-värdet, och jämfört med besökare i en enda kategori är lyften betydande:

![Beräkning 11](assets/calc11.png) ![Beräkning 12](assets/calc12.png)

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

1. **Kontrollera formelsyntaxen.** Kontrollera att formelsyntaxen är korrekt och att den följer Adobe Analytics-syntaxen för att vara säker på att du får meningsfull information.
1. **Verifiera åtgärdsordningen.** Använd behållarna försiktigt och placera materialet i rätt matematisk ordning.
1. **Dubbelräkna inte data**. Du kan undvika dubbelräkning genom att se till att formeln som används i det beräknade måttet inte räknar samma data flera gånger. Detta uppnås ofta genom att man kombinerar *Inkludera* och *Exkludera* villkor i det beräknade mätvärdet eller genom användning av segment.
1. **Kontrollera tidsprecision.** Se till att det beräknade måttet har samma tidsgranularitet som källmåtten som används i formeln.
1. **Använd korrekta data:** Du får bara värdefulla resultat om du använder korrekta och tillförlitliga data i beräkningen.

## Metodtips för anpassade segment

När du skapar segment i Adobe Analytics bör du tänka på följande:

1. **Gör det enkelt.** Undvik att komplicera segmentet för mycket. Förvara det så enkelt som möjligt och använd endast de villkor som är nödvändiga för att säkerställa noggrannheten.
1. **Använd rätt behållartyper**. Använd rätt behållartyp - besökare, besök eller tryck - i segmentdefinitionen för att undvika felaktiga resultat.
1. **Dubbelräkna inte data**. Precis som med beräknade värden kan du se till att segmentet inte räknar samma data flera gånger. Det kan vara till hjälp att inkludera och exkludera behållare.
   1. När en inkluderingsbehållare används *inkluderar* *allt innehåll i besöket* om en träff matchar villkoret inom besöket.
   1. När en exkluderingsbehållare används är det *utelämnar allt innehåll i besöket* om en träff matchar villkoret inom besöket.
1. **Kapsla behållare korrekt**. Bestäm vilka data som ska inkluderas med den yttersta behållaren och tillämpa sedan kapslade regler på återstående data. När kapslade regler tillämpas fungerar segmentflödet som en tratt, och efterföljande regler gäller inte för träffar som den första regeln har exkluderat.
1. **Se till att dina data är aktuella.** Se till att använda korrekta och aktuella data i segmentdefinitionen för att få korrekta resultat.
1. **Testa segmentet.** Testa alltid segmentet för att kontrollera att det fungerar som det ska innan du släpper det till andra.
1. **Tänk på prestanda.** Segment kan göra rapportbearbetningen långsammare, så tänk på den effekten när du skapar dem.

## Viktiga uppgifter

Genom att kombinera segment och beräknade värden i Adobe Analytics kan ni få en mer robust och effektiv dataanalys. Genom att segmentera och dela upp era data och bygga upp beräkningar för jämförelse kan ni få djupare insikter i kundbeteenden som ni kan använda för att optimera era marknadsföringskampanjer och skapa skräddarsydda instrumentpaneler och rapporter. Tänk dock på att beräknade värden inte är tillgängliga inom alla områden av Adobe Analytics, och glöm inte att följa bästa praxis för att säkerställa att ni får korrekta och användbara data.


## Upphovsman

Det här dokumentet har skrivits av:

![Debbie Kern](assets/calc13.jpeg)

**Debbie Kern**, Senior Adobe Analytics Manager på Adswerve

![Adswerve](assets/calc14.png)
