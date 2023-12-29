---
title: Campaign Standard Mobile Guide
description: Läs mer om de allmänna riktlinjerna för mobila leveranser i Adobe Campaign Standard, till exempel hur du konfigurerar dina mobilprogram eller skapar push-meddelanden och meddelanden i appen.
audience: channels
content-type: reference
topic-tags: mobile-guide
feature: Overview
role: User
level: Beginner
exl-id: d4e1b935-b21f-4a24-99ba-f455db0f7cfc
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 19%

---

# Kom igång med mobila kanaler {#mobile-guide}

<table style="table-layout:fixed">
<tr>
<td><img src="assets/do-not-localize/config_push.png" width="60px"><p>Lär dig hur du konfigurerar ditt mobilprogram för push-meddelanden </br><a href="#configuration-push">Klicka här</a></p></td>
<td><img src="assets/do-not-localize/config_inapp.png" width="60px"><p>Lär dig konfigurera ditt mobilprogram för meddelanden i appen </br><a href="#configuring-mobile-app">Klicka här</a></p></td>
</tr>
<tr>
<td><img src="assets/do-not-localize/push2.png" width="60px"><p>Läs mer om hur du skapar push-meddelanden </br><a href="#create-push">Klicka här</a></p></td>
<td><img src="assets/do-not-localize/inapp.png" width="60px"><p>Lär dig hur du skapar meddelanden i programmet</br><a href="#create-inapp">Klicka här</a></p></td></tr>
</table>

## Om mobilleverans {#about-mobile}

Med Adobe Campaign kan ni skapa och skicka personaliserade meddelanden i olika kanaler och mäta hur effektiva de är genom dedikerade rapporter.

Med Adobe Campaign Standard kan ni skicka mobilleveranser via tre olika kanaler:

* SMS, presenteras i avsnittet Om SMS-meddelanden.
* Push-meddelanden, som visas i avsnittet Om push-meddelanden.
* Meddelanden i appen som presenteras i avsnittet Om meddelanden i appen.

## Konfigurera ditt mobilprogram för push-meddelanden {#configuration-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Konfigurera ett mobilprogram med Adobe Experience Platform SDK</strong></p>
    </div>
    <p>Om du vill skicka meddelanden i appen och push-meddelanden måste dina mobilprogram konfigureras i Adobe Campaign med hjälp av Adobe Experience Platform SDK:er.</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>Klicka här</strong></a> för mer information.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Förstå Campaign Standardens nyttolaststruktur för push-meddelanden</strong></p>
    </div>
    <p>Läs mer om strukturen för den nyttolast som tas emot i mobilprogram när ett push-meddelande skickas till en app från Adobe Campaign Standard.</br><a href="../../administration/using/push-payload.md"><strong>Klicka här</strong></a> för mer information.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Implementera lokal meddelandespårning</strong></p>
    </div>
    <p>Lär dig här hur du säkerställer att lokal meddelandespårning har implementerats korrekt. </br><a href="../../administration/using/local-tracking.md"><strong>Klicka här</strong></a> för mer information.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Implementera push-spårning</strong></p>
    </div>
    <p>Lär dig hur du kontrollerar att spårning av push-meddelanden har implementerats korrekt på iOS och Android.</br><a href="../../administration/using/push-tracking.md"><strong>Klicka här</strong></a> för mer information.</p>
    <br>
  </td>
</tr>
</table>

## Konfigurera ett mobilprogram för meddelanden i appen {#configuring-mobile-app}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Konfigurera ett mobilprogram med Adobe Experience Platform SDK</strong></p>
    </div>
    <p>Om du vill skicka meddelanden i appen och push-meddelanden måste dina mobilprogram konfigureras i Adobe Campaign med hjälp av Adobe Experience Platform SDK:er.</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>Klicka här</strong></a> för mer information.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Mobil användning som stöds med Adobe Experience Platform SDK</strong></p>
    </div>
    <p>Läs mer om användningen av mobiler i Adobe Campaign Standard med Adobe Experience Platform SDK:er.</br><a href="../../administration/using/supported-mobile-use-cases.md"><strong>Klicka här</strong></a> för mer information.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Konfigurera taggningsregler för att stödja användningsfall i Adobe Campaign Standard</strong></p>
    </div>
    <p><a href="../../administration/using/configuring-rules-launch.md"><strong>Klicka här</strong></a> för att börja skapa dataelement och regler i användargränssnittet för datainsamling för att skicka PII och andra data från mobilprogram till Adobe Campaign Standard.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Implementera lokal meddelandespårning</strong></p>
    </div>
    <p>Lär dig här hur du säkerställer att lokal meddelandespårning har implementerats korrekt. </br><a href="../../administration/using/local-tracking.md"><strong>Klicka här</strong></a> för mer information.</p>
    <br>
  </td>
</tr>
</table>

## Skapa ett push-meddelande {#create-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Förbereda och skicka ett push-meddelande</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-a-push-notification.md"><strong>Läs här</strong></a> hur du förbereder ditt push-meddelande och hur du skickar det till målgruppen.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Anpassa ett push-meddelande</strong></p>
    </div>
    <p>I Adobe Campaign kan du finjustera leveransen genom att ha tillgång till en uppsättning alternativ när du utformar ett push-meddelande.</br><a href="../../channels/using/customizing-a-push-notification.md"><strong>Klicka här</strong></a> för mer information.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Skapa ett flerspråkigt push-meddelande</strong></p>
    </div>
    <p>Anpassa innehållet i push-meddelanden genom att skicka meddelanden baserat på de språk och regioner användarna föredrar.</br><a href="../../channels/using/creating-a-multilingual-push-notification.md"><strong>Klicka här</strong></a> för mer information.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Visa en bild från ett push-meddelande från Adobe Campaign Standard</strong></p>
    </div>
    <p><a href="../../administration/using/image-push-notification.md"><strong>Läs här</strong></a> hur du visar en bild från ett push-meddelande från Adobe Campaign på en iOS-enhet.</p>
    <br>
  </td>
</tr>
</table>

## Skapa ett meddelande i appen {#create-inapp}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Förbereda och skicka ett meddelande i appen</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-an-in-app-message.md"><strong>Läs här</strong></a> hur ni förbereder era meddelanden i appen och hur ni skickar dem till er målgrupp.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Anpassa meddelanden i appen</strong></p>
    </div>
    <p>Om du vill finjustera leveransen kan du använda Adobe Campaign till att få tillgång till en uppsättning avancerade alternativ när du utformar en app.</br><a href="../../channels/using/customizing-an-in-app-message.md"><strong>Klicka här</strong></a> för mer information.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Anpassa en lokal meddelandetyp</strong></p>
    </div>
    <p>Lokala meddelanden kan bara aktiveras av ett program vid en viss tidpunkt och beroende på en händelse. </br><a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type"><strong>Klicka här</strong></a> för mer information.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Rapport i appen</strong></p>
    </div>
    <p>Rapporten i appen innehåller information om leveranser i appen.</br><a href="../../reporting/using/in-app-report.md"><strong>Klicka här</strong></a> för mer information.</p>
    <br>
  </td>
</tr>
</table>

## Skapa SMS-meddelanden {#create-sms}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Skapa ett SMS-meddelande</strong></p>
    </div>
    <p>Att skapa en SMS-leverans påminner mycket om hur man skapar ett vanligt e-postmeddelande. </br>Stegen <a href="../../channels/using/creating-an-sms-message.md"><strong>detaljerad här</strong></a> beskriver konfigurationen som är specifik för den här kanalen.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Anpassa ett SMS
</strong></p>
    </div>
    <p>För att finjustera leveransen kan du med Adobe Campaign få tillgång till en uppsättning avancerade alternativ när du utformar ett SMS-meddelande.</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong>Klicka här för mer information.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Hantera inkommande SMS</strong></p>
    </div>
    <p>När en profil svarar på ett SMS-meddelande som skickades via Campaign kan du konfigurera meddelanden som automatiskt skickas tillbaka till dem samt åtgärden som ska utföras.Anpassa en lokal meddelandetyp</br><a href="../../channels/using/managing-incoming-sms.md"><strong>Klicka här för mer information.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>SMS-rapport</strong></p>
    </div>
    <p>SMS-rapporten innehåller information om SMS-leveranser, som levererade och avhoppsfrekvenser.</br><a href="../../reporting/using/sms-report.md"><strong>Klicka här</strong></a> för mer information.</p>
    <br>
  </td>
</tr>
</table>

## Felsökning för mobiler {#mobile-troubleshooting}

Följande sidor hjälper dig att lösa de vanligaste problemen som kan uppstå när du använder mobilleverans i Adobe Campaign Classic.

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Vanliga frågor om push-meddelanden</strong></p>
    </div>
    <p><a href="../../channels/using/about-push-notifications.md#push-faq"><strong>Klicka här för mer information.</p>
  </td>
  <td>
    <div>
    <p><strong>Vanliga frågor och svar om synkronisering i Adobe Launch</strong></p>
    </div>
    <p><a href="../../channels/using/in-app-faq.md"><strong>Klicka här för mer information.</p>
  </td>
  <td>
    <div>
    <p><strong>Vanliga frågor i appen</strong></p>
    </div>
    <p><a href="../../administration/using/syncwithlaunch-faq.md"><strong>Klicka här för mer information.</p>
  </td>
</tr>
</table>
