---
title: Felsökning av leveransproblem i Adobe Campaign Standard
description: Lär dig vad du ska göra när du får leveransproblem med Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 0470b986-c00a-4441-8621-82c7112a9953
source-git-commit: 449187bba167f9ce00e644d44a124b36030ba001
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# Felsökning{#troubleshooting}

Har du något leveransproblem? Du kan hitta lösningen här.

## Samma felmeddelande för en Internet-leverantör {#same-error-for-an-isp}

**Varför får jag alltid samma felmeddelande för en viss Internet-leverantör?**

Om du alltid får samma felmeddelande för en Internet-leverantör, kan din e-postadress eller IP-adress ha identifierats som defekt av Internet-leverantören. Utför följande rekommendationer:

* Kontrollera om du får ett stort antal fel som är kopplade till obefintliga e-postadresser (**Okänd användare**).
* Uppdatera dina prenumerationsformulär för att upptäcka eventuella fel i de angivna domännamnen (till exempel: gmaul.com eller yaho.com).
* Om du märker fel som anger att dina meddelanden har deklarerats som skräppost, eller att dina meddelanden alltid är blockerade, kan du försöka utesluta mottagare som inte har öppnat eller klickat i något av dina meddelanden de senaste 12 månaderna från målet.

Om problemet kvarstår kontaktar du den kommersiella tjänsten, leveransprogrammet eller Adobe Campaign support.

## Blockeringslista kontra karantän {#denylist-versus-quarantine}

* **Vad är skillnaden mellan en e-postadress på blockeringslista och en e-postadress i karantän?**

   * Statusen **[!UICONTROL On denylist]** är ett resultat av en [feedbackslinga](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=sv-SE#feedback-loops) (när en person rapporterar ett meddelande som skräppost).

   * Statusen **[!UICONTROL Quarantined]** är ett resultat av ett mjukt eller hårt studsande.

  Mer information finns i [det här avsnittet](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist).

* **Vad betyder de olika karantänfelen?**

  Här är tio möjliga orsaker: inte definierad, okänd användare, ogiltig domän, adress på blockeringslista, nekad, fel ignorerad, kontot inaktiverat, postlådan full, inte ansluten.

  Mer information finns i [Om karantänhantering](../../sending/using/understanding-quarantine-management.md).

## Tar bort från blockeringslista {#removing-from-denylist}

* **En av mina mottagare lades till i blockeringslista av misstag. Hur tar jag bort dem från blockeringslista så att jag kan börja skicka dem igen?**

   * Gå till **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * Ange värdet för fältet **[!UICONTROL Status]** till **[!UICONTROL Valid]** i informationen för motsvarande post.
   * Spara posten.

* **Hur kan jag ta reda på om en av mina IP-adresser finns på blockeringslista? Hur tar jag bort mina IP-adresser från en blockeringslista?**

  Om du vill kontrollera om din IP-adress finns i blockeringslista kan du använda olika webbplatser för att verifiera den, till exempel:
   * [MX-verktygslåda](https://mxtoolbox.com/)
   * [Vad är min IP-adress](https://whatismyipaddress.com)

  I allmänhet returnerar resultatet av IP-adresskontrollen en lista som innehåller information om blockeringslista och även namnet på den webbplats som blockerade IP-adressen.

  Genom att klicka på motsvarande länk kan du komma åt webbplatsinformationen.

  Sedan kan du begära att din webbplats tas bort från den webbplats som lade till IP-adressen till blockeringslista.

  >[!NOTE]
  >
  >Borttagningsprocessen kan variera beroende på webbplatsen. Vissa webbplatser kräver att du skapar ett konto, medan andra bara behöver du ange IP-adressen.
