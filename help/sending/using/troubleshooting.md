---
title: Felsöka leveransproblem i Adobe Campaign Standard
description: Lär dig vad du ska göra när du får leveransproblem med Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87168dca3604073d8a540c579448ab65f07cd976

---


# Felsökning{#troubleshooting}

Har du något leveransproblem? Du kan hitta lösningen här.

## Samma felmeddelande för en Internet-leverantör {#same-error-for-an-isp}

**Varför får jag alltid samma felmeddelande för en viss Internet-leverantör?**

Om du alltid får samma felmeddelande för en Internet-leverantör, kan din e-postadress eller IP-adress ha identifierats som defekt av Internet-leverantören. Utför följande rekommendationer:
* Kontrollera om du får en stor andel fel kopplade till obefintliga e-postadresser (okända **** användare).
* Uppdatera dina prenumerationsformulär för att upptäcka eventuella fel i de angivna domännamnen (till exempel: gmaul.com eller yaho.com).
* Om du märker fel som anger att dina meddelanden har deklarerats som skräppost, eller att dina meddelanden alltid är blockerade, kan du försöka utesluta mottagare som inte har öppnat eller klickat i något av dina meddelanden de senaste 12 månaderna från målet.

Om problemet kvarstår kontaktar du de kommersiella tjänsterna, leveranstjänsterna eller Adobe Campaign-supporten.

## Svartlistning kontra karantän {#blacklisting-versus-quarantine}

* **Vad är skillnaden mellan en svartlistad e-postadress och en e-postadress i karantän?**

   * Statusen **[!UICONTROL Blacklisted]** är ett resultat av en feedbackslinga (när en person rapporterar ett meddelande som skräppost).

   * Statusen **[!UICONTROL Quarantined]** är ett resultat av en mjuk eller hård studsa.
   Mer information finns i det här [avsnittet](../../sending/using/understanding-quarantine-management.md#quarantine-vs-blacklisting).

* **Vad betyder de olika anledningarna till karantänfel?**

   Här följer tio möjliga orsaker: inte definierad, okänd användare, ogiltig domän, svartlistad adress, nekad, fel ignorerad, ej tillgänglig, konto inaktiverat, postlåda full, inte ansluten.

   Mer information finns i [Om karantänhantering](../../sending/using/understanding-quarantine-management.md).

## Osvartlistning {#unblacklisting}

* **En av mina mottagare blev svartlistad av misstag. Hur avlistar jag dem så att jag kan börja skicka dem igen?**

   * Gå till **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * I informationen för motsvarande post anger du värdet för **[!UICONTROL Status]** fältet till **[!UICONTROL Valid]**.
   * Spara posten.

* **Hur kan jag ta reda på om en av mina IP-adresser är svartlistad? Hur avsvartlistar jag mina IP-adresser?**

   Om du vill kontrollera om din IP-adress är svartlistad kan du använda olika webbplatser för att verifiera den:
   * https://mxtoolbox.com/
   * https://whatismyipaddress.com/blacklist-check
   * https://www.blacklistalert.org/
   I allmänhet returnerar resultatet av IP-adresskontrollen en lista som innehåller information om svartlistan och även namnet på den webbplats som svartlistade IP-adressen.

   Genom att klicka på motsvarande länk kan du komma åt webbplatsinformationen.

   Sedan kan du begära att din webbplats avlistas från den webbplats som svartlistade IP-adressen.

   >[!NOTE]
   >
   >Borttagningsprocessen kan variera beroende på webbplatsen. Vissa webbplatser kräver att du skapar ett konto, medan andra bara behöver du ange IP-adressen.
