---
title: Kommande ändringar i push-meddelandekanalen
description: Kommande ändringar i push-meddelandekanalen
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: f9a0d01196ac4c31e57ae14cdfa448a9ffd6106f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 1%

---

# Kommande ändringar i push-meddelandekanalen {#push-upgrade}

Du kan använda Campaign för att skicka push-meddelanden på Android- och iOS-enheter. För att kunna göra detta förlitar sig Campaign på specifika prenumerationstjänster. Vissa viktiga ändringar av tjänsten Android Firebase Cloud Messaging (FCM) kommer att släppas 2024 och kommer att påverka din Adobe Campaign-implementering. För iOS-program ändrar dessutom Adobe sättet att tillåta administratörer att konfigurera certifikat.

## Vad har ändrats? {#push-changes}

### Android {#push-android}

Som en del av Google kontinuerliga arbete med att förbättra sina tjänster kommer de äldre FCM-API:erna att upphöra på **20 juni 2024**. Läs mer om HTTP-protokollet för Firebase Cloud Messaging i [Google Firebase-dokumentation](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

För närvarande använder Adobe Campaign Standard äldre HTTP-API:er för att skicka push-meddelanden för Android och kommer att göra ändringar under de kommande månaderna för att uppgradera till API:erna för HTTP v1.

### iOS {#push-ios}

Adobe kommer också att uppgradera Adobe Campaign Standard för iOS Push Notification Channel och ändra det sätt på vilket vi tillåter administratörer att konfigurera certifikat för sina iOS-program. Administratörer måste nu ladda upp iOS-certifikaten via Adobe Campaign Standard användargränssnitt.

## Påverkas du? {#push-impact}

Om du som Campaign Standard skickar push-meddelanden till dina målgrupper påverkas du.

## Hur migrerar jag? {#push-migration}

Dessa uppdateringar kräver en uppgradering av Campaign Standarden eftersom de påverkar konfigurationen av mobilkanalen och behörighetshanteringen.

Detaljerade instruktioner kommer snart att ges för att underlätta en smidig övergångsprocess.

Vårt kundsupportteam kommer att finnas tillgängligt för att hjälpa dig under denna övergång. Vi kan också vara värd för webbinarier och hjälpmedelsseminarier som täcker de tekniska aspekterna och bästa metoderna för övergången.

Under tiden rekommenderar vi att du tar dig tid att granska din nuvarande konfiguration och anpassning i Adobe Campaign Standard så att du är redo att göra nödvändiga ändringar om det behövs.

Om du har frågor eller funderingar direkt kan du kontakta vårt supportteam.
