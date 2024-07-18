---
title: Använd en global rapportsvit
description: Ett enda globalt rapportpaket kan hjälpa dig på många sätt och förenkla implementeringen.
feature: Implementation Basics
topic: Administration
role: Admin
level: Beginner
doc-type: article
thumbnail: 10536.jpg
kt: 10536
exl-id: 490addfd-b810-4f15-b065-e0e58048c882
source-git-commit: df00d4fb8cc5093903ed4628dfe12f152294123a
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 0%

---

# Använd en global rapportsvit

**VAD:** Det är frestande att skapa rapportsviter för var och en av dina webbplatser, men detta kan snabbt bli din värsta mardröm - både när det gäller att komplicera både din rapportering och implementeringen. Ett enda globalt rapportpaket kan hjälpa dig på många sätt och förenkla implementeringen.

**VARFÖR:** Det enda alternativet att skapa en global rapportsvit är att ha en enhetlig vy över dina digitala egenskaper och användarnas resor för varje egenskap. Om ni har en mobilapp och en webbplats bör ni alltid kombinera appdata och webbdata i en enda rapportserie för att dra nytta av enhetsövergripande resor och spåra dem som besöker båda egenskaperna som en enskild besökare jämfört med separata rapportsviter, där ni har en osammanhängande datauppsättning som visar 2 besökare - 1 till varje egendom - utan att kunna känna till förskjutningen.

Nedan följer några fördelar och nackdelar med att ha ett och samma rapportpaket som hjälper dig att väga olika alternativ:

* PROS:
   * Förmåga att enkelt förstå hela det digitala landskapet. Om du har implementerat dimensionen &quot;egenskaper&quot; (eVar) som det hänvisas till i andra tips blir det enkelt att få en enda vy över alla webbplatser och appar, trafik och konverteringar. Att ha en helhetsbild är avgörande för att förstå er verksamhet som helhet.
   * På samma sätt kan ni nu se hur användarna flödar över alla era resurser och förstå deras resa genom hela det digitala landskapet.
   * Enkel administrering. När du använder flera rapportsviter måste du ha kvar gränssnittet på flera ställen, samt flera taggningsdokument (eller ett mer komplicerat dokument). Att ha allt på ett ställe innebär att det bara finns ett ställe att göra uppdateringar på. Det gör det också mycket enklare att bevilja åtkomst.
   * Bättre användarvänlighet i gränssnittet. Om användarna bara har en plats att gå till behöver de inte tänka på vilken rapportsvit de ska välja. Tänk på att du inte kan använda flera rapportsviter på samma arbetsyta, och att flera av dem kan förvirra användarna.
   * Färre serversamtal = lägre kostnader. Om du ringer till flera rapportsviter ökar du kostnaderna. Om ni förenklar implementeringen håller ni också kostnaderna nere.
   * Man kan helt enkelt utnyttja VRS (Virtual Report Suites) för att bryta ut platsspecifika data i den globala rapportsviten och begränsa användarbehörigheterna baserat på ett VRS vid behov. När data har delats upp i enskilda rapportsviter kan du inte kavla upp dem, men om de redan ingår i en datamängd (global RS) är det enkelt att dela upp dem.
* KONS:
   * Om du har väldigt olika egenskaper där användarna inte klipper över från den ena till den andra och aldrig förväntas göra det, kanske du vill ha separata rapportsviter.
   * Om dina egenskaper har mycket olika taggnings- och rapporteringsbehov kan det vara bra att skapa separata rapportsviter för variabel effektivitet. Separata rapportsviter ger större flexibilitet när det gäller att använda anpassade variabler (fler eVars).
   * Uniques har överskridits: I Adobe Analytics-gränssnittet kan du bara se 500 000 unika värden inom en dimension under en given tidsperiod. När du har överskridit detta grupperas värdena som &#39;uniques beyond&#39; eller &#39;low Trafiken&#39; i gränssnittet. Dessa värden är fortfarande tillgängliga för dig på backend-sidan (dvs. Data Warehouse, dataflöden), men kan inte visas i gränssnittet. Om du har mycket detaljerade data (som användar-ID, PSN osv.) är det enkelt att nå den här nivån. Separata rapportsviter kan vara till hjälp i det här problemet.

**HUR:** Det är enkelt och enkelt att börja med en ny AA-implementering och att använda en global rapportserie. Du behöver bara skapa den globala rapportsviten (en för Dev och en för Prod) i användargränssnittet för AA-administratörer och använda samma värden för rapportsvitens-ID (RSID) för alla dina egenskaper.

Att migrera från en strategi för flera taggar med ett unikt rapportpaket per egenskap kräver mer strategi och planering. Några av de saker du bör tänka på:

* Justera variablerna (dvs. eVar1 i egenskap A måste hämta samma datapunkt som eVar1 i egenskap B)
* Konsolidera eventuella bearbetningsregler, regler för marknadsföringskanaler, klassificeringar (SAINT och Rule Builder)
* Migrera alla dataflöden och datakällor
* Välja ett brytdatum och kommunicera detta med alla företagsanvändare

## Författare

Det här dokumentet skrevs tillsammans av:

![Christel Guidon](assets/Christel-Headshot-150.png)

Christel Guidon, Digital Analytics Platform Manager på NortonLifeLock
Adobe Analytics Champion

![Rachel Fenwick](assets/Rachel-Fenwick-150.png)

Rachel Fenwick, Senior Consultant på Adobe
