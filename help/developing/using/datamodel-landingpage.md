---
title: DataModel landingPage
description: Läs mer om datamodellen
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
context-tags: delivery,smsContent,back
feature: Data Model
role: Developer
level: Experienced
exl-id: bd12a214-5998-4fb9-9f54-0c886067b58b
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1728'
ht-degree: 1%

---

# landingPage (nms:landingPage)

## Objektbeskrivning

<table>
      <tr>
         <th>Namn</th>
         <th>Etikett</th>
         <th>Typ (längd)</th>
         <th>Uppräkningsvärden</th>
      </tr>
      <tr>
         <td>PKey</td>
         <td>Huvudresurs-ID</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>additionalData</td>
         <td>Ytterligare data</td>
         <td>samling </td>
         <td> </td>
      </tr>
      <tr>
         <td>additionalLanguages</td>
         <td>Andra språk</td>
         <td>artikel </td>
         <td> </td>
      </tr>
      <tr>
         <td>allowNonIdentifiedTarget</td>
         <td>Auktorisera oidentifierade besökare</td>
         <td>boolesk </td>
         <td> </td>
      </tr>
      <tr>
         <td>branding (brandingBase)</td>
         <td>Varumärke</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>builtIn</td>
         <td>Inbyggt programobjekt</td>
         <td>boolesk </td>
         <td> </td>
      </tr>
      <tr>
         <td>cache</td>
         <td>Cache</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>kampanj (campaignBase)</td>
         <td>Campaign</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>closedLog</td>
         <td>Logg för stängd landningssida</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>contextResourceType</td>
         <td>ContextResourceType</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>skapad</td>
         <td>Skapad</td>
         <td>datum </td>
         <td> </td>
      </tr>
      <tr>
         <td>createdBy (userBase)</td>
         <td>Skapad av</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>cryptKey</td>
         <td>AES-krypteringsnyckel</td>
         <td>sträng (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>defaultLanguage</td>
         <td>Standardspråk</td>
         <td>enumeration (sträng) (255)</td>
         <td>
            <ul>
               <li>Grekiska - el - el</li>
               <li>Engelska - en - en</li>
               <li>Kinesiska - zh - zh</li>
               <li>Franska (Frankrike) - fr_FR - fr_FR</li>
               <li>Vietnamesiska - vi - vi</li>
               <li>Portugisiska (Portugal) - pt_PT - pt_PT</li>
               <li>Italienska (Italien) - it_IT - it_IT</li>
               <li>Italienska - it - it</li>
               <li>Dutch (Belgium) - nl_BE - nl_BE</li>
               <li>Norwegian (Norway) - no_NO - no_NO</li>
               <li>Nederländska (Nederländerna) - nl_NL - nl_NL</li>
               <li>Arabiska - ar - ar</li>
               <li>Engelska (USA) - en_US - en_US</li>
               <li>Iriska - ga - ga</li>
               <li>Tjeckiska - cs - cs</li>
               <li>Estniska - et - et</li>
               <li>Indonesiska - id - id</li>
               <li>Spanska - es - es</li>
               <li>Ryska - ru - ru</li>
               <li>Dutch - nl - nl</li>
               <li>Wallon - wa - wa</li>
               <li>Portugisiska - pt - pt</li>
               <li>French (Belgium) - fr_BE - fr_BE</li>
               <li>Lettiska - lv - lv</li>
               <li>Litauiska - lt - lt</li>
               <li>Thailändska - th - th</li>
               <li>Engelska (Storbritannien) - en_GB - en_GB</li>
               <li>French - fr - fr</li>
               <li>Portugisiska (Brasilien) - pt_BR - pt_BR</li>
               <li>German - de - de</li>
               <li>Danish - da - da</li>
               <li>Finska - fi - fi</li>
               <li>Ungerska - hu - hu</li>
               <li>Swedish (Finland) - sv_FI - sv_FI</li>
               <li>Japanska - ja - ja</li>
               <li>Hebreiska - han - han</li>
               <li>Koreanska - ko - ko</li>
               <li>Svenska - sv - sv</li>
               <li>Sverige (Swedish) - sv_SE - sv_SE</li>
               <li>Slovakiska - sk - sk</li>
               <li>Maltesiska - mt - mt</li>
               <li>Italian (Schweiz) - it_CH - it_CH</li>
               <li>Polish - pl - pl</li>
               <li>Slovenska - sl - sl</li>
               <li>OGILTIGT VÄRDE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>defaultOrigin (delivery)</td>
         <td>Trafikkälla</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>desc</td>
         <td>Beskrivning</td>
         <td>sträng (512)</td>
         <td> </td>
      </tr>
      <tr>
         <td>designLanguage</td>
         <td>Designspråk</td>
         <td>enumeration (sträng) (255)</td>
         <td>
            <ul>
               <li>Grekiska - el - el</li>
               <li>Engelska - en - en</li>
               <li>Kinesiska - zh - zh</li>
               <li>Franska (Frankrike) - fr_FR - fr_FR</li>
               <li>Vietnamesiska - vi - vi</li>
               <li>Portugisiska (Portugal) - pt_PT - pt_PT</li>
               <li>Italienska (Italien) - it_IT - it_IT</li>
               <li>Italienska - it - it</li>
               <li>Dutch (Belgium) - nl_BE - nl_BE</li>
               <li>Norwegian (Norway) - no_NO - no_NO</li>
               <li>Nederländska (Nederländerna) - nl_NL - nl_NL</li>
               <li>Arabiska - ar - ar</li>
               <li>Engelska (USA) - en_US - en_US</li>
               <li>Iriska - ga - ga</li>
               <li>Tjeckiska - cs - cs</li>
               <li>Estniska - et - et</li>
               <li>Indonesiska - id - id</li>
               <li>Spanska - es - es</li>
               <li>Ryska - ru - ru</li>
               <li>Dutch - nl - nl</li>
               <li>Wallon - wa - wa</li>
               <li>Portugisiska - pt - pt</li>
               <li>French (Belgium) - fr_BE - fr_BE</li>
               <li>Lettiska - lv - lv</li>
               <li>Litauiska - lt - lt</li>
               <li>Thailändska - th - th</li>
               <li>Engelska (Storbritannien) - en_GB - en_GB</li>
               <li>French - fr - fr</li>
               <li>Portugisiska (Brasilien) - pt_BR - pt_BR</li>
               <li>German - de - de</li>
               <li>Danish - da - da</li>
               <li>Finska - fi - fi</li>
               <li>Ungerska - hu - hu</li>
               <li>Swedish (Finland) - sv_FI - sv_FI</li>
               <li>Japanska - ja - ja</li>
               <li>Hebreiska - han - han</li>
               <li>Koreanska - ko - ko</li>
               <li>Svenska - sv - sv</li>
               <li>Sverige (Swedish) - sv_SE - sv_SE</li>
               <li>Slovakiska - sk - sk</li>
               <li>Maltesiska - mt - mt</li>
               <li>Italian (Schweiz) - it_CH - it_CH</li>
               <li>Polish - pl - pl</li>
               <li>Slovenska - sl - sl</li>
               <li>OGILTIGT VÄRDE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>dynamicService</td>
         <td>Dynamisk tjänst</td>
         <td>boolesk </td>
         <td> </td>
      </tr>
      <tr>
         <td>end</td>
         <td>Utgångsdatum</td>
         <td>datum </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorContextResourceType</td>
         <td>ErrorContextResourceType</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorPage</td>
         <td>Felsida</td>
         <td>artikel </td>
         <td> </td>
      </tr>
      <tr>
         <td>geoUnit (geoUnitBase)</td>
         <td>Geografisk enhet</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>htmlPage</td>
         <td>Sidor</td>
         <td>samling </td>
         <td> </td>
      </tr>
      <tr>
         <td>identityByUrlParam</td>
         <td>Identifiering med URL-parametrar</td>
         <td>boolesk </td>
         <td> </td>
      </tr>
      <tr>
         <td>inactiveUrlRedirection</td>
         <td>URL för omdirigering</td>
         <td>sträng (4096)</td>
         <td> </td>
      </tr>
      <tr>
         <td>isExternal</td>
         <td>Är extern resurs</td>
         <td>boolesk </td>
         <td> </td>
      </tr>
      <tr>
         <td>isTemplate</td>
         <td>Mall</td>
         <td>boolesk </td>
         <td> </td>
      </tr>
      <tr>
         <td>jobb</td>
         <td>Jobb</td>
         <td>samling </td>
         <td> </td>
      </tr>
      <tr>
         <td>jobLogs</td>
         <td>Loggar</td>
         <td>samling </td>
         <td> </td>
      </tr>
      <tr>
         <td>label</td>
         <td>Etikett</td>
         <td>sträng (128)</td>
         <td> </td>
      </tr>
      <tr>
         <td>lastModified</td>
         <td>Senast ändrad</td>
         <td>datum </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilter (queryFilterBase)</td>
         <td>Inläsningsnyckel</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilterMapping</td>
         <td>Parametrar för inläsningsnyckeln</td>
         <td>samling </td>
         <td> </td>
      </tr>
      <tr>
         <td>logicalStatus</td>
         <td>Körningsstatus</td>
         <td>enumeration (sträng) (255)</td>
         <td>
            <ul>
               <li>Pågår - igång</li>
               <li>Redigering - utgåva - utgåva</li>
               <li>Slutförd - avslutad - avslutad</li>
               <li>Varning - varning - varning</li>
               <li>Fel - fel - fel</li>
               <li>OGILTIGT VÄRDE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>messageAction</td>
         <td>Börja skicka meddelande</td>
         <td>boolesk </td>
         <td> </td>
      </tr>
      <tr>
         <td>messageActionDelivery (deliveryMCTemplateBase)</td>
         <td>Transaktionsmeddelande</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>modifiedBy (userBase)</td>
         <td>Ändrad av</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>name</td>
         <td>ID</td>
         <td>sträng (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>orgUnit (orgUnitBase)</td>
         <td>Organisationsenhet</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>prefill</td>
         <td>Förhandsladda besöksdata</td>
         <td>boolesk </td>
         <td> </td>
      </tr>
      <tr>
         <td>program (programBase)</td>
         <td>Program</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicUrl</td>
         <td>Offentlig URL</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicationDate</td>
         <td>Publiceringsdatum</td>
         <td>datum </td>
         <td> </td>
      </tr>
      <tr>
         <td>Avstämningsfilter (queryFilterBase)</td>
         <td>Avstämningsnyckel</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>justificationFilterMapping</td>
         <td>Parametrar för avstämningsnyckel</td>
         <td>samling </td>
         <td> </td>
      </tr>
      <tr>
         <td>comparisonUpdateStrategy</td>
         <td>Uppdateringsstrategi</td>
         <td>uppräkning (byte) </td>
         <td>
            <ul>
               <li>Uppdatering - updateTarget - 1</li>
               <li>Obehörig - obehörig - 0</li>
               <li>OGILTIGT VÄRDE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>service (serviceBase)</td>
         <td>Prenumerationstjänst</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>specificAction</td>
         <td>Särskild åtgärd</td>
         <td>uppräkning (byte) </td>
         <td>
            <ul>
               <li>Blacklist - blackList - 3</li>
               <li>Ingen specifik åtgärd - ingen - 0</li>
               <li>Unsubscription - unsubscription - 2</li>
               <li>OGILTIGT VÄRDE - __Invalid_value__ - __Invalid_value__</li>
               <li>Prenumeration - prenumeration - 1</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>start</td>
         <td>Distributionsdatum</td>
         <td>datum </td>
         <td> </td>
      </tr>
      <tr>
         <td>läge</td>
         <td>Status</td>
         <td>uppräkning (byte) </td>
         <td>
            <ul>
               <li>Redigering - redigera - 0</li>
               <li>Publiceringen misslyckades - misslyckades - 99</li>
               <li>Stängd - stängd - 20</li>
               <li>OGILTIGT VÄRDE - __Invalid_value__ - __Invalid_value__</li>
               <li>Online - öppnad - 10</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>targetResource</td>
         <td>Måldimension</td>
         <td>sträng (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>template (landingPage)</td>
         <td>Landningssidmall</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>testUrl</td>
         <td>Test URL</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>miniatyrbild</td>
         <td>Miniatyrbild</td>
         <td>sträng (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>tidszon</td>
         <td>Tidszon</td>
         <td>uppräkning (sträng) (64)</td>
         <td>
            <ul>
               <li>(GMT-02:00) Centralatlanten - Atlantic_South_Georgia - Atlantic/South_Georgia</li>
               <li>(GMT+02.00) Amman - Asien_Amman - Asien/Amman</li>
               <li>(GMT-03.00) Brasi - America_Sao_Paulo - America/Sao_Paulo</li>
               <li>(GMT+06.00) Astana, Dhaka - Asien_Dhaka - Asien/Dhaka</li>
               <li>(GMT+06.00) Novossibirsk - Asien_Novosibirsk - Asien/Novosibirsk</li>
               <li>(GMT+02.00) Windhoek - Africa_Windhoek - Africa/Windhoek</li>
               <li>(GMT+04.00) Kaukasus, Erevan - Asien_Jerevan - Asien/Jerevan</li>
               <li>(GMT-04.00) Manaus - America_Manaus - America/Manaus</li>
               <li>(GMT+03.30) Teheran - Asien_Teheran - Asien/Teheran</li>
               <li>(GMT+12.00) Auckland, Wellington - Pacific_Auckland - Pacific/Auckland</li>
               <li>(GMT+02.00) Jerusalem - Asien_Jerusalem - Asien/Jerusalem</li>
               <li>(GMT+03.00) Moskva, St. Petersburg, Volgograd - Europe_Moskva - Europa/Moskva</li>
               <li>(GMT+09.30) Adelaïde - Australia_Adelaide - Australien/Adelaide</li>
               <li>(GMT+10.00) Canberra, Melbourne, Sydney - Australia_Canberra - Australien/Canberra</li>
               <li>(GMT+08.00) Perth - Australia_Perth - Australia/Perth</li>
               <li>(GMT+09.00) Jakutsk - Asien_Jakutsk - Asien/Yakutsk</li>
               <li>(GMT-10.00) Hawai - Pacific_Honolulu - Pacific/Honolulu</li>
               <li>(GMT+04.00) Baku - Asien_Baku - Asien/Baku</li>
               <li>(GMT+10.00) Vladivostok - Asien_Vladivostok - Asien/Vladivostok</li>
               <li>(GMT+09.00) Söul - Asien_Söul - Asien/Söul</li>
               <li>(GMT+01.00) Sarajevo, Skoplje, Sofia, Warszawa, Zagreb - Europe_Sarajevo - Europa/Sarajevo</li>
               <li>Servertidszon - _server_ - _server_</li>
               <li>(GMT+04.00) Abu Dhabi, Muscat - Asia_Muscat - Asien/Muscat</li>
               <li>(GMT+08.00) Kuala Lumpur, Singapore - Asien_Kuala_Lumpur - Asien/Kuala_Lumpur</li>
               <li>(GMT+09.00) Osaka, Sapporo, Tokyo - Asien_Tokyo - Asien/Tokyo</li>
               <li>(GMT+10.00) Brisbane - Australia_Brisbane - Australien/Brisbane</li>
               <li>(GMT+05.30) Sri Jayawardenepura - Asien_Colombia - Asien/Colombia</li>
               <li>(GMT+02.00) Harare, Pretoria - Africa_Harare - Africa/Harare</li>
               <li>(GMT+08.00) Ulan-Bator - Asien_Ulan_Bator - Asien/Ulan_Bator</li>
               <li>(GMT-02:00) Greenwich Mean Time minus 2 timmar - Gmt_m2 - ETC/GMT+2</li>
               <li>(GMT-03.00) Greenwich Mean Time minus 3 timmar - Gmt_m3 - ETC/GMT+3</li>
               <li>(GMT-01:00) Greenwich Mean Time minus 1 timme - Gmt_m1 - ETC/GMT+1</li>
               <li>(GMT-06.00) Greenwich Mean Time minus 6 timmar - Gmt_m6 - ETC/GMT+6</li>
               <li>(GMT-07.00) Greenwich Mean Time minus 7 timmar - Gmt_m7 - ETC/GMT+7</li>
               <li>(GMT-04.00) Greenwich Mean Time minus 4 timmar - Gmt_m4 - ETC/GMT+4</li>
               <li>(GMT) Casablanca - Africa_Casablanca - Africa/Casablanca</li>
               <li>(GMT+05.30) Kolkata, Chennai, Mumbai, New Delhi - Asien_Kolkata - Asien/Kolkata</li>
               <li>(GMT-11:00) Greenwich Mean Time minus 11 timmar - Gmt_m11 - ETC/GMT+11</li>
               <li>(GMT-09.00) Greenwich Mean Time minus 9 timmar - Gmt_m9 - ETC/GMT+9</li>
               <li>(GMT-03:30) Newfoundland - America_St_Johns - America/St_Johns</li>
               <li>Standard - _inherit_ - _inherit_</li>
               <li>(GMT+03.00) Greenwich Mean Time plus 3 timmar - Gmt_p3 - ETC/GMT-3</li>
               <li>(GMT-04.30) Caracas - America_Caracas - America/Caracas</li>
               <li>(GMT+01.00) Amsterdam, Berlin, Berne, Rom, Stockholm, Wien - Europa_Berlin - Europa/Berlin</li>
               <li>(GMT-07.00) Chihuahua, La Paz, Mazatlan - America_Chihuahua - Amerika/Chihuahua</li>
               <li>(GMT+03.00) Nairobi - Africa_Nairobi - Africa/Nairobi</li>
               <li>(GMT-04.00) Asunción - America_Asuncion - America/Asuncion</li>
               <li>(GMT+03.00) Bagdad - Asien_Bagdad - Asien/Bagdad</li>
               <li>(GMT-10.00) Greenwich Mean Time minus 10 timmar - Gmt_m10 - ETC/GMT+10</li>
               <li>(GMT-03.00) Grönland - Amerika_Godthab - Amerika/Godthab</li>
               <li>(GMT+02.00) Damas - Asien_Damaskus - Asien/Damaskus</li>
               <li>(GMT-11.00) Samoa - Stilla havet_Samoa - Stilla havet/Samoa</li>
               <li>(GMT-05.00) Bogota, Lima, Quito - America_Bogota - Amerika/Bogota</li>
               <li>(GMT+01.00) Bryssel, Köpenhamn, Madrid, Paris - Europa_Paris - Europa/Paris</li>
               <li>(GMT+08.00) Beijing, Chongqing, Hongkong, Urumqi - Asien_Shanghai - Asien/Shanghai</li>
               <li>(GMT+12.00) Fidji - Pacific_Fiji - Stilla havet/Fiji</li>
               <li>(GMT+02.00) Aten, Istanbul, Minsk - Europa_Aten - Europa/Aten</li>
               <li>(GMT+04.00) Tbilissi - Asien_Tbilisi - Asien/Tbilisi</li>
               <li>OGILTIGT VÄRDE - __Invalid_value__ - __Invalid_value__</li>
               <li>(GMT+05:45) Katmandu - Asien_Katmandu - Asien/Katmandu</li>
               <li>(GMT-05:00) Indiana (östra) - America_Indianapolis - Amerika/Indianapolis</li>
               <li>(GMT-01:00) Kap Verde-öarna - Atlanten_Kap Verde - Atlanten/Kap Verde</li>
               <li>(GMT+04.00) Port Louis - Indian_Mauritius - Indien/Mauritius</li>
               <li>(GMT+08.00) Taipei - Asien_Taipei - Asien/Taipei</li>
               <li>Tidszon för databasen - _wdbc_ - _wdbc_</li>
               <li>(GMT+06.30) Rangoon - Asien_Rangoon - Asien/Rangoon</li>
               <li>(GMT+11.00) Magadan, Salomonöarna, Nya Kaledonien - Stilla havet_Guadalkanalen - Stilla havet/Guadalkanalen</li>
               <li>(GMT+02.00) Kairo - Afrika_Kairo - Afrika/Kairo</li>
               <li>(GMT+05.00) Iekaterinburg - Asien_Jekaterinburg - Asien/Jekaterinburg</li>
               <li>(GMT+08.00) Irkoutsk - Asien_Irkutsk - Asien/Irkutsk</li>
               <li>(GMT+10.00) Guam, Port Moresby - Pacific_Guam - Pacific/Guam</li>
               <li>(GMT-04.00) Atlantic, normaltid (Kanada) - America_Halifax - America/Halifax</li>
               <li>(GMT) Greenwich, medeltid - GMT - GMT</li>
               <li>(GMT-04.00) La Paz - America_La_Paz - America/La_Paz</li>
               <li>Operatörens tidszon - _login_ - _login_</li>
               <li>(GMT-06:00) Guadalajara, Mexico, Monterrey - America_Mexico_City - Amerika/Mexico_City</li>
               <li>(GMT+09.30) Darwin - Australia_Darwin - Australien/Darwin</li>
               <li>(GMT-05:00) Est (USA och Kanada) - America_New_York - America/New_York</li>
               <li>(GMT-05:00) Greenwich Mean Time minus 5 timmar - Gmt_m5 - ETC/GMT+5</li>
               <li>(GMT+05.00) Islamabad, Karachi, Tachkent - Asien_Karachi - Asien/Karachi</li>
               <li>(GMT+03.00) Koweït, Riyad - Asien_Riyadh - Asien/Riyadh</li>
               <li>(GMT-08.00) Greenwich Mean Time minus 8 timmar - Gmt_m8 - ETC/GMT+8</li>
               <li>(GMT-01.00) Azorerna - Atlanten/Azorerna - Atlanten/Azorerna</li>
               <li>(GMT+07.00) Bangkok, Hanoi, Djakarta - Asien_Bangkok - Asien/Bangkok</li>
               <li>(GMT) Monrovia - Afrika_Monrovia - Afrika/Monrovia</li>
               <li>(GMT-09.00) Alaska - America_Anchorage - America/Anchorage</li>
               <li>(GMT+01:00) Belgrad, Bratislava, Budapest, Ljubljana, Prag - Europa_Belgrad - Europa/Belgrad</li>
               <li>(GMT) Reykjavik - Atlantic_Reykjavik - Atlantic/Reykjavik</li>
               <li>(GMT+02.00) Bukarest - Europe_Bukarest - Europe/Bukarest</li>
               <li>(GMT+05.00) Greenwich Mean Time plus 5 timmar - Gmt_p5 - ETC/GMT-5</li>
               <li>(GMT+04.00) Greenwich Mean Time plus 4 timmar - Gmt_p4 - ETC/GMT-4</li>
               <li>(GMT+07.00) Greenwich Mean Time plus 7 timmar - Gmt_p7 - ETC/GMT-7</li>
               <li>(GMT+06.00) Greenwich Mean Time plus 6 timmar - Gmt_p6 - ETC/GMT-6</li>
               <li>(GMT+01:00) Greenwich Mean Time plus 1 timme - Gmt_p1 - ETC/GMT-1</li>
               <li>(GMT-08.00) Stilla havet (USA och Kanada) - America_Los Angeles - America/Los Angeles</li>
               <li>(GMT+02.00) Greenwich Mean Time plus 2 timmar - Gmt_p2 - ETC/GMT-2</li>
               <li>(GMT+07.00) Krasnoïarsk - Asien_Krasnojarsk - Asien/Krasnojarsk</li>
               <li>(GMT+09.00) Greenwich Mean Time plus 9 timmar - Gmt_p9 - ETC/GMT-9</li>
               <li>(GMT+08.00) Greenwich Mean Time plus 8 timmar - Gmt_p8 - ETC/GMT-8</li>
               <li>(GMT+10.00) Hobart - Australien_Hobart - Australien/Hobart</li>
               <li>(GMT+13.00) Nuku'alofa - Pacific_Tongatapu - Stilla havet/Tongatapu</li>
               <li>(GMT-06.00) Centralamerika - Amerika_Regina - Amerika/Regina</li>
               <li>(GMT-03:00) Buenos Aires, Cayenne, Fortaleza - America_Buenos_Aires - America/Buenos_Aires</li>
               <li>(GMT-07:00) Rocky Mountains (USA och Kanada) - America_Denver - Amerika/Denver</li>
               <li>(GMT+01.00) Centralafrika - Väst - Afrika_Luanda - Afrika/Luanda</li>
               <li>(GMT+02.00) Helsingfors, Kiev, Riga, Sofia, Tallinn, Vilnius - Europe_Helsingfors - Europa/Helsingfors</li>
               <li>(GMT) Greenwich Mean Time: Dublin, Edinburgh, Lissabon - London - Europa_London - Europa/London</li>
               <li>(GMT-07.00) Arizona - America_Phoenix - America/Phoenix</li>
               <li>(GMT+02.00) Beirut - Asien_Beirut - Asien/Beirut</li>
               <li>(GMT+04.30) Kabul - Asien_Kabul - Asien/Kabul</li>
               <li>(GMT-06.00) Center (USA och Kanada) - America_Chicago - America/Chicago</li>
               <li>(GMT+11.00) Greenwich Mean Time plus 11 timmar - Gmt_p11 - ETC/GMT-11</li>
               <li>(GMT+10.00) Greenwich Mean Time plus 10 timmar - Gmt_p10 - ETC/GMT-10</li>
               <li>(GMT+13.00) Greenwich Mean Time plus 13 timmar - Gmt_p13 - ETC/GMT-13</li>
               <li>(GMT+12.00) Greenwich Mean Time plus 12 timmar - Gmt_p12 - ETC/GMT-12</li>
               <li>(GMT-04.00) Santiago - America_Santiago - Amerika/Santiago</li>
               <li>(GMT-03.00) Montevideo - America_Montevideo - America/Montevideo</li>
               <li>(GMT-04:00) Cuiaba - America_Cuiaba - America/Cuiaba</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>title</td>
         <td>Landningssida</td>
         <td>sträng (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingEnabled</td>
         <td>Loggsvar</td>
         <td>boolesk </td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingUrlName</td>
         <td>URL-namn för spårning</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>type</td>
         <td>Typ</td>
         <td>uppräkning (byte) </td>
         <td>
            <ul>
               <li>Allmän - allmän - 0</li>
               <li>Avbeställ en tjänst - avbeprenumeration - 3</li>
               <li>Blacklist - blackList - 4</li>
               <li>OGILTIGT VÄRDE - __Invalid_value__ - __Invalid_value__</li>
               <li>Anskaffning - förvärv - 1</li>
               <li>Prenumeration på en tjänst - prenumeration - 2</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>uuid</td>
         <td>Säkerhets-ID</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>webTrackingEnabled</td>
         <td>Aktivera webbspårning</td>
         <td>boolesk </td>
         <td> </td>
      </tr>
   </table>

## Filter

Efter logisk status (byLogicalStatus)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>läge</td>
    <td>uppräkning</td>
    </tr>
</table>

Efter namn eller etikett (byText)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>text</td>
    <td>string</td>
    </tr>
</table>

Efter status (efter stat)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>läge</td>
    <td>uppräkning</td>
    </tr>
</table>

Efter målresurs (byTargetResource)

<table>
<tr>
<th>Namn</th>
<th>Typ</th>
</tr>
<tr>
<td>targetResource</td>
<td>string</td>
</tr>
</table>

Inkludera avancerade landningssidor (med avancerad)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>avancerat</td>
    <td>boolesk</td>
    </tr>
</table>

Inkludera kontinuerliga leveranser från en heterogen lista (withContinuous)

<table>
        <tr>
        <th>Namn</th>
        <th>Typ</th>
        </tr>
        <tr>
        <td>withContinuous</td>
        <td>boolesk</td>
        </tr>
    </table>

Finns under angiven period (efter kalender)

<table>
        <tr>
        <th>Namn</th>
        <th>Typ</th>
        </tr>
        <tr>
        <td>startDate</td>
        <td>datum</td>
        </tr>
        <tr>
        <td>endDate</td>
        <td>datum</td>
        </tr>
    </table>

Publicerat under angiven period (av Planning)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>datum</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>datum</td>
    </tr>
</table>
