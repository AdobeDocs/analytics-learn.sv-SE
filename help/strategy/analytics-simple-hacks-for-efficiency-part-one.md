---
title: Enkla hacks för ökad effektivitet och självbetjäning - del 1
description: Lär dig de viktigaste utmaningarna som analysteamen står inför idag och våra rekommendationer för att lösa dem med hjälp av strategier utanför Adobe Analytics användargränssnitt.
feature: Analytics Basics
role: Admin, Leader
level: Intermediate
solution: Analytics
exl-id: 5d1077fd-d006-4a85-bf1c-54f6b2d31934
source-git-commit: d7fd77640928697f5857ccfcaf2c0f561aebeac3
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 0%

---

# Adobe Analytics: Enkla hacks för ökad effektivitet och självbetjäning

**Del 1: Utanför användargränssnittet**

I den här artikeln beskrivs viktiga utmaningar som analysteam står inför idag, och våra rekommendationer för att lösa dem genom att använda strategier utanför Adobe Analytics gränssnitt.

## Viktiga utmaningar för analysteam

Många analysteam har en obalanserad arbetsfördelning. Istället för en blandning av 80-procentig analys och 20-procentig implementering hamnar många organisationer i motsatsen till det. De ser de flesta av de satsningar de gjort på att skapa, rapportera och ge stöd i stället för att producera analyser som ger värdefulla insikter.

Analysteam håller på att tappa bort sin produktivitet och effektivitet av olika anledningar. Dessa omfattar de ständigt föränderliga och föränderliga implementeringarna, ett försök att upprätthålla organisationens förtroende för data och minska analytikernas omsättning. Genom att minska omsättningen undviker du den långa processen med att utbilda nya medarbetare i okända verktyg för anpassad implementering.

Andra viktiga utmaningar som analytiker står inför:

* **Konkurrens:** Online- och flerkanalsföretag blir mer konkurrenskraftiga.
* **Kundens förväntningar:** Kundens upplevelser och marknadsföringsstrategier blir mer komplexa.
* **Datavärde:** Värdet på korrekta data och insikter för att skapa konkurrensfördelar blir viktigare.
* **Intressentförväntningar:** Affärspartners, intressenter och chefer begär i allt högre grad data innan de godkänns.
* **Projekthantering:** Analysteamet drunknar i förfrågningar om att implementera datainsamling för en oändlig ström av nya funktioner, samtidigt som de skapar korrekta rapporter, introducerar nya analytiker och avslöjar nästa nya insikter.

## Effektivitetstangenter: Utanför användargränssnittet

1. Håll din [SDR-referens](/help/implementation/implementation-basics/creating-and-maintaining-an-sdr.md) (Solution Design Reference) uppdaterad:

   * SDR är den primära källan till sanning för definition och avsedd användning av alla variabler i analysimplementeringen.
   * SDR är den viktigaste referensen som användare måste känna till för att få ut mer av Adobe Analytics användargränssnitt.
   * Det är viktigt att du håller den uppdaterad och har en version (ett enkelt datumformat kan användas).

1. Dokumentation och styrning av datainsamling - tekniska specifikationer:

   Teknisk specifikation har en mer begränsad publik än SDR men är lika viktig, om inte mer, för en fullt fungerande implementering. En bra teknisk specifikation bör omfatta alla resurser för utveckling, kvalitetssäkring och tagghantering som behövs för att implementera lösningen. Se till att ha så många dokument som behövs för unika implementeringsarkitekturer.

   **Tech Spec**

   _Användningsfall:_ Instruktioner som beskriver hur du skapar skript för datainsamling

   _Primära användare:_ Utvecklare

   _Andra anteckningar:_

   * Mycket tekniskt dokument som är särskilt framtaget för era driftsättningsmiljöer
   * Användbart för både inledande implementering och efterföljande underhåll/referens
   * Ordnat efter lösningstyp (t.ex. kampanjspårning, sidmetadata o.s.v.)
   * Det primära dokumentet måste uppdateras och underhållas när SDR-ändringar görs
   * Central databas
   * Synkroniserade versionsnummer för SDR och Tech Spec

1. Kommunicera och dokumentera lösningar när de lanseras:

   * Kommunicera med användaren i fokus
   * Skapa enkla sammanfattningar som kan delas med intressenter när du startar eller förbättrar datainsamlingen
   * Förbättra korrekt variabel användning utanför porten
   * Skicka en sammanfattning av startmeddelanden till viktiga intressenter och analytiker
   * Skapa ett bibliotek som kan användas för kontorstid, gruppaktiveringssessioner eller för teamspecifik introduktion

1. Dokumentation, styrning och datahygien - AHD:

   AHD (Analytics Health Dashboard) tränger in i en _enskild_ rapportserie och ger en översikt över data som samlats in i varje komponent (eVar, prop och event). Detta kan vara till hjälp när du vill ta reda på om insamlingen av data i en komponent har upphört, så att du kan vidta åtgärder för att åtgärda problemet. Du kan köra den här instrumentpanelen när som helst i framtiden för alla rapportsviter.

   Analytics Health Dashboard (AHD):

   _Användningsfall:_ Ögonblicksbild av alla mått och dimensioner som fångas av en enda rapportserie

   _Primära användare:_ Lead Analytics SME och/eller Dev

   _Andra anteckningar:_
   * Levereras via Excel med en anpassad integrering av Adobe Reporting API
   * Användare måste ha tillgång till API:t för webbtjänster i Analytics
   * Det finns alternativ för att halvautomatisera

1. Vinn genom att utöka världen med ämnesexperter (SME):

   * Etablera små och medelstora företag inom de olika grupperna i organisationen
   * Bygg upp sin närvaro genom att hjälpa till att skapa sociala releaser och vinster
   * Använd vanliga kontorstider för att utbilda utbildarna och minska antalet tillfälliga ärenden

Läs mer om strategi och tankeledarskap på navet [Nöjda kunder](https://experienceleague.adobe.com/docs/customer-success/customer-success/overview.html?lang=sv-SE).