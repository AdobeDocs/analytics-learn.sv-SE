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
exl-id: 1da9334b-0edb-4237-b7ca-57640865208c
source-git-commit: f1bb981a83eb698f4185a22c367346a9ddd0c755
workflow-type: tm+mt
source-wordcount: '1664'
ht-degree: 0%

---

# Om Adobe Analytics attribueringspanel och uppslagsfönster

När jag först funderade på [attribueringspanelen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/panels/attribution.html?lang=en) och **lookback-fönstret** påmindes jag omedelbart om konceptet med *tidsresor*. Sedan påmindes jag förstås också om vårt vanliga svar på många nya verktyg som dessa är att helt enkelt skjuta upp användningen, eftersom de ser så komplicerade ut.

Ärligt talat, titta bara på alla alternativ, växlar, paneler, avläsningar och knappar.  Och seriöst, låt oss prata om de komplicerade blinkande ljusen, slangarna, mätarna... VÄNTA!  Det här är inte rätt tillfälle att bli distraherad när vi pratar om tidsmaskiner, vi har inte tid.. eller har vi det?

Jag erkänner att **attribueringspanelen** är ett ganska komplext verktyg, men vårt typiska jobb som analytiker, dag in och dag ut, är att använda ett annat av våra favoritverktyg och mycket komplexa verktyg för att också ta en titt på det som har hänt tidigare. Verktyget kallas ***Adobe Analytics***!  Så ja, för att svara på vår mycket relevanta fråga, tror jag att dessa två saker säger att vi har gott om tid.

Därför bör vi låta något som en liten rädsla stå i vägen för sådana fantastiska, sofistikerade och kraftfulla verktyg som dessa som bokstavligen låter oss se *bakåt* i tiden, var och en för varje dag?

Det här är ju TIME TRAVEL!  Vi handlar om såna saker.  Eller hur?!!

Så vad väntar vi på - en blankt metallbil, en polislåda eller en vintagebuske telefonbutik med änden av ett gammalt paraply som antenn att dyka upp i vår dörr?

Nej!  Vi har något ännu bättre, så vi sticker in och hänger på!

Du fattar.


Nu när vi alla är glada över tidsresor ska vi ta ett djupt andetag, ta ett steg bakåt lite, fastställa vad **attribueringspanelen** *verkligen* är och bryta ned lite:

![Attribution](assets/attribution.png)

*Figur 1 - De siffror som visas är textbundna med texten längre ned*

I **attribuering** kan du helt enkelt tänka på hur händelser/åtgärder kan orsakas av en individ, flera individer eller ett antal olika händelser över tiden.

Enligt [Adobe](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/overview.html?lang=en) ger *attribution* analytiker möjlighet att anpassa hur *Dimension* -objekt får kredit för *success-händelser*.


>[!WARNING]
>
>**Attribution models** är så ofta associerade med **marknadsföringskanaler** att jag med avsikt *stryker över* ❷ CHANNEL i bilden ovan för att visa att det går att utföra **attribution** -analys mot de flesta andra ***dimension***.


Det är faktiskt sällan någon viss kundresa är helt linjär och ännu mindre förutsägbar.  Dessutom kommer varje kund att fortsätta i sin egen takt. Ofta kan de dubbelklicka, stoppa, släppa ut eller engagera sig i andra icke-linjära beteenden. Dessa organiska åtgärder gör det svårt eller praktiskt taget omöjligt att veta hur marknadsföringssatsningarna påverkar hela kundresan. Det hämmar också arbetet med att knyta samman olika datakanaler.

Det stämmer.  Låt era &quot;domino&quot;-anletsdrag vara vid dörren och öppna era tankar för koncept mer i samma riktning som fjärilseffekten och strängteori - men precis som allt annat behöver vi börja med några av grunderna.

## **Attributionsmodeller**

När vi använder **attribueringspanelen** kan vi börja observera flera olika saker.  Till exempel visar **attribueringsmodellerna** för oss hur våra *konverteringar* (d.v.s. ❶ **framgångsmått**) kan fördelas över *träffar* i alla grupper.

Kort sagt, om **10 personer** trycker på en **BIG RED-KNAPP** för att gå igenom en dörr, kommer våra **attribueringsmodeller** att berätta för oss vilken av de **10 personer** vi vill tilldela&quot;kredit&quot; - eller ännu bättre säga, hur *mycket*&quot;kredit&quot; vi vill tilldela dem - för att trycka på knappen.

![Knapp](assets/button.png)

Här är några exempel på hur de ❸ **attribueringsmodellerna** kan påverka de **10 personerna**:

- **Första beröringen**: Den här modellen fungerar exakt som den låter genom att ge **100 % kredit** till den *förste* personen som gick genom dörren.  Marknadsförarna är mer benägna att använda den här metoden för taktik som ***sociala medier*** eller ***display***. Det är dock också en bra taktik att ofta använda för produktrekommendationseffektivitet på plats.
- **Senaste beröring**: Den här taktiken fungerar också exakt som den låter, men ger istället **100 % kredit** till den SIST-person som gick genom dörren.  Den här modellen används vanligtvis för att analysera saker som ***naturlig (organisk) sökning*** och andra *kortsiktiga* marknadsföringskampanjer.
- **Linjär**: Den här modellen distribuerar lika många krediter till alla enskilda personer som gick genom dörren.

  >[!CAUTION]
  >
  >Du bör dock vara försiktig här eftersom du kan sprida dina resultat mycket snabbt när du använder den här taktiken, med tanke på hur lång tid den är och ju större målgrupp den träffar.

- **U-Shaped**: Den här metoden tilldelar **40%** av krediten till den *första personen* i dörren, sprider **20%** av krediten till *alla i mellan* och ger sedan **40%** till den **sista** genom. Den här modellen används oftast i situationer när du har en **lång konverterings-/försäljningscykel** som innehåller *flera kontaktytor* längs vägen.  I det här fallet är ditt mål att i första hand lyfta fram marknadsföringstaktiken ***first*** och ***last*** som bidrog till kundkonverteringen.
- **J**-**Form** och **Omvänd J**:
   - Fundera på **U-Shaped**, men i stället tilldelar den här modellen **60%** kredit till den *sista personen* som går genom dörren, **20%** till den *första* och sedan *delar* återstående **20%** över *4}alla andra* i mitten.  **Inverterad J** utför den exakta motsatsen.

     Målet här är att lägga större vikt vid det mesta, antingen vid *början* eller *slutet* av kampanjen. Du vill dock ändå tilldela ett visst belopp kredit till det bidragande objektet i motsatt ände samtidigt som du bekräftar &quot;små killar&quot; längs vägen.

- **Tidsminskning**: Nu skulle jag sakna mig om jag inte delade den här. Den här modellen har bokstavligen en halveringstid som sjunker exponentiellt - med tiden!  I det här fallet är parametern *default* för den här modellens halveringstid **7 dagar**.  Det sätt som det fungerar på är att sedan tillämpa *weight* på varje **marknadsföringskanal**, *baserat på den tid* som går efter den *första kontaktytan* och när kunden konverterar.

  **Tidsminskningsmodeller** och **U-formade attribueringsmodeller** används båda vanligtvis för att mäta mer långvariga kampanjer, men som du ser har de något olika mål baserat på hur de *viktar* resultatvärdet.

- **Anpassad**: Du väljer och väljer vem som ska få kredit.  Det är din kampanj!

[Klicka här](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=en) om du vill ha mer information om dessa och andra attribueringsmodeller

För att göra detta ännu intressantare ska vi prata om att vrida tillbaka klockan!

## **Sökfönster**

Nu är det dags att ta dig till nästa nivå.  Här lägger vi bokstavligen in tidsreseelementet i vår analys - och återigen börjar vi med grunderna.

***Adobe*** definierar ❹ **sökfönster** som&quot;hur lång tid en konvertering ska ta tillbaka för att inkludera beröringspunkter. Attributionsmodeller som ger större tilltro till första interaktioner ser större skillnader när du tittar på olika uppslagsfönster.&quot;


Med andra ord bestämmer **uppslagsfönster** den tidsperiod under vilken *konverteringar* övervägs och tillhandahåller *kontext* till attribueringsanalysen. ***Adobe Analytics*** har tre typer av **uppslagsfönster**:

- **Besök uppslagsfönstret:** Återgår till början av ett ***besök*** när en konvertering inträffade och ger insikter i de omedelbara interaktioner som leder fram till konverteringar.

  Kom ihåg att detta vanligtvis är det kortaste **uppslagsfönstret** att använda.
- **Besökarfönstret:** Tittar på alla ***besök*** fram till den första i månaden inom det valda **datumintervallet**, vilket ger en mycket bredare bild av kundens interaktioner och hjälper till att identifiera mönster över tid.
- **Anpassat uppslagsfönster:** Gör att du kan expandera **attribueringsfönstret** utanför **rapportens datumintervall** upp till *maximalt* på **90 dagar**.  Den ger *flexibilitet* när det gäller att hämta kontaktpunkter som inträffade *utanför* det valda **datumintervallet**, vilket ger en heltäckande analys.

Genom att justera ett givet **uppslagsfönster** kan analytiker sedan undersöka effekten av en eller flera kontaktytor inom specifika tidsramar och få bättre insikter om hur olika varaktigheter påverkar attribueringsresultaten.

## **Sammanför allt**

Så vad betyder allt det här för oss som analytiker?

**attribueringspanelen** och **uppslagsfönstret** ger oss möjlighet att se bortom panelerna, data på ytnivå och fördjupa oss i kundresan. Genom att förstå vilka kontaktytor som hade störst effekt på *konverteringar* kan vi fatta välgrundade beslut om våra marknadsföringsstrategier och fördela resurser mer effektivt.

Kom ihåg att när du har markerat dina **attribueringsmodeller** och **uppslagsfönster** kan du fortfarande ändra dina data ytterligare genom att filtrera dem med ett ❺ **segment,** eller någon annan komponent som du vill ha just nu.  När panelen har renderats har du dessutom tillgång till alla funktioner i en traditionell Workspace.

## **Äntligen kan du omsätta det i praktiken**

Nu när du är klar med koncepten kan du föreställa dig att du kör en marknadsföringskampanj och försöker avgöra vilken kanal som är den *mest effektiva* för konverteringar. Med hjälp av **attribueringspanelen** kan du inte bara se den **sista beröringen**, utan även den **första beröringen**, **samma beröring** och alla andra **modeller** som du väljer för att avgöra vilka **kanaler** som är de *mest effektiva* när det gäller din *konvertering sions*. Den här informationen kan sedan användas för att *optimera* dina kampanjer och förbättra resultatet genom att helt enkelt vrida tillbaka klockan med **bakåtsökningsfönstret** som du väljer!

Nu när du har sett vad det kan göra ska du inte luras eller skrämmas av de till synes komplexa funktionerna i attribueringspanelen.  **Ansikte**.  *Krymp*.  **Förstå** det.
MEN DET FLESTA AV ALLA - *Använd det till din fördel.* På **attribueringspanelen** och **uppslagspanelen** kan du låsa upp en djupare förståelse för dina kunder och deras resa med ditt varumärke.

Nu kan vi tryggt resa [tillbaka i tid](https://youtu.be/gVryJmZNFdU) och använda styrkan hos vår betrodda tidsdator (t.ex. ***Adobe Analytics***) för att fatta datadrivna beslut.

## Upphovsman

Det här dokumentet har skrivits av:

![Jeff Bloomer](assets/jeff-headshot.png)

**Jeff Bloomer**, Manager, Digital Analytics på Kroger Personal Finance

Adobe Analytics Champion
