---
solution: Campaign Standard
product: campaign
title: Om import och export av data
description: Lär dig olika sätt att importera och exportera data med Adobe Campaign.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 24%

---


# Om import och export av data{#about-data-import-and-export}

Beroende på ditt företags behov har du flera sätt att importera och exportera data med Adobe Campaign:

* **Paket**: paket är XML-filer som gör att du kan exportera och importera konfigurationer och datauppsättningar från en Adobe Campaign-instans till en annan. Systemuppdateringar utförs även via paketimporter.
* **Listor**: alla listskärmar kan konfigureras och de data som visas exporteras i en separat fil.
* **Arbetsflöden**: importera data från filer och använda dem för att uppdatera databasen eller skicka e-postmeddelanden. Du kan också markera data som ska exporteras i filer. Arbetsflöden är det bästa sättet att automatisera regelbundna uppdateringar, till exempel profilimporter.

   * Med den här **[!UICONTROL Load file]** aktiviteten kan du importera data i ett strukturerat formulär och använda denna data i Adobe Campaign.  Data importeras tillfälligt och en annan aktivitet krävs för att den slutgiltigt ska kunna integreras i Adobe Campaign-databasen. Mer information om hur du använder den här aktiviteten finns i [det här avsnittet](../../automating/using/load-file.md).
   * Med den här **[!UICONTROL Transfer file]** aktiviteten så kan du ta emot eller skicka filer och testa om det finns filer eller listfiler i Adobe Campaign. Du kan använda den här aktiviteten före en **[!UICONTROL Load file]** om du behöver hämta filen från en extern källa. Mer information om hur du använder den här aktiviteten finns i [det här avsnittet](../../automating/using/transfer-file.md).

När du utformar importprocesser är det bäst att använda arbetsflödesmallar som du kan anpassa efter dina behov. Mer information om hur du konfigurerar en arbetsflödesmall för import av data finns i [det här användningsexemplet](../../automating/using/creating-import-workflow-templates.md).

Adobe Campaign erbjuder också ett förenklat sätt att utföra vanliga importer som består av att utforma **importmallar**. Importmallar är specialiserade arbetsflödesmallar som är tillgängliga via en dedikerad skärm. När den har designats behöver den användare som utför importen bara överföra filen för import i en förenklad vy.

**Relaterade ämnen**:

* [Importera data med importmallar](../../automating/using/importing-data-with-import-templates.md)
* [Definiera importmallar](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Hantera paket](../../automating/using/managing-packages.md)
