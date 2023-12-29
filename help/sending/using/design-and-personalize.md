---
title: Skapa personaliserat innehåll
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Lär dig hur du utformar meddelandeinnehållet och försöker undvika vanliga problem som kan hindra dig från att utföra leveransen. 
feature: Deliverability
role: User
level: Intermediate
exl-id: 938989c9-ef19-4297-9b8b-c38eb1cec1f0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 3%

---

# Skapa personaliserat innehåll {#build-personalized-content}

När du utformar meddelandeinnehållet bör du undvika vanliga problem som kan hindra dig från att utföra leveransen. För det mesta är möjliga fel relaterade till [personalisering](../../designing/using/personalization.md), formatera när [använda befintligt innehåll](../../designing/using/using-existing-content.md) - och [konvertera HTML](../../designing/using/using-existing-content.md#converting-an-html-content) - och [bilder](../../designing/using/images.md).

## Optimera personalisering {#optimize-personalization}

För att undvika vanliga problem som kan hindra dig från att utföra leveransen och för att förbättra mottagarnas upplevelse kan du anpassa dina meddelanden med Adobe Campaign.

Du kan använda mottagarnas data som lagras i Adobe Campaign-databasen, eller som samlats in via spårning, landningssidor, prenumerationer osv.
Grundläggande om personalisering presenteras i [det här avsnittet](../../designing/using/personalization.md).

Se till att meddelandeinnehållet är rätt utformat för att undvika fel, som vanligtvis är relaterade till personalisering.

Dynamiskt innehåll kan läggas till manuellt för att visa olika innehåll för mottagarna enligt villkoren som definieras i uttrycksredigeraren. När du lägger till dynamiskt innehåll måste du alltid lämna en standardvariant för mottagare som inte uppfyller de valda villkoren.
Mer information om dynamiskt innehåll finns i [det här avsnittet](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

**Tips** - Förhandsgranska e-postmeddelandet med olika testprofiler för att kontrollera att det dynamiska innehållet har konfigurerats korrekt.

## Bygg optimerat innehåll {#optimize-content}

När du skapar e-postmeddelanden bör du tänka på de allmänna bästa metoderna nedan.

* Behåll designen enkel

* Tänk på mobilanvändare

* Undvik helt bildbaserade mejl

* Använda e-postsäkra teckensnitt

* Koda specialtecken

### Subject line

Arbeta på [ämnesrad](../../designing/using/subject-line.md) för att förbättra öppningsfrekvenserna:

* Undvik för långa motiv. Använd högst 50 tecken

* Undvik att använda upprepade ord som &quot;free&quot; eller &quot;offer&quot; som kan betraktas som spam

* Undvik versaler och specialtecken som &quot;!&quot;, &quot;£&quot;, &quot;€&quot;, &quot;$&quot;

### Spegelsida

Inkludera alltid en länk för spegelsida. Önskad position är högst upp i e-postmeddelandet. [Läs mer](../../designing/using/personalization.md#adding-a-content-block)

### Länk för att avbryta prenumeration

Länken för att avbeställa prenumerationer är viktig. Den måste vara synlig och giltig och formuläret måste vara funktionellt. Lär dig riktlinjerna för prenumerationslänk [i det här avsnittet](../../designing/using/personalization.md#about-targeting-dimension).

När meddelandet analyseras är som standard en kontroll [typologiregel](../../sending/using/control-rules.md) kontrollerar om en avanmälningslänk har inkluderats och genererar en varning om den saknas.

**Tips**: Eftersom mänskliga fel alltid är möjliga bör du kontrollera att länken för avanmälan fungerar korrekt före varje gång du skickar. När du t.ex. skickar ett bevis ska du kontrollera att länken är giltig, att formuläret är online och att fältet för att inte längre kontakta den här mottagaren har ändrats till Ja.

Lär dig hur du infogar en länk för avanmälan [i det här avsnittet](../../designing/using/personalization.md#adding-a-content-block).

### E-poststorlek {#email-size}

För att undvika problem med prestanda och leverans är den rekommenderade maxstorleken för ett e-postmeddelande ungefär **35 kB**.

Tänk på följande om du vill hålla din e-post under gränsen:

* Ta bort överflödiga eller oanvända format

* Flytta en del av e-postinnehållet till en [landningssida](../../channels/using/getting-started-with-landing-pages.md)

* Minimera koden

Kontrollera att du har testat ändringarna innan du skickar det.

I Adobe Campaign är standardstorleken för ett e-postmeddelande inställd på **100MB**. <!--This limit enables to prevent any error that could indefinitely increase the size of an email, which can lead to a system crash.-->

Om gränsen nås kommer det meddelande som överskrider gränsen att misslyckas och ett felmeddelande visas i leveransloggarna. Övriga meddelanden i samma leverans påverkas inte. I så fall måste du anpassa den dynamiska delen av e-postmallen eller de innehållsfragment som används av leveransen. <!--If you need assistance, or if you have any question or request about the **[!UICONTROL Maximum message size]** option, reach out to your Adobe contact.-->

Adobe rekommenderar att du behåller standardvärdet för maximal meddelandestorlek. Det här värdet kan dock ändras i **[!UICONTROL Maximum message size]** via **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** meny, av [funktionsadministratörer](../../administration/using/users-management.md#functional-administrators) endast.

>[!IMPORTANT]
>
>Om du anger värdet som noll tillämpas ingen begränsning.

### SMS-längd

Som standard uppfyller antalet tecken i ett SMS GSM-system (Global System for Mobile Communications). SMS-meddelanden som använder GSM-kodning kan innehålla högst 160 tecken eller 153 tecken per SMS för meddelanden som skickas i flera delar.

Translitterering består i att ersätta ett tecken i ett SMS med ett annat om det tecknet inte beaktas av GSM-standarden. Observera att om du infogar anpassningsfält i innehållet i SMS-meddelandet kan det medföra tecken som GSM-kodningen inte tar hänsyn till. Du kan auktorisera teckentranskribering genom att markera motsvarande ruta på fliken SMPP-kanalinställningar i motsvarande **[!UICONTROL External account]**.
Läs mer [i det här avsnittet](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

**Tips**:

* Om du vill behålla alla tecken i SMS-meddelanden som de är, ska du inte aktivera transkribering för att t.ex. inte ändra egennamn.

* Om dina SMS-meddelanden innehåller många tecken som inte beaktas av GSM-standarden kan du aktivera transkribering för att begränsa kostnaderna för att skicka meddelanden.

Läs mer [i det här avsnittet](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

### Responsiv e-postdesign

Responsiv design säkerställer att ett e-postmeddelande återges optimalt för den enhet där det öppnas.

* Använd responsiv e-post HTML i stället för web HTML

* Använd förhandsgranskningsläget och skicka korrektur för att testa återgivningen på så många enheter som möjligt. Lär dig hur [förhandsgranskningsmeddelande](../../sending/using/previewing-messages.md) före sändning.

* Campaign Email Designer innehåller responsiva designformaterade mallar för mobiler. Läs mer [på den här sidan](../../designing/using/using-reusable-content.md#content-templates).

## Hantera bilder {#manage-images}

Följ riktlinjerna nedan när det gäller att använda bilder.

### Förhindra blockering av bilder

Vissa e-postklienter blockerar bilder som standard, och vissa användare ändrar sina inställningar till blockbilder för att spara på dataanvändningen. Om bilderna inte hämtas kan därför hela meddelandet gå förlorat. Så här undviker du:

* Balansera innehållet med bild och text. Undvik helt bildbaserade e-postmeddelanden.

* Om texten måste finnas i en bild använder du alt- och titeltext för att vara säker på att meddelandet når fram. Formatera din alt-/titeltext för att förbättra utseendet.

* Undvik att använda bakgrundsbilder eftersom de inte stöds av vissa e-postklienter.

### Gör bilderna responsiva

Försök att göra bilderna responsiva och ändra storlek. Observera att detta kan ha en kostnadseffekt eftersom det tar längre tid att bygga.

### Använd absoluta bildreferenser

För att vara tillgängliga utifrån måste de bilder som används i e-postmeddelanden och offentliga resurser som är kopplade till kampanjer finnas på en externt tillgänglig server.

## Förhandsgranska meddelandet {#preview-msg}

Adobe rekommenderar att du förhandsgranskar ditt meddelande för att kontrollera hur det är anpassat och hur mottagarna ser det.

I e-postdesignern **[!UICONTROL Preview]** kan du visa återgivningen av varje innehåll för en mottagare. Anpassningsfälten och de villkorliga elementen i innehållet ersätts med motsvarande information för den valda profilen. [Läs mer](../../sending/using/previewing-messages.md)
