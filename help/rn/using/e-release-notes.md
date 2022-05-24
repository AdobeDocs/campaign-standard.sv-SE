---
title: Tidig versionsinformation
description: Tidig versionsinformation
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 104855851906b96f79a89179108548b3dde17b4f
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 24%

---

# Tidig versionsinformation {#new-release}

Den här sidan beskriver nya funktioner, förbättringar och korrigeringar som ingår i nästa version av Campaign Standard.

>[!CAUTION]
>
> Innehållet kan ändras utan föregående meddelande fram till uppgraderingsdatumet för mellanlagringsmiljöerna. Läs mer på [sidan för versionsplanering](../../rn/using/release-planning.md).

## Version 22.2 – juni 2022 {#rn-2022}

**Förbättringar**

* **Adobe Notification Service** - Campaign innehåller Adobe Notification Service som gör det möjligt för Experience Cloud att informera användare över Experience Cloud om aktiviteter som är viktiga för dem att känna till. Från och med version 22.2 har användarupplevelsen förbättrats: meddelanden prioriteras och produktgenererade meddelanden skiljs från statusmeddelanden i Adobe. När meddelandet dessutom hänvisar till ett specifikt arbetsflöde kan du nu komma åt motsvarande arbetsflöde direkt från e-postmeddelandet eller produktmeddelandet.  Mer information om Adobe Campaign-meddelanden finns i [Adobe Campaign-meddelanden](../../administration/using/sending-internal-notifications.md).

* **Fördröjd start av arbetsflöde** - Du kan nu fördröja körningen av dina arbetsflöden för att undvika överbelastning. Denna garanti aktiveras av Adobe via ett dedikerat alternativ och säkerställer att det blir en fördröjning mellan arbetsflödena. Funktionsalternativen anger antalet arbetsflöden som kan köras samtidigt och fördröjningen (i sekunder) mellan dem.


**Säkerhetsuppgradering**

* Den här versionen innehåller en säkerhetsuppgraderingsaktivitet som minskar Apache-problemet och gör instansmiljön säkrare. [Läs mer](https://experienceleague.adobe.com/docs/campaign-classic/using/technotes/technote-migration/acc-apache-upgrade.html){target=&quot;_blank&quot;}.

