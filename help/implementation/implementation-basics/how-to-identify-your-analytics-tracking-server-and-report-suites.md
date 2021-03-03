---
title: Identifiera er analysspårningsserver och rapportsviter
description: När du konfigurerar Adobe Analytics, eller refererar till det i andra Experience Cloud-lösningar, är det ofta praktiskt eller till och med nödvändigt att känna till den analysserver som du använder, eller den rapportsvit som du skickar data till. I den här videon visas hur du hittar båda värdena, oavsett om du redan har implementerat Adobe Analytics eller inte.
feature: Implementeringsgrunder
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2358
role: '"Utvecklare, datatekniker"'
level: Nybörjare
translation-type: tm+mt
source-git-commit: f3b3fa7d91b0cb21005b57768ca23ed6700fcc03
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 2%

---


# Identifiera din analys [!DNL Tracking Server] och [!UICONTROL Report Suites] {#how-to-identify-your-analytics-tracking-server-and-report-suites}

När du konfigurerar Adobe Analytics, eller när du refererar till det i andra Experience Cloud-lösningar, är det ofta praktiskt eller till och med nödvändigt att känna till [!DNL Analytics] &quot;[!DNL Tracking Server]&quot; som du använder, eller också &quot;[!UICONTROL Report Suite]&quot; som du skickar data till. I den här videon visas hur du hittar båda värdena, oavsett om du redan har implementerat Adobe Analytics eller inte.

## Efter implementering {#after-implementation}

När du har implementerat [!DNL Analytics] på en plats kan du hitta [!DNL tracking server] och [!DNL report suite ID] till höger i spårningsfunktionen. [!DNL tracking server] är värdnamnet i beacon, så det är lätt att hitta. ID:na för [!UICONTROL report suite] är en kommaavgränsad lista direkt efter &quot;/b/ss/&quot; i sökvägen till beacon.

Om du vill visa fyren, samt all annan information som kommer till [!DNL Analytics] och andra Experience Cloud-lösningar, installerar du Chrome-tillägget [&quot;Experience Cloud Debugger&quot;](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=sv).

## Före implementering {#before-implementation}

**[!DNL Tracking Server]** - Om du inte har börjat använda din Adobe Analytics-implementering ännu väljer du en underdomän för &quot;.sc.omtrdc.net&quot;  [!DNL tracking server]. Låt oss till exempel säga att jag har en onlinebutik som heter&quot;Jim’s Brims&quot;. Jag kan helt enkelt ställa in [!DNL tracking server] på:

&quot;jimsbrims.sc.omtrdc.net&quot;.

**[!UICONTROL Report Suite]** - Om du vill hitta en lista över  [!UICONTROL report suites] de objekt du har skapat loggar du in  [!DNL Analytics] och går till  [!UICONTROL Admin] >  [!UICONTROL Report Suites] på den översta menyn för att visa en lista med  [!UICONTROL report suites]namn och ID.

Se videon nedan för mer information.

>[!VIDEO](https://video.tv.adobe.com/v/26061/?quality=12)
