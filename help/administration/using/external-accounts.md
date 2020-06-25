---
title: Externa konton
description: Konfigurera externa konton för att konfigurera anslutningar till externa system som SFTP-servrar.
page-status-flag: never-activated
uuid: 5d2e2e3d-5d1f-4466-97e5-842c50390146
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: d5c6a3d4-f767-46c1-a8c0-3b9dc52dcea8
internal: n
snippet: y
context-tags: extAccount,main;extAccount,overview
translation-type: tm+mt
source-git-commit: 85dc2b3ba9a781483f88238fbf5a9208a0c18c37
workflow-type: tm+mt
source-wordcount: '1559'
ht-degree: 0%

---


# Externa konton{#external-accounts}

Ett externt konto är en konfiguration som gör att du kan konfigurera och testa åtkomsten till en server som ligger utanför Adobe Campaign.

Dessa externa konton kan användas i Campaign-arbetsflöden för att få tillgång till och hantera data.

Du kan ställa in följande typer av externa konton:

* SFTP. For more on this, refer to [this section](#sftp-external-account).
* Amazon Storage Service (S3). For more on this, refer to [this section](#amazon-s3-external-account).
* Adobe Experience Manager. For more on this, refer to [this section](#adobe-experience-manager-external-account).
* Adobe Analytics. For more on this, refer to [this section](../../integrating/using/configure-campaign-analytics-integration.md).
* Google reCAPTCHA. For more on this, refer to [this section](#google-recaptcha-external-account).
* Microsoft Azure Blob-lagring. For more on this, refer to [this section](#microsoft-azure-external-account).

>[!NOTE]
>
>Andra typer av externa konton används av Adobe under produktprovisioneringsprocessen. Från och med Campaign Standard 17.9 kan FTP-externa konton fortfarande definieras, men de kan inte längre användas i nya arbetsflödesaktiviteter. Om du redan har konfigurerat en anslutning är den fortfarande aktiverad.

Externa konton kan konfigureras av administratörer på **[!UICONTROL Administration > Application settings > External accounts]** menyn.

## Skapa ett externt konto {#creating-an-external-account}

Adobe Campaign har en uppsättning fördefinierade externa konton. Om du vill skapa anslutningar till externa system, t.ex. FTP-servrar som används för filöverföringar, kan du skapa egna externa konton.

Externa konton används av tekniska processer som tekniska arbetsflöden eller kampanjarbetsflöden. När du konfigurerar en filöverföring i ett arbetsflöde eller ett datautbyte med något annat program (Adobe Target, Experience Manager, osv.) måste du välja ett externt konto.

1. Klicka på **[!UICONTROL Create]** knappen.
1. Ange en etikett. Etiketten och ID:t används när du väljer externa konton i arbetsflöden.
1. Välj vilken typ av konto du vill skapa.
1. Konfigurera åtkomsten till kontot genom att ange autentiseringsuppgifter, serveradress, portnummer och nycklar när det är relevant.

   Den nödvändiga informationen tillhandahålls vanligtvis av providern för den server som du ansluter till.

1. Spara ditt konto.

Det externa kontot skapas och läggs till i kontolistan. Den är nu tillgänglig för dina data-/filöverföringar eller routningskonfigurationer i arbetsflödesaktiviteter och leveransegenskaper.

## Externt SFTP-konto {#sftp-external-account}

Olika externa kontotyper kräver att annan information anges.

Ange följande information för ett externt SFTP-konto:

* Serveradress. Till exempel **ftp.domain.com**.
* Portnummer. For example, **22**.
* Autentiseringsuppgifter för SFTP-server: kontonamn och lösenord som används för att ansluta till servern.

### Adobe SFTP-serverrekommendationer {#adobe-hosted-sftp-server-recommendations}

När du hanterar filer och data för ETL-ändamål lagras dessa filer på en SFTP-värdserver som tillhandahålls av Adobe. Denna SFTP är avsedd att vara ett tillfälligt lagringsutrymme där du kan styra lagring och borttagning av filer.

Om utrymmet inte används eller övervakas korrekt kan det snabbt fylla det fysiska utrymmet på servern och orsaka allvarliga problem. Det kan leda till dataförluster eller skador på din plattform.

För att undvika sådana problem rekommenderar Adobe att du följer god praxis nedan:

* Behåll minsta möjliga data.
* Använd nyckelbaserad autentisering för att undvika att lösenordet förfaller. Format som stöds är **endast OpenSSH** och **SSH2** . Du måste ange den offentliga nyckeln till Adobes supportteam för att få den överförd till Campaign-servern.
* Spara data så länge som krävs. 15 dagar är den maximala tidsgränsen.
* Använd arbetsflöden för att ta bort data på rätt sätt (hantera lagring från arbetsflöden som förbrukar data).
* Använd gruppbearbetning i SFTP-överföringar och i arbetsflöden.
* Hantera fel/undantag.
* Det kan hända att du loggar in på SFTP för att direkt kontrollera vad som finns där.
* Kom ihåg att SFTP-diskhantering i första hand är ditt ansvar.

Observera också att de offentliga IP-adresser som du försöker initiera SFTP-anslutningen från måste läggas till i listan över tillåtna i Campaign-instansen. Du kan begära att få lägga till IP-adresser i listan över tillåtna användare via en [supportanmälan](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html), tillsammans med den offentliga nyckeln som ska användas för autentisering.

SFTP-servrar kan hanteras från Kontrollpanelen. Mer information finns i dokumentationen för [Kontrollpanelen](https://docs.adobe.com/content/help/en/control-panel/using/sftp-management/about-sftp-management.html).

>[!NOTE]
>
>Kontrollpanelen är bara tillgänglig för administratörer som använder AWS som värd.
Kontrollera om din instans finns på AWS [här](https://docs.adobe.com/content/help/en/control-panel/using/faq.html#ims-org-id).

## Externt Amazon S3-konto {#amazon-s3-external-account}

Serverfältet för Amazon S3 ska fyllas i enligt följande:

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

Markera **[!UICONTROL Keep files in S3 encrypted]** kryssrutan om du vill lagra filen i S3-krypterat läge.

![](assets/external_accounts_2.png)

Den nödvändiga informationen tillhandahålls vanligtvis av providern för den server som du ansluter till.

Ange den **[!UICONTROL AWS Region]** associerade slutpunkten. Du kan kontrollera vilka regioner och signaturversioner som stöds i den officiella [Amazon S3-dokumentationen](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region).

>[!NOTE]
>
>Du **[!UICONTROL Receiver server]** bör ange din adress utan din AWS-region. Den läggs sedan automatiskt till i din URL.

### Kontorekommendationer för Amazon S3 {#amazon-s3-account-recommendations}

Vi rekommenderar att du följer dessa rekommendationer för att hjälpa dig att konfigurera ditt Amazon S3-konto:

* Skapa en strikt bucketprincip för att begränsa åtkomsten till S3-bucket. Bucket-principen kan konfigureras när en bucket skapas. Mer information finns i [Amazon S3-dokumentationen](https://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html).
* När du skapar ett externt konto aktiverar du krypteringen för att lagra känsliga data i S3-bucket genom att markera **[!UICONTROL Keep files in S3 encrypted]** rutan.
* Bevilja bucket-behörigheter för att ange vem som får åtkomst till objektet i en bucket. Mer information om bucket-behörighet finns i [Amazon S3-dokumentationen](https://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html).

## Adobe Experience Manager external account {#adobe-experience-manager-external-account}

Adobe Experience Manager externa konton används när Campaign integreras med Experience Manager.

Processer och krav som rör den här integreringen är tillgängliga i [det här dokumentet](../../integrating/using/get-started-campaign-integrations.md).

När du konfigurerar det nya externa kontot måste du ange följande information:

* Server: Ange webbadressen till Adobe Experience Manager-servern. Exempel:

   ```
   http://aem.domain.com:4502
   ```

* Autentiseringsuppgifter för AEM-konto: använd det konto som kommer att få åtkomst till instansen Adobe Experience Manager. Det ska vara ett konto i kampanjfjärrgruppen i Experience Manager.

## Externt Google reCAPTCHA-konto {#google-recaptcha-external-account}

>[!NOTE]
>
>Google reCAPTCHA-konfigurationen kräver ett Google-konto.

Med Google reCAPTCHA-mekanismen kan du skydda din landningssida mot skräppost och missbruk som orsakas av stötar. Detta är inte påträngande för era kunder eftersom det inte kräver någon interaktion från dem och baseras på interaktioner med er webbplats. Om du vill registrera din webbplats läser du den här [sidan](https://www.google.com/recaptcha/admin/create). Du måste välja typen V3 reCAPTCHA.

Om du vill lägga till Google reCAPTCHA V3 på din landningssida måste du först konfigurera det på ditt externa konto. Mer information om hur du lägger till den på landningssidan finns i det här [avsnittet](../../channels/using/configuring-landing-page.md#setting-google-recaptcha).

Ange följande information för ett externt Google reCAPTCHA V3-konto:

* A **[!UICONTROL Label]** och **[!UICONTROL ID]** A för ditt externa konto
* **[!UICONTROL Type]**: Google reCAPTCHA
* Dina **[!UICONTROL Site key]** och **[!UICONTROL Site secret]**
* A **[!UICONTROL Threshold]** mellan 0 och 1

   Värdet 0,0 **[!UICONTROL Threshold]** innebär att det troligtvis är en bot och 1,0 troligtvis en bra interaktion. Som standard kan du använda ett tröskelvärde på 0,5.

![](assets/external_accounts_3.png)

## Externt konto för Microsoft Azure Blob Storage {#microsoft-azure-external-account}

>[!NOTE]
>
>Information som behövs för att konfigurera ditt externa konto i Adobe Campaign Standard finns i Azure Portal genom att välja **[!UICONTROL Settings]** > **[!UICONTROL Access keys]**.

Azure Blob-lagringskopplingen kan användas för att importera eller exportera data till Adobe Campaign med hjälp av en **[!UICONTROL Transfer file]** arbetsflödesaktivitet. For more on this, refer to this [section](../../automating/using/transfer-file.md#azure-blob-configuration-wf).

Ange följande information för ett externt Microsoft Azure Blob Storage-konto:

* A **[!UICONTROL Label]** och **[!UICONTROL ID]** A för ditt externa konto
* **[!UICONTROL Type]**: Microsoft Azure Blob Storage
* Ditt **[!UICONTROL Account name]** och **[!UICONTROL Account key]**. Om du vill veta var du hittar kontonamn och nyckel kan du gå till den här [sidan](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage).
* Din **[!UICONTROL Endpoint suffix]**. Den finns på din **[!UICONTROL Connection string]** av **[!UICONTROL Access keys]** menyn i Azure Portal. Mer information finns på den här [sidan](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage).
* Ditt **[!UICONTROL Container]** namn. Om du planerar att använda mer än en behållare måste du skapa så många externa konton som behållare.
* Med det här **[!UICONTROL Concurrency]** alternativet kan du finjustera hastigheten på filöverföringar.

![](assets/external_accounts_4.png)

När konfigurationen är klar klickar du på **[!UICONTROL Test connection]** för att länka Adobe Campaign till Microsoft Azure Blob Storage.

### Rekommendationer för Microsoft Azure Blob-lagring {#azure-blob-recommendations}

**Kryptering**

Adobe Campaign använder en säker anslutning (HTTPS) för att komma åt ditt Microsoft Azure Blob-lagringskonto.

**Kontonyckel**

När du konfigurerar ditt externa konto måste du använda något av de **[!UICONTROL Account key]** tillgängliga alternativen i Azure Portal. Mer information om var du hittar dina kontonycklar finns på den här [sidan](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage#view-access-keys-and-connection-string).

**Optimera filöverföringshastigheten**

Med det här **[!UICONTROL Concurrency]** alternativet kan du finjustera hastigheten på filöverföringar.
Det representerar antalet trådar som ska användas för att utföra filöverföringen. Var och en av dessa trådar laddar ned ungefär 1 MB från blobben. De köas sedan för att skrivas till disk. Observera att genom att öka antalet trådar ökar du även belastningen på de resurser som används av programmet under filöverföringen.

När filöverföringen är klar hittar du prestandamått i arbetsflödesloggarna.

**Försök igen**

Som standard har filöverföringen för Azure Blob upp till fyra försök.  Om Azure Storage-tjänsten returnerar en felkod som 503 (servern är upptagen) eller 500 (timeout för åtgärden), kan det tyda på att du närmar dig eller överskrider skalbarheten för ditt lagringskonto. Det här kan hända om du använder ett nytt konto eller utför tester.

Om felet kvarstår kan du öka antalet försök genom att skapa ett alternativ under den avancerade menyn **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

Om det implementeras måste alternativet skapas på följande sätt:

```
ID:        AzureBlob_Max_Retries
Date type: Integer
Default:   <the number of retries needed>
```
