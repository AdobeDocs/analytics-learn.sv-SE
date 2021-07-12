---
title: Spåra åtgärder (AKA Custom Links) i en mobilapp med Experience Platform SDK
description: 'Åtgärder är händelser som inträffar i din mobilapp. I den här videon får du lära dig hur du använder API:t trackAction för att spåra och mäta en åtgärd. '
feature: Mobile SDK
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2563
topic: Mobil
role: Developer, Data Engineer
level: Experienced
exl-id: 541c51b8-638e-43b4-90ac-0ce94290a141
source-git-commit: 32424f3f2b05952fe4df9ea91dcbe51684cee905
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# Spåra åtgärder (AKA Custom Links) i en mobilapp med Experience Platform SDK {#tracking-actions-aka-custom-links-in-a-mobile-app-with-the-experience-platform-sdk}

Åtgärder är händelser som inträffar i din mobilapp. I den här videon får du lära dig hur du använder API:t trackAction för att spåra och mäta en åtgärd.

>[!VIDEO](https://video.tv.adobe.com/v/26268/?quality=12)

Det här är det API som du bör använda för att spåra alla åtgärder som inte är skärmladdade på webbplatsen. Om skärmen kommer upp använder du trackState, som aktiverar en sidvisningseffekt. I annat fall använder du trackAction för att skicka in variabler som är associerade med den åtgärd som utförs.

Dessa data kommer in som `contextData`, vilket även innebär att du måste använda [!UICONTROL Processing Rules] för att ta mobildata från dessa `contextData`-variabler och mappa dem till [!DNL eVars], [!DNL Props], händelser osv. i Adobe Analytics.

Mer information om trackAction finns i [dokumentationen](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/configuration-reference/mobile-core-api-reference).
