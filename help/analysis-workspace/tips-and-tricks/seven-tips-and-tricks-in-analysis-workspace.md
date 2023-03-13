---
title: 7 Tips och tricks som gör det enklare och snabbare att skapa anpassade analysprojekt
description: Analysis Workspace är ett kraftfullt verktyg i Adobe Analytics som kan hjälpa er att skapa slagkraftigare analysprojekt. Det har en omfattande funktionsuppsättning som gör att du kan göra vilken typ av frihandsanalys som helst, men en enkel användarupplevelse som gör den här kraften och skalan tillgänglig.
feature: Workspace Basics
topics: topics
activity: use
doc-type: feature video
team: Technical Marketing
kt: 3945
role: User, Developer, Data Engineer, Architect, Data Architect, Admin, Leader
level: Beginner
exl-id: af0e66cb-4e74-4ce0-9429-4a461fd54263
source-git-commit: 32424f3f2b05952fe4df9ea91dcbe51684cee905
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 0%

---

# 7 Tips och tricks som gör det enklare och snabbare att skapa anpassade analysprojekt

**Bygg ut er Analysis Workspace-kompetens!**
Analysis Workspace är ett kraftfullt verktyg i Adobe Analytics som kan hjälpa er att skapa slagkraftigare analysprojekt. Det har en omfattande funktionsuppsättning som gör att du kan göra vilken typ av frihandsanalys som helst, men en enkel användarupplevelse som gör den här kraften och skalan tillgänglig.

## Bygg: Gå ned till rätt datapunkter

### ***Tips 1: Släpp alla [!UICONTROL dimension], [!UICONTROL date range], [!UICONTROL segment], eller [!UICONTROL metric] i alla delar av projektet***

Bara dra och släpp [!UICONTROL segment] eller någon annan komponent till [!UICONTROL segment] och du kan snabbt segmentera den panelen till vissa datapunkter. Du kan t.ex. segmentera panelen och bara visa träffar där det finns order genom att släppa [!UICONTROL metric] &quot;beställningar&quot; i [!UICONTROL segment] släppzon. Du kan till och med segmentera efter data som inte finns i en komponent (för att se träffar utan ordning, till exempel) genom att släppa dimensionsobjektet &quot;unspecified&quot; eller &quot;none&quot; i zonen.

>[!VIDEO](https://video.tv.adobe.com/v/24036/?quality=12)

>[!TIP]
>
>**Prova det här:** Det finns en hel värld av effektivitet som väntar på dig i snabbmenyn. På den här menyn har du tillgång till många verktyg och funktioner direkt i ditt Analysis Workspace-arbetsflöde. Om du är osäker kan du högerklicka för att se om verktyget eller funktionen du behöver är nära till hands

### ***Tips 2: Skapa enkla mätvärden utan att lämna arbetsflödet***

Med snabb [!UICONTROL Calculated Metrics]kan du skapa nya [!UICONTROL metrics] i Analysis Workspace istället för att navigera till [!UICONTROL Calculated Metric] Builder. Välj bara [!UICONTROL metric] kolumner som du vill beräkna och sedan väljer du &quot;[!UICONTROL Create Metric From Selection].&quot; Nu kan du lägga till, subtrahera, dela upp, multiplicera och mycket mer utan att lämna projektet och bryta tankebanan.

>[!VIDEO](https://video.tv.adobe.com/v/23126/?quality=12)

>[!TIP]
>
>**Användbart tips:** Upp till två [!UICONTROL metric] kolumner kan markeras när du använder Snabb [!UICONTROL Calculated Metrics]. Använd [!UICONTROL Calculated Metric] Skapa [!UICONTROL metrics] som innehåller mer än två [!UICONTROL metrics].

## Visualisera: Ge liv åt data i projekt

### ***Tips 3: Kopiera och infoga visualiseringar och paneler var som helst***

Kopiera enkelt visualiseringar och paneler från ett ställe och lägg till dem i ett annat, till och med i ett annat projekt. Det innebär att ni enkelt kan flytta data i takt med att projektet växer och dela med er av resultaten till nya användare så att de inte behöver börja en analys från grunden. Högerklicka bara på den panel eller visualisering som du vill kopiera och välj &quot;[!UICONTROL Copy Visualization]och högerklicka på en tom panel för att infoga den.

>[!VIDEO](https://video.tv.adobe.com/v/23230/?quality=12)

>[!TIP]
>
>**Mycket efterfrågad kapacitet:** Våra kunder bad oss att göra det enkelt att kopiera och infoga visualiseringar och paneler. Nu ägnar de mindre tid åt att återskapa insikter och mer tid åt att hitta nya.

### ***Tips 4: Växla mellan tidsvisualiseringar med bara ett klick***

Ändra enkelt tidsvyn när du arbetar med trendade visualiseringar. I tidigare versioner av Analysis Workspace innebar en ändring av tiden att en källtabell togs bort och att en ny [!UICONTROL dimension]och sedan dölja tabellen igen. Nu är det lika enkelt som att välja den tidshöjande detaljrikedom du vill visa direkt i[!UICONTROL Visualizations Settings]&quot; (övre högra kugghjulet).

>[!VIDEO](https://video.tv.adobe.com/v/23548/?quality=12)

## Dela: Göra det enkelt för andra att använda och förstå sina resultat

### ***Tips 5: Skapa en egen [!DNL Virtual Report Suite] för specifika affärsenheter***

Adobe Analytics samlar in enorma mängder data. Komponenturval i [!DNL Virtual Report Suites] ger administratörer möjlighet att skapa en datauppsättning för varje affärsenhet i en organisation. Det innebär att analytiker som arbetar i Analysis Workspace inte behöver gå igenom data för att hitta det som betyder mest för dem. Markera rutan &quot;[!UICONTROL Enable Customization of Virtual Report Suite Components]&quot; i [!UICONTROL Virtual Report Suites] builder under [!UICONTROL “Components],&quot; och sedan väljer du [!UICONTROL components] som matchar vad ett specifikt team gör.

>[!VIDEO](https://video.tv.adobe.com/v/23544/?quality=12)

>[!TIP]
>
>**Användbart tips:** Du kan också ändra namnet på komponenter i en [!UICONTROL Virtual Report Suite] som överensstämmer med nomenklaturen för särskilda affärsenheter. Klicka bara på pennikonen bredvid komponenten och skriv in ett nytt namn.

### ***Tips 6: Länka till paneler och visualiseringar inom ett projekt eller mellan projekt***

Skapa länkar som tar målgrupper överallt inom Analysis Workspace. Högerklicka bara på panelen som du vill länka till och välj &quot;[!UICONTROL Get Panel Link]och kopiera. Markera sedan den text du vill länka från, markera länkikonen i textredigeraren för en textruta eller beskrivning och klistra in. Om du vill länka till ett helt projekt klickar du bara på[!UICONTROL Share]&quot; väljer du &quot;[!UICONTROL Get Project Link]&quot; och följer samma steg som ovan.

>[!VIDEO](https://video.tv.adobe.com/v/23724/?quality=12)

>[!TIP]
>
>**Användbart tips:** Det finns flera sätt att länka kan förbättra läsarens upplevelse. Du kan peka dem mot illustrationer som matchar resultat och rekommendationer i projekt. Eller låt dem gå direkt från en innehållsförteckning till de avsnitt de är intresserade av. Du kan även länka till andra användares projekt som relaterar till din analys

### ***Tips 7: Spara projekt som återanvändbara mallar***

Nu kan du enkelt omvandla vilket projekt som helst till en egen mall. Välj bara &quot;[!UICONTROL Save As Template]&quot; från &quot;[!UICONTROL Project]&quot;, lägg till taggar som gör mallen enkel att hitta och klicka på &quot;[!UICONTROL Save Project As Template].&quot; Mallen kommer nu att vara tillgänglig för alla Analysis Workspace-användare under &quot;[!UICONTROL Custom Templates]&quot;. På så sätt kan analytiker påbörja sina projekt med meningsfulla datapunkter i stället för att börja från ruta ett.

>[!VIDEO](https://video.tv.adobe.com/v/23231/?quality=12)

>[!TIP]
>
>**Mycket efterfrågad kapacitet:** Flera kunder bad oss att göra det möjligt att spara projekt som anpassade mallar. Den här funktionen har blivit en av deras favoriter.

[Klicka här för att hitta fler tips och tricks på Experience League](https://experienceleague.adobe.com/?search=tips&amp;tag=Analysis+Workspace#recommended/solutions/analytics)

| Om författaren |  |
|------------|------------|
| ![Jen Lasser](assets/jlasser-headshot-s.jpg) | Jen Lasser är chef för Adobe Analytics produkthanteringsteam. <br> I den här rollen möter hon kunder för att förstå deras affärsbehov, <br>använda det hon lär sig för att informera om Adobe Analytics produktplan <br>och prioritera nya produktfunktioner. Före hennes nuvarande position, <br>Jen var rektor i Adobe Consulting-gruppen och arbetade som <br>ämnesexpert inom datavisualisering, Analysis Workspace och [!DNL Report Builder]. <br><br>Med hjälp av hennes verkliga insikter har vi kuraterat följande tips och trick för att <br>gör det enklare att skapa, visualisera och dela dina Analysis Workspace-projekt |
