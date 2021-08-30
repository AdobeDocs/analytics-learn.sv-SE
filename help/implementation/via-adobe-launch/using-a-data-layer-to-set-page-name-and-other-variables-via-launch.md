---
title: Använda ett datalager för att ange sidnamn och andra variabler i Adobe Analytics via Launch
description: Att använda ett datalager för Analytics och andra Experience Cloud-lösningar anses vara en bra metod. I den här videon får du se hur du tar bort dina värden från datalagret och använder dem i Launch för att fylla i variabler i Adobe Analytics.
feature: Launch Implementation
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1852
role: Developer, Data Engineer
level: Beginner
exl-id: 408ceb47-df05-4456-85bb-0ef2798a05a5
source-git-commit: fe861dfd541c1b9cb3b233fa3f56d55054305fd9
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Använda ett datalager för att ange sidnamn och andra variabler via [!DNL Experience Platform Launch] {#using-a-data-layer-to-set-page-name-and-other-variables-in-adobe-analytics-via-launch}

Att använda ett datalager för [!DNL Analytics] och andra Experience Cloud-lösningar anses vara en god vana. I den här videon får du se hur du tar bort dina värden från datalagret och använder dem i [!DNL Experience Platform Launch] för att fylla i variabler i Adobe Analytics.

## Datalager {#data-layers}

Det är en god vana att använda ett datalager när du arbetar med data på din webbplats och Adobe Experience Cloud lösningar, särskilt med Adobe Analytics. Ett _datalager_ är ett ramverk med JavaScript-objekt som utvecklare infogar på sidor. Datalager kan användas med spårningsverktyg (inklusive tagghanteringssystem som [!DNL Experience Platform Launch]) för att fylla i rapporter. Mer information om datalager finns i [dokumentationen för Experience Cloud](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=en) eller på [W3C-webbplatsen](https://www.w3.org/).

Se även bloggen [Datalager: Från Buzzword till Best Practice,](https://theblog.adobe.com/data-layers-buzzword-best-practice/), som ger dig bra information om datalager, samt några exempel.

## Datalager, [!DNL Experience Platform Launch] och Adobe Analytics (Oj?){#data-layers-launch-and-adobe-analytics-oh-my}

1. Skapa en datalagerstandard som ska användas på din webbplats, som kan refereras av [!DNL Experience Platform Launch].

   1. Placera det här datalagret så högt som möjligt i sidhuvudet, före anropet till [!DNL Experience Platform Launch], så att värdena kan användas omedelbart av [!DNL Launch], och av Adobe-lösningar som måste vara höga på sidan, som Adobe Target.

1. Fyll i data i datalagret.
1. I [!DNL Experience Platform Launch] skapar du [!UICONTROL data elements] som refererar till datapunkterna i datalagret och som kan användas i hela [!DNL Experience Platform Launch] i [!UICONTROL rules], [!UICONTROL extensions] och så vidare.
1. Använd [!UICONTROL data elements] i antingen de globala variablerna för tillägget [!DNL Analytics] eller i en regel, om du tilldelar värdena till [!UICONTROL props], [!UICONTROL eVars], [!UICONTROL pageName] eller andra [!DNL Analytics]-variabler.
1. Utlös en fyr som skickar data till [!DNL Analytics].

I följande video får du hjälp med processen.

>[!VIDEO](https://video.tv.adobe.com/v/25899/?quality=12)
