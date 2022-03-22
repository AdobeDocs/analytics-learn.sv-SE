---
title: A Comprehensive Guide for Transitioning to Adobe Analytics from Google Analytics
description: En av de största utmaningarna när det gäller att gå över mellan olika verktyg är att lära sig var man hittar motsvarande funktionalitet och hur man använder den effektivt. Den här diskussionen ingår i en större guide som underlättar övergången till Adobe Analytics.
feature: Third-party Integration
role: User
level: Beginner
doc-type: feature video
thumbnail: 34749.jpg
kt: 9830
exl-id: b2be6081-a1c0-4435-affb-454ed5a74662
source-git-commit: de78868e07b0fa59a7babc092c463bbe4d8e2da7
workflow-type: tm+mt
source-wordcount: '3690'
ht-degree: 0%

---

# A Comprehensive Guide for Transitioning to Adobe Analytics from Google Analytics

## 1. Introduktion

En av de största utmaningarna när det gäller att gå över mellan olika verktyg är att lära sig var man hittar motsvarande funktionalitet och hur man använder den effektivt. Diskussionen är en del av en större guide som hjälper användare att övergå till Adobe Analytics (antingen som en ny användare eller en som kommer från Google Analytics) på ett enklare sätt. En ingående jämförelse med GA. som det mest troliga komparativa verktyg som de flesta användare kommer att känna till, är till för att hjälpa användarna att koppla befintliga kunskaper till den nya verktygsuppsättningen. Det finns ingen ersättning för praxis. Detta hjälper dig att komma igång och förhoppningsvis minska de frustrationer du kan stöta på under den här tiden (eller till och med som en uppdaterare när du har börjat lära dig saker och ting).

Vi bör också bara göra en snabb jämförelse av terminologi:

| **Beskrivning** | **Adobe Analytics** | **Google Analytics** |
|--------------------------------------------------------------------------------------------------------------------------------|---------------------|----------------------|
| Ett händelsemått som representerar en sida (eller skärm i ett program) har visats | Sidvisning | Sidvy |
| Ett mätvärde som representerar en grupp interaktioner på webbplatsen eller appen som äger rum inom samma tidsram | Gå in på | Session |
| Ett mätvärde som definierar en identifierad enhet (baserat på flera kriterier som cookies och andra beteendemönster för att sammanfoga användarinformation) | Unik besökare | Användare |

## 2. Gränssnitten

En av de saker jag ser oftast när folk jämför Adobe Analytics och Google Analytics är att Adobe har mycket att göra - det är skrämmande för folk. Detta är sant, men det är också; tro på det eller inte, en styrka, inte en svaghet. Adobe har ett brett utbud av verktyg och flexibilitet i datavisualiseringen, vilket ger dig större frihet att skapa det du behöver.

Vi börjar med att titta på rapporten&quot;in-site&quot;.

### 2.1. Rapportering på plats

#### 2.1.1 Hemskärm

Både Adobe Analytics och Google Analytics kan anpassa den första vyn som en användare ser när han/hon loggar in.

##### 2.1.1.1 Arbetsyta/hemskärm för anpassad uppsättning (Adobe Analytics)

Adobe Analytics förutsätter inte att man skapar en färdig rapport som alla användare kan se vid inloggning. Standardstartsidan tar användaren till startskärmen för arbetsytan, som visar alla arbetsyterapporter som de har skapat eller delats med användaren. Dessutom kan varje användare ange vilken som helst av dessa rapporter som hemskärm om de så önskar.

![image1](assets/ga-to-aa_1.png)

Mer information om arbetsytan finns nedan. Se avsnitt 2.1.2.1

>[!TIP]
>
>Skapa/dela några standardrapporter för din organisation så att de får en startpunkt för att se information utan att behöva dyka upp i sina egna rapporter direkt.



##### 2.1.1.2 Insikter från startskärmen (Google Analytics)

* Google Analytics hemskärm har några färdiga visualiseringar för dig.  De här täcker saker som:
* Användare, sessioner, avhoppsfrekvens och sessionsvaraktighet de senaste 7 dagarna
* Användare efter tid på dygnet de senaste 30 dagarna
* Aktuella användare just nu och de viktigaste aktiva sidorna
* Trafikkanal, källa/medium och hänvisningar under de senaste 7 dagarna
* Sessioner per land de senaste 7 dagarna
* De vanligaste sidorna för de senaste 7 dagarna
* Trenden Aktiva användare de senaste 30 dagarna
* med mera

I GA4 har användare fler alternativ för att anpassa och lägga till egna rapporter på hemskärmen.

![image2](assets/ga-to-aa_2.png)

Detta är antagligen det du kommer att sakna mest när du kommer till Adobe; de inte har någon sådan hemskärm fördefinierad för dig, men du kan enkelt skapa en anpassad arbetsyta för att replikera det du behöver från ovanstående och om du väljer att göra det, ange den som din startskärm. Mer information om detta senare (eller se avsnitt 2.1.2.1 Adobe Workspace).

#### 2.1.2 Report Builder på plats

Förutom de enkla rapporter som analysverktygen ger innehåller varje verktyg också kraftfullare verktyg för att ta fram egna anpassade rapporter.

##### 2.1.2.1 Adobe Analytics Workspace

Det här är Adobe Analytics kraftcentrum, som sedan det introducerades 2017 har blivit en viktig plats för Analytics-analys och den främsta anledningen till att rapportavsnittet snart kommer att vara sluten.

Med det här verktyget kan du skapa rapporter med nästan fullständig frihet.

Rapporten kan delas upp i paneler och dessa paneler kan innehålla valfritt antal visualiseringar. Paneler kan ställas in på vanlig information, som datumintervall och vanliga segmentfilter.

Både panelerna och de visualiseringar som finns inuti dem kan storleksändras och dras runt så att objekt visas sida vid sida, eller skiktas. Om du vill jämföra två olika datauppsättningar sida vid sida kan du skapa paneler som delar 50/50 nedåt i mitten och visar de två webbplatserna sida vid sida för att enkelt kunna jämföra.

Det finns en mängd visualiseringar för användarna:

* Frihandstabell
* Kohorttabell
* Utfall
* Flöde
* Diagram
   * Område (staplat och Ostaplat)
   * Linjediagram
   * Spridning
   * Stolpstreck (staplade och Ostaplade)
   * Punkt
   * Ringdiagram
   * Histogram
   * Vågrätt streck (staplat och uppdelat)
* Mappa
* Sammanfattningsblock
   * Sammanfattningsändring
   * Sammanfattningstext
   * Text (fritextfält för att ange extra information för att ge sammanhang)
* Venn

Varje panel och visualisering kan namnges och en beskrivning tillämpas för att ge sammanhang åt vad informationen visar.
I Adobe tillämpas segment (egentligen datafilter) retroaktivt och dessa kan dras in i kolumner i frihandstabellerna för att jämföra data sida vid sida. t.ex. om en användare vill jämföra två olika kategorier på sin plats för trafik, de kan skapa ett segment för&quot;kategori A&quot; och ett annat segment för&quot;kategori B&quot;.

![image3](assets/ga-to-aa_3.png)

Frihandstabeller möjliggör flera kolumner och segmentering efter behov för att visualisera data som du vill.

Vill du inte se någon uppdelning efter datum? Bara dra och släpp ytterligare en dimension eller ett segment där för att se data på ett annat sätt.. som att t.ex. använda segment för enhetstyp, och lägg sedan till en uppdelning efter operativsystem för dina Mobile-/surfanvändare:

![image3](assets/ga-to-aa_4.png)

Med Workspace kan kreativiteten flöda - du begränsas inte till&quot;standarduppgraderingar&quot;. Ni kan bygga ut de visualiseringar ni behöver för att fördjupa er i de jämförelser ni behöver köra.

>[!TIP]
>
>Var inte rädd för att leka och utforska, det finns så många sätt att tänka utanför lådan här, se vad du kan göra! Men du måste också kontrollera att du försöker validera att det du har skapat verkligen visar vad du tror att det är. Upplevelsen här kommer att hjälpa!

Man kan till och med skapa direkt beräknade mätvärden eller segment som bara finns i rapporten (vilket förhindrar att segmentet och beräkningsdatabasen översvämmas), men också se till att man kan skapa fokuserade objekt som behövs för specifika rapporter utan att blanda ihop organisationen med saker som inte är särskilt användbara i andra sammanhang.

Det här är bara en introduktion till det här verktyget, det kommer att finnas andra mer omfattande guider som hjälper dig att komma igång, men när du gör det kan du skapa omfattande rapporter som:

![image3](assets/ga-to-aa_5.png)

Observera också att arbetsytor inte sparas automatiskt, så det är enklare att göra en engångs ad hoc-rapport utan att behöva svepa in rapportdatabasen.

En annan kraftfull funktion i arbetsytorna är möjligheten att använda interaktiva modifieringar i rapporter i form av listrutor. De här listrutorna fungerar inte med exporterade CSV-filer eller PDF-filer i dina rapporter, men i liverapporten kan du uppdatera alla visualiseringar i en panel för att visa samma rapport under olika förhållanden. Du kan använda flera listrutor, och så länge alternativen inte utesluter varandra kommer de markerade objekten att staplas så att du kan presentera information på ett rent sätt.

>[!IMPORTANT]
>
>Mer information om hur du använder listrutor och frihandsbanor finns i <https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-power-of-dropdown-filters-and-dimension-breakdowns-in-adobe/td-p/434680>

##### 2.1.2.2 Google Analytics: Kontrollpaneler, anpassade rapporter och sparade rapporter

Google har ett fåtal verktyg för att skapa rapporter i gränssnittet, men de har fortfarande samma utseende och begränsningar som rapportavsnittet.

För dem som står i Google Analytics när du läser det här kanske du säger: &quot;Vänta en sekund, vad är det med Google Data Studio, är inte det bättre motsvarigheten till Adobe Workspace?&quot; och du skulle ha rätt, men eftersom Data Studio inte är tekniskt en del av analysverktyget och tillåter anslutningar till olika datakällor beskrivs det här verktyget senare i avsnittet&quot;Utökad rapportåtkomst&quot; i den här diskussionen (särskilt avsnitt 2.2.3)

Med Google Dashboards och Custom Reports kan du samla flera visualiseringar i en rapport, men till skillnad från Workspace är du fortfarande låst i enkla korrelationer och vilka data som kan placeras i vilka kolumner.

I Anpassade rapporter är en av de största utmaningarna att när du skapar ett filter gäller det alla flikar i rapporten ... det finns inget sätt att jämföra två olika filter i samma rapport.

För ytjämförelser utförs jobbet. De liknar alla Adobe äldre kontrollpaneler, anpassade rapporter och bokmärken. Grundläggande verktyg som uppfyller era behov och som ingår i rapportsviten.

#### 2.1.3 Rapporter

Både Google och Adobe har navigerbara rapporter som är per-byggda tabeller och grundläggande tidslinjediagram baserade på en dimension.

##### 2.1.3.1 Adobe Analytics Reports

Adobe Analytics har också ett rapportavsnitt, men i stort sett fasas detta ut till förmån för deras Analysis Workspace (och i själva verket har slutet av livet annonserats för det här gränssnittet, sedan Workspace [Avsnitt 2.1.2.1] är ett mycket kraftfullare verktyg) där de flesta av dessa tabeller kan byggas och ändras enklare. Adobe är mer utspridda och det här kan vara skrämmande:

![image3](assets/ga-to-aa_6.png)

Eftersom de flesta av ovanstående är tillgängliga via Workspaces ger jag en kort översikt över dessa avsnitt och hur de hänger ihop med Google Analytics, och jag vill betona de rapporter som fortfarande är relevanta.

Webbplatsstatistik är vad du förväntar dig, det omfattar standardmått (sidvisningar, unika besökare, besök samt anpassade händelser som du har konfigurerat). Detta liknar beteenderapporten GA, men innehåller också en del av vad du skulle hitta i Audience (eftersom Adobe inte delar upp mättyperna).

Här hittar du även &quot;Bot&quot;-rapporter, trafik från bots tas inte med i alla dina standardrapporter, men det finns två rapporter som gör att du kan se vad som händer och vilka botar som kommer till din webbplats. Det här är särskilt bra om du ställer in anpassade Bot Rules för att exkludera kända spammer-botar som ofta kommer in på webbplatsen. Du kan få insikt i vad de här boterna gör utan att dina huvudrapporter översvämmas, men den trafiken. Bot-rapporter är för närvarande inte tillgängliga via Workspace (men nya rapporteringsfunktioner som kommer snart gör det möjligt för användarna att hämta den här informationen även).

Webbplatsinnehåll är en gruppering av Adobe standarddimensioner: Sidnamn, Webbplatsavsnitt (kanaler), Hierarkier (ett sätt att skapa anpassade fördjupningsrapporter för organisationen inom din webbplats), Servrar (detta är särskilt användbart om du har flera underdomäner på din webbplats, eller om du taggar flera webbplatser tillsammans i en spårningssvit) osv. Alla dessa finns i Workspace.

Mobile är en gruppering av Mobile enhetsspecifika data, som enheter, enhetstyper etc. Alla dessa finns i Workspace.

Banor är en annan av dessa &quot;inte helt tillgängliga i arbetsytan&quot;-objekt... medan arbetsytan har ett flödesdiagram kan du bara se in- och utflödena för en sida/ett värde.. medan du kan använda banor för att se de vanligaste sökvägarna som används på webbplatsen. Som standard är Sidor den första sökvägsrapporten som är konfigurerad för dig, men du kan aktivera den för anpassade utkast (till exempel om du håller reda på ett värde för sidtyp, kan du titta på en målning inom sidtyper. Det andra jag personligen gillar med banor är det enkla sätt som informationen presenteras på... Flödesdiagrammet på arbetsytan (beroende på hur mycket du försöker titta på) kan bli överväldigande. Jag rekommenderar att du testar båda ... de båda har ett användande och värde beroende på vad du försöker uppnå. Det bör noteras att alla dimensioner kan användas i flöden, medan Pathing måste ställas in på en Prop på Admin-panelen.

Rapporterna om trafikkällor, kampanjer och marknadsföringskanaler liknar alla rapporterna om förvärvet i Google. Traffic Sources fokuserar också på Actual Referrers, Campaigns Focuses on your Campaign Codes och Marketing Channels fokuserar också på Campaign Codes, men tillämpar även extra logik som bestäms av er för hur informationen ska behandlas. Jag tycker att Adobe ger mycket större frihet att sätta upp regler, att Google gör mycket åt dig och att det blir lite mer tankeförskjutning. Det bör också noteras att som standard är Google attribuering i kampanjkoder sex månader, medan Adobe är inställt på 1 vecka som standard. Detta kan ändras i dina administratörsinställningar, men i Workspace kan du faktiskt använda anpassad attribuering ovanpå alla dimensioner, vilket ger dig mycket större flexibilitet direkt.

Bevaranderapporter för besökare och besökarprofilrapporter liknar målgruppsrapporter i Google Analytics. Bevarandet fokuseras mer på returfrekvensen, medan besöksprofilen fokuserar mer på användarnas geografiska och tekniska marknadsföring.

Anpassad konvertering och Anpassad trafik är båda anpassade dimensionsrapporter, konverteringar är dina eVars (där du kan ange ett anpassat förfallodatum för värdet, t.ex. träff, besök, månad, år osv., och det här värdet kommer att finnas kvar för användaren under angiven tid om det inte skrivs över). Trafikvariablerna är dina utkast, men du kan också ställa in dem för Pathing Reports eller som listobjekt (som delar upp flera värden baserat på en avgränsare som du väljer).

Media är till exempel för videoklipp eller ljudfiler där du har ställt in särskild mediespårning.

Anpassade rapporter är ett avsnitt där en användare kan anpassa kolumner och uppdelningar som de har skapat i rapportgränssnittet och spara dem som en anpassad rapport. Men eftersom Workspace tillåter så mycket kraftfullare nedbrytning och korrelationer, bör allt som är anpassat bara göras där. Det här var en bra lösning innan Workspace fanns.

Avsnittet Bokmärken liknar Egna rapporter, där ofta använda rapporter kan markeras i rapportgränssnittet så att de blir lättare att hitta.

Dashboard var en äldre produkt som gjorde det möjligt att kombinera rapportlets med data till en enda visualisering. Funktionen i Workspace (Avsnitt 2.1.2.1) är dock så mycket enklare att arbeta med att den bara finns som en åtkomstpunkt till äldre rapporter som bör byggas om innan den här funktionen upphör att gälla.

Målgrupper är ett särskilt rapportområde där man kan skapa en rapport som baseras på ett mål inom en viss tidsram, så att man kan övervaka saker som kampanjer och se om de var på rätt spår för att nå sina trafikmål.

Alla rapporter här tillåts för flera måttkolumner och dimensionsanalyser. men enkelheten i visualiseringarna och en del av logiken bakom vilka element som kan korreleras kan ibland vara frustrerande.

##### 2.1.3.2 Google Analytics rapporter

Google Analytics delar upp rapporterna i följande avsnitt: Realtime, Audience, Acquisition, Behavior and Conversations (i GA3) och in i Lifecycle (med underavsnitten: Anskaffning, engagemang, intäktsgenerering, lagring) och användare (med underavsnitten: Demografi och teknik).

![image3](assets/ga-to-aa_7.png)

Du kan göra vissa smärre förändringar av dessa visualiseringar, lägga till en sekundär dimensionsbrytning, ändra visualiseringen, skapa ett filter på data osv. Du kan spara dina anpassningar som en sparad rapport.

Dessa ger er snabba och enkla insikter om era data. Du kan dock inte jämföra saker som Användare med sidvyer för en sida i samma tabell, och du kan inte lägga till mer än en extra dimension om du vill se ytterligare data.

De här är bra för snabba analysdata, men om du verkligen behöver gräva djupt, har de begränsningarna.

### 2.2. Utökad rapportåtkomst

Förutom&quot;Rapportering på plats&quot; erbjuder de flesta verktyg utökade funktioner som gör att du kan ta analysen utanför verktygen och skapa något lite mer anpassat.

#### 2.2.1 Adobe Analytics Report Builder (Microsoft Excel-tillägg)

Arbetsytan är ett utmärkt verktyg, men ibland behöver du få in data i ett anpassat kalkylblad, kanske så att du kan sammanfoga flera datakällor. Det är här som Report Builder kommer till pjäsen.

Report Builder är en plugin för Microsoft Excel som gör att du kan skapa anslutningar till dina Adobe Analytics-data för att hämta in tabelldata som du kan hantera i Excel. För att använda detta effektivt skulle du i allmänhet hämta in data på vissa rådataflikar, sedan använda Excel-cellreferenser för att hämta data från dessa flikar till en enda konsoliderad rapport och sedan skapa diagram och visualiseringar.

>[!NOTE]
>
>Report Builder har en speciell behörighet som måste tillämpas på dina användare för att få tillgång till det här plugin-programmet. Detta bör antagligen endast beviljas användare som har lärt sig att använda verktyget på rätt sätt.

#### 2.2.2 Adobe Analytics API Connection

Om du vill att din Adobe Analytics ska kunna hämtas av något annat än Excel, men ändå vill ha fördelarna med bearbetade data (inklusive undantag för robotregler), kan du använda Adobe API för att hämta data direkt och sedan bearbeta dem via skript eller lägga till dem i en databas för användning med ett annat system.

Det bör noteras att API:t fortfarande hämtar in korrelationsdata med de indelningar och segment som anges i pull-begäran.

Adobe Workspace (Avsnitt 2.1.2.1) använder faktiskt API:t för att skapa alla rapporter, och om du aktiverar felsökningsläget i Workspace visas de exakta API-anrop som används. Detta är ett snabbt sätt att bygga ut API-anrop genom att använda Workspace för att bygga och validera data som du vill hämta och sedan använda dessa API-anrop för att få ut data till din egen bearbetning.


#### 2.2.3 Google Analytics Data Studio

Om du har läst vidare kommer du redan ovan att veta att jag nämnde Data Studio som en motsvarighet till Adobe Workspace. Med Data Studio kan du hämta in Google Analytics-data, men även data från andra källor. Detta är bra om du vill konsolidera analysdata med andra insamlade data. Men när det gäller Google Analytics har jag funnit samma typ av visualiseringsbegränsningar som finns i Google Analytics. Det sätt på vilket raderna och kolumnerna formateras är fortfarande mycket begränsat i vad som kan göras.

Det är fortfarande ett kraftfullt verktyg, och jag vill inte avskräcka människor från att använda det på något sätt, men min personliga erfarenhet är att när jag har använt Workspace så länge tycker jag personligen att det stelbenta beteendet är ganska begränsat.


#### 2.2.4 Google kalkylbladstillägg

För egen del är Google kalkylbladstillägg det självklara valet när jag behöver hämta in data från Google Analytics. Visst måste jag göra flera anslutningar till mina GA-tabeller, men precis som Adobe Report Builder kan jag referera till cellerna från rådata och bygga ut de rapporter jag behöver och sedan visualisera dem med hjälp av diagramfunktionerna i Google kalkylblad.


## 3. Export av rådata

För de tillfällen då ni verkligen behöver rådata erbjuder både Adobe och Google möjligheten att hämta in information på det här sättet.

### 3.1. Datafeed för Adobe

I avsnitt 2.2.2 nämnde jag att Adobe Analytics API hämtade från&quot;bearbetade data&quot;. Rådatafeeden hämtar fortfarande in data som bearbetas av de bearbetningsregler som har ställts in på administratörspanelen (se till att dina rådata fördröjs så att alla dessa regler har slutförts innan rådatafeeden hämtas), men dessa rådata inkluderar alla data som har uteslutits överallt.

Det innebär att alla dina Bot-undantag, interna IP-filtrerade data osv. kommer att inkluderas i rådataflödena. Det finns flaggor som identifierar dessa data, så om du bygger upp en datasjö kan teknikteamet skapa logik för att bearbeta dessa data därefter.

Rådataflödena kan anpassas för att skicka alla datakolumner, eller bara specifika kolumner om du behöver en mer fokuserad feed.

Feeds kan skickas direkt till FTP, SFTP, S3 osv.


### 3.2. Google Big Query

Tyvärr är detta ett Google-verktyg som jag inte har haft någon erfarenhet av, men i teorin bör det likna Adobe Data Feed, som gör det möjligt för teknikerna att få tillgång till rådata från ditt Google Analytics-konto.

Men jag tror snarare än en fullständig dump av rådata, så att dina tekniker kan komma åt data via SQL-frågor, så att de kan hämta antingen riktade rådata eller om de vill att alla kolumner med rådata ska kunna hämtas in i en datasö.

## 4. Slutsats

Precis som alla andra system behövs övningar för att du ska känna dig bekväm med dem, men den här guiden kommer förhoppningsvis att hjälpa dig att komma igång, eller ge dig tips om hur du kan förbättra din användning av Adobe Analytics om du bara har skrapat på ytan.

Jag vill emellertid betona att jag skulle rekommendera att använda både Adobe Analytics och Google Analytics i er implementeringsstrategi (även om Google Analytics endast är den kostnadsfria versionen). Detta gör att du kan ha ett säkerhetskopieringssystem som ser till att du har data eftersom inget system är ofelbart.

Du har tillgång till många resurser utöver den här guiden som kan förbättra din strategi:

* [Adobe Experience League](https://experienceleague.adobe.com/#home) - Innehåller självstudiekurser, videor, dokumentation och communityforum
* [Adobe användargrupper](https://analytics-augs.adobe.com/) - Ett nav av communityaktiviteter som hjälper användare att ansluta till varandra och förbättra sina implementeringar - eftersom dessa är baserade i en viss tidszon är det bäst att även kontrollera vilka andra regioner som körs.
* [Adobe Analytics User Groups YouTube Channel](https://www.youtube.com/channel/UCQOHnCs7KZgsuFHVzwboQuA) - Kunde du inte skapa en användargruppsession i Adobe Analytics? Titta på sessioner med tidigare användargrupper över hela världen för att lära dig mer om hur andra använder verktyget.
* [Mät Chatt Slack-kanalen](https://www.measure.chat/) - Håll kontakt med Adobe Analytics-användare över hela världen och dela med dig av branschinformation, ställa frågor till andra och delta i mät intressegrupper.
* med mera!

## Upphovsman

Det här dokumentet har skrivits av:

![Jennifer Dungan](assets/Jennifer_Dungan_Headshot150.png)

Jennifer Dungan, Optimization Manager Analytics på Torstar

Adobe Analytics Champion

