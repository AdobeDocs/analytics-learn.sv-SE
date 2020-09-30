---
title: Använda Report Builder för att lära sig mer om Adobe Analytics API
description: Report Builder är något vi alla känner till och älskar. Och om jag sa att du kan använda det du vet om Report Builder för att förbättra din Adobe Analytics kompetens ännu mer? I den här videon ska vi gå igenom hur vi tar felsökningsbegäranden från Report Builder och använder dem för att lära oss hur du skapar egna API-frågor för Analytics.
feature: report builder
topics: null
audience: analyst
activity: use
doc-type: feature video
team: Technical Marketing
kt: 2345
translation-type: tm+mt
source-git-commit: 24ad92b0ccdf1112e3ed4a0968cd47db757598c3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Använda [!UICONTROL Report Builder] för att lära dig Adobe Analytics API {#using-report-builder-to-learn-the-adobe-analytics-api}

[!UICONTROL Report Builder] är något vi alla känner till och älskar. Och om jag sa att du kan använda det du vet om [!UICONTROL Report Builder] för att utveckla dina Adobe Analytics-kunskaper ännu mer? I den här videon går vi igenom hur du tar felsökningsbegäranden [!UICONTROL Report Builder] och använder dem för att lära dig hur du skapar egna [!DNL Analytics] API-frågor.

>[!VIDEO](https://video.tv.adobe.com/v/25442/?quality=12)

**UPPDATERA**: [!UICONTROL Report Builder] har uppdaterat hur data efterfrågas något. Du kan fortfarande använda metoden från den här videon, men informationen kommer att vara något annorlunda i en felsökare.

I en felsökare:

1 - Sök efter api5.omniture.com. Antalet kan variera mellan 1 och 5 beroende på ditt datacenter.

2 - Gå till [!UICONTROL Request] fliken

3 - Sök efter &#39;[!DNL Report.Queue]&#39; i begäran.

Det finns också en alternativ metod för att felsöka förfrågningar som den här, och den fungerar lika bra. Du kan aktivera [!UICONTROL Report Builder] loggning från [!UICONTROL Options] menyn och då registreras samma information som en felsökare. Loggar finns under [!UICONTROL Documents] > [!UICONTROL ReportBuilderLogs]och ordnas per dag. Du kan söka efter &#39;Report.Queue&#39; i filen för att hitta dina förfrågningar. Loggarna kan även hjälpa till med felsökning av eventuella problem.

Mer information om den här funktionen finns i [dokumentationen](https://www.adobe.io/).
