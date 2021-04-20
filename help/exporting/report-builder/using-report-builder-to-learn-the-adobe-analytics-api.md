---
title: Använda Report Builder för att lära sig mer om Adobe Analytics API
description: Report Builder är något vi alla känner till och älskar. Och om jag sa att du kan använda det du vet om Report Builder för att förbättra din Adobe Analytics kompetens ännu mer? I den här videon ska vi gå igenom hur vi tar felsökningsbegäranden från Report Builder och använder dem för att lära oss hur du skapar egna API-frågor för Analytics.
feature: Report Builder
topics: null
activity: use
doc-type: feature video
team: Technical Marketing
kt: 2345
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: f3b3fa7d91b0cb21005b57768ca23ed6700fcc03
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---


# Lär dig Adobe Analytics API {#using-report-builder-to-learn-the-adobe-analytics-api} med [!UICONTROL Report Builder]

[!UICONTROL Report Builder] är något vi alla känner till och älskar. Och om jag sa att du skulle kunna använda det du vet om [!UICONTROL Report Builder] för att förbättra din Adobe Analytics-kompetens ännu mer? I den här videon går vi igenom hur du tar felsökningsbegäranden från [!UICONTROL Report Builder] och använder dem för att lära oss hur du skapar egna [!DNL Analytics] API-frågor.

>[!VIDEO](https://video.tv.adobe.com/v/25442/?quality=12)

**UPPDATERA**:  [!UICONTROL Report Builder] har uppdaterat hur data efterfrågas något. Du kan fortfarande använda metoden från den här videon, men informationen kommer att vara något annorlunda i en felsökare.

I en felsökare:

1 - Sök efter api5.omniture.com. Antalet kan variera mellan 1 och 5 beroende på ditt datacenter.

2 - Gå till fliken [!UICONTROL Request]

3 - Sök efter [!DNL Report.Queue] i begäran.

Det finns också en alternativ metod för att felsöka förfrågningar som den här, och den fungerar lika bra. Du kan aktivera [!UICONTROL Report Builder]-loggning från [!UICONTROL Options]-menyn och då registreras samma information som en felsökare gör. Loggar finns under [!UICONTROL Documents] > [!UICONTROL ReportBuilderLogs] och kommer att ordnas per dag. Du kan söka efter &#39;Report.Queue&#39; i filen för att hitta dina förfrågningar. Loggarna kan även hjälpa till med felsökning av eventuella problem.

Mer information om den här funktionen finns i [dokumentationen](https://www.adobe.io/).
