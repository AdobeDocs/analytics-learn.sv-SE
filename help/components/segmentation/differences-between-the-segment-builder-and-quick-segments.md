---
title: Skillnader mellan segmentbyggaren och snabbsegment i Analysis Workspace
description: Segment kan vara ett av de mest kraftfulla verktygen i er dataanalysverktygslåda. Lär dig skillnaden mellan att använda segmentbyggaren och snabbsegmenten i Analysis Workspace för att bli effektivare.
feature: Segmentation
role: User
level: Beginner
doc-type: article
kt: KT-13118
source-git-commit: 9484b2e981d78be59b6ea16eeae2cf6f212c81ab
workflow-type: tm+mt
source-wordcount: '1264'
ht-degree: 0%

---


# Skillnader mellan segmentbyggaren och snabbsegment i Analysis Workspace

Segment kan vara ett av de mest kraftfulla verktygen i er dataanalysverktygslåda. Lär dig skillnaden mellan att använda segmentbyggaren och snabbsegmenten i Analysis Workspace för att bli effektivare.

>[!TIP]
>
> Klicka på bilden längst ned på sidan för att hämta en påminnelse om när du ska använda verktygen i Analysis Workspace.

Segment kan vara ett av de mest kraftfulla verktygen i er dataanalysverktygslåda. När du vill titta på specifika grupper av trafik, webbplatsavsnitt eller kundresor kan det vara ett bra sätt att fokusera analysen på en viss del av trafiken till din webbplats om du använder segment. Från en detaljhandelsmiljö är några av de mest användbara segmenten jag har skapat för olika typer av kundgrupper, till exempel nya jämfört med befintliga kunder, kunder som har loggat in på ett konto eller gäster, och så vidare. Men du kan också skapa dem för olika webbplatsavsnitt, kunder som utför specifika åtgärder eller något annat du kan tänka dig!

**Det finns två sätt att skapa segment:**

* Använda segmentverktyget på komponentmenyn
* Använda snabbsegmenten högst upp på en panel

Om du skapar ditt segment med segmentverktyget kan du spara det och återanvända det i andra projekt. Detta är ett bra sätt att kunna fokusera på specifika kundgrupper, till exempel personer som besöker vissa delar av webbplatsen och sedan gör ett köp. Å andra sidan, om du gör en undersökande analys och vill testa olika segmentinställningar, kan snabbsegmentbyggaren vara till stor hjälp. Låt oss titta på några av de viktigaste fördelarna med varje metod.

## Snabbsegment

Överst på varje panel kan du klicka på snabbsegmentsikonen (en tratt med symbolen +) för att öppna byggaren. På så sätt kan du skapa ett segment på alla nivåer (träffad, besök eller besökare) med upp till tre villkor. På samma sätt som huvudsegmentsbyggaren ger detta en indikation till höger om att om segmentet returnerar data och % av den totala trafikpopulationen i segmentet, även om det är en enklare version än helsegmentsvyn som visas i segmentbyggaren. När du lägger till mer än ett villkor kan du använda operatorerna&quot;och&quot; och&quot;eller&quot;. Tyvärr finns det inget &#39;then&#39;-alternativ för snabbsegment, så om du behöver sekventiella segment måste du använda hela segmentbyggaren. Det finns också en begränsning för en behållare i ett snabbsegment. Eftersom det är tänkt att användas för enkla segment som snabbt kan skapas och redigeras. När ett snabbsegment har använts på en panel eller sparats kan det inte längre redigeras på panelen.

När du gör en undersökande analys och vill testa olika typer av segment för att se hur olika kundgrupper reagerar eller hur olika kategorier fungerar - det går mycket snabbare att använda snabbsegment än att använda segmentbyggaren. Dessutom är dessa segment bara tillgängliga i det projekt de skapades i, så om det visar sig att de inte ger det resultat du vill ha behöver du inte bekymra dig om att ta bort det sparade segmentet från den överordnad listan. Om du efter att ha testat segmenten vet att det kommer att vara användbart i andra projekt, kan du alltid klicka på knappen &#39;open builder&#39; för att öppna segmentet i hela segmentbyggaren och spara det som ett vanligt segment. När du gjort det kan du dock inte längre redigera det i snabbsegmentsverktyget.

![Snabbsegment](assets/quick-segement.png)

## Segment Builder

Du kommer åt segmentbyggaren genom att klicka på symbolen + ovanför listan med segment på komponentmenyn till vänster, eller genom att klicka på komponentlistrutan och välja Skapa segment.. till skillnad från snabbsegmenten, har detta alla alternativ som är tillgängliga för dig. Om du vill lägga till flera villkor kan du skapa sekventiella segment med hjälp av operatorn&quot;then&quot;. Med sekventiella segment kan du även använda&quot;logikgrupp&quot; som din nivå (i stället för träffad, besök eller besökare). Med segmentbyggaren kan du också lägga till en beskrivning till segmenten, som kan lägga till kontext om vem som skapade segmentet eller vilken typ av data som det har skapats för att filtrera, eller lägga till taggar till segmentet för organisatoriska syften som inte är möjliga i snabbsegmentsbyggaren.

Det är viktigt att du använder segmentbyggaren när segmentet ska ha fler än tre villkor, om du behöver använda behållare eller vill ha sekventiella segment. Den kompletta segmentbyggaren har många fler alternativ för att göra mer komplicerade segment, vilket kan hjälpa er att dela upp olika kundtyper, kategorier, kundresor osv. När dessa segment har skapats och sparats läggs de till i den överordnad listan över segment, vilket innebär att de kan taggas, godkännas, delas, användas i flera rapporter och publiceras på Experience Cloud. Genom att publicera i Experience Cloud kan ni använda segmentet i andra Adobe-produkter, till exempel Adobe Target för personalisering. Segment som har byggts i segmentbyggaren kan inte redigeras på snabbsegmentpanelen. Du måste öppna segmentbyggaren för att kunna göra ändringar i dem. Som tur är ger förhandsvisningen till höger en mer detaljerad analys av den trafik som segmentet skulle ha fört in de senaste 90 dagarna, vilket innebär att det är lättare att vara säker på att segmentet kommer med det du vill ha innan du sparar.

![Segment Builder](assets/segment-builder-quick.png)

## Användningsexempel

I olika branscher kan användningen för att skapa anpassade segment vara annorlunda. Vi arbetar för e-handelsdivisionen hos en stor återförsäljare och genomför ofta utforskande analyser för att avgöra vilka vägar kunderna ska köpa. När vi ser toppar eller fall i aktiviteter som att lägga till produkter i varukorgar eller beställa kan det här vara praktiskt att använda snabbsegmenten. Under en analys kan jag snabbt skapa ett segment för en viss typ av kund eller för en viss åtgärd/länk som de klickar på. Genom att inte behöva öppna segmentbyggaren och spara varje segment kan jag lägga till villkoren snabbt och sedan ta bort dem lika snabbt. Detta sparar mycket tid när vi försöker förklara varför vi ser en förändring på vår webbplats.

Det finns också tillfällen då segmentbyggaren har varit min tur. Alla kunder är inte likadana och ofta vill vi titta på specifika typer av kunder som identifieras av åtgärder eller kundvägar som de vidtar. Genom att använda segmentbyggaren kan vi lägga till flera villkor för att identifiera olika typer av kunder och spara segmenten så att de kan delas och användas av flera analytiker. Det är viktigt att dessa typer av segment är konsekventa i alla rapporter, så att det finns en inbyggd funktion som alla kan använda som är bättre än var och en som bygger sin egen version, eftersom resultaten kan skilja sig åt.

Generellt sett är både snabbsegmenten och segmentbyggaren utmärkta verktyg att använda i din analys. De har sina syften, fördelar och nackdelar. Se till att du tar en titt på våra praktiska tips och tricks nedan.

## Upphovsman

Det här dokumentet har skrivits av:

![Mandy George](assets/mandy-george.jpg)

**Mandy George**, Digital Analyst III at Best Buy Canada

Adobe Analytics Champion

## Hämta

[![Ladda ned snabbsegment](assets/quick-segments-download-small.jpg)](assets/Adobe_Analytics_Segments_Vs_Segment_Builder_Reference_Guide.pdf)
