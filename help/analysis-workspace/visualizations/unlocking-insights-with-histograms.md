---
title: Lås upp insikter med histogram, bortom medelvärden i Analytics
description: Upptäck hur histogrammen påverkar analyser för att få insikter utöver medelvärdet.
feature: Visualizations
role: User
level: Experienced
doc-type: Article
last-substantial-update: 2023-08-18T00:00:00Z
jira: KT-13833
thumbnail: KT-13833.jpeg
source-git-commit: f38a35067bf95fe02200d1409e3e70c1ef28abb3
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 0%

---


# Lås upp insikter med histogram: bortom medelvärden i Analytics

_Upptäck hur histogrammen påverkar analyser för att få insikter utöver medelvärdet. Histogram avslöjar datamönster i kundbeteende, besökarbetsengagemang, tekniska prestanda och formulärfel, vilket ger djupare insikter och välgrundade beslut i Adobe Workspace._

Kom så hoppar vi in. Du bör använda [histogram](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/histogram.html). Jag ska förklara varför, men jag vill svara på din första fråga: Vad i världen är ett histogram? Jag fattar. Oftast när man ser en massa staplar som går upp, tror man att det är ett stolpdiagram. Ja, histogrammen ser likadana ut, men jag försäkrar er att de är annorlunda. I ett stapeldiagram jämförs saker, medan ett histogram visar hur ofta en variabel inträffade. Ta en titt. Här är ett stapeldiagram:

![Stapeldiagram 1](assets/bar-chart-1.png)

Vi har sex modeller, och vi kan jämföra intäkterna för varje modell. Vi ser att Johannesburgmodellen har störst intäkter, medan Berlin har minst.

Låt oss titta på ett histogram:

![Histogram 1](assets/histogram-1.png)

Längst ned på x-axeln har vi antalet enheter som köpts av varje kund. Det första fältet visar hur ofta en kund har köpt en enhet, det andra fältet visar hur många kunder som köpt två enheter och så vidare, till kunder som köpt tio eller fler enheter.

Hur är det här användbart? De flesta köper bara en enhet. Den minskar tills vi når fem enheter. Då avtar det igen tills vi når tio enheter. Detta pekar på det faktum att kunderna verkligen gillar att köpa i multipler av fem, och vi kanske borde erbjuda specialpriser eller förpackningar för att kunna utnyttja detta. Men det finns säkert många andra användningsområden också.

## Om besökarengagemang

Om webbplatsen eller appen bygger på upprepad trafik vill du veta hur många besökare som kommer tillbaka och hur ofta. Ett av de enklaste histogrammen du kan använda är att ta reda på hur många besökare som återvänder mer än en gång. När du spårar histogrammet över tiden kan du se förloppet, eftersom staplarna till höger blir högre och de till vänster blir kortare.

Du kanske vill behålla folk på webbplatsen, läsa artiklar. Ett histogram som visar hur många besökare som läser olika antal artiklar ger er insikt i hur hög engagemanget är. Varför är det till hjälp? Låt oss säga att de flesta besökare läser en artikel och går, men en del mycket engagerade besökare läser tre artiklar och går. Det är jättebra information! Nu vet du att du bör personalisera sidan på de första och tredje artiklarna som läses med målet att få besökarna att läsa en artikel till.

## Förstå kundbeteende

Produktägaren för patientjournaler på ett sjukhus bad mig om vissa data. Det fanns sex områden att välja mellan för att få tag i era journaler. Hon ville veta hur många människor som klickade på mer än en. Jag skapade ett histogram som visade hur många besökare som klickade på alternativen 1, 2, 3, 4, 5 eller 6. Det kan tyckas överdrivet, men över hälften av besökarna klickade på minst två alternativ, och hela 3,2 % av besökarna klickade på alla sex. Med histogrammet framför sig gav hon sig in på handling, omstrukturerade sin färdplan och förenklade alternativen ner till två. Detta gjorde patientens upplevelse mycket enklare.

## Tekniska prestanda

Om du skapar ett histogram för hur många besökare som upplever hur många tekniska fel som finns, kan du få en bra förståelse för hur webbplatsen fungerar tekniskt. Många besökare som råkar ut för många tekniska fel är ett tecken på att börja prioritera dessa tekniska korrigeringar.

## Förstå formulärprestanda

Felmeddelanden i ett formulär är något helt annat. Det är besökarfel, inte fel från din sida. Men du kan dra nytta av ett histogram som visar hur många besökare som upplever hur många fel som inträffar. Om du ser ett histogram som anger att många besökare har många fel, är det inte säkert att det är deras fel. Detta är en bra indikation på att formuläret har dåligt namngivna fält, otydliga instruktioner eller kanske en design som döljer obligatoriska fält.

## Varför inte ett beräknat mått?

Du kan fråga, hur skiljer det sig från att bara ha ett beräknat mått? Jag ser bra ut med beräknade mätvärden. Jag tycker att de är oumbärliga verktyg för att förstå hur webbplatsen fungerar. Problemet med många av användningsexemplen som jag har listat är att ett genomsnitt kan visa hur stort problemet är men dölja omfattningen av det. Låt oss gå igenom hur histogrammen ger dig ytterligare information om några av användningsområdena ovan:

- Besökarengagemang - Om du i genomsnitt har läst 1.2 är det ganska tydligt att du personaliserar den första artikeln. Du kommer att missa att det finns en annan stor grupp som avslutas efter att ha läst den tredje artikeln, vilket är vad histogrammet gör uppenbart.

  ![Histogram 2](assets/histogram-2.png)

- Tekniska fel - Om du såg i genomsnitt 8,7 fel per besökare skulle du veta att du hade ett problem. Histogrammet skulle kunna visa att 97 % av besökarna upplever ett eller färre fel, men en handfull av avvikelser ökar genomsnittet. Då kanske du bestämmer dig för att det inte är värt besväret att ägna mycket tid åt att förbättra upplevelsen för den lilla gruppen av avvikelser.

  ![Histogram 3](assets/histogram-3.png)

- Formulärfel - Om du har i genomsnitt 3,6 felmeddelanden per besökare är det en indikator på ett problem. Du kan ha samma avvikande problem som tekniska fel, men det finns också insikter du kan få genom att se en spik i histogrammet vid ett visst antal fel. En stor spike på ett fel? Detta kan vara ett vanligt problem som alla besökare upplever eller så har de kanske ett annat fel en gång. En jättepinke vid tre fel? Ah, nu är det intressant. Om detta leder till en utredning som visar att det är samma tre fel, har du nollställt data som ger dig en förståelse för besökarna och hjälper dig att åtgärda det som troligen är en grupp av relaterade problem.

  ![Histogram 4](assets/histogram-4.png)

Som du ser har histogrammen inte bara sina egna användningar, utan de fördjupar också den insikt du får av ett genomsnitt. De är färdiga visualiseringar i Adobe Analytics och enkla att skapa. Förhoppningsvis är dessa användningsexempel till hjälp för dig eller inspirerar till något. Glad visualisering!

## Upphovsman

Det här dokumentet har skrivits av:

![Gitai Ben-Ammi](assets/gitai-headshot.png)

**Gitai Ben-Ammi**, rektor konsult på Concentrix Catalyst

Adobe Analytics Champion
