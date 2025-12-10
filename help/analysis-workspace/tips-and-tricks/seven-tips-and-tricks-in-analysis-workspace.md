---
title: 7 Tips och tricks som gör det enklare och snabbare att skapa anpassade analysprojekt
description: Analysis Workspace är ett kraftfullt verktyg i Adobe Analytics som kan hjälpa er att skapa slagkraftigare analysprojekt. Det har en omfattande funktionsuppsättning som gör att du kan göra vilken typ av frihandsanalys som helst, men en enkel användarupplevelse som gör den här kraften och skalan tillgänglig.
feature: Workspace Basics
topics: topics
activity: use
doc-type: feature video
team: Technical Marketing
kt: 3945
role: User, Developer, Admin, Leader
level: Beginner
exl-id: af0e66cb-4e74-4ce0-9429-4a461fd54263
source-git-commit: 474e68e2937c82efa459b6ed8048a4abd2753285
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 0%

---

# 7 Tips och tricks som gör det enklare och snabbare att skapa anpassade analysprojekt

**Utöka din Analysis Workspace-kompetens!**
Analysis Workspace är ett kraftfullt verktyg i Adobe Analytics som kan hjälpa er att skapa slagkraftigare analysprojekt. Det har en omfattande funktionsuppsättning som gör att du kan göra vilken typ av frihandsanalys som helst, men en enkel användarupplevelse som gör den här kraften och skalan tillgänglig.

## Bygg: Gå ned till rätt datapunkter

### ***Tips 1: Släpp [!UICONTROL dimension], [!UICONTROL date range], [!UICONTROL segment] eller [!UICONTROL metric] i någon del av ditt projekt***

Det är bara att dra och släppa en [!UICONTROL segment] eller någon annan komponent i släppzonen [!UICONTROL segment] överst på en panel, så kan du snabbt segmentera panelen nedåt till vissa datapunkter. Du kan till exempel segmentera panelen så att den bara visar träffar där det finns order genom att släppa [!UICONTROL metric] &quot;order&quot; i släppzonen [!UICONTROL segment]. Du kan till och med segmentera efter data som inte finns i en komponent (för att se träffar utan ordning, till exempel) genom att släppa dimensionsobjektet &quot;unspecified&quot; eller &quot;none&quot; i zonen.

>[!VIDEO](https://video.tv.adobe.com/v/24036/?quality=12&learn=on)

>[!TIP]
>
>**Prova det här:** Det finns en hel värld av effektivitet som väntar på dig i snabbmenyn. På den här menyn har du tillgång till många verktyg och funktioner direkt i ditt Analysis Workspace-arbetsflöde. Om du är osäker kan du högerklicka för att se om verktyget eller funktionen du behöver är nära till hands

### ***Tips 2: Skapa enkla mätvärden utan att lämna arbetsflödet***

Med Snabb [!UICONTROL Calculated Metrics] kan du skapa nya [!UICONTROL metrics] direkt i Analysis Workspace i stället för att navigera till [!UICONTROL Calculated Metric] Builder. Markera bara de [!UICONTROL metric] kolumner som du vill beräkna och välj sedan [!UICONTROL Create Metric From Selection] på högerklicksmenyn. Nu kan du lägga till, subtrahera, dela upp, multiplicera och mycket mer utan att lämna projektet och bryta tankebanan.

>[!VIDEO](https://video.tv.adobe.com/v/23126/?quality=12&learn=on)

>[!TIP]
>
>**Användbart tips:** Upp till två [!UICONTROL metric] kolumner kan markeras när du använder snabbkommandot [!UICONTROL Calculated Metrics]. Använd [!UICONTROL Calculated Metric] Builder för att skapa [!UICONTROL metrics] som innehåller fler än två [!UICONTROL metrics].

## Visualisera: Ge liv åt data i projekt

### ***Tips 3: Kopiera och infoga visualiseringar och paneler var som helst***

Kopiera enkelt visualiseringar och paneler från ett ställe och lägg till dem i ett annat, till och med i ett annat projekt. Det innebär att ni enkelt kan flytta data i takt med att projektet växer och dela med er av resultaten till nya användare så att de inte behöver börja en analys från grunden. Högerklicka bara på den panel eller visualisering som du vill kopiera, välj [!UICONTROL Copy Visualization] och högerklicka på en tom panel för att infoga den.

>[!VIDEO](https://video.tv.adobe.com/v/23230/?quality=12&learn=on)

>[!TIP]
>
>**Funktion som begärts mycket:** Våra kunder har bett oss att göra det enkelt att kopiera och infoga visualiseringar och paneler. Nu ägnar de mindre tid åt att återskapa insikter och mer tid åt att hitta nya.

### ***Tips 4: Växla mellan visualiseringar av tidsgranularitet med bara ett klick***

Ändra enkelt tidsvyn när du arbetar med trendade visualiseringar. I tidigare versioner av Analysis Workspace innebar en ändring av tiden att en källtabell skulle tas bort, att en ny [!UICONTROL dimension] skulle dras och att tabellen skulle döljas igen. Nu är det lika enkelt som att välja den tidsgranularitet som du vill visa direkt i listrutan [!UICONTROL Visualizations Settings] (övre högra kugghjulet).

>[!VIDEO](https://video.tv.adobe.com/v/23548/?quality=12&learn=on)

## Dela: Gör det enkelt för andra att använda och förstå vad de tycker

### ***Tips 5: Skapa en anpassad [!DNL Virtual Report Suite] för specifika affärsenheter***

Adobe Analytics samlar in enorma mängder data. Komponenturval i [!DNL Virtual Report Suites] gör att administratörer kan skapa en datauppsättning för varje affärsenhet i en organisation. Det innebär att analytiker som arbetar i Analysis Workspace inte behöver gå igenom data för att hitta det som betyder mest för dem. Markera bara rutan [!UICONTROL Enable Customization of Virtual Report Suite Components] i [!UICONTROL Virtual Report Suites] builder under [!UICONTROL “Components] och välj sedan den [!UICONTROL components] som matchar vad ett specifikt team mäter.

>[!VIDEO](https://video.tv.adobe.com/v/23544/?quality=12&learn=on)

>[!TIP]
>
>**Användbart tips:** Du kan också ändra namnet på komponenter i en [!UICONTROL Virtual Report Suite] så att det matchar nomenklaturen för specifika affärsenheter. Klicka bara på pennikonen bredvid komponenten och skriv in ett nytt namn.

### ***Tips 6: Länka till paneler och visualiseringar inom ett projekt eller mellan projekt***

Skapa länkar som tar målgrupper överallt inom Analysis Workspace. Högerklicka bara på panelen som du vill länka till, välj [!UICONTROL Get Panel Link] och kopiera. Markera sedan den text du vill länka från, markera länkikonen i textredigeraren för en textruta eller beskrivning och klistra in. Om du vill länka till ett helt projekt klickar du bara på fliken [!UICONTROL Share], väljer [!UICONTROL Get Project Link] och följer stegen ovan.

>[!VIDEO](https://video.tv.adobe.com/v/23724/?quality=12&learn=on)

>[!TIP]
>
>**Användbart tips:** Det finns flera sätt att länka för att förbättra läsarens upplevelse. Du kan peka dem mot illustrationer som matchar resultat och rekommendationer i projekt. Eller låt dem gå direkt från en innehållsförteckning till de avsnitt de är intresserade av. Du kan även länka till andra användares projekt som relaterar till din analys

### ***Tips 7: Spara projekt som återanvändbara anpassade mallar***

Nu kan du enkelt omvandla vilket projekt som helst till en egen mall. Välj bara [!UICONTROL Save As Template] i listrutan [!UICONTROL Project], lägg till taggar som gör mallen enkel att hitta och klicka på [!UICONTROL Save Project As Template]. Nu är mallen tillgänglig för alla Analysis Workspace-användare på fliken [!UICONTROL Custom Templates]. På så sätt kan analytiker påbörja sina projekt med meningsfulla datapunkter i stället för att börja från ruta ett.

>[!VIDEO](https://video.tv.adobe.com/v/23231/?quality=12&learn=on)

>[!TIP]
>
>**Mycket begärd kapacitet:** Flera kunder bad oss att spara projekt som anpassade mallar. Den här funktionen har blivit en av deras favoriter.

[Klicka här för att hitta fler tips och tricks om Experience League](https://experienceleague.adobe.com/?search=tips&tag=Analysis+Workspace#recommended/solutions/analytics)

| Om författaren |            |
|------------|------------|
| ![Jen Lasser](assets/jlasser-headshot-s.jpg) | Jen Lasser är chef för Adobe Analytics produkthanteringsteam. <br> I den här rollen möter hon kunder för att förstå deras affärsbehov, <br>med hjälp av vad hon lär sig för att informera Adobe Analytics produktplan <br> och för att prioritera nya produktfunktioner. Före sin nuvarande position var <br>Jen huvudkonsult i Adobe Consulting-teamet och arbetade som <br>ämnesexpert inom datavisualisering, Analysis Workspace och [!DNL Report Builder]. <br><br>Med hjälp av hennes verkliga insikter har vi kuraterat följande tips och trick för att <br>hjälpa till att göra det enklare att skapa, visualisera och dela dina Analysis Workspace-projekt |
