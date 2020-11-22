---
solution: Campaign Standard
product: campaign
title: Styra e-postinnehåll i Adobe Campaign Standard
description: Lär dig hur du kan förbättra leveransen i Adobe Campaign Standard när du redigerar e-postinnehåll.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 7%

---


# Kontrollera e-postinnehåll{#control-email-content}

För att förbättra e-postleveransen och se till att dina e-postmeddelanden når dina mottagare måste e-postmeddelandet följa ett visst antal regler.

* **Avsändarens namn och adress**: Adressen måste uttryckligen identifiera avsändaren. Domänen måste ägas av och registreras hos avsändaren. Domänregistret får inte privatiseras.
* **Ämne**: Undvik stora skiftlägen och skiljetecken och ord som ofta används av skräppost (&quot;Win&quot;,&quot;Free&quot;, osv.).
* **Anpassa e-postmeddelandet**: Om du anpassar e-postmeddelandet ökar risken för att meddelandet öppnas.
* **Bilder och text**: Respektera ett bra förhållande mellan text och bild (till exempel 60 % text och 40 % bilder).
* **Länk till Unsubscription och landningssida**: Avprenumerationslänken är viktig. Den måste vara synlig och giltig och formuläret måste vara funktionellt.
* **Använd verktyg** från Adobe Campaign för att optimera innehållet i e-postmeddelandet (leveransanalys, skräppostanalys).

Mer information om hur du redigerar e-postinnehåll finns i Översikt över [](../../designing/using/designing-content-in-adobe-campaign.md) e-postdesignern och i Bästa tillvägagångssätt [för](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)meddelandedesign.

## Avsändarens namn och adress {#sender-name}

Vissa Internet-leverantörer kontrollerar giltigheten för avsändaradressen (Från) innan de accepterar meddelanden. En felformaterad adress kan leda till att den nekas av den mottagande servern. Du måste se till att rätt adress anges på förekomstnivå eller i de vanligaste scenarierna. Kontakta administratören.

![](assets/delivery_content_edition16.png)

Mer information finns i [Anpassa avsändarens namn](../../designing/using/personalization.md#personalizing-the-sender).

## Subject line {#subject-line}

När du redigerar ett e-postmeddelande kan du testa olika ämnesrader och få en uppskattning av öppningsfrekvensen innan du skickar det. Mer information finns i [Testa ämnesraden i ett e-postmeddelande](../../sending/using/testing-subject-line-email.md).

![](assets/predictive_subject_line_example.png)

Mer information om hur du definierar ämnesraden i ett e-postmeddelande finns i [det här avsnittet](../../designing/using/subject-line.md).

## Send time optimization {#send-time-optimization}

Om du vill förbättra antalet meddelanden som skickas kan du definiera en sändningstid per mottagare manuellt. Varje profil får meddelandet vid det angivna datumet och den angivna tidpunkten, när det är möjligt.

Mer information finns i [Optimera sändningstiden](../../sending/using/optimizing-the-sending-time.md).

## Länk och formulär för avanmälan {#opt-out}

När meddelandet analyseras kontrollerar en typologiregel som standard om en avanmälningslänk har inkluderats och genererar en varning om den saknas.

Du måste kontrollera att avanmälningslänken fungerar som den ska innan du skickar iväg den. När du t.ex. skickar korrekturet ska du kontrollera att länken är giltig, att formuläret är online och att värdet på kontaktrutorna inte längre är markerat när du validerar det här. Du bör göra den här kontrollen systematiskt eftersom det alltid är möjligt att göra mänskliga fel när du anger länken eller när du ändrar formuläret.

Om ett problem upptäcks med att prenumerationen inte längre kan tas emot efter att leveransen har startats går det fortfarande att göra en manuell avanmälan (med funktionen för massuppdatering till exempel) för de mottagare som klickar på avanmälningslänken, även om de inte kunde bekräfta sitt val.

Som allmän regel ska du inte försöka hindra mottagare som vill avanmäla sig genom att kräva att de fyller i fält som e-postadress eller namn, till exempel. Startsidan för den sista prenumerationen bör bara ha en valideringsknapp. Begäran om ytterligare bekräftelse är inte tillförlitlig: en användare kan ha två e-postadresser som omdirigeras till samma ruta (till exempel: firstname.lastname@club.com och firstname.lastname@internet-club.com). Om profilen bara kommer ihåg den första adressen och vill avbeställa prenumerationen via ett meddelande som skickas till den andra, kommer formuläret att avslå detta eftersom den krypterade identifieraren och den angivna e-postadressen inte matchar.

## Analys av skräppostskydd {#anti-spam-analysis}

Adobe Campaign meddelanderedigerare integrerar en **skräppostanalys** som gör att du kan göra e-postpoäng för att avgöra om ett meddelande löper risk att betraktas som skräppost av de skräppostverktyg som används vid mottagande. For more on this, see [Previewing messages](../../sending/using/previewing-messages.md).

Klicka på i meddelandets innehållsredigerare **[!UICONTROL Preview]**. Ett meddelande varnar dig om skräppostkontrollen har upptäckt en hög risk för det här meddelandet. Klicka **[!UICONTROL Anti-spam analysis]** för att visa information.

![](assets/sending_anti-spam_analysis.png)

## Kontrollera meddelandets svarstid {#message-responsiveness}

Innan du skickar meddelandet kan du kontrollera hur meddelandet kommer att se ut på olika enheter. Det är för att säkerställa att den visas på ett optimalt sätt på olika webbklienter, webbmejl och enheter.

Adobe Campaign hämtar återgivningen och gör den tillgänglig i en dedikerad rapport. På så sätt kan du förhandsgranska det skickade meddelandet i olika sammanhang där det kan tas emot.

Se [E-poståtergivning](../../sending/using/email-rendering.md) för mer information.

![](assets/inbox_rendering_report_3.png)
