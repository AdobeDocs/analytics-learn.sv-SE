---
title: Använda Report Builder för att lära sig mer om Adobe Analytics API
description: Report Builder är något vi alla känner till och älskar. Och om jag sa att du kan använda det du vet om Report Builder för att förbättra din Adobe Analytics kompetens ännu mer? I den här videon ska vi gå igenom hur vi kan ta felsökningsförfrågningar från Report Builder och använda dem för att lära oss hur du skapar egna API-frågor för Analytics.
feature: Report Builder
topics: null
activity: use
doc-type: feature video
team: Technical Marketing
kt: 2345
role: User
level: Intermediate
exl-id: 8b8e0dac-2498-4fba-ba4b-585b309ae1fd
source-git-commit: 8fc641743bc9e07b838a22ca64ccc15344d52764
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Använda [!UICONTROL Report Builder] för att lära dig Adobe Analytics API {#using-report-builder-to-learn-the-adobe-analytics-api}

[!UICONTROL Report Builder] är något vi alla känner till och älskar. Vad händer om jag säger att du kan använda det du vet om [!UICONTROL Report Builder] för att förbättra din Adobe Analytics-kompetens ytterligare? I den här videon går vi igenom hur du tar felsökningsbegäranden från [!UICONTROL Report Builder] och använder dem för att lära oss hur du skapar egna [!DNL Analytics] API-frågor.

>[!VIDEO](https://video.tv.adobe.com/v/25442/?quality=12&learn=on)

**UPPDATERA**: [!UICONTROL Report Builder] uppdaterade hur data begärdes en aning. Du kan fortfarande använda metoden från den här videon, men informationen kommer att vara något annorlunda i en felsökare.

I en felsökare:

1 - Sök efter api5.omniture.com. Antalet kan variera mellan 1 och 5 beroende på ditt datacenter.

2 - Gå till fliken [!UICONTROL Request]

3 - Sök efter [!DNL Report.Queue] i begäran.

Det finns också en alternativ metod för att felsöka förfrågningar som den här, och den fungerar lika bra. Du kan aktivera [!UICONTROL Report Builder]-loggning från menyn [!UICONTROL Options] och då registreras samma information som en felsökare skulle göra. Loggar finns under [!UICONTROL Documents] > [!UICONTROL ReportBuilderLogs] och kommer att ordnas per dag. Du kan söka efter &#39;Report.Queue&#39; i filen för att hitta alla dina förfrågningar. Loggarna kan även hjälpa till med felsökning av eventuella problem.

Mer information om den här funktionen finns i [dokumentationen](https://www.adobe.io/).
