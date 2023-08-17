---
title: Konfigurera SMS-kanal
description: Lär dig SMS-konfigurationssteg, inklusive routning, kodning, format och avancerade egenskaper
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5ff1d636-eac7-4909-be16-4f4b439b19ff
source-git-commit: 6c96a5d294c6e96d20571d176898290c9c026f0b
workflow-type: tm+mt
source-wordcount: '1591'
ht-degree: 89%

---

# Konfigurera SMS-kanal{#configuring-sms-channel}

Om du vill skicka SMS-meddelanden måste ett eller flera externa konton konfigureras av en administratör i menyn **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL SMS]** > **[!UICONTROL SMS accounts]** .

Stegen för att skapa och ändra ett externt konto finns i avsnittet [Externa konton](../../administration/using/external-accounts.md).  Nedan hittar du specifika parametrar för externa konton för att skicka SMS-meddelanden.

## Definiera en SMS-dirigering {#defining-an-sms-routing}

>[!IMPORTANT]
>
>Om du använder samma konto och lösenord för flera externa SMS-konton kan det leda till konflikter och överlappning mellan kontona. Se [Felsökningssida för SMS](troubleshooting-sms.md#external-account-conflict).

Det externa kontot **[!UICONTROL SMS routing via SMPP]** anges som standard. Det kan dock vara användbart att lägga till andra konton.

Om du vill använda SMPP-protokollet kan du även skapa ett nytt externt konto.  Mer information om SMS-protokoll och inställningar finns i den här [tekniska informationen](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html).

1. Skapa ett nytt externt konto från **[!UICONTROL Administration > Application settings > External accounts]**.
1. Definiera kontotypen som **[!UICONTROL Routing]**, kanalen som **[!UICONTROL Mobile (SMS)]** och leveransläget som **[!UICONTROL Bulk delivery]**.

   ![](assets/sms_routing.png)

1. Definiera anslutningsinställningar.

   Om du vill ange anslutningsinställningar som är specifika för att skicka SMS-meddelanden kontaktar du din SMS-tjänstleverantör som förklarar hur du fyller i de olika externa kontofälten.

   ![](assets/sms_connection.png)

   Med det här **[!UICONTROL Enable TLS over SMPP]** alternativet så kan du kryptera SMPP-trafik.

   **[!UICONTROL Enable verbose SMPP traces in the log file]** ger dig möjligheten att dumpa all SMPP-trafik i loggfiler.  Det här alternativet måste vara aktiverat för att kunna felsöka anslutningen och jämföra med den trafik som leverantören ser.

1. Kontakta Adobe som kommer att ge dig det värde som du behöver ange i fältet **[!UICONTROL SMS-C implementation name]** beroende på vilken leverantör du väljer.
1. Definiera inställningarna för SMPP-kanalen.  Du kan läsa mer i avsnittet [SMS-kodning och format](#sms-encoding-and-formats).

   Aktivera **[!UICONTROL Store incoming MO in the database]** om du vill att alla inkommande SMS ska lagras i tabellen inSMS.  Mer information om hur du hämtar inkommande SMS hittar du i det här [avsnittet](../../channels/using/managing-incoming-sms.md#storing-incoming-sms).

   Med det här **[!UICONTROL Enable Real-time KPI updates during SR processing]** alternativet kan **[!UICONTROL Delivered]** eller **[!UICONTROL Bounces + Errors]** KPI:er uppdateras i realtid när leveransen är klar.  Dessa KPI:er finns i **[!UICONTROL Deployment]**-fönstret och beräknas om direkt från den SR (Statusrapport) som tagits emot av leverantören.  

   ![](assets/sms_connection_1.png)

1. Definiera **[!UICONTROL Throughput and timeouts]**-parametrarna.

   Du kan ange maximal genomströmning för utgående meddelanden (&quot;MT&quot;, Mobile Terminated) i MT per sekund.  Om du anger &quot;0&quot; i motsvarande fält är dataflödet obegränsat.

   Värdena för alla fält som motsvarar varaktighet måste fyllas i i sekunder.

1. Definiera SMS-C-specifika parametrar om du måste definiera en specifik kodmappning. Mer information finns i avsnittet [SMSC-specifikationer](#smsc-specifics) .

   Aktivera **[!UICONTROL Send full phone number (send characters other than digits)]**-alternativet om du inte vill följa SMPP-protokollet och överföra **[!UICONTROL +]** prefixet till SMS-leverantörens server (SMS-C).

   Eftersom vissa leverantörer kräver att **[!UICONTROL +]** prefixet används bör du kontakta leverantören och föreslå att du aktiverar det här alternativet om det behövs.

1. Definiera vid behov automatiska svar för att utlösa åtgärder baserat på innehållet i ett svar.  Mer information om detta hittar du i [det här avsnittet](../../channels/using/managing-incoming-sms.md#managing-stop-sms).
1. Spara konfigurationen för det externa SMS-dirigeringskontot.

Nu kan du använda din nya dirigering för att skicka SMS-meddelanden med Adobe Campaign.

## SMS-kodning och format {#sms-encoding-and-formats}

### SMS-kodning, längd och transkribering {#sms-encoding--length-and-transliteration}

Som standard uppfyller antalet tecken i ett SMS-meddelande GSM-standarden (Global System for Mobile Communications).

SMS-meddelanden som använder GSM-kodning kan innehålla högst 160 tecken eller 153 tecken per SMS för meddelanden som skickas i flera delar.

>[!NOTE]
>
>Vissa tecken räknas som två (parenteser, hakparanteser, eurosymbolen etc.).  En lista med tillgängliga GSM-tecken finns i avsnittet [Teckentabell - GSM-standard](#table-of-characters---gsm-standard) .

Om du vill kan du tillåta teckentranskribering genom att markera motsvarande ruta.

![](assets/sms_transliteration.png)

Transkriberingen ersätter ett tecken i ett SMS med ett annat om det tecknet inte beaktas av GSM-standarden.

* Om transkribering är **tillåtet** ersätts varje tecken som inte beaktas som ett GSM-tecken när meddelandet skickas.  Bokstaven &quot;ë&quot; kommer exempelvis att ersättas med &quot;e&quot;.  Meddelandet ändras därför något men teckengränsen förblir densamma.
* När transkriberingen **inte är godkänd** skickas varje meddelande som innehåller tecken som inte beaktas i binärt format (Unicode). Alla tecken skickas då som de är.  SMS-meddelanden som använder Unicode är dock begränsade till 70 tecken (eller 67 tecken per SMS för meddelanden som skickas i flera delar).  Om det maximala antalet tecken överskrids skickas flera meddelanden vilket kan medföra extra kostnader.

>[!IMPORTANT]
>
>Om du infogar anpassningsfält i innehållet av SMS-meddelandet kan det medföra tecken som GSM-kodningen inte tar hänsyn till.  Ett exempel på innehåll finns i avsnittet [Anpassa SMS-meddelanden](../../channels/using/personalizing-sms-messages.md) .

Som standard är teckentranskribering inaktiverat.  Om du vill att samtliga tecken i SMS-meddelanden ska behållas som de är bör du inte aktivera det här alternativet.

Om dina SMS-meddelanden innehåller många tecken som genererar Unicode-meddelanden kan du välja att aktivera det här alternativet för att begränsa kostnaderna för att skicka meddelanden.

### Teckentabell - GSM-standard {#table-of-characters---gsm-standard}

I det här avsnittet beskrivs de tecken som GSM-standarden tar hänsyn till.  Alla tecken som infogats i meddelandetexten förutom de som nämns nedan konverterar hela meddelandet till binärt format (Unicode) och begränsar det därför till 70 tecken.  Mer information om detta hittar du i avsnittet [SMS-kodning, längd och transkribering](#sms-encoding--length-and-transliteration).

**Grundläggande tecken**

<table> 
 <tbody> 
  <tr> 
   <td> @<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> SP<br /> </td> 
   <td> 0<br /> </td> 
   <td> ¡<br /> </td> 
   <td> P<br /> </td> 
   <td> ¿<br /> </td> 
   <td> P<br /> </td> 
  </tr> 
  <tr> 
   <td> £<br /> </td> 
   <td> _<br /> </td> 
   <td> !<br /> </td> 
   <td> 1<br /> </td> 
   <td> A<br /> </td> 
   <td> Q<br /> </td> 
   <td> a<br /> </td> 
   <td> q<br /> </td> 
  </tr> 
  <tr> 
   <td> $<br /> </td> 
   <td> <img height="21px" src="assets/phi.png" /> <br /> </td> 
   <td> "<br /> </td> 
   <td> 2<br /> </td> 
   <td> B<br /> </td> 
   <td> R<br /> </td> 
   <td> b<br /> </td> 
   <td> r<br /> </td> 
  </tr> 
  <tr> 
   <td> ¥<br /> </td> 
   <td> <img height="21px" src="assets/gamma.png" /> <br /> </td> 
   <td> #<br /> </td> 
   <td> 3<br /> </td> 
   <td> C<br /> </td> 
   <td> S<br /> </td> 
   <td> c<br /> </td> 
   <td> s<br /> </td> 
  </tr> 
  <tr> 
   <td> è<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> ¤<br /> </td> 
   <td> 4<br /> </td> 
   <td> D<br /> </td> 
   <td> T<br /> </td> 
   <td> d<br /> </td> 
   <td> t<br /> </td> 
  </tr> 
  <tr> 
   <td> é<br /> </td> 
   <td> <img height="21px" src="assets/omega.png" /> <br /> </td> 
   <td> %<br /> </td> 
   <td> 5<br /> </td> 
   <td> E<br /> </td> 
   <td> U<br /> </td> 
   <td> e<br /> </td> 
   <td> u<br /> </td> 
  </tr> 
  <tr> 
   <td> ù<br /> </td> 
   <td> <img height="21px" src="assets/pi.png" /> <br /> </td> 
   <td> &amp;<br /> </td> 
   <td> 6<br /> </td> 
   <td> F<br /> </td> 
   <td> V<br /> </td> 
   <td> f<br /> </td> 
   <td> v<br /> </td> 
  </tr> 
  <tr> 
   <td> ì<br /> </td> 
   <td> <img height="21px" src="assets/psi.png" /> <br /> </td> 
   <td> '<br /> </td> 
   <td> 7<br /> </td> 
   <td> G<br /> </td> 
   <td> W<br /> </td> 
   <td> g<br /> </td> 
   <td> w<br /> </td> 
  </tr> 
  <tr> 
   <td> ò<br /> </td> 
   <td> <img height="21px" src="assets/sigma.png" /> <br /> </td> 
   <td> (<br /> </td> 
   <td> 8<br /> </td> 
   <td> H<br /> </td> 
   <td> X<br /> </td> 
   <td> h<br /> </td> 
   <td> x<br /> </td> 
  </tr> 
  <tr> 
   <td> Ç<br /> </td> 
   <td> <img height="21px" src="assets/theta.png" /> <br /> </td> 
   <td> )<br /> </td> 
   <td> 9 </td> 
   <td> I<br /> </td> 
   <td> Y<br /> </td> 
   <td> i<br /> </td> 
   <td> y<br /> </td> 
  </tr> 
  <tr> 
   <td> LF<br /> </td> 
   <td> <img height="21px" src="assets/xi.png" /> <br /> </td> 
   <td> *<br /> </td> 
   <td> :<br /> </td> 
   <td> J<br /> </td> 
   <td> Z<br /> </td> 
   <td> j<br /> </td> 
   <td> z<br /> </td> 
  </tr> 
  <tr> 
   <td> Ø<br /> </td> 
   <td> ESC<br /> </td> 
   <td> +<br /> </td> 
   <td> ;<br /> </td> 
   <td> K<br /> </td> 
   <td> Ä<br /> </td> 
   <td> k<br /> </td> 
   <td> ä<br /> </td> 
  </tr> 
  <tr> 
   <td> ø<br /> </td> 
   <td> Æ<br /> </td> 
   <td> ,<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> L<br /> </td> 
   <td> Ö<br /> </td> 
   <td> l<br /> </td> 
   <td> ö<br /> </td> 
  </tr> 
  <tr> 
   <td> CR<br /> </td> 
   <td> æ<br /> </td> 
   <td> -<br /> </td> 
   <td> = </td> 
   <td> M<br /> </td> 
   <td> Ñ<br /> </td> 
   <td> m<br /> </td> 
   <td> ñ<br /> </td> 
  </tr> 
  <tr> 
   <td> Å<br /> </td> 
   <td> ß<br /> </td> 
   <td> .<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> N<br /> </td> 
   <td> Ü<br /> </td> 
   <td> n<br /> </td> 
   <td> ü<br /> </td> 
  </tr> 
  <tr> 
   <td> å<br /> </td> 
   <td> É<br /> </td> 
   <td> /<br /> </td> 
   <td> ?<br /> </td> 
   <td> O<br /> </td> 
   <td> §<br /> </td> 
   <td> o<br /> </td> 
   <td> à<br /> </td> 
  </tr> 
 </tbody> 
</table>

SP: Blanksteg

ESC: Escape

LF: Radmatning

CR: Radretur

**Avancerade tecken (räknas två gånger)**

^ { } [~] | €

### SMSC-specifikationer {#smsc-specifics}

>[!NOTE]
>
>Dessa alternativ gör så att du kan anpassa anslutningen så att den fungerar med ickestandardiserad SMSC (d.v.s. som inte exakt följer SMPP 3.4-specifikationen) eller särskilda kodningskrav. Detta bör endast konfigureras av avancerade användare.

När du skickar ett SMS kan Adobe Campaign använda en eller flera textkodningar.  Varje kodning har en egen specifik teckenuppsättning och avgör antalet tecken som får plats i ett SMS.

I fältet **[!UICONTROL DATA_CODING]** kan Adobe Campaign kommunicera med den SMS-C som kodning används.

>[!NOTE]
>
>Mappningen mellan **data_coding**-värdet och den kodning som faktiskt används är standardiserad.  Vissa SMS-C har dock en egen specifik mappning: I det här fallet måste **Adobe Campaign**-administratören deklarera den här mappningen.  Kontakta din leverantör för mer information.

Med funktionen **[!UICONTROL Define a specific mapping of encodings]** kan du deklarera **data_codings** och tvinga fram kodningen om det behövs. Om du vill göra detta anger du en enda kodning i tabellen.

**Konfiguration**

* När funktionen **[!UICONTROL Define a specific mapping of encodings]** inte är markerad får kopplingen ett standardbeteende:

   * Den försöker då använda GSM-kodning som den tilldelar värdet **data_coding = 0**.
   * Om GSM-kodningen misslyckas används **UCS2**-kodning som värdet **data_coding = 8** tilldelas till.

  ![](assets/sms_data_coding.png)

* När funktionen **[!UICONTROL Define a specific mapping of encodings]** är markerad kan du definiera de kodningar som du vill använda samt de länkade **[!UICONTROL data_coding]** fältvärdena.  Adobe Campaign kommer att försöka använda den första kodningen i listan om den första kodningen visar sig vara omöjlig. Därefter kommer den försöka följande:

  Deklarationsordningen är viktig: Vi rekommenderar att du placerar listan i stigande ordning **för omkostnader** så att du kan välja kodningar som gör att du får plats med så många tecken som möjligt i varje SMS.

  Deklarera bara de kodningar som du vill använda.  Om vissa av kodningarna som tillhandahålls av SMS-C inte stämmer överens med ditt användningsändamål bör du inte deklarera dem i listan.

  ![](assets/sms_data_coding1.png)

### Automatiskt svar skickat till MO {#automatic-reply-sent-to-the-mo}

När en profil svarar på ett SMS-meddelande som skickades via Campaign kan ni konfigurera meddelanden som automatiskt skickas tillbaka till dem samt vilken åtgärd som ska utföras.

Mer information hittar du i [det här avsnittet](../../channels/using/managing-incoming-sms.md).

## Konfigurera SMS-egenskaper {#configuring-sms-properties}

I det här avsnittet finns en lista med parametrar som är unika för SMS på egenskapsskärmen för en SMS-leverans eller en SMS-mall.

De specifika parametrarna för att skicka SMS grupperas i avsnitten **[!UICONTROL Send]** och i **[!UICONTROL Advanced parameters]**.

![](assets/sms_options.png)

Från **[!UICONTROL Advanced parameters]** avsnitt:

* The **[!UICONTROL Short code]** gör att du kan lägga till en viss kort kod i leveransen. Mottagare som valde bort den här korta koden exkluderas automatiskt när meddelandet förbereddes. Mer information om hur du konfigurerar kort kod finns i [det här avsnittet](../../channels/using/managing-incoming-sms.md).

  >[!NOTE]
  >
  >Om **[!UICONTROL Short code]** fältet är tomt, värdet för **[!UICONTROL Short code]** fält som angetts i det externa kontot kommer att användas.

Från **[!UICONTROL Send]** i en SMS-mall:

* Med det här **[!UICONTROL Maximum number of SMS per message]** alternativet kan du definiera antalet SMS som ska användas för att skicka ett meddelande.  Om det här antalet överskrids skickas inte meddelandet.

  >[!IMPORTANT]
  >
  >Om du har infogat ett personaliserat fält eller villkorlig text i innehållet av SMS-meddelandet kan längden på meddelandet och därmed antalet SMS som skickas variera från en mottagare till en annan.  Mer information om detta hittar du i avsnittet [Anpassa SMS-meddelanden](../../channels/using/personalizing-sms-messages.md) .

  ![](assets/sms_smpp_3.png)

* I fältet **[!UICONTROL Transmission mode]** kan du bestämma leveransmetoden för SMS-meddelanden:

   * **[!UICONTROL Saved on SIM card]**: meddelandet lagras på mottagarens SIM-kort.
   * **[!UICONTROL Saved on mobile]**: meddelandet lagras på telefonens interna minne.
   * **[!UICONTROL Flash]**: meddelandet visas på mottagarens mobiltelefon som en notis och försvinner utan att sparas.
