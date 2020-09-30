---
title: 'Använda bästa praxis vid spårning av SPA (Single Page Applications) i Adobe Analytics '
description: I det här dokumentet beskriver vi flera metodtips som du bör följa och vara medveten om när du använder Adobe Analytics för att spåra Single Page-program (SPA). Det här dokumentet fokuserar på att använda Experience Platform Launch, vilket är den rekommenderade implementeringsmetoden.
feature: implementation basics
topics: spa
audience: implementer
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1389
translation-type: tm+mt
source-git-commit: 548ac75589383dfd4da4ae02412de91a0a3b28d6
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Använda bästa praxis vid spårning av SPA (Single Page Applications) i Adobe Analytics {#using-best-practices-when-tracking-spa-in-adobe-analytics}

I det här dokumentet beskriver vi flera metodtips som du bör följa och vara medveten om när du använder Adobe Analytics för att spåra Single Page-program (SPA). Det här dokumentet fokuserar på att använda Adobe [!DNL Experience Platform Launch], vilket är den rekommenderade implementeringsmetoden.

INLEDANDE ANMÄRKNINGAR:

* Objekten nedan förutsätter att du använder [!DNL Experience Platform Launch] för implementering på din webbplats. Övervägandena finns fortfarande kvar om du inte använder [!DNL Experience Platform Launch]dem, men du måste anpassa dem till din implementeringsmetod.
* Alla SPA-program är olika, så du kan behöva justera några av följande saker för att bäst uppfylla dina behov, men vi ville dela några av de bästa metoderna med dig: saker som du behöver tänka på när du implementerar Adobe Analytics på SPA-sidor.

## Enkelt diagram över hur du arbetar med SPA i [!DNL Experience Platform Launch] {#simple-diagram-of-working-with-spas-in-launch}

![omfång för analyser vid start](assets/spa_for_analyticsinlaunch.png)

**OBS!** Detta är som sagt en förenklad bild av hur SPA-sidor hanteras i en Adobe Analytics-implementering med [!DNL Experience Platform Launch]. I följande avsnitt på den här sidan kommer vi att diskutera de åtgärder och eventuella problem som du bör tänka på noga eller vidta.

## Ställa in datalagret {#setting-the-data-layer}

När nytt innehåll läses in på en SPA-sida, eller när en åtgärd utförs på en SPA-sida, är det första du bör göra att uppdatera datalagret. Detta måste ske INNAN den anpassade händelsen utlöser och aktiverar regler i [!DNL Experience Platform Launch], så att [!DNL Experience Platform Launch] du kan hämta nya värden från datalagret och överföra dem till Adobe Analytics.

Här följer ett exempel på ett datalager, vars element kan ändras vid visningsändringar eller åtgärder i din SPA. Om du till exempel ändrar en helskärm eller en större skärm är det vanligt att ändra ett&quot;[!DNL pageName]&quot;-element så att det nya kan hämtas in [!DNL Experience Platform Launch] och skickas till Adobe Analytics.

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

## Ange anpassade händelser och avlyssning i [!DNL Experience Platform Launch] {#setting-custom-events-and-listening-in-launch}

När nytt innehåll läses in på sidan, eller när en åtgärd inträffar på webbplatsen, vill du informera [!DNL Experience Platform Launch] så att den kan köra en regel och skicka data till [!DNL Analytics]. Det finns några olika sätt att göra detta: [!UICONTROL Direct Call] [!UICONTROL rules] eller Anpassade händelser.

* [!UICONTROL Direct Call] [!UICONTROL Rules]: i [!DNL Experience Platform Launch]kan du konfigurera en [!UICONTROL direct call] [!UICONTROL rule] som körs när den anropas direkt från sidan. Om sidinläsningen eller åtgärden på webbplatsen är mycket enkel, eller om den är unik och kan utföra en viss uppsättning instruktioner varje gång (anges [!DNL eVar4] till X och utlöses [!DNL event2] varje gång), kan du använda en [!UICONTROL direct call] [!UICONTROL rule]. Se [!DNL Experience Platform Launch] dokumentationen om hur du skapar [!UICONTROL direct call] [!UICONTROL rules].
* Anpassade händelser: Om du vill ha mer funktionalitet, och om du vill kunna koppla en nyttolast med olika värden, bör du ställa in anpassade JavaScript-händelser och lyssna efter dem i [!DNL Experience Platform Launch], där du kan använda nyttolasten för att ställa in variabler och skicka data till Adobe Analytics. Det är troligare att du kommer att behöva den här funktionen, så det här alternativet anses vara den bästa metoden. Varje funktion på platsen kan dock avgöra vilken metod som är lämpligast. Vi går framåt i det här dokumentet under förutsättning att du måste använda den här anpassade händelsemetoden.

**Exempel:** I [DET HÄR](https://helpx.adobe.com/experience-manager/kt/integration/using/launch-reference-architecture-SPA-tutorial-implement.html) hjälpdokumentet finns det länkar till exempel på SPA-platser som har implementerats [!DNL Analytics] (och andra Experience Cloud-lösningar) samt dokument som beskriver vad som har implementerats. I dessa SPA-exempel har följande anpassade händelser använts:

* [!DNL event-view-start]: Den här händelsen bör utlösas när vyn/läget som läses in startar.
* [!DNL event-view-end]: Den här händelsen bör utlösas även när en vy-/lägesändring har gjorts och alla SPA-komponenter på sidan har lästs in. Detta är händelsen som oftast utlöser ett anrop till Adobe Analytics.
* [!DNL event-action-trigger]: Den här händelsen bör utlösas när en händelse inträffar på sidan, förutom inläsning av vy/läge. Det kan vara en klickningshändelse eller en mindre innehållsändring utan en vyändring.

Mer information om hur/när de utlöses finns i de ovannämnda sidorna/dokumenten. Du behöver inte använda samma händelsenamn, men de funktioner som listas här är rekommenderade metodtips. I följande video visas en exempelwebbplats och var i [!DNL Experience Platform Launch] för att avlyssna anpassade händelser.

>[!VIDEO](https://video.tv.adobe.com/v/23024/?quality=12)

## Kör s.t() eller s.tl() i [!DNL Experience Platform Launch] [!UICONTROL Rule] {#running-s-t-or-s-tl-in-the-launch-rule}

En av de viktigaste sakerna att förstå [!DNL Analytics] när man arbetar med ett SPA är skillnaden mellan `s.t()` och `s.tl()`. Du kommer att aktivera någon av dessa metoder i [!DNL Experience Platform Launch] för att skicka data till [!DNL Analytics], men du måste veta när vart och ett ska skickas.

* **s.t()** - &quot;t&quot; står för &quot;track&quot; och är en normal sidvy. Även om URL:en kanske inte ändras, ändras vyn tillräckligt så att du *ser* det som en ny sida? I så fall anger du s.[!DNL pageName] variabel och använd `s.t()` för att skicka anropet till [!DNL Analytics]

* **s.tl()** - &quot;tl&quot; står för &quot;track link&quot; och används vanligtvis för att spåra klickningar eller små innehållsändringar på sidan, i motsats till helskärmsändringar. Om ändringen på sidan är liten, så att du inte ser den som en helt ny sida, ska du använda `s.tl()` och inte bekymra dig om att ställa in variabeln s.pageName, vilket ignorerar den [!DNL Analytics] .

**TIPS:** En del personer använder en allmän riktlinje att om skärmen ändras till mer än 50 % bör den betraktas som en sidvy och användas `s.t()`. Om det är mindre än 50 % ändring av skärmen ska du använda `s.tl()`. Det är dock helt upp till dig och vad du anser vara en ny&quot;sida&quot; och hur du vill spåra din webbplats i Adobe Analytics.

I följande video visas var/hur du ska utlösa `s.t()` eller `s.tl()` i Launch by Adobe.

>[!VIDEO](https://video.tv.adobe.com/v/23048/?quality=12)

## Rensar variabler {#clearing-variables}

När du spårar din webbplats med Adobe Analytics vill du förstås bara skicka rätt data till [!DNL Analytics] vid rätt tidpunkt. I en SPA-miljö kan ett värde som spåras i en [!DNL Analytics] variabel finnas kvar och skickas in på nytt [!DNL Analytics], kanske när vi inte längre vill. Av den anledningen finns det en funktion i tillägget som [!DNL Analytics] rensar variablerna så att du får ett nytt skiffer när du kör nästa bildbegäran och skickar data till [!DNL Launch] [!DNL Analytics].

I diagrammet ovan visas den i slutet av processen och variablerna rensas *när* du har skickat in träffen. I själva verket kan det göras antingen före ELLER efter att träffen har skickats in, men det ska vara konsekvent i dina [!DNL Experience Platform Launch] regler, så att du alltid rensar före eller efter att du har angett variabler och skickat in dem. Kom ihåg att om du ska rensa variablerna *innan* du kör `s.t()`måste du först rensa variablerna, sedan ange de nya variablerna och slutligen skicka de nya data till [!DNL Analytics].

**OBS!** Du behöver inte alltid rensa variabler när du kör `s.tl()`, eftersom `s.tl()` det kräver att [!DNL linkTrackVars] variabeln används tillsammans med variabeln varje gång för att avgöra [!DNL Analytics] vilka variabler som ska ställas in (läggs automatiskt till bakom scenerna i [!DNL Experience Platform Launch]). Det innebär att felaktiga variabler vanligtvis inte kommer in när de används, `s.tl()`men det rekommenderas mycket när du använder `s.t()` i en SPA-miljö. Trots detta skulle jag vilja rekommendera att det är en bra metod att använda funktionen Rensa variabler för både `s.t()` och `s.tl()` i en SPA-miljö, bara för att säkerställa att data samlas in med hög kvalitet.

I följande video visas var/hur du rensar variablerna i [!DNL Launch].

>[!VIDEO](https://video.tv.adobe.com/v/23049/?quality=12)

## Ytterligare överväganden {#additional-considerations}

### Anpassade kodfönster i [!DNL Experience Platform Launch] {#custom-code-windows-in-launch}

I [!DNL Launch][!DNL Analytics] tillägget finns det två ställen där du kan infoga egen kod: Avsnittet [!UICONTROL library management] och det extra&quot;[!UICONTROL Configure Tracker Using Custom Code]&quot;-avsnittet.

![Starta anpassade kodfönster för Analytics](assets/launch_analyticscustomcodewindows.png)

Det är viktigt att veta att någon av dessa platser egentligen bara kommer att köra koden i dem en gång, när den inledande sidinläsningen sker på din SPA-sida. Om du vill att koden ska köras på en vyändring eller på en åtgärd på din webbplats, bör du lägga till ytterligare en åtgärd till lämplig **[!UICONTROL rule]** (t.ex. i &quot;sidinläsning: event-view-end&quot; [!UICONTROL rule]) så att koden körs varje gång den [!UICONTROL rule] körs. När du skapar den åtgärden i [!UICONTROL rule]anger du *Extension = Core* och *Action Type = Custom Code*.

### &quot;Hybrid&quot; SPA/Vanliga platser {#hybrid-spa-regular-sites}

Vissa webbplatser består av en kombination av&quot;vanliga&quot; sidor och SPA-sidor. I det här fallet måste du använda en strategi som fungerar för båda sidtyperna. När du konfigurerar anpassade händelser på webbplatsen och aktiverar reglerna i [!DNL Experience Platform Launch]ska du vara försiktig så att det inte uppstår dubbla träffar [!DNL Analytics] från sidan, baserat på hash-ändringar o.s.v. (om det är så du har valt att utlösa [!DNL Experience Platform Launch] regeln). I det här fallet måste du utelämna en av sidvyerna så att den inte ger felaktiga data i Adobe Analytics.

Om du bestämmer dig för att dela upp funktionaliteten [!UICONTROL rules] så att du får mer kontroll över den, ska du komma ihåg/dokumentera att du har gjort detta, så att eventuella ändringar av den ena [!UICONTROL rule] kan göras [!UICONTROL rule] också, vilket skyddar din [!DNL Analytics] dataintegritet.

### Integrering med [!DNL Target] A4T {#integration-with-target-via-a4t}

Bara en kort pratbubbla här. Om du integrerar med [!DNL Target] A4T måste du se till att [!DNL Target] [!DNL Analytics] begäran och begäran på samma vyändring har samma SDID. Detta säkerställer att dina data synkroniseras korrekt med lösningarna.

Om du vill se träffarna använder du ett felsöknings- eller paketutlösarprogram. Du kan också använda Experience Cloud Debugger, ett Chrome-tillägg som kan laddas ned [HERE](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj). [!DNL Target] ska aktiveras först på sidan, så du kan även kontrollera det i JavaScript-konsolen eller felsökaren.

## Ytterligare material {#additional-resources}

* [SPA-diskussion i Adobe-forumen](https://forums.adobe.com/thread/2451022)
* [Referensarkitektursajter som visar hur man implementerar SPA i Experience Platform Launch](https://helpx.adobe.com/experience-manager/kt/integration/using/launch-reference-architecture-SPA-tutorial-implement.html)