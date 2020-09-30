---
title: Använda ett datalager för att ange sidnamn och andra variabler i Adobe Analytics via Launch
description: Att använda ett datalager för Analytics och andra Experience Cloud-lösningar anses vara en bra metod. I den här videon får du se hur du tar bort dina värden från datalagret och använder dem i Launch för att fylla i variabler i Adobe Analytics.
feature: launch implementation
topics: null
audience: implementer
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1852
translation-type: tm+mt
source-git-commit: ee6c03cff5b051d9293d75965e9fd98f151d7fce
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Använda ett datalager för att ange sidnamn och andra variabler via [!DNL Experience Platform Launch] {#using-a-data-layer-to-set-page-name-and-other-variables-in-adobe-analytics-via-launch}

Att använda ett datalager för [!DNL Analytics] och andra Experience Cloud-lösningar anses vara en god vana. I den här videon får du se hur du tar bort dina värden från datalagret och använder dem i [!DNL Experience Platform Launch] för att fylla i variabler i Adobe Analytics.

## Datalager {#data-layers}

Det är en god vana att använda ett datalager när du arbetar med data på din webbplats och Adobe Experience Cloud lösningar, särskilt med Adobe Analytics. Ett _datalager_ är ett ramverk med JavaScript-objekt som utvecklare infogar på sidor. Datalagret kan användas av spårningsverktyg (inklusive tagghanteringssystem som [!DNL Experience Platform Launch]) för att fylla i rapporter. Mer information om datalager finns i dokumentationen [till](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-data-layer.html) Experience Cloud eller på [W3C-webbplatsen](https://www.w3.org/).

Se även bloggdatalagret [: Från Buzzword till Best Practice,](https://theblog.adobe.com/data-layers-buzzword-best-practice/)som ger dig bra information om datalager samt några exempel.

## Data Layers, [!DNL Experience Platform Launch]och Adobe Analytics (Oj?){#data-layers-launch-and-adobe-analytics-oh-my}

1. Skapa en datalagerstandard som du kan använda på din webbplats och som kan refereras till av [!DNL Experience Platform Launch].

   1. Placera datalagret så högt som möjligt i sidhuvudet, före anropet till [!DNL Experience Platform Launch]så att värdena kan användas direkt av [!DNL Launch]och av Adobe som behöver vara höga på sidan, som Adobe Target.

1. Fyll i data i datalagret.
1. I [!DNL Experience Platform Launch]skapar du&quot;[!UICONTROL data elements]&quot; som refererar till datapunkterna i datalagret och som kan användas genomgående [!DNL Experience Platform Launch] i [!UICONTROL rules], [!UICONTROL extensions]osv.
1. Använd [!UICONTROL data elements] i antingen [!DNL Analytics] tilläggets globala variabler eller i en regel för att tilldela värdena till [!UICONTROL props], [!UICONTROL eVars], [!UICONTROL pageName]eller andra [!DNL Analytics] variabler.
1. Utlös en fyr som skickar data till [!DNL Analytics].

I följande video får du hjälp med processen.

>[!VIDEO](https://video.tv.adobe.com/v/25899/?quality=12)
