---
title: Använd ett datalager för att ange Analytics-variabler i Experience Platform [!DNL tags]
description: Lär dig hur du använder ett datalager för att hämta analysdata och andra Experience Cloud-lösningar.
feature: Tags
topics: Development
role: Developer, Data Engineer
level: Beginner
kt: 1852
thumbnail: 25899.jpg
exl-id: 408ceb47-df05-4456-85bb-0ef2798a05a5
source-git-commit: a45667a8d7ccb46b9e33bd11a78fac9714a61df5
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 0%

---

# Använd ett datalager för att ange Analytics-variabler i Experience Platform [!DNL tags]

Använda ett datalager för [!DNL Analytics] och andra Experience Cloud-lösningar är bästa praxis. I den här videon får du lära dig hur du tar bort värden från datalagret och använder dem i Experience Platform [!DNL tags] för att fylla i variabler i Adobe Analytics.

## Datalager

A _datalager_ är ett ramverk med JavaScript-objekt som utvecklare lägger till på digitala webbsidor. Analyslösningar använder slutligen datalagret för att fylla i rapporter. Tagghanteringssystem, inklusive Experience Platform [!DNL tags]) är de mellanhänder som läser datalagret, mappar värdena till variabler och skickar dessa data till digitala upplevelselösningar.

Granska ytterligare information om datalager i [Experience Cloud dokumentation](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=en).

## datalager, Experience Platform [!DNL tags]och Adobe Analytics

1. Definiera eller identifiera en datalagerstandard som ska användas på webbplatsen.

   1. Placera datalagret så högt som möjligt i sidans head-avsnitt och före anropet till Experience Platform [!DNL tags]. Detta garanterar att värdena nås omedelbart av [!DNL tags] och av Adobe som behöver vara höga på sidan, som Adobe Target.

1. Fyll i data i datalagret.
1. I EXPERIENCE PLATFORM [!DNL tags], skapa &quot;[!UICONTROL data elements]&quot; som mappar datapunkter i datalagret. Dessa dataelement används i hela Experience Platform [!DNL tags] in [!UICONTROL rules] och [!UICONTROL extensions].
1. I antingen [!DNL Analytics] tilläggets avsnitt med globala variabler eller i en [!DNL Tags rule]tilldelar du värdena i [!UICONTROL data elements] till [!UICONTROL props], [!UICONTROL eVars], [!UICONTROL pageName]och andra [!DNL Analytics] variabler.
1. Utlös en signal som skickar data till [!DNL Analytics].

I följande video får du hjälp med processen.

>[!NOTE]
>
> Starta nu **[!DNL tags]**

>[!VIDEO](https://video.tv.adobe.com/v/25899/?quality=12&learn=on)

>[!NOTE]
>
>Det specifika datalager som används i den här videon kanske inte betraktas som&quot;bästa praxis&quot; för din organisation. Konceptet att använda ett datalager för att få viktiga data att komma till rätta med era digitala marknadsföringslösningar är bästa praxis.
