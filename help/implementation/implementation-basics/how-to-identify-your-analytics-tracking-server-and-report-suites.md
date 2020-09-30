---
title: Identifiera er analysspårningsserver och rapportsviter
description: När du konfigurerar Adobe Analytics, eller refererar till det i andra Experience Cloud-lösningar, är det ofta praktiskt eller till och med nödvändigt att känna till den analysserver som du använder, eller den rapportsvit som du skickar data till. I den här videon visas hur du hittar båda värdena, oavsett om du redan har implementerat Adobe Analytics eller inte.
feature: implementation basics
topics: null
audience: implementer
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2358
translation-type: tm+mt
source-git-commit: 60f4ce4f563a990576b3331b01cd87c29d424f43
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Identifiera era analyser [!DNL Tracking Server] och [!UICONTROL Report Suites] {#how-to-identify-your-analytics-tracking-server-and-report-suites}

När du konfigurerar Adobe Analytics, eller när du refererar till det i andra Experience Cloud-lösningar, är det ofta praktiskt eller till och med nödvändigt att känna till [!DNL Analytics] &quot;[!DNL Tracking Server]&quot; som du använder eller&quot;[!UICONTROL Report Suite]&quot; som du skickar data till. I den här videon visas hur du hittar båda värdena, oavsett om du redan har implementerat Adobe Analytics eller inte.

## Efter implementering {#after-implementation}

När du har implementerat [!DNL Analytics] en webbplats kan du hitta [!DNL tracking server] och [!DNL report suite ID] höger i spårningsfunktionen. Det [!DNL tracking server] är värdnamnet i beacon, så det är lätt att hitta. ID: [!UICONTROL report suite] en är en kommaavgränsad lista direkt efter &quot;/b/ss/&quot; i beacons sökvägsnamn.

Installera Chrome-tillägget [!DNL Analytics] &quot;Experience Cloud Debugger&quot; om du vill se beacon, all annan information som kommer till [och andra Experience Cloud-lösningar](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=sv).

## Före implementering {#before-implementation}

**[!DNL Tracking Server]** - Om du inte har börjat använda din Adobe Analytics-implementering ännu väljer du en underdomän för &quot;.sc.omtrdc.net&quot; [!DNL tracking server]. Låt oss till exempel säga att jag har en onlinebutik som heter&quot;Jim’s Brims&quot;. Jag kan helt enkelt ställa in min [!DNL tracking server] till:

&quot;jimsbrims.sc.omtrdc.net&quot;.

**[!UICONTROL Report Suite]** - Om du vill hitta en lista över dina [!UICONTROL report suites] skapelser loggar du in [!DNL Analytics] och går till [!UICONTROL Admin] > [!UICONTROL Report Suites] på den översta menyn för att visa en lista med [!UICONTROL report suites], inklusive deras ID och titel.

Se videon nedan för mer information.

>[!VIDEO](https://video.tv.adobe.com/v/26061/?quality=12)
