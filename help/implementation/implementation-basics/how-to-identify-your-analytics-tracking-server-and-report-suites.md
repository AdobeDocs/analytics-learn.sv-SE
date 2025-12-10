---
title: Identifiera en analysspårningsserver och ett rapport-Suite-ID
description: När du konfigurerar Adobe Analytics, eller refererar till det i andra Experience Cloud-lösningar, är det ofta praktiskt eller till och med nödvändigt att känna till den Analytics "Tracking Server" som du använder, eller också den "Report Suite" som du skickar data till. I den här videon visas hur du hittar båda värdena, oavsett om du redan har implementerat Adobe Analytics eller inte.
feature: Implementation Basics
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2358
role: Developer
level: Beginner
exl-id: 3925026f-69f1-4425-b3a9-6fef26375fed
source-git-commit: 474e68e2937c82efa459b6ed8048a4abd2753285
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 0%

---

# Identifiera dina analyser [!DNL tracking server] och [!UICONTROL report suite ID] {#how-to-identify-your-analytics-tracking-server-and-report-suites}

När du konfigurerar Adobe Analytics, eller när du refererar till det i andra Experience Cloud-lösningar, är det ofta praktiskt eller till och med nödvändigt att känna till den &quot;spårningsserver&quot; för Analytics som du använder, eller också den &quot;[!UICONTROL report suite]&quot; som du skickar data till. I den här videon visas hur du hittar båda värdena, oavsett om du redan har implementerat Adobe Analytics eller inte.

>[!IMPORTANT]
>
>Den här artikeln och videon gäller en&quot;AppMeasurement&quot;-implementering av Adobe Analytics, och inte en implementering som använder Web SDK.

## Efter implementering {#after-implementation}

När du har implementerat Analytics på en webbplats kan du hitta [!DNL tracking server] och [!DNL report suite ID] direkt i spårningsfunktionen. [!DNL tracking server] är värdnamnet i beacon, så det är lätt att hitta. [!UICONTROL report suite]-ID:n är en kommaavgränsad lista precis efter /b/ss/ i sökvägen till beacon.

Installera Chrome-tillägget [ för ](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=sv)&quot;Experience Cloud Debugger&quot; om du vill se fyren, samt all annan information som kommer till Analytics och andra Experience Cloud-lösningar.

## Före implementering {#before-implementation}

**[!DNL Tracking server]** - Om du inte har startat med din Adobe Analytics-implementering ännu väljer du en underdomän för &quot;.sc.omtrdc.net&quot; [!DNL tracking server]. Låt oss till exempel säga att jag har en onlinebutik som heter&quot;Jim&#39;s Brims&quot;. Jag kan helt enkelt ställa in min [!DNL tracking server] på:

jimsbrims.sc.omtrdc.net.

**[!UICONTROL Report suite]** - Om du vill hitta en lista över dina [!UICONTROL report suites] som har skapats loggar du in på [!DNL Analytics] och går till [!UICONTROL Admin] > [!UICONTROL Report Suites] på den översta menyn för att visa en lista över [!UICONTROL report suites], inklusive deras ID och titel.

Se videon nedan för mer information.

>[!VIDEO](https://video.tv.adobe.com/v/26061/?quality=12&learn=on)
