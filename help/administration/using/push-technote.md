---
title: Kommande ändringar i push-meddelandekanalen
description: Kommande ändringar i push-meddelandekanalen
audience: channels
feature: Push
role: Admin
level: Experienced
exl-id: e273b443-7c43-482b-8f86-60ada4b57cbf
source-git-commit: ac4a52263482557a6d5c370af6df5d54a42671b4
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 5%

---

# Kommande ändringar i push-meddelandekanalen {#push-upgrade}

Du kan använda Campaign för att skicka push-meddelanden på Android- och iOS-enheter. För att kunna göra detta förlitar sig Campaign på specifika prenumerationstjänster. Vissa viktiga ändringar av tjänsten Android Firebase Cloud Messaging (FCM) kommer att släppas i vinterversionen 24.1 2024 och kommer att påverka din Adobe Campaign-implementering. För iOS-program ändrar dessutom Adobe sättet att tillåta administratörer att konfigurera certifikat.

## Vad har ändrats? {#push-changes}

### Android {#push-android}

Som en del av Google kontinuerliga arbete med att förbättra sina tjänster kommer de äldre FCM-API:erna att upphöra på **20 juni 2024**. Läs mer om HTTP-protokollet för Firebase Cloud Messaging i [Google Firebase-dokumentation](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

För närvarande använder Adobe Campaign Standard äldre HTTP-API:er för att skicka push-meddelanden för Android och kommer att göra ändringar under de kommande månaderna för att uppgradera till API:erna för HTTP v1.

### iOS {#push-ios}

Adobe kommer också att uppgradera Adobe Campaign Standard för iOS Push Notification Channel och ändra det sätt på vilket vi tillåter administratörer att konfigurera certifikat för sina iOS-program. Från och med Winter-utgåvan 24.2 2024 måste administratörer överföra iOS-certifikaten via Adobe Campaign Standard användargränssnitt i dina mobila programegenskaper.

## Påverkas du? {#push-impact}

Om du som Campaign Standard skickar push-meddelanden till dina målgrupper påverkas du.

## Hur migrerar jag? {#push-migration}

Uppdateringarna kräver en uppgradering av Campaign Standarden till vinterversionen 24.1 2024 eftersom de påverkar konfigurationen av mobilkanalen och behörighetshanteringen.

Detaljerade instruktioner kommer snart att ges för att underlätta en smidig övergångsprocess.

Vårt kundsupportteam kommer att finnas tillgängligt för att hjälpa dig under denna övergång. Vi kan också vara värd för webbinarier och hjälpmedelsseminarier som täcker de tekniska aspekterna och bästa metoderna för övergången.

Under tiden rekommenderar vi att du tar dig tid att granska din nuvarande konfiguration och anpassning i Adobe Campaign Standard så att du är redo att göra nödvändiga ändringar om det behövs.

Om du har frågor eller funderingar direkt kan du kontakta vårt supportteam.
