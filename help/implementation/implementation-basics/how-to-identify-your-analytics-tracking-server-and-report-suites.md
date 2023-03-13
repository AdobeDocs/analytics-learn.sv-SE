---
title: Identifiera er analysspårningsserver och rapportsviter
description: När du konfigurerar Adobe Analytics, eller refererar till det i andra Experience Cloud-lösningar, är det ofta praktiskt eller till och med nödvändigt att känna till den analysserver som du använder, eller den rapportsvit som du skickar data till. I den här videon visas hur du hittar båda värdena, oavsett om du redan har implementerat Adobe Analytics eller inte.
feature: Implementation Basics
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2358
role: Developer, Data Engineer
level: Beginner
exl-id: 3925026f-69f1-4425-b3a9-6fef26375fed
source-git-commit: 32424f3f2b05952fe4df9ea91dcbe51684cee905
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 2%

---

# Identifiera era analyser [!DNL Tracking Server] och [!UICONTROL Report Suites] {#how-to-identify-your-analytics-tracking-server-and-report-suites}

När du skapar Adobe Analytics eller refererar till i andra Experience Cloud-lösningar är det ofta praktiskt eller till och med nödvändigt att känna till [!DNL Analytics] &quot;[!DNL Tracking Server]&quot; som du använder, eller också &quot;[!UICONTROL Report Suite]&quot; som du skickar data till. I den här videon visas hur du hittar båda värdena, oavsett om du redan har implementerat Adobe Analytics eller inte.

## Efter implementering {#after-implementation}

Efter implementering [!DNL Analytics] på en webbplats hittar du [!DNL tracking server] och [!DNL report suite ID] direkt i spårningsfyren. The [!DNL tracking server] är värdnamnet i beacon, så det är lätt att hitta. The [!UICONTROL report suite] ID:n är en kommaavgränsad lista direkt efter &quot;/b/ss/&quot; i beacons sökvägsnamn.

För att se fyren och all annan information som kommer till [!DNL Analytics] och andra Experience Cloud-lösningar kan du installera [&quot;Experience Cloud Debugger&quot; Chrome Extension](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=sv).

## Före implementering {#before-implementation}

**[!DNL Tracking Server]** - Om du inte har börjat använda din Adobe Analytics-implementering ännu väljer du en underdomän för &quot;.sc.omtrdc.net&quot; [!DNL tracking server]. Låt oss till exempel säga att jag har en onlinebutik som heter&quot;Jim’s Brims&quot;. Jag kan helt enkelt ställa in [!DNL tracking server] till:

&quot;jimsbrims.sc.omtrdc.net&quot;.

**[!UICONTROL Report Suite]** - För att hitta en lista över [!UICONTROL report suites] som har skapats, logga in [!DNL Analytics] och gå till [!UICONTROL Admin] > [!UICONTROL Report Suites] i den övre menyn för att se en lista över [!UICONTROL report suites], inklusive deras ID och titel.

Se videon nedan för mer information.

>[!VIDEO](https://video.tv.adobe.com/v/26061/?quality=12)
