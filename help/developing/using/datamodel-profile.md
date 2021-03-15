---
solution: Campaign Standard
product: campaign
title: DataModel
description: Läs mer om datamodellen
audience: developing
content-type: reference
feature: Datamodell
role: Utvecklare
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 1%

---


# Profil (nms:mottagare)

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
                  <td>age</td>
                  <td>Ålder</td>
                  <td>heltal </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>appSubscription</td>
                  <td>Prenumerationer på program</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>födelsedatum</td>
                  <td>Födelsedatum</td>
                  <td>datum </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackList</td>
                  <td>Inte längre kontakt (via någon kanal)</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListEmail</td>
                  <td>Kontakta inte längre via e-post</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListFax</td>
                  <td>Inte längre kontakt via fax</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListMobile</td>
                  <td>Kontakta inte längre SMS</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPhone</td>
                  <td>Kontakten tas inte längre via telefon</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPostalMail</td>
                  <td>Inte längre kontakt via direktreklam</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPushnotification</td>
                  <td>Kontakta inte längre via push-meddelanden</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>land (länder)</td>
                  <td>Land</td>
                  <td>link </td>
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
                  <td>cryptedId</td>
                  <td>Krypterat ID</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusHobbieslink (cusHobbies)</td>
                  <td>CusHobbieslink</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusLastTransactionDate</td>
                  <td>Senaste transaktionsdatum</td>
                  <td>datum </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusTransactionslink</td>
                  <td>Transaktioner</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>domän</td>
                  <td>E-postdomän</td>
                  <td>sträng (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>e-post</td>
                  <td>E-post</td>
                  <td>sträng (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>E-postformat</td>
                  <td>uppräkning (byte) </td>
                  <td>
                     <ul>
                        <li>Text - text - 1</li>
                        <li>HTML - html - 2</li>
                        <li>OGILTIGT VÄRDE - __Invalid_value__ - __Invalid_value__</li>
                        <li>Okänd - okänd - 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>emailStatus (addressStatus)</td>
                  <td>Information om e-postmeddelandet</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>Uteslutningsloggar</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>externalId</td>
                  <td>Externt resurs-ID</td>
                  <td>string(100) </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fax</td>
                  <td>Fax</td>
                  <td>sträng (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>firstName</td>
                  <td>Förnamn</td>
                  <td>sträng (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kön</td>
                  <td>Kön</td>
                  <td>uppräkning (byte) </td>
                  <td>
                     <ul>
                        <li>Ospecificerad - okänd - 0</li>
                        <li>Man - man - man - 1</li>
                        <li>Kvinna - kvinna - 2</li>
                        <li>OGILTIGT VÄRDE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>Är extern resurs</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>Senast ändrad</td>
                  <td>datum </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastName</td>
                  <td>Efternamn</td>
                  <td>sträng (50)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>plats</td>
                  <td>Plats</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>loggar</td>
                  <td>Leveransloggar</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>middleName</td>
                  <td>Mellannamn</td>
                  <td>sträng (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Mobil</td>
                  <td>sträng (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>Ändrad av</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>telefon</td>
                  <td>Telefon</td>
                  <td>sträng (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>platser</td>
                  <td>Platser</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mailAddress</td>
                  <td>Postadress</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hälsning</td>
                  <td>Titel</td>
                  <td>sträng (20)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (tillstånd)</td>
                  <td>Läge</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subHistory</td>
                  <td>Prenumerationshistorik</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>prenumerationer</td>
                  <td>Prenumerationer</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatyrbild</td>
                  <td>Miniatyrbild</td>
                  <td>sträng (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>timeZone</td>
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
                        <li>(GMT+09.00) Söul - Asien_Seoul - Asien/Söul</li>
                        <li>(GMT+01.00) Sarajevo, Skoplje, Sofia, Warszawa, Zagreb - Europe_Sarajevo - Europa/Sarajevo</li>
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
                        <li>(GMT+06.30) Rangoon - Asien_Rangoon - Asien/Rangoon</li>
                        <li>(GMT+11.00) Magadan, Salomonöarna, Nya Kaledonien - Stilla havet_Guadalkanalen - Stilla havet/Guadalkanalen</li>
                        <li>(GMT+02.00) Kairo - Afrika_Kairo - Afrika/Kairo</li>
                        <li>(GMT+05.00) Iekaterinburg - Asien_Jekaterinburg - Asien/Jekaterinburg</li>
                        <li>(GMT+08.00) Irkoutsk - Asien_Irkutsk - Asien/Irkutsk</li>
                        <li>(GMT+10.00) Guam, Port Moresby - Pacific_Guam - Pacific/Guam</li>
                        <li>(GMT-04.00) Atlantic, normaltid (Kanada) - America_Halifax - America/Halifax</li>
                        <li>(GMT) Greenwich, medeltid - GMT - GMT</li>
                        <li>Standard - ingen - ingen</li>
                        <li>(GMT-04.00) La Paz - America_La_Paz - America/La_Paz</li>
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
                        <li>(GMT-08:00) Stilla havet (USA och Kanada) - America_Los Angeles - America/Los Angeles</li>
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
                  <td>Profil</td>
                  <td>sträng (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>spårning</td>
                  <td>Spårningsloggar</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
            </table>


## Filter


Födelsedag (födelsedag)

<table>
<tr>
<th>Namn</th>
<th>Typ</th>
</tr>
<tr>
<td>includeStart</td>
<td>boolesk</td>
</tr>
<tr>
<td>previousUnitsValue</td>
<td>heltal</td>
</tr>
<tr>
<td>nextUnitsValue</td>
<td>heltal</td>
</tr>
<tr>
<td>endDay</td>
<td>datum</td>
</tr>
<tr>
<td>precision</td>
<td>uppräkning</td>
</tr>
<tr>
<td>relativeValue</td>
<td>string</td>
</tr>
<tr>
<td>månad</td>
<td>datum</td>
</tr>
<tr>
<td>operator</td>
<td>uppräkning</td>
</tr>
<tr>
<td>includeEnd</td>
<td>boolesk</td>
</tr>
<tr>
<td>endMonth</td>
<td>datum</td>
</tr>
<tr>
<td>type</td>
<td>uppräkning</td>
</tr>
<tr>
<td>dag</td>
<td>datum</td>
</tr>
</table>

Per e-post (via e-post)

<table>
<tr>
<th>Namn</th>
<th>Typ</th>
</tr>
<tr>
<td>e-post</td>
<td>string</td>
</tr>
</table>

Efter tangenter (byKeysProfile)

<table>
<tr>
<th>Namn</th>
<th>Typ</th>
</tr>
<tr>
<td>e-post</td>
<td>string</td>
</tr>
</table>

Efter namn eller e-postadress (efterText)

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

Efter statisk målgrupp (byStaticAudience)

<table>
<tr>
<th>Namn</th>
<th>Typ</th>
</tr>
<tr>
<td>publik</td>
<td>link</td>
</tr>
</table>

Klickad (hasClickDelivery)

<table>
<tr>
<th>Namn</th>
<th>Typ</th>
</tr>
<tr>
<td>leverans</td>
<td>link</td>
</tr>
</table>

Öppnad (hasOpenedDelivery)

<table>
<tr>
<th>Namn</th>
<th>Typ</th>
</tr>
<tr>
<td>leverans</td>
<td>link</td>
</tr>
</table>

Profil (profil)

<table>
<tr>
<th>Namn</th>
<th>Typ</th>
</tr>
<tr>
<td>profil</td>
<td>link</td>
</tr>
</table>

Mottaget (hasReceivedDelivery)

<table>
<tr>
<th>Namn</th>
<th>Typ</th>
</tr>
<tr>
<td>leverans</td>
<td>link</td>
</tr>
</table>

Prenumeranter (prenumeranter)

<table>
<tr>
<th>Namn</th>
<th>Typ</th>
</tr>
<tr>
<td>service</td>
<td>link</td>
</tr>
</table>