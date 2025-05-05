---
title: Ladda ned spelningsboken för Adobe Analytics-implementering
description: Ett dokument om affärskrav (kallas ofta BRD) är en mycket viktig dokumentation som viktiga intressenter, affärsanvändare och teknikanvändare kommer att vilja samarbeta med. Här kan du dokumentera alla dina önskade nyckeltal, rapporteringskrav och alla datapunkter du vill se när implementeringen av AA är klar.
feature: Implementation Basics
topic: Administration
role: Admin
level: Beginner
doc-type: article
thumbnail: 10530.jpg
kt: 10530
exl-id: aab53a12-3f11-49c9-aba4-dc926bcf776b
source-git-commit: df00d4fb8cc5093903ed4628dfe12f152294123a
workflow-type: tm+mt
source-wordcount: '1802'
ht-degree: 0%

---

# Ladda ned spelningsboken för Adobe Analytics-implementering

[Hämta spelboken](assets/aa-implementation-playbook.xlsx) innan du börjar.

## Fliken Krav för företag

**VAD:** Ett dokument med affärskrav (kallas ofta BRD) är en mycket viktig dokumentation som viktiga intressenter, affärsanvändare och teknikanvändare kommer att vilja samarbeta med. Här kan du dokumentera alla nyckeltal, rapporteringskrav och alla datapunkter du vill se när implementeringen av Adobe Analytics (AA) är klar.

**VARFÖR:** Detta fungerar som en brytpunkt för den dokumentation som följer (SDR, teknisk specifikation osv.) och är en gemensam sanningskälla för en överenskommen slutstat i AA. I det här dokumentet ordnas tankar mellan olika team i organisationen i en och samma riktning för att komma vidare med att bygga ut eller förbättra implementeringen.

**HUR:** Att dokumentera affärskraven görs vanligtvis av AAA:s slutanvändare, men det är viktigt att få feedback från teknikanvändare eftersom det kan finnas tekniska problem att notera, och vissa datapunkter kan kräva mer arbete än andra, vilket prioriterar.

Fråga dig själv:&quot;vad det är vi vill spåra på vår webbplats&quot;,&quot;vilka datapunkter som är viktiga för mig när jag rapporterar användning&quot; och viktigast av allt,&quot;hur ska dessa datapunkter kunna fatta beslut&quot;. Det är viktigt att se till att alla era affärskrav är kopplade till en datapunkt som kan användas för att fatta affärsbeslut. Det kan till exempel vara frestande att vilja spåra varje klick på webbplatsen, men i slutet av dagen, vilka insikter ger du av den rapporten?

Börja med att fylla i kolumn C i skärmbilden nedan (affärskrav). Det ska vara som&quot;Hur många interna sökningar som görs på vår webbplats&quot; eller&quot;Vilken intern kampanjplats är mest effektiv när det gäller visningar&quot;. När du har fyllt i den här detaljnivån kan du gå tillbaka och fylla i kolumn B (Kategori) och gruppera kraven i kategorier som &quot;Sök&quot; eller &quot;Intern kampanj&quot;, som passar bra ihop med tekniska specifikationer.

Du kan även ange om du tänker använda en eVar, händelse, prop eller kombination för att uppnå det du vill spåra.

Slutligen fungerar kolumnen Implementeringsstatus som en statuskontroll när du börjar lägga till saker på webbplatsen.

![Dokument för affärskrav](assets/brd-template.png)

## Variabelmappning, flik (tagging doc/SDR)

**VAD:** Ett tagging-dokument (kallas ofta SDR) är en viktig dokumentation som är värdefull för både tekniker- och affärsanvändare av AA. Den visar alla variabler som används av rapportsviter tillsammans med all relevant information om variabelinställningarna, hur variabeln implementeras och vad den har för syfte att rapportera. Precis som med dina egenskapsdokument bör det här vara ett välstyrt Excel-dokument med en punktperson som ansvarar för att hålla det uppdaterat när taggningsförbättringar eller implementeringsändringar införs.

**VARFÖR:** Det här dokumentet har många syften, men det viktigaste är följande:

* För alla som är nyanställda i er implementering (nyanställd, företagsägare som vill få en bättre förståelse för tillgängliga rapporter osv.) det här dokumentet ger den bästa bilden av alla variabler som implementerats och vad de är avsedda för så att individer kan vara självbetjänade när det gäller att lära sig din AA-konfiguration.
* För produktägaren/teknikanvändaren fungerar det här dokumentet som en påminnelse om hur andra variabler ställs in och vilka variabler som är tillgängliga för användning när en ny dimension läggs till.

**HUR:** Börja med att lista alla variabler som inte finns i Adobe (sida, produkt, geo osv.) samt eVars, props, events och listvariabler i ett Excel-dokument. Detta bör ha en flik per webbplats/rapportserie.
För var och en av dessa dimensioner lägger jag till följande kolumner:
* **Namn:** Ange ett enkelt och kort namn som kan förstås av de flesta. Detta bör vara tillräckligt intuitivt så att en ny användare kan hämta det och förstå vad variabeln är avsedd att fånga.
* **Beskrivning:** Mer information om vad variabeln används för och vilka data den spårar. Jag håller det här kort och enkelt och ser till att det matchar beskrivningen som används i gränssnittet. Helst vill jag inte att mina användare någonsin ska behöva läsa taggningsdokumentet. När en ny dimension har ställts in på administratörens serverdel lägger jag till samma beskrivning där. På så sätt kan användaren klicka på informationsikonen direkt i Workspace för att förstå vad en dimension är - du behöver inte ta fram ett Excel-dokument!

![Förenklad sid-URL](assets/page-url-simplified.png)

* **Kod:** Koden från serverdelen som anger värdet. Detta kan vara fältet från datalagret på sidan eller så kan du anropa att detta görs med en startregel, en bearbetningsregel osv.
* **Klassificeringsrapporter:** Anropa alla klassificeringsrapporter som utförs med Klassificeringsimporteraren eller Klassificeringsregelbyggaren
* **Lösningsomfång:** Jag tycker att det är användbart att lista ut alla egenskaper (åtminstone de som använder fler än standardvariabler) i små kolumner och lägga till en bock för varje dimension som anges för den egenskapen. På så sätt kan du enkelt filtrera efter en viss egenskap och snabbt se var en viss dimension ställs in.
* **Konfiguration:** Användargränssnittsinställningar för administratörer för varje variabel (t.ex. för eVars - utgångsdatum, allokering, försäljning osv.)

Skärmbild av SDR-exempel:
![Exempel-SDR](assets/sample-sdr.png)

Vi rekommenderar även att du använder det här taggningsdokumentet för att hålla reda på alla kostnadsfria variabler och alla skräppostvariabler. När en dimension inte längre är användbar behöver den oftast tas bort en stund. Även efter det kan cachning förekomma, eller så kanske du inser att dimensionen också ställdes in någon annanstans. Det är inte lätt att rensa upp dimensionerna, och det krävs ofta tålamod. Här följer några tips om hur du kan dölja skräpet under sängen så att dina användare inte blir förvirrade när de håller reda på det.

* Alla dimensioner/händelser som inte används är antingen kostnadsfria eller tas bort
   * Om dimensionen har skräppostvärden de senaste 90 dagarna tas den bort
   * Om dimensionen är fri och tydlig under åtminstone de senaste 90 dagarna är den &#39;fri&#39;
   * Markera dem som så under Namn i taggningsdokumentet, så att du enkelt kan filtrera efter dem. Jag håller dessa omarkerade i taggningsdokumentet (Excel-datafilter) så att användarna inte kan se dem
   * Markera dessa som eVar-namn i gränssnittet så att användare inte hittar dem i en sökning (d.v.s. &#39;(v6)&#39;) och ta bort beskrivningen i gränssnittet
* När en ny dimension behövs kan du enkelt filtrera efter &quot;gratis&quot; i kolumnen &quot;Namn&quot; för att hitta en ren dimension att använda
* För de dimensioner och händelser som tas bort rekommenderar jag att du håller reda på dem med Workspace:
   * Skapa ett projekt som bara är synligt för administratörer med tre tabeller: eVars, props och events. Jag använder &#39;instanser&#39; för de specifika eVars, och för props skapar jag HIT-segment med &#39;prop5 exists&#39;.
   * Ange datum till de senaste 90 dagarna
   * Använd ovanstående som rader i de tre tabellerna tillsammans med förekomster
   * Så fort något kommer till &#39;0&#39; markerar jag det som &#39;kostnadsfritt&#39; i taggningsdokumentet och tar bort det från Workspace-projektet

På det här sättet är era data alltid rena och ni har en tydlig uppfattning om ert skräp.

![Variabler och händelser - översikt](assets/variables-and-events-overview.png)

## Fliken Egenskaper

**VAD:** Ett egenskapsdokument ska visa alla dina digitala egenskaper - webbplatser, mobilappar, andra verktyg (chatt, feedback osv.), oavsett om dessa egenskaper är taggade med Adobe Analytics eller inte. Detta bör fungera som ett centralt och levande dokument för affärsanvändare och teknikanvändare.

**VARFÖR:** Detta ger dig en tydlig bild av din användares resa över alla dina digitala egenskaper, och vad Adobe Analytics gör och inte täcker, så att du kan börja prioritera att lägga till taggning till alla egenskaper där den saknas. Genom att utforma det digitala ekosystemet på det här sättet kan ni identifiera potentiella möjligheter i taggningsstrategin och få en fullständig bild av användarens resa. Behöver du till exempel en global rapportsserie för att spåra flera domäner/webbplatser? Krävs det att besökar-ID skickas mellan domäner eller appar till en hybridupplevelse? Behöver interna URL-filter uppdateras för spårning mellan domäner?

**HUR:** Identifiera en ägare av dokumentet för att tillhandahålla styrning och en enda ansvarskälla för att hantera uppdateringar.
Visa följande på fliken Egenskaper:
* **Egenskapsnamn:** Det kan vara en domän, underdomän, appnamn osv. Även inom samma domän, om vissa delar av den hanteras separat (som av ett annat team eller en annan teknik), bör dessa delar separeras.
* **Länk (URL)** till egenskap där den är tillgänglig
* **Ägare och kontakter:** Ange huvudägare eller huvudkontakter för egenskapen
* **Taggmetod:** Många av oss har olika kodmetoder och implementeringar (Launch, JS-filer, AEP, osv.). Du kan dela upp detta ytterligare om det behövs (t.ex. via kodversion eller tagghanteringssystem), men det är avsett att hålla reda på alla olika kodmetoder och -versioner, där koden behöver uppdateras och hur den behöver underhållas. Om du använder Adobe Launch anger du namnet på Launch-egenskapen.

Kom ihåg att ta med alla digitala egenskaper, även om de inte är taggade med Adobe Analytics. Detta hjälper er att förstå det digitala landskapet och hur era användare interagerar med alla era resurser.

Vi rekommenderar att du håller det här dokumentet så enkelt som möjligt och inte kramar ned det med för mycket information så att det förblir enkelt att tolka i olika delar av organisationen. Analysteam förstår ofta det digitala landskapet bättre än något annat team, så det här dokumentet används ofta av andra team och chefer för att ge en grundlig översikt.

>[!TIP]
>
>Skapa en webbplatsens namn/egenskapsdimension i Adobe Analytics. Med en dedikerad dimension (vanligtvis en eVar) i Adobe Analytics som identifierar platsnamnet/appnamnet kan du segmentera, felsöka, skapa virtuella rapportsviter osv. Fördelarna är oändliga, särskilt när du kombinerar flera webbplatser i en (global) rapportserie. Nyckeln är att se till att utvecklingsgruppen alltid anger det här värdet i egenskapsdimensionen, inklusive alla sidinläsningar (s.t-anrop/trackState) och alla anpassade händelser (s.tl-anrop/trackAction). Bearbetningsregler kan vara ett värdefullt verktyg som hjälper dig att ange dessa värden på ett korrekt och konsekvent sätt.

[Titta på den här videon av Doug Moore](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=sv-SE){target="_blank"} om du vill ha mer information om hur du fyller i implementeringens spelningsbok.

## Författare

Det här dokumentet skrevs tillsammans av:

![Christel Guidon](assets/Christel-Headshot-150.png)

Christel Guidon, Digital Analytics Platform Manager på NortonLifeLock
Adobe Analytics Champion

![Rachel Fenwick](assets/Rachel-Fenwick-150.png)

Rachel Fenwick, Senior Consultant på Adobe
