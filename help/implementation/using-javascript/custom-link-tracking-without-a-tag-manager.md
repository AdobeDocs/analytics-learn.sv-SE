---
title: Anpassad länkspårning utan tagghanterare
description: För många åtgärder på sidan ska spårning inte behandlas som en sidvy. I den här videon får du lära dig att koda en länkspårningsfyr till Analytics, om du inte använder en tagghanterare (som Experience Platform Launch). Se koden och lär dig ett viktigt tips.
feature: appmeasurement implementation
topics: null
audience: implementer
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1845
translation-type: tm+mt
source-git-commit: 8276828e9e759a1964ca5ea89bb1395e5e78b500
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Anpassad länkspårning utan tagghanterare {#custom-link-tracking-without-a-tag-manager}

För många åtgärder på sidan ska spårning inte behandlas som en sidvy. I den här videon får du lära dig att koda en länkspårningsfyr till Analytics, om du inte använder en tagghanterare (som Adobe [!DNL Experience Platform Launch]). Se koden och lär dig ett viktigt tips.

## Skicka en s.tl()-fyr {#sending-an-s-tl-beacon}

Det finns två funktioner som skickar data till Adobe Analytics:

1. s.t() - En&quot;track&quot;-fyr, som är en sidvyträff, som ökar sidvisningen för det angivna sidnamnet samt anger andra variabler
1. s.tl() - en&quot;spårlänk&quot;-fyr, som ofta kallas för en&quot;anpassad länk&quot;-träff/fyr, som inte ökar sidvisningar, och ignorerar variabeln pageName. Detta används vanligtvis för att spåra mindre åtgärder på sidan som inte läser in en ny sida/skärm, eller andra åtgärder som inte gör att en ny sida läses in.

>[!NOTE]
>
>I den här videon visar vi hur du kodar en anpassad länkträff när du INTE använder en tagghanterare som Adobe [!DNL Experience Platform Launch]. Vi rekommenderar att du använder [!DNL Experience Platform Launch]våra rekommendationer för implementering. Men om du behöver koda i en `s.tl()`kod gör du så här.

>[!VIDEO](https://video.tv.adobe.com/v/25832/?quality=12)

## Exempelkod {#sample-code}

Här är exempelkoden som används för den anpassade länken i videon:

```JavaScript
<a href="#" onclick="
    s.linkTrackVars='events,eVar2,prop2';
    s.linkTrackEvents=s.events='event2';
    s.eVar2='facebook share';
    s.prop2='facebook share';
    s.tl(this,'o','Social Share');
    s.manageVars('clearVars',s.linkTrackVars,1);">
    Click here to share on FaceBook
</a>
```

Mer information om anpassade länkar finns i [dokumentationen](https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html).