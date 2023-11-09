---
title: Kommande ändringar i push-meddelandekanalen
description: Kommande ändringar i push-meddelandekanalen
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: 870b01f118974ed62755dd79143b990cfa2e4e85
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 0%

---

# Kommande ändringar i push-meddelandekanalen {#push-upgrade}

Den här sidan beskriver de kommande ändringarna av Android- och iOS Push Notification Channel i Adobe Campaign Standard.

Det finns viktiga uppdateringar om kommande ändringar av Push Notification Channel på Android- och iOS-enheter som kan påverka Adobe Campaign Standard-implementeringen.

## Android {#push-android}

Som en del av Google kontinuerliga arbete med att förbättra sina tjänster gör Google ändringar i HTTP-protokollet för Firebase Cloud Messaging. Detta innebär att Firebase Cloud Messaging &quot;HTTP legacy APIs&quot; som togs bort den 20 juni 2023 kommer att ersättas med &quot;HTTP v1 APIs&quot; i juni 2024. (https://firebase.google.com/docs/cloud-messaging/http-server-ref). För närvarande använder Adobe Campaign Standard äldre HTTP-API:er för att skicka push-meddelanden för Android och kommer att göra ändringar under de kommande månaderna för att uppgradera till API:erna för HTTP v1. Mer information om dessa ändringar kommer att ges när Adobe arbetar med dessa uppdateringar.

## iOS {#push-ios}

Adobe kommer också att uppgradera Adobe Campaign Standard för iOS Push Notification Channel och ändra det sätt på vilket vi tillåter administratörer att konfigurera certifikat för sina iOS-program. Administratörer måste nu ladda upp iOS-certifikaten via Adobe Campaign Standard användargränssnitt.

Vi förstår att ni, våra kunder, förlitar er på dessa tjänster för era marknadsföringskampanjer och kommunikationsbehov och vill försäkra er om att ni är medvetna om våra pågående planer och support.

## Vad gör vi?

* **Produktändringar**: Arbeta med produktändringar för att stödja uppgraderingar av tekniska stackar i Android/iOS Push-meddelandekanal.

* **Detaljerade instruktioner**: Vi kommer att tillhandahålla stegvisa guider och andra resurser som underlättar en smidig övergångsprocess.

* **Support**: Vårt kundsupportteam kommer att finnas tillgängligt för att hjälpa dig under den här övergången. Vi kan också vara värd för webbinarier och hjälpmedelsseminarier som täcker de tekniska aspekterna och bästa metoderna för övergången.

## Hur påverkar det dig?

* **Håll dig informerad**: Håll ett öga på inkorgen för mer information från oss, inklusive den detaljerade övergångsplanen.

* **Granska aktuell inställning**: Ta den här tiden till att granska din nuvarande konfiguration och anpassning i Adobe Campaign Standard så att du är redo att göra nödvändiga ändringar om det behövs.

* **Kontakta oss**: Om du har frågor eller funderingar direkt kan du kontakta vårt supportteam.

## Nästa steg

Under de närmaste veckorna kommer vi att dela mer information om de ändringar som planeras för Push Channel för Android/iOS, inklusive tidslinjer och åtgärdsobjekt. Vårt främsta mål är att göra övergången så smidig som möjligt för dig och ditt team.

Tack för din förståelse för att vi anpassar oss till dessa förändringar. Er framgång är vår högsta prioritet, och vi strävar efter att stödja er i varje steg på vägen.