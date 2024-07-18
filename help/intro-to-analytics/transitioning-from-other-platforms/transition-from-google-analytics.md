---
title: Omfattande guide för övergång till Adobe Analytics från Google Analytics
description: Lär dig mer om var det finns likvärdiga funktioner och hur du använder dem effektivt när du går över från Google Analytics till Adobe Analytics
feature: Third-party Integration
role: User
level: Beginner
kt: 9830
thumbnail: 34749.jpg
exl-id: b2be6081-a1c0-4435-affb-454ed5a74662
source-git-commit: d78c3351d2a98704396ceb8f84d123dd463befe5
workflow-type: tm+mt
source-wordcount: '3413'
ht-degree: 0%

---

# Omfattande guide för övergång till Adobe Analytics från Google Analytics{#comprehensive-guide-for-transitioning-to-Adobe-Analytics}

## 1. Inledning

En av de största utmaningarna när det gäller att gå över mellan olika verktyg är att lära sig var man hittar motsvarande funktionalitet och hur man använder den effektivt. Diskussionen är en del av en större guide som hjälper användare att övergå till Adobe Analytics (antingen som en ny användare eller en som kommer från Google Analytics) på ett enklare sätt. En djupgående jämförelse med GA, som det mest troliga komparativa verktyget som de flesta användare känner till, finns för att hjälpa användarna att korrelera befintliga kunskaper med de nya verktygen. När det inte finns något alternativ till övningar hjälper detta dig att komma igång och minska de frustrationer du kan stöta på under den här tiden.

Vi bör göra en snabb jämförelse av terminologi:

| **Beskrivning** | **Adobe Analytics** | **Google Analytics** |
|--------------------------------------------------------------------------------------------------------------------------------|---------------------|----------------------|
| Ett händelsemått som representerar en sida (eller skärm i ett program) har visats | Sidvy | Sidvy |
| Ett mätvärde som representerar en grupp interaktioner på webbplatsen eller appen som äger rum inom samma tidsram | Besök | Session |
| Ett mätvärde som definierar en identifierad enhet (baserat på flera kriterier som cookies och andra beteendemönster för att sammanfoga användarinformation) | Unik besökare | Användare |

## 2. Gränssnitten

När folk jämför Adobe Analytics och Google Analytics kommenterar de att Adobe gränssnitt är skrämmande först. Detta är sant, men det är också; tro det eller ej; en styrka, inte en svaghet. Adobe har ett brett utbud av verktyg och flexibilitet i datavisualiseringen, vilket ger dig större frihet att skapa det du behöver.

Vi börjar med att titta på rapporten&quot;in-site&quot;.

### 2.1. Rapportering på plats

#### 2.1.1. Hemskärm

Både Adobe Analytics och Google Analytics kan anpassa den första vyn som en användare ser när han/hon loggar in.

##### 2.1.1.1. Workspace/hemskärmen för anpassad uppsättning (Adobe Analytics)

Adobe Analytics förutsätter inte att man skapar en färdig rapport som alla användare kan se vid inloggning. Standardstartsidan tar användaren till startskärmen i Workspace, där alla användare ser alla arbetsyterapporter som de har skapat eller som delats med dem. Dessutom kan varje användare ange vilken som helst av dessa rapporter som hemskärm om de så önskar.

![workspace-create-project](assets/ga-to-aa_1.png)

Mer information om arbetsytan finns nedan. Se avsnitt 2.1.2.1

>[!TIP]
>
>Skapa/dela några standardrapporter för din organisation så att de får en startpunkt för att se information utan att behöva dyka upp i sina egna rapporter direkt.



##### 2.1.1.2. Insikter från hemskärmen (Google Analytics)

* Google Analytics hemskärm har några färdiga visualiseringar för dig. De här täcker saker som:
* Användare, sessioner, studsfrekvens och sessionsvaraktighet de senaste sju dagarna
* Användare efter tid på dygnet de senaste 30 dagarna
* Aktuella användare just nu och de viktigaste aktiva sidorna
* Traffic Channel, Source/Medium och Referrings de senaste sju dagarna
* Sessioner per land de senaste sju dagarna
* De vanligaste sidorna de senaste sju dagarna
* Trenden Aktiva användare de senaste 30 dagarna
* med mera

GA4-användare har fler alternativ för att anpassa och lägga till egna rapporter på hemskärmen.

![google-analytics-interfaces](assets/ga-to-aa_2.png)

Det här är antagligen det du saknar mest i Adobe Analytics. Det finns ingen hemskärm som är färdig för dig. Du kan dock enkelt konfigurera en anpassad Workspace för att replikera det du behöver från ovanstående lista och ange den som din landningsskärm. Det finns mer om detta ämne senare (eller se avsnitt 2.1.2.1 Adobe Workspace).

#### 2.1.2 Report Builder på plats

Förutom de enkla rapporter som analysverktygen ger innehåller varje verktyg också kraftfullare verktyg för att ta fram egna anpassade rapporter.

##### 2.1.2.1. Adobe Analytics Workspace

Det här är Adobe Analytics kraftcentrum, som sedan det introducerades 2017 har blivit en viktig plats för Analytics-analys och den främsta anledningen till att rapportavsnittet snart kommer att vara sluten.

Med det här verktyget kan du skapa rapporter med nästan fullständig frihet.

Rapporten kan delas upp i paneler och dessa paneler kan innehålla valfritt antal visualiseringar. Paneler kan ställas in på vanlig information, som datumintervall och vanliga segmentfilter.

Både panelerna och de visualiseringar som finns inuti dem kan storleksändras och dras runt så att objekt visas sida vid sida, eller skiktas. Om du vill jämföra två olika datauppsättningar sida vid sida kan du skapa paneler som delar 50/50 nedåt i mitten och visar de två webbplatserna sida vid sida för att enkelt kunna jämföra.

Det finns en mängd visualiseringar för användarna:

* Frihandstabell
* Kohortabell
* Utfall
* Flöde
* Diagram
   * Område (staplat och Ostaplat)
   * Linje
   * Spridning
   * Stolpstreck (staplade och Ostaplade)
   * Punkt
   * Munk
   * Histogram
   * Vågrätt streck (staplat och uppdelat)
* Karta
* Sammanfattningsblock
   * Sammanfattningsändring
   * Sammanfattningstext
   * Text (fritextfält för att ange extra information för att ge sammanhang)
* Venn

Varje panel och visualisering kan namnges och en beskrivning tillämpas för att ge sammanhang åt vad informationen visar.
I Adobe tillämpas segment (egentligen datafilter) retroaktivt och dessa kan dras in i kolumner i frihandstabellerna för att jämföra data sida vid sida. Om en användare till exempel vill jämföra två olika kategorier på sin plats för trafik, kan de skapa ett segment för kategori A och ett annat segment för kategori B.

![analytics-page-views-report](assets/ga-to-aa_3.png)

Frihandstabeller möjliggör flera kolumner och segmentering efter behov för att visualisera data som du vill.

Om du inte vill se en uppdelning efter datum drar och släpper du bara en annan dimension eller ett segment där för att se data på ett annat sätt. Använd till exempel segment för Enhetstyp och lägg sedan till en uppdelning efter operativsystem för dina Mobile-/Tablet-användare:

![analytics-compare-page-views-report](assets/ga-to-aa_4.png)

Workspace låter kreativiteten flöda - du begränsas inte till&quot;standarduppgraderingar&quot;. Ni kan bygga ut de visualiseringar ni behöver för att fördjupa er i de jämförelser ni behöver köra.

>[!TIP]
>
>Var inte rädd för att leka och utforska. Det finns så många sätt att tänka utanför lådan. Dessutom kan du validera vad du har skapat genom att visa vad du tycker. Upplevelsen hjälper er!

Du kan skapa direkt beräknade värden eller segment som bara finns i rapporten för att förhindra att ditt segment och din beräkningsdatabas översvämmas. På så sätt kan du skapa fokuserade objekt som behövs för specifika rapporter utan att blanda ihop organisationen med saker som inte kan användas i andra sammanhang.

Det här är bara en introduktion till det här verktyget. Det finns andra omfattande guider som hjälper dig att komma igång. När du har granskat de här guiderna kan du göra omfattande rapporter som följande:

![arbetsyta-kontrollpanel](assets/ga-to-aa_5.png)

Arbetsytor sparas inte automatiskt, så det är enklare att göra en engångs ad hoc-rapport utan att behöva svepa in rapportdatabasen.

En annan kraftfull funktion i arbetsytorna är möjligheten att använda interaktiva modifieringar i rapporter i form av listrutor. De här listrutorna fungerar inte på exporterade CSV-filer eller PDF-filer i dina rapporter. I den publicerade rapporten kan du dock uppdatera alla visualiseringar i en panel så att samma rapport visas under olika förhållanden. Du kan använda flera listrutor, och förutsatt att alternativen inte utesluter varandra, kan du använda den valda objektstacken för att presentera information på ett rent sätt.

>[!IMPORTANT]
>
>Om du vill läsa mer om hur du använder listrutor och frihandsbanor kan du läsa <https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-power-of-dropdown-filters-and-dimension-breakdowns-in-adobe/td-p/434680>

##### 2.1.2.2. Google Analytics: Kontrollpaneler, anpassade rapporter och sparade rapporter

Google har ett fåtal verktyg för att skapa rapporter i gränssnittet, men de har fortfarande samma utseende och begränsningar som rapportavsnittet.

För dem som står i Google Analytics när du läser det här kanske du säger: &quot;Vänta en sekund, vad är det med Google Data Studio, är inte det bättre motsvarigheten till Adobe Workspace?&quot; Ja, men Data Studio är inte tekniskt en del av Analytics-verktyget och möjliggör anslutningar till olika datakällor. Det här verktyget beskrivs senare i avsnittet&quot;Utökad rapportåtkomst&quot;, särskilt avsnitt 2.2.3.

Med Google Dashboards och Custom Reports kan du samla flera visualiseringar i en rapport, men till skillnad från Workspace är du fortfarande låst i enkla korrelationer och vilka data som kan placeras i vilka kolumner.

I Anpassade rapporter är en av de största utmaningarna när du skapar ett filter. Den gäller alla rapportflikar. Det finns inget sätt att jämföra två olika filter i samma rapport.

För ytjämförelser är det själva jobbet. De liknar alla Adobe äldre kontrollpaneler, anpassade rapporter och bokmärken. Grundläggande verktyg som uppfyller era behov och som ingår i rapportsviten.

#### 2.1.3 Rapporter

Både Google och Adobe har navigerbara rapporter som är per-byggda tabeller och grundläggande tidslinjediagram baserade på en dimension.

##### 2.1.3.1. Adobe Analytics-rapporter

Adobe Analytics har också ett rapportavsnitt, som fasas ut till förmån för Analysis Workspace. Det här gränssnittet har faktiskt lanserats som slutprodukt eftersom Workspace är ett kraftfullare verktyg. De flesta av dessa tabeller kan enkelt byggas och ändras. Adobe är mer utspridda och det här kan vara skrämmande:

![analytics-site-metrics](assets/ga-to-aa_6.png)

Eftersom de flesta av ovanstående är tillgängliga via Workspaces ger jag en kort översikt över dessa avsnitt och hur de hänger ihop med Google Analytics, och jag sätter fokus på de rapporter som fortfarande är relevanta.

Webbplatsstatistik är vad du förväntar dig, det omfattar standardmått (sidvisningar, unika besökare, besök och anpassade händelser som du har konfigurerat). Detta liknar beteenderapporten GA, men innehåller också en del av vad du skulle hitta i Audience (eftersom Adobe inte delar upp mättyperna).

Här finns &quot;Bot&quot;-rapporter. Trafik från robotar ingår inte i alla dina standardrapporter, men det finns två rapporter som ger insikt i vad som händer och vilka botar som kommer till din webbplats. Det här är särskilt bra om du ställer in anpassade Bot Rules för att exkludera kända spammer-botar som ofta kommer in på webbplatsen. Du kan få insikt i vad de här boterna gör utan att dina huvudrapporter översvämmas, men den trafiken. Bot-rapporter är för närvarande inte tillgängliga via Workspace (men med de nya rapporteringsfunktionerna kan användarna snart få tillgång till den här informationen också).

Webbplatsinnehåll är en gruppering av Adobe standarddimensioner: Sidnamn, Webbplatsavsnitt, Hierarkier, Servrar med mera. Alla dessa dimensioner är tillgängliga i Workspace.

Mobilen är en gruppering av mobilenhetsspecifika data, inklusive enheter, enhetstyper med mera. Dessa finns i Workspace.

Banor är inte tillgängliga i Workspace. Workspace har ett flödesdiagram där du kan se in- och utflödena för en sida/ett värde. Med Banor kan du däremot se de vanligaste banorna som används på webbplatsen. Som standard är Sidor den första sökvägsrapporten som är konfigurerad för dig. Du kan emellertid aktivera detta för anpassade utkast, t.ex. ett värde för Sidtyp. Du kan titta på en del av sidtypen. Det andra jag personligen gillar med banor är det enkla sätt som informationen presenteras på... Flödesdiagrammet på arbetsytan (beroende på hur mycket du försöker titta på) kan bli överväldigande. Jag rekommenderar att du testar båda ... de båda har ett användande och värde beroende på vad du försöker uppnå. Det bör noteras att alla dimensioner kan användas i flöden, medan Pathing måste ställas in på en Prop på Admin-panelen.

Trafikkällor, kampanjer och marknadsföringskanaler liknar alla förvärvsrapporten hos Google. Traffic Sources fokuserar också på Actual Referrers, Campaigns Focuses on your Campaign Codes och Marketing Channels fokuserar också på Campaign Codes, men tillämpar även extra logik som bestäms av er för hur informationen ska behandlas. Adobe ger större frihet att sätta upp regler. Google gör däremot många saker för dig, och det här är en förändring av tankeförmågan. Som standard är Google attribuering för kampanjkoder sex månader. Adobe tillskrivs som standard en vecka. Detta kan ändras i dina administratörsinställningar, men i Workspace kan du faktiskt använda anpassad attribuering ovanpå vilken dimension som helst, vilket ger dig mycket större flexibilitet direkt.

Bevaranderapporter för besökare och besökarprofilrapporter liknar målgruppsrapporter i Google Analytics. Bevarandet fokuseras mer på returfrekvensen, medan besöksprofilen fokuserar mer på användarnas geografiska och tekniska marknadsföring.

Rapporterna om anpassad konvertering och anpassad trafik är båda anpassade dimensionsrapporter. Konverteringar är eVars. Du kan ange en anpassad förfallotid till värdet som träff, besök, månad och år. Det här värdet är beständigt för en användare under den konfigurerade tidsramen om det inte skrivs över. Trafikvariablerna är avtryck. Du kan också ställa in dessa för Pathing Reports eller som listobjekt som delar upp flera värden baserat på en avgränsare som du väljer.

Media är till exempel för videoklipp eller ljudfiler där du har ställt in särskild mediespårning.

Anpassade rapporter är ett avsnitt där en användare kan anpassa kolumner och uppdelningar som de har skapat i rapportgränssnittet och spara dem som en anpassad rapport. Men som nämnts ovan, eftersom Workspace tillåter så mycket kraftfullare nedbrytning och korrelationer, bör allt som är anpassat göras där. Det här var en bra lösning innan Workspace existerade.

Avsnittet Bokmärken liknar Egna rapporter, där ofta använda rapporter kan markeras i rapportgränssnittet så att de blir lättare att hitta.

Dashboard var en äldre produkt som gjorde det möjligt att kombinera rapportlets med data till en enda visualisering. Funktionen i Workspace (avsnitt 2.1.2.1) är dock så mycket enklare att arbeta med att den bara finns som en åtkomstpunkt till äldre rapporter som bör byggas om innan den här funktionen upphör att gälla.

Med målgrupper kan användare skapa en rapport baserad på ett mål inom en viss tidsram. Teamen övervakar kampanjer för att se om de är på rätt väg för att nå sina trafikmål.

Alla rapporter här tillåts för flera måttkolumner och dimensionsanalyser. Men enkelheten i visualiseringarna och en del av logiken bakom vilka element som kan korreleras kan ibland vara frustrerande.

##### 2.1.3.2 Rapporter från Google Analytics

Google Analytics delar upp rapporterna i följande avsnitt: Realtime, Audience, Acquisition, Behavior, and Conversations (i GA3) och i Lifecycle (med underavsnitten: Acquisition, Engagement, Monetization, Retention) och User (med underavsnitten Demographics and Tech).

![google-analytics-interface-compare](assets/ga-to-aa_7.png)

Du kan göra vissa smärre förändringar av dessa visualiseringar, lägga till en sekundär dimensionsbrytning, ändra visualiseringen, skapa ett filter på data och mycket mer. Du kan spara dina anpassningar som en sparad rapport.

Dessa ger snabba och enkla insikter om era data. Du kan dock inte jämföra saker som Användare med sidvyer för en sida i samma tabell, och du kan inte lägga till mer än en extra dimension om du vill se ytterligare data.

De här är bra för snabba analysdata, men om du verkligen behöver gräva djupt, har de begränsningarna.

### 2.2. Utökad rapportåtkomst

Förutom&quot;Rapportering på plats&quot; erbjuder de flesta verktyg utökade funktioner som gör att du kan ta analysen utanför verktygen och skapa något lite mer anpassat.

#### 2.2.1. Adobe Analytics Report Builder (Microsoft® Excel Extension)

Workspace är ett bra verktyg, men ibland behöver du få in data i ett anpassat kalkylblad, kanske så att du kan sammanfoga flera datakällor. Det är här som Report Builder kommer till pjäsen.

Report Builder är en plugin för Microsoft® Excel som gör att du kan skapa anslutningar till dina Adobe Analytics-data för att hämta in tabelldata som du kan hantera i Excel. För att kunna använda detta effektivt skulle du hämta data till vissa rådataflikar, sedan använda Excel-cellreferenser för att hämta data från dessa flikar till en enda konsoliderad rapport och sedan skapa diagram och visualiseringar.

>[!NOTE]
>
>Report Builder har en speciell behörighet som måste tillämpas på dina användare för att få tillgång till det här plugin-programmet. Detta bör beviljas användare som har lärt sig att använda verktyget på rätt sätt.

#### 2.2.2. Adobe Analytics API Connection

Om du vill att Adobe Analytics-data ska kunna samlas in av något annat än Excel, och du vill att bearbetade data, inklusive undantag för robotregler, ska du använda Adobe API för att hämta data direkt. Bearbeta sedan data med hjälp av ett skript eller lägg till dem i en databas för användning med ett annat system.

Det bör noteras att API:t fortfarande hämtar in korrelationsdata med de indelningar och segment som anges i pull-begäran.

Adobe Workspace (Avsnitt 2.1.2.1) använder API:t för att skapa rapporter, och om du aktiverar felsökningsläget i Workspace visas de exakta API-anrop som används. Det här är ett snabbt sätt att bygga ut API-anrop. Genom att använda Workspace för att skapa och validera data som du vill hämta använder du dessa API-anrop för att få ut data till din egen bearbetning.


#### 2.2.3. Google Analytics Data Studio

Om du har läst vidare vet du redan från början att jag nämnde Data Studio som en motsvarighet till Adobe Workspace. Med Data Studio kan du hämta in Google Analytics-data, men även data från andra källor. Detta är bra om du vill konsolidera analysdata med andra insamlade data. I Google Analytics finns dock samma typ av visualiseringsbegränsningar. Det sätt på vilket raderna och kolumnerna formateras är fortfarande begränsat.

Det är fortfarande ett kraftfullt verktyg, och jag vill inte hindra folk från att använda det på något sätt. Min personliga erfarenhet är att jag tycker att det stelbenta beteendet är ganska begränsat.


#### 2.2.4. Google-kalkylbladstillägg

För egen del är Google kalkylbladstillägg det självklara valet när jag behöver hämta in data från Google Analytics. Även om jag behöver göra flera anslutningar till mina GA-tabeller kan jag referera till cellerna från rådata och bygga ut de rapporter jag behöver. Sedan visualiserar jag dem med grafikfunktionerna i Google Spreadsheet.


## 3. Export av rådata

När ni verkligen behöver rådata kan både Adobe och Google hämta in information på det här sättet.

### 3.1. Datafeed för Adobe

I avsnitt 2.2.2 nämnde jag att Adobe Analytics API hämtade från&quot;bearbetade data&quot;. Rådatafeeden hämtar data som bearbetas av de bearbetningsregler som har ställts in på administratörspanelen, men dessa rådata innehåller alla data som har uteslutits överallt.

Det innebär att alla era Bot-undantag, interna IP-filtrerade data och andra exkluderade data finns i rådataflödena. Det finns flaggor som identifierar dessa data, så om du bygger en datasjö kan ingenjörsteamet skapa logik för att bearbeta dessa data därefter.

Rådataflödena kan anpassas för att skicka alla datakolumner, eller bara specifika kolumner om du behöver en mer fokuserad feed.

Feeds kan skickas direkt till FTP, SFTP eller S3.


### 3.2. Google Big Query

Tyvärr är detta ett Google-verktyg som jag inte har någon erfarenhet av. Teoretiskt sett bör det likna Adobe Data Feed, som gör det möjligt för teknikerna att få tillgång till rådata från ditt Google Analytics-konto.

I stället för att tillhandahålla en fullständig dump av rådata, ger det dina tekniker åtkomst till data via SQL-frågor för att hämta riktade rådata eller alla kolumner med rådata.

## 4. Slutsats

Precis som alla andra system behövs övningar för att du ska känna dig bekväm med verktyget. Förhoppningsvis hjälper den här guiden dig att komma igång eller ger tips om hur du kan använda Adobe Analytics bättre.

Jag vill emellertid betona att jag skulle rekommendera att använda både Adobe Analytics och Google Analytics i er implementeringsstrategi (även om Google Analytics endast är den kostnadsfria versionen). Detta gör att du kan ha ett säkerhetskopieringssystem som ser till att du har data eftersom inget system är ofelbart.

Du har tillgång till många resurser utöver den här guiden som kan förbättra din strategi:

* [Adobe Experience League](https://experienceleague.adobe.com/#home) - Innehåller självstudiekurser, videor, dokumentation och communityforum
* [Adobe-användargrupper](https://analytics-augs.adobe.com/) - Ett nav med communityaktiviteter som hjälper användare att ansluta till varandra och förbättra sina implementeringar.
* [Adobe Analytics-användargrupper YouTube Channel](https://www.youtube.com/channel/UCQOHnCs7KZgsuFHVzwboQuA) - Kunde inte skapa en Adobe Analytics-användargruppsession? Titta på sessioner med tidigare användargrupper över hela världen för att lära dig mer om hur andra använder verktyget.
* [Mät Chat Slack channel](https://www.measure.chat/) - Kommunicera med Adobe Analytics-användare över hela världen och dela branschinformation, ställa frågor till kollegor och delta i mät intressegrupper.
* med mera!

## Upphovsman

Det här dokumentet har skrivits av:

![Jennifer Dungan](assets/Jennifer_Dungan_Headshot150.png)

Jennifer Dungan, Optimization Manager Analytics på Torstar

Adobe Analytics Champion

