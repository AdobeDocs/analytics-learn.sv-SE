---
title: Identifiera en analysspårningsserver och ett rapport-Suite-ID
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
source-git-commit: 42bf16df9585d1f41206b81bf509a72c10f1d7f2
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 2%

---

# Identifiera era analyser [!DNL tracking server] och [!UICONTROL report suite ID] {#how-to-identify-your-analytics-tracking-server-and-report-suites}

När du konfigurerar Adobe Analytics, eller refererar till det i andra Experience Cloud-lösningar, är det ofta praktiskt eller till och med nödvändigt att känna till den&quot;spårningsserver&quot; för Analytics som du använder, eller också &quot;[!UICONTROL report suite]&quot; som du skickar data till. I den här videon visas hur du hittar båda värdena, oavsett om du redan har implementerat Adobe Analytics eller inte.

>[!IMPORTANT]
>
>Den här artikeln och videon gäller en&quot;AppMeasurement&quot;-implementering av Adobe Analytics, och inte en implementering med Web SDK.

## Efter implementering {#after-implementation}

När du har implementerat Analytics på en webbplats kan du hitta [!DNL tracking server] och [!DNL report suite ID] direkt i spårningsfyren. The [!DNL tracking server] är värdnamnet i beacon, så det är lätt att hitta. The [!UICONTROL report suite] ID:n är en kommaavgränsad lista direkt efter &quot;/b/ss/&quot; i beacons sökvägsnamn.

Om du vill se fyndet och all annan information som kommer till Analytics och andra Experience Cloud-lösningar installerar du [&quot;Experience Cloud Debugger&quot; Chrome Extension](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=sv).

## Före implementering {#before-implementation}

**[!DNL Tracking server]** - Om du inte har börjat använda din Adobe Analytics-implementering ännu väljer du en underdomän för &quot;.sc.omtrdc.net&quot; [!DNL tracking server]. Låt oss till exempel säga att jag har en onlinebutik som heter&quot;Jim&#39;s Brims&quot;. Jag kan helt enkelt ställa in [!DNL tracking server] till:

jimsbrims.sc.omtrdc.net.

**[!UICONTROL Report suite]** - För att hitta en lista över [!UICONTROL report suites] som har skapats, logga in [!DNL Analytics] och gå till [!UICONTROL Admin] > [!UICONTROL Report Suites] i den översta menyn för att se en lista över [!UICONTROL report suites], inklusive deras ID och titel.

Se videon nedan för mer information.

>[!VIDEO](https://video.tv.adobe.com/v/26061/?quality=12&learn=on)
