---
title: Om Adobe Analytics attribueringspanel och uppslagsfönster
description: Lär dig hur du använder attribueringspanelen och lookback-fönstret för att förstå kundbeteenden och anpassa hur dimensionsobjekt får kredit för lyckade händelser.
feature: Attribution
role: User
level: Experienced
doc-type: Article
last-substantial-update: 2023-06-20T00:00:00Z
jira: KT-13181
thumbnail: KT-13181.jpeg
source-git-commit: ae6fb85c3903986940463a4133f7b46f5efb64e1
workflow-type: tm+mt
source-wordcount: '1662'
ht-degree: 0%

---


# Om Adobe Analytics attribueringspanel och uppslagsfönster

När jag först tänkte på [attribueringspanel](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/attribution.html?lang=en) och **uppslagsfönster**, påmindes jag omedelbart om begreppet *tidsresa*; Sedan påmindes jag förstås också om vårt typiska svar på många nya verktyg som dessa är att helt enkelt skjuta upp användningen, eftersom de ser så komplicerade ut.

Ärligt talat, titta bara på alla alternativ, växlar, paneler, avläsningar och knappar.  Och seriöst, låt oss prata om de komplicerade blinkande ljusen, slangarna, mätarna... VÄNTA!  Det här är inte rätt tillfälle att bli distraherad när vi pratar om tidsmaskiner, vi har inte tid.. eller har vi det?

Jag ska erkänna **attribueringspanel** är ett ganska komplext verktyg, Men vårt typiska jobb som analytiker, dag in och dag ut, är att använda ett annat av våra favoritverktyg och mycket komplexa verktyg för att också ta en titt på det som hänt tidigare. Verktyget kallas ***Adobe Analytics***!  Så ja, för att svara på vår mycket relevanta fråga, tror jag att dessa två saker säger att vi har gott om tid.

Därför bör vi låta något som en liten rädsla stå i vägen för sådana fantastiska, sofistikerade och kraftfulla verktyg som dessa som bokstavligen låter oss se *bakåt* i tid, varje dag?

Det här är ju TIME TRAVEL!  Vi handlar om såna saker.  Eller hur?!!

Så vad väntar vi på - en blankt metallbil, en polislåda eller en vintagebuske telefonbutik med änden av ett gammalt paraply som antenn att dyka upp i vår dörr?

Nej!  Vi har något ännu bättre, så vi sticker in och hänger på!

Du fattar.


Nu när vi alla är glada över tidsresor, kan vi ta ett djupt andetag, ta ett steg bakåt lite och fastställa vad **attribueringspanel** *riktigt* är, och bryt ner lite:

![Attribuering](assets/attribution.png)

*Bild 1 - Nummer som visas textbundet med text längre ned*

I **attribuering** Tänk bara på hur händelser/händelser kan orsakas av en individ, flera personer eller något av ett antal olika händelser över tiden.

Enligt [Adobe](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/overview.html?lang=en), *attribuering* ger analytiker möjlighet att anpassa hur *Dimension* artiklar får kredit för *success events*.


**⛔** DETOUR: Bara en kort anteckning som visar att **attribueringsmodeller** är så ofta associerade med **marknadsföringskanaler** som jag menar *genomstruken* KANAL i bilden ovan för att visa att det går att utföra **attribuering** analys mot de flesta andra ***dimension***.


Det är faktiskt sällan någon viss kundresa är helt linjär och ännu mindre förutsägbar.  I ännu högre grad kommer varje kund att fortsätta i sin egen takt. ofta kan de fördubbla, stoppa, släppa ut eller engagera sig i andra icke-linjära beteenden. Dessa organiska åtgärder gör det svårt eller praktiskt taget omöjligt att veta hur marknadsföringssatsningarna påverkar hela kundresan. Det hämmar också arbetet med att knyta samman olika datakanaler.

Det stämmer.  Låt era &quot;domino&quot;-anletsdrag vara vid dörren och öppna era tankar för koncept mer i samma riktning som fjärilseffekten och strängteori - men precis som allt annat behöver vi börja med några av grunderna.

## **Attributionsmodeller**

När vi använder **attribueringspanel** kan vi börja observera flera olika saker.  Till exempel **attribueringsmodeller** visa oss hur *konverteringar* (dvs. ***framgångsmått***) kan fördelas över *träffar* i en viss grupp.

Kort sagt, om **10 personer** tryck på en **STOR RÖD-KNAPP** för att ta sig genom en dörr, vår **attribueringsmodeller** kommer att berätta vilka av dem **10 personer** vi vill tilldela &quot;kredit&quot; - eller ännu bättre säga, hur *mycket* &quot;credit&quot; vill vi tilldela dem - för att du trycker på knappen.

![Knapp](assets/button.png)

Här är några exempel på hur **attribueringsmodeller** kan påverka **10 personer**:

- **Första beröringen**: Den här modellen fungerar exakt som den låter genom att **100 % kredit** till *först* person som gick genom dörren.  Marknadsförarna är mer benägna att använda den här metoden för taktiker som ***sociala medier*** eller ***visa***; Men det är också en bra taktik att ofta använda för att rekommendera produkter på plats.
- **Senaste beröring**: Den här taktiken fungerar också exakt som den låter, men ger i stället **100 % kredit** till den sista personen som gick genom dörren.  Den här modellen används vanligtvis för att analysera saker som ***naturlig (organisk) sökning*** och andra *kortfristig* marknadsföringskampanjer.
- **Linjär**: Den här modellen distribuerar lika mycket beröm till alla enskilda personer som gick genom dörren.

Du bör dock vara försiktig här eftersom du kan sprida dina resultat mycket snabbt när du använder den här taktiken, med tanke på hur lång tid den är och ju större målgrupp den träffar.

- **U-formad**: Den här metoden tilldelar **40 %** av krediten till *första person* i dörren, uppslag **20 %** av krediten över *alla däremellan* och sedan ger **40 %** till **sista** genom. Den här modellen används oftast i situationer när du har en **lång konverterings-/försäljningscykel** innehållande *flera kontaktytor* längs vägen.  I det här fallet är ditt mål att i första hand lyfta fram ***först*** och ***sista*** marknadsföringstaktik som bidrog till att kunden konverterade.
- **J**-**Form** och **Inverterad J**:
   - Fundera på **U-formad**, men i stället tilldelas i den här modellen **60 %** kreditera *senaste person* gå genom dörren, **20 %** till *först* och sedan *divides* återstående **20 %** tvärs över *alla andra* i mitten.  **Inverterad J** gör raka motsatsen.

Målet här är att lägga större vikt vid dig, antingen i *början* eller *end* av er kampanj, Men du vill ändå tilldela ett visst belopp kredit till det bidragande objektet i motsatt ände samtidigt som du bekräftar &quot;små killar&quot; under resans gång.

- **Tidsminskning**: Nu skulle jag vara borta om jag inte delade den här. Den här modellen har bokstavligen en halveringstid som sjunker exponentiellt - med tiden!  I det här fallet *standard* parametern för den här modellens halveringstid är **7 dagar**.  Så fungerar det sedan *vikt* för varje **marknadsföringskanal**, *baserat på hur lång tid det tar* som skickas efter *inledande kontaktyta* och när kunden konverterar.

  **Tidsminskning** och **U-formade attribueringsmodeller** används båda ofta för att mäta mer långvariga kampanjer, men som ni ser har de något olika mål, baserat på hur de i slutändan *vikta* resultatets värde.

- **Egen**: Välj vem som ska få kredit.  Det är din kampanj!

Ytterligare information om dessa och andra attribueringsmodeller finns i [klicka här](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=en)

För att göra detta ännu intressantare ska vi prata om att vrida tillbaka klockan!

## **Sökfönster**

Nu är det dags att ta dig till nästa nivå.  Här lägger vi bokstavligen in tidsreseelementet i vår analys - och återigen börjar vi med grunderna.

***Adobe*** definierar **sökfönster** som&quot;hur lång tid en konvertering ska ta tillbaka för att inkludera beröringspunkter. Attributionsmodeller som ger större tilltro till första interaktioner ser större skillnader när du tittar på olika uppslagsfönster.&quot;


Med andra ord: **sökfönster** fastställa den tidsperiod under vilken *konverteringar* beaktas och *kontext* till attribueringsanalysen. ***Adobe Analytics*** erbjuder tre typer av **sökfönster**:

- **Besök fönstret för sökning:** Återgår till början av en ***besök*** när en konvertering skett, och ge insikter om de omedelbara interaktionerna som leder till konverteringar.

  Kom ihåg att det här vanligtvis är det kortaste **uppslagsfönster** att använda.
- **Sökfönster:** Ser ut som alla ***besök*** fram till den första i månaden i den markerade **datumintervall**, som ger en mycket bredare bild av kundens interaktioner och hjälper till att identifiera mönster över tid.
- **Anpassat uppslagsfönster:** Gör att du kan utöka **attribueringsfönster** bortom rapporteringen **datumintervall** upp till *maximum* av **90 dagar**.  Den ger *flexibilitet* vid hämtning av kontaktpunkter som har inträffat *utanför* den markerade **datumintervall**, vilket ger en heltäckande analys.

Genom att justera en viss **uppslagsfönster** kan analytiker sedan undersöka effekten av en eller flera kontaktytor inom specifika tidsramar och få bättre insikter om hur olika varaktigheter påverkar attribueringsresultaten.

## **Samla allt**

Så vad betyder allt det här för oss som analytiker?

The **attribueringspanel** och **uppslagsfönster** ger oss möjlighet att se bortom alla kanaler, data på ytnivå och fördjupa oss i kundresan. Genom att förstå vilka kontaktytor som hade störst effekt på *konverteringar* kan vi fatta välgrundade beslut om våra marknadsföringsstrategier och fördela resurser mer effektivt.

Kom ihåg, när du har **attribueringsmodeller** och **sökfönster** kan du fortfarande ändra dina data ytterligare genom att filtrera dem med  **segment,** eller någon annan komponent som du vill ha.  När panelen har renderats har du dessutom tillgång till alla funktioner i en traditionell arbetsyta.

## **Till sist i praktiken**

Nu när du har lagt ner idéerna kan du föreställa dig att du kör en marknadsföringskampanj och försöker avgöra vilken kanal som är *mest effektiv* för konverteringar. Med hjälp av **attribueringspanel** kan du inte bara se **senaste beröring**, men även **första beröringen**, **samma beröring** och andra **modell** du väljer att avgöra vilka **kanaler** är *mest effektiv* när du kör *konverteringar*. Sedan kan den här informationen användas för att *optimera* era kampanjer och förbättra det övergripande resultatet genom att helt enkelt vrida tillbaka klockan med **uppslagsfönster** efter ditt val!

Nu när du har sett vad det kan göra ska du inte luras eller skrämmas av de till synes komplexa funktionerna i attribueringspanelen.  **Ansiktet**.  *Reparera* den.  Förstå det*.* MEN DET FLESTA AV ALLA - *Använd det till din fördel.* The **attribueringspanel** och **uppslagsfönster** är nyckeln till en djupare förståelse för era kunder och deras resa med ert varumärke.

Nu kan vi resa[tillbaka i tiden](https://youtu.be/gVryJmZNFdU)&quot; med tillförsikt och med hjälp av kraftfulla tidsmaskiner (alias ***Adobe Analytics***) för att fatta databaserade beslut.
