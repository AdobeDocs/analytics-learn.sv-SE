---
title: Använd ett datalager för att ställa in Analytics-variabler via Taggar
description: Lär dig hur du använder ett datalager för att hämta analysdata och andra Experience Cloud-lösningar.
feature: Launch Implementation
role: Developer, Data Engineer
level: Beginner
kt: 1852
thumbnail: 25899.jpg
exl-id: 408ceb47-df05-4456-85bb-0ef2798a05a5
source-git-commit: 8fc641743bc9e07b838a22ca64ccc15344d52764
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---

# Använd ett datalager för att ställa in Analytics-variabler via [!DNL Tags] {#use-a-data-layer-to-set-analytics-variables-in-adobe-analytics-via-tags}

Använda ett datalager för [!DNL Analytics] och andra Experience Cloud-lösningar är bästa praxis. I den här videon får du lära dig hur du tar bort värden från datalagret och använder dem i [!DNL Experience Platform Tags] för att fylla i variabler i Adobe Analytics.

## Datalager {#data-layers}

A _datalager_ är ett ramverk med JavaScript-objekt som utvecklare lägger till på digitala webbsidor. Analyslösningar använder slutligen datalagret för att fylla i rapporter. Tagghanteringssystem, inklusive [!DNL Experience Platform Tags]) är de mellanhänder som läser datalagret, mappar värdena till variabler och skickar dessa data till digitala upplevelselösningar.

Granska ytterligare information om datalager i [Experience Cloud dokumentation](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=en) och bloggen [Datalager: Från Buzzword till Best Practice](https://blog.adobe.com/en/2014/03/13/data-layers-buzzword-best-practice).

## datalager, [!DNL Experience Platform Tags]och Adobe Analytics{#data-layers-launch-and-adobe-analytics}

1. Definiera eller identifiera en datalagerstandard som ska användas på webbplatsen.

   1. Placera datalagret så högt som möjligt i sidans head-avsnitt och före anropet till [!DNL Experience Platform Tags]. Detta garanterar att värdena nås omedelbart av [!DNL Tags] och av Adobe som behöver vara höga på sidan, som Adobe Target.

1. Fyll i data i datalagret.
1. I [!DNL Experience Platform Tags], skapa &quot;[!UICONTROL data elements]&quot; som mappar datapunkter i datalagret. Dessa dataelement används genomgående [!DNL Experience Platform Tags] in [!UICONTROL rules] och [!UICONTROL extensions].
1. I antingen [!DNL Analytics] tilläggets avsnitt med globala variabler eller i en [!DNL Tags rule]tilldelar du värdena i [!UICONTROL data elements] till [!UICONTROL props], [!UICONTROL eVars], [!UICONTROL pageName]och andra [!DNL Analytics] variabler.
1. Utlös en signal som skickar data till [!DNL Analytics].

I följande video får du hjälp med processen.

>[!VIDEO](https://video.tv.adobe.com/v/25899/?quality=12&learn=on)

>[!NOTE]
>
>Det specifika datalager som används i den här videon kanske inte betraktas som&quot;bästa praxis&quot; för din organisation. Konceptet att använda ett datalager för att få viktiga data att komma till rätta med era digitala marknadsföringslösningar är bästa praxis.