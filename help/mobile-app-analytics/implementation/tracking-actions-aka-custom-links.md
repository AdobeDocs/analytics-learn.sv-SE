---
title: Spåra åtgärder (AKA Custom Links) i en mobilapp med Experience Platform SDK
description: Åtgärder är händelser som inträffar i din mobilapp. I den här videon får du lära dig hur du använder API:t trackAction för att spåra och mäta en åtgärd.
feature: Mobile SDK
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2563
topic: Mobile
role: Developer, Data Engineer
level: Experienced
exl-id: 541c51b8-638e-43b4-90ac-0ce94290a141
source-git-commit: 4d467928756950074620388645523021b21fb0d5
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---

# Spåra åtgärder (AKA Custom Links) i en mobilapp med Experience Platform SDK {#tracking-actions-aka-custom-links-in-a-mobile-app-with-the-experience-platform-sdk}

Åtgärder är händelser som inträffar i din mobilapp. I den här videon får du lära dig hur du använder API:t trackAction för att spåra och mäta en åtgärd.

>[!VIDEO](https://video.tv.adobe.com/v/26268/?quality=12&learn=on)

Det här är det API som du bör använda för att spåra alla åtgärder som inte är skärmladdade på webbplatsen. Om skärmen kommer upp använder du trackState, som aktiverar en sidvisningseffekt. I annat fall använder du trackAction för att skicka in variabler som är associerade med den åtgärd som utförs.

Dessa data kommer in som `contextData`, vilket även innebär att du då måste använda [!UICONTROL Processing Rules] att hämta in mobildata från dessa `contextData` variabler och mappa dem till [!DNL eVars], [!DNL Props], händelser osv. i Adobe Analytics.

Mer information om trackAction finns i [dokumentation](https://developer.adobe.com/client-sdks/documentation/getting-started/track-events/#track-user-actions-for-adobe-analytics).
