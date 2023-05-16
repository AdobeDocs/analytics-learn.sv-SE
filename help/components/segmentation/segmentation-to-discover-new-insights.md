---
title: Vänta nu bara på ett segment.. Använda segmentering för att hitta nya insikter i Analysis Workspace
description: Lär dig hur du använder segment i Adobe Analytics för att hitta nya insikter från Analysis Workspace visualiseringar och frihandstabeller.
feature: Segmentation
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2023-05-16T00:00:00Z
jira: KT-13268
thumbnail: KT-13268.jpeg
source-git-commit: b11a329ca3f5c676aea08c7037e5ee87003edfe6
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 1%

---


# Vänta nu bara på ett segment.. Använda segment för att hitta nya insikter i Analysis Workspace

Vare sig du är nybörjare eller proffs på Adobe Analytics kommer du att utnyttja segment en hel del i dina Analysis Workspace-projekt. Som [Adobe Experience League](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-overview.html?lang=en) &quot;Med segment kan du identifiera undergrupper av besökare baserat på egenskaper eller webbplatsinteraktioner.&quot; Det grundläggande resultatet av den här funktionen är att isolera grupper av användare, besök eller träffar på webbplatsen, men en analytiker som du själv kan bli kreativ med det här verktyget och hitta nya sätt att få insikter om webbplatsens aktivitet. Listan med möjliga alternativ är enorm, så tveka inte att försöka skapa en egen och dela den med andra på din organisation eller online i communityn som [Adobe Analytics Community](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community) på Experience League eller [#measure Slack](https://www.measure.chat/) community.

Om du behöver få en snabb genomgång av hur du skapar ett segment kan du läsa Experience League i dokumentationen om hur du använder [Segment Builder](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=en) i Analysis Workspace.

## Jämförelse och kontrast av segment

I Analysis Workspace kan du jämföra två segment med &quot;[Segmentjämförelse](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html?lang=en)&quot;. Segmentjämförelsen finns under Paneler i det vänstra navigeringsfältet:

![Avsn 01](assets/seg01.png)

Ibland behöver du dock inte ha en komplett jämförelsepanel för att kunna ge slutanvändarna insikter i hemnyckeln. Som tur är kan vissa funktioner också jämföras på en standardpanel.

The [Visualisering av Venndiagram](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/venn.html?lang=en) kan hjälpa dig att skapa en snabb jämförelse, så att du kan hovra och se de överlappande sessionerna, beställningarna, användarna osv. mellan 2 och 3 anpassade segment. Du kan också snabbt skapa segment genom att högerklicka på något av de överlappande avsnitten:

![Avsn 02](assets/s02.png)

Ibland finns den viktiga informationen inte i överlappande data, men de data som inte överlappar varandra. Ett snabbt sätt att visa detta är att skapa en kopia av ett segment och göra det till ett&quot;Uteslut&quot;-segment:

![Avsn 03](assets/s03.png)

Genom att stapla&quot;utelämna&quot; segment i det andra segmentet i jämförelsen kan du nu snabbt beräkna hur många besök som kommer till menysidan utan att också visa hemsidan i samma session:

![Avsn 04](assets/s04.png)

## Stack Attack

På samma sätt kan du skapa data som överlappar ett Venndiagram genom att helt enkelt stapla alla segment tillsammans. Det finns ingen gräns för hur många segment eller enskilda dimensioner du staplar. Om jag till exempel snabbt vill ta reda på vilka dagar i veckan min webbplats förra månaden hade ett besök på en mobiltelefon, närmare bestämt en Samsung Galaxy A52s, som såg min meny och närliggande sidor, men som INTE såg min hemsida, kan jag snabbt bygga den på följande sätt:

![Avsn 05](assets/s05.png)

Men ännu bättre är att när jag hittar den perfekta delmängden av min användare eller besök basen kan jag välja alla dessa värden, högerklicka och skapa ett segment direkt:

![Avsn 06](assets/s06.png)

![Avsn 07](assets/s07.png)

![Avsn 08](assets/s08.png)

Det är mycket kraft i ett segment.

## Ett segment med siffror för ett antal segment

Många användare tittar ofta på nominella värden, ordvärden eller intervallvärden när de skapar segment - t.ex. en besökt sida, ett stort antal användare eller antalet besök en användare har gjort tidigare. Men ni kan också använda kvotdata när ni skapar ett segment genom att bygga upp dessa värden, oavsett om de är standardmått, standardvärden eller anpassade variabler och mätvärden för organisationen.

Exempel: Den tid som används på sidan eller den tid som spenderats per besök har fördefinierade grupper:

![Avsn 09](assets/s09.png)

Det kanske inte alltid passar organisationens behov - de flesta av webbplatsens besök är kortare än 10 minuter. Du kan använda detaljmätning för att skapa bucket med olika storlek. Här följer en som tittar på besök som varar mellan 1 minut, 1 sekund och 1 minut, 30 sekunder:

![Avsn 10](assets/s10.png)

När jag väl har skapat programmet kan jag börja titta på mina besök, beställningar och andra evenemang från de olika tidsgrupper jag har anpassat:

![Avsn 11](assets/s11.png)

Du kan till och med börja undersöka hur nyckeltal (KPI:er) ändras beroende på hur mycket tid en användare tillbringar, hur många sidor han/hon träffar på ett besök, hur många gånger han/hon har besökt ett besök tidigare eller vilket annat numeriskt värde som helst - så att du i princip kan se ett mätvärde som en faktor för ett annat mätresultat:

![Avsn 12](assets/s12.png)

Möjligheterna att använda segment för att hitta nya insikter är oändliga! Detta är bara en utgångspunkt. Prova några få själv och låt communityn veta vad du upplever: [Adobe Analytics Community](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community) på Experience League eller [#measure Slack](https://www.measure.chat/) community.

Glad segmentering!

## Upphovsman

Det här dokumentet har skrivits av:

![Dan Cummings](assets/seg13.png)

**Dan Cummings**, Sr. Product Engineering Analytics Manager på McDonald&#39;s Corporation

Adobe Analytics Champion

