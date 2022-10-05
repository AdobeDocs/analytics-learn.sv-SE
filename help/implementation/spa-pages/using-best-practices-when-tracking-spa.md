---
title: Bästa praxis för implementering av Single Page-program (SPA)
description: Lär dig några tips om hur du implementerar Adobe Analytics i Single Page-program (SPA). Detta inkluderar användning av Experience Platform-taggar, den rekommenderade implementeringsmetoden.
feature: Implementation Basics
topics: spa
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1389
topic: SPA
role: Developer, Data Engineer
level: Intermediate
exl-id: 8fe63dd1-9629-437f-ae07-fe1c5a05fa42
source-git-commit: d78c3351d2a98704396ceb8f84d123dd463befe5
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 0%

---

# Bästa praxis för implementering av Single Page-program (SPA) {#implementation-best-practices-for-single-page-appliations}

Lär dig några metodtips för implementering [!DNL Adobe Analytics] på Single Page Applications (SPA). Detta inkluderar användning av [!DNL Experience Platform Tags], den rekommenderade implementeringsmetoden.

INLEDANDE ANMÄRKNINGAR:

* Innehållet nedan refererar till användningen av [!DNL Experience Platform Tags] för att implementera Adobe Analytics på er webbplats. Dessa överväganden gäller om [!DNL Experience Platform Tags] används inte, därför måste ni anpassa dem till er implementeringsmetod.
* Det finns skillnader i SPA. Du bör därför anpassa ditt tillvägagångssätt efter dina behov.

## Enkelt diagram över att arbeta med SPA i [!DNL Experience Platform Tags] {#simple-diagram-of-working-with-spas-in-tags}

![SPA för analys i taggar](assets/spa_for_analyticsinlaunch.png)

**OBS!** Det här är en förenklad bild av hur SPA sidor hanteras i en Adobe Analytics-implementering med [!DNL Experience Platform Tags]. I följande avsnitt beskrivs steg och problem som du bör tänka på.

## Ange datalagret {#set-the-data-layer}

När nytt innehåll läses in eller när en åtgärd utförs på en SPA sida, *uppdatera datalagret först*. Det här måste hända **före** en anpassad händelse som utlöser en regel körs i [!DNL Experience Platform Tags]. På så sätt säkerställs att rätt värden från datalagret överförs till Taggar och sedan till Adobe Analytics.

Här följer ett exempel på ett datalager. Alla dessa element kan ändras baserat på den inledande vyn eller efterföljande ändring av vyn med hänsyn till en åtgärd som har vidtagits på din SPA. Om du till exempel ändrar en vy som är fullständig eller flersidig är det ett vanligt krav att skicka in en unik[!DNL pageName]&quot; för att skilja mellan vyerna i Adobe Analytics rapporter.

```JavaScript
<script>
    digitalData = {
        pageInstanceID: "Launch Demo Site",
        page:{
            pageInfo:{
                pageID: '2745374',
                pageName: 'acs demo - product listing page'
            },
            attributes:{
                project: "Experience Platform Launch Project"
            }
        },
        user : [ {
          "profile" : [ {
            "attributes" : {
              "gender" : "male",
              "age" : "35"
            }
          } ]
        }],
        libraries : {
          adobe : {
            launch : {
              state : 0, // 0 = not loaded , 1 = loaded
              domain : "assets.adobedtm.com"
            }
          }
        }

     };
    </script>
```

## Ange anpassade händelser och lyssna efter dessa händelser i [!DNL Experience Platform Tags] {#setting-custom-events-and-listening-in-tags}

När nytt innehåll läses in eller när en åtgärd inträffar på SPA sida måste Experience Platform-taggar informeras för att köra en regel som skickar data till [!DNL Analytics]. Det finns ett par strategier för detta: [!UICONTROL Direct Call rules] eller Anpassade händelser.

* [!UICONTROL Direct Call rules]: Konfigurera en [!UICONTROL direct call rule] som körs när den anropas direkt från sidan. Om sidinläsningen eller åtgärden är enkel eller unik och kan köra en specifik uppsättning instruktioner varje gång (till exempel ange [!DNL eVar4] till X och utlösare [!DNL event2] varje gång) är detta tillvägagångssätt lämpligt. Se [!DNL Experience Platform Tags] mer information om hur du skapar [!UICONTROL direct call rules].
* Anpassade händelser: Om du behöver bifoga en nyttolast dynamiskt med unika värden för händelser som inträffar på SPA sidor använder du anpassade JavaScript-händelser och lyssnar efter dem i [!DNL Experience Platform Tags]. Använd nyttolasten för att ange dataelement och analysvariabler i taggar. Denna metod anses vara den bästa metoden, eftersom behovet vanligtvis är vanligt för SPA. I våra exempel nedan används metoden för anpassade händelser.

**Exempel:** [I den här](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html) hjälpdokument, det finns länkar till exempelwebbplatser SPA implementerar [!DNL Analytics] och andra Experience Cloud-lösningar. I dessa exempel används följande anpassade händelser:

* **[!DNL Event-view-start]**: Kör vid vystart för den vy/det läge som läses in.
* **[!DNL Event-view-end]**: Kör när en vy-/lägesändring inträffar och alla SPA på sidan har lästs in. Detta är händelsen som vanligtvis skickar data till Adobe Analytics.
* **[!DNL Event-action-trigger]**: Kör när en händelse inträffar på sidan, förutom inläsning av vy/läge. Exempel på detta är en klickningshändelse eller en mindre innehållsändring utan vyändring.

Mer information om hur och när de här händelserna utlöses finns i de sidor och dokument som det hänvisas till ovan. Du behöver inte använda samma händelsenamn i implementeringen. Argumentet för den använda metodens funktionalitet är viktigt för att förstå att det är den rekommenderade bästa metoden för varje metod. I följande video visas ett exempel SPA sidan och exempelkoden i [!DNL Experience Platform Tags] som lyssnar efter anpassade händelser.

>[!VIDEO](https://video.tv.adobe.com/v/23024/?quality=12)

## Kör s.t() eller s.tl() i [!DNL Experience Platform Tags] {#running-s-t-or-s-tl-in-the-launch-rule}

Ett viktigt koncept att förstå för [!DNL Analytics] när du arbetar med ett SPA är skillnaden mellan `s.t()` och `s.tl()`. Din kod utlöser en eller flera av dessa metoder i [!DNL Experience Platform Tags] att skicka data till [!DNL Analytics].

* **s.t()** - &quot;t&quot; står för &quot;track&quot; och representerar en sidvy. Om vyn ändras så mycket att du  *överväg* om det är en ny sida, använd detta samtal. Ange ett unikt värde för [!DNL s.pageName] variabel och användning `s.t()` för att skicka data till [!DNL Analytics].

* **s.tl()** -&quot;tl&quot; står för&quot;track link&quot;, och detta representerar en länkklickning eller en liten innehållsändring. Om vyändringen är minimal kan du använda `s.tl()` att skicka in ett unikt värde om interaktionen till [!DNL Analytics]. Den här variabeln som skickades är inte [!DNL s.pageName], eftersom detta ignoreras i Analytics när `s.tl()` samtal tas emot.

**TIPS:** Om skärmen ändras med mer än 50 % kan du som en allmän riktlinje använda `s.t()` sidvyanrop. Annars använder du `s.tl()`. Du bör dock använda ditt omdöme när du överväger åtgärder som utgör en ny&quot;sida&quot; och hur detta bör presenteras i Adobe Analytics rapporter.

I följande video visas var och hur utlösaren ska göras `s.t()` eller `s.tl()` i taggar.

>[!VIDEO](https://video.tv.adobe.com/v/23048/?quality=12)

## Rensa variabler {#clear-variables}

Skicka rätt data till [!DNL Analytics] vid rätt tidpunkt. I en SPA miljö är ett värde lagrat i en [!DNL Analytics] variabeln består och återställs till [!DNL Analytics], kanske när du inte längre vill ha det. En funktion finns i [!DNL Analytics] [!DNL Tags] för att rensa variablerna så att nästa anrop inte skickar data till [!DNL Analytics].

Diagrammet ovan visar variabler som rensats *efter* du skickar in data. I själva verket kan detta hända före eller efter anropet, men du måste vara konsekvent i [!DNL Experience Platform Tags] regler för en renare implementering. Om du tar bort variabler *före* du kör `s.t()`anger du de nya variablerna direkt efter anropet och fortsätter sedan att skicka nya data till [!DNL Analytics].

**OBS!** Rensning av variabler behövs inte alltid när du kör `s.tl()`. Det här anropet kräver att [!DNL linkTrackVars] variabel att instruera [!DNL Analytics] vilka variabler som ska anges. Detta sker automatiskt [!DNL Experience Platform Tags] via konfiguration. Det förhindrar att felaktiga variabler ställs in i kontrast till beteendet med `s.t()` i en SPA miljö. För att säkerställa en renast och tillförlitligare implementering är det troligtvis enklare att använda funktionen för tydliga variabler för båda anropen i en SPA miljö.

I följande video visas var och hur variabler rensas i [!DNL Tags].

>[!VIDEO](https://video.tv.adobe.com/v/23049/?quality=12)

## Ytterligare överväganden {#additional-considerations}

### Anpassade kodfönster i [!DNL Experience Platform Tags] {#custom-code-windows-in-tags}

I [!DNL Tags] [!DNL Analytics] finns det två ställen där anpassad kod kan infogas: The &quot;[!UICONTROL library management]&quot; och &quot;[!UICONTROL Configure tracker using custom code]-avsnitt.

![Anpassade kodfönster för tagganalys](assets/launch_analyticscustomcodewindows.png)

På någon av dessa platser körs koden som finns där en gång för den första sidan som läser in SPA. Om koden ska köras på en vy eller en åtgärdsändring implementerar du koden i lämplig **[!UICONTROL rule]** (t.ex. &quot;page load: event-view-end&quot;-regel) för att se till att koden körs varje gång [!UICONTROL rule] kör. När du skapar en HTML-åtgärd i [!UICONTROL rule], ange *Tillägg = kärna* och *Åtgärdstyp = Anpassad kod*.

### &quot;Hybrid&quot; SPA traditionella sajter {#hybrid-spa-and-traditional-sites}

Vissa webbplatser består av en kombination av traditionella och SPA sidor. I det här fallet använder du en strategi som fungerar för båda sidtyperna. När du konfigurerar anpassade händelser på webbplatsen och aktiverar regler i [!DNL Experience Platform Tags], se till att dubbla träffar inte skickas till [!DNL Analytics] baserat på hash-ändringar och så vidare. I så fall utelämnar du en av sidvyerna för att förhindra att duplicerade data skickas till Adobe Analytics.

Om du bestämmer dig för att dela upp funktionaliteten i unika [!UICONTROL rules] Kom ihåg att du har gjort detta för att få mer kontroll. Om du ändrar en [!UICONTROL rule], gör samma ändringar i den andra [!UICONTROL rule].

### Integration med [!DNL Target] med A4T {#integration-with-target-using-a4t}

Vid integrering med [!DNL Target] med A4T, bekräfta att [!DNL Target] och [!DNL Analytics] begäranden som skickas i samma vy eller åtgärd skickar samma SDID-parametervärde. Detta säkerställer att dina data synkroniseras korrekt i serverdelen.

Använd ett felsöknings- eller paketövervakningsverktyg om du vill visa träffar. Adobe tillhandahåller en Experience Platform-felsökare för detta ändamål. Det är ett Chrome-tillägg som kan vara [laddas ned här](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob?hl=en). [!DNL Target] ska köras först på sidan. Detta kan även verifieras i felsökaren.

## Ytterligare resurser {#additional-resources}

* [SPA om Adobe forum](https://experienceleaguecommunities.adobe.com:443/t5/adobe-experience-platform-launch/best-practices-for-single-page-apps/m-p/267940)
* [Referensarkitektursajter som visar hur du implementerar SPA i Experience Platform Launch](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)
