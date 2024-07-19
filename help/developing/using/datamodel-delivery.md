---
title: DataModel-leverans
description: Läs mer om datamodellen
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: aea3e72d-8e89-46c7-a796-bf856414c654
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 1%

---

# Leverans (nms:delivery)

## Objektbeskrivning

<table>
               <tr>
                  <th>Namn</th>
                  <th>Etikett</th>
                  <th>Typ (längd)</th>
                  <th>Uppräkningsvärden</th>
               </tr>
               <tr>
                  <td>FCP</td>
                  <td>Korrektur</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>Huvudresurs-ID</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abTesting</td>
                  <td>A/B-tester</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>avancerat</td>
                  <td>Avancerad leverans</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>advancedParameters</td>
                  <td>Avancerade parametrar</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aemContents</td>
                  <td>Innehåll i Adobe Experience Manager</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMessage</td>
                  <td>Varningsmeddelande</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMode</td>
                  <td>Varningstyp</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>bifogad</td>
                  <td>Bifogade filer</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>branding (brandingBase)</td>
                  <td>Varumärke</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>broadLogs</td>
                  <td>Leveransloggar</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>builtIn</td>
                  <td>Inbyggt programobjekt</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kampanj (campaignBase)</td>
                  <td>Campaign</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount (extAccountAEMBase)</td>
                  <td>Adobe Experience Manager</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kommandon</td>
                  <td>Kommandon</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>innehåll</td>
                  <td>Innehåll</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>contentSource</td>
                  <td>Innehållskälla</td>
                  <td>uppräkning (byte) </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager - aem - 1</li>
                        <li>Adobe Campaign - kampanj - 0</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>contextResourceType</td>
                  <td>Resurstyp</td>
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
                  <td>deliveryMode</td>
                  <td>Leveransläge</td>
                  <td>uppräkning (byte) </td>
                  <td>
                     <ul>
                        <li>Massleverans - bulk - 1</li>
                        <li>Mid-sourcing - middagsförsäljning - 4</li>
                        <li>Beskrivning - beskrivande - 2</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                        <li>Extern - extern - 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider (extAccountBase)</td>
                  <td>Routning</td>
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
                  <td>emailPreview</td>
                  <td>Förhandsgranska e-post</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>Uteslutningsloggar</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>undantag</td>
                  <td>Uteslutningsorsaker</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>körning</td>
                  <td>Parametrar för leveranskörning</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executionType</td>
                  <td>Körningstyp</td>
                  <td>uppräkning (byte) </td>
                  <td>
                     <ul>
                        <li>Unik - en gång - 0</li>
                        <li>Kontinuerlig - kontinuerlig - 1</li>
                        <li>Message Center - messageCenter - 2</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>prognosLogs</td>
                  <td>Prognoslogg</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Geografisk enhet</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasAttachments</td>
                  <td>Lägg till bifogade filer</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>icon</td>
                  <td>Ikon</td>
                  <td>uppräkning (byte) </td>
                  <td>
                     <ul>
                        <li>Transaktionell e-post - e-postLightning - 60</li>
                        <li>Fax - fax - 4</li>
                        <li>Mobil (SMS) - sms - 1</li>
                        <li>Återkommande e-post - e-postUppdatera - 30</li>
                        <li>Direktreklam - papper - 3</li>
                        <li>Telefon - telefon - 2</li>
                        <li>Övrigt - annat - 120</li>
                        <li>Återkommande SMS - smsRefresh - 31</li>
                        <li>Mobilprogram - pushNotification - 40</li>
                        <li>Transactional SMS - smsLightning - 61</li>
                        <li>E-post - e-post - 0</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
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
                  <td>isMaster</td>
                  <td>Master</td>
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
                  <td>iterationer</td>
                  <td>Leveranser</td>
                  <td>samling </td>
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
                  <td>kpis</td>
                  <td>Indikatorer</td>
                  <td>artikel </td>
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
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mailParameters</td>
                  <td>Parametrar för e-posthuvud</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>Datum</td>
                  <td>datum </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mappning (deliveryMapping)</td>
                  <td>Målmappning</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>master (deliveryBase)</td>
                  <td>Huvudinstans</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpis</td>
                  <td>Huvudindikatorer</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>Kanal</td>
                  <td>uppräkning (byte) </td>
                  <td>
                     <ul>
                        <li>Fax - fax - 4</li>
                        <li>Mobil (SMS) - sms - 1</li>
                        <li>E-post - e-post - 0</li>
                        <li>Telefon - telefon - 2</li>
                        <li>Direktreklam - papper - 3</li>
                        <li>Mobilprogram - pushNotification - 40</li>
                        <li>Övrigt - annat - 120</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
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
                  <td>offerManagement</td>
                  <td>Erbjudandehantering</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Organisationsenhet</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>parent (deliveryBase)</td>
                  <td>Överordnad leverans</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>prioritet</td>
                  <td>Leveransprioritet</td>
                  <td>uppräkning (byte) </td>
                  <td>
                     <ul>
                        <li>Hög - hög - 20</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                        <li>Normal - normal - 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>program (programBase)</td>
                  <td>Program</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>korrektur</td>
                  <td>Korrektur</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotificationPreview</td>
                  <td>Förhandsgranska push-meddelanden</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotificationParameters</td>
                  <td>PushNotification-parametrar</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Realtime-rapporter</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>Resursversion</td>
                  <td>sträng (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ribbonMessage</td>
                  <td>Ribbon message</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>scenario</td>
                  <td>Parametrar för leveransmall</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>schemaläggning</td>
                  <td>Leveransplanering</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsParameters</td>
                  <td>SMS-parametrar</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>SMS-förhandsgranskning</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>läge</td>
                  <td>Status</td>
                  <td>uppräkning (byte) </td>
                  <td>
                     <ul>
                        <li>Väntande start - startPending - 51</li>
                        <li>Klar att levereras - klar - 45</li>
                        <li>Väntande nytt försök - Väntande nytt försök - 61</li>
                        <li>Pågående nytt försök - nytt pågående försök - 62</li>
                        <li>Misslyckades - misslyckades - 87</li>
                        <li>Pågår - startat - 55</li>
                        <li>Väntande mål - targetPrepPending - 11</li>
                        <li>Väntande Personalization - messagePrepPending - 21</li>
                        <li>Pausad - pausad - 75</li>
                        <li>Redigering - utgåva - 0</li>
                        <li>Slutförd - färdig - 95</li>
                        <li>Antal pågående - targetSelection - 12</li>
                        <li>Meddelandet har slutförts - messageReady - 25</li>
                        <li>Personalization eller antal misslyckades - PreparationError - 37</li>
                        <li>Stoppad - annullerad - 85</li>
                        <li>Personalization in progress - messagePreparation - 22</li>
                        <li>Klart som mål - targetReady - 15</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                        <li>Godkännande pågår - targetArbitration - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mål</td>
                  <td>Målgrupp för leverans</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (deliveryTemplateSummary)</td>
                  <td>Leveransmall</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatyrbild</td>
                  <td>Leveransminiatyr</td>
                  <td>sträng (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>Leverans</td>
                  <td>sträng (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>spårning</td>
                  <td>Spårningsparametrar</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingLogs</td>
                  <td>Spårningsloggar</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingUrls</td>
                  <td>Spårade URL:er</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>triggerMessage</td>
                  <td>Parametrar för transaktionsmeddelandet</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>typologi (typologyBase)</td>
                  <td>Typologi</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>arbetsflöde (workflowBase)</td>
                  <td>Målarbetsflöde</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowStatus</td>
                  <td>Arbetsflödesstatus</td>
                  <td>enumeration (sträng) (255)</td>
                  <td>
                     <ul>
                        <li>Pågår - igång</li>
                        <li>Redigering - utgåva - utgåva</li>
                        <li>Slutförd - avslutad - avslutad</li>
                        <li>Varning - varning - varning</li>
                        <li>Fel - fel - fel</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
            </table>

## Filter

Efter kanaltyp (byChannel)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>kanal</td>
    <td>uppräkning</td>
    </tr>
</table>

Efter körningstyp (byExecutionType)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>executionType</td>
    <td>uppräkning</td>
    </tr>
</table>

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
    <tr>
    <td>mc</td>
    <td>string</td>
    </tr>
</table>

Efter period (efter period)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>string</td>
    </tr>
</table>

Efter punkt (byStartPeriod)

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
    <td>timePeriod</td>
    <td>string</td>
    </tr>
</table>

Efter publiceringsstatus (byPublicationStatus)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>pStatus</td>
    <td>uppräkning</td>
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

Uppföljningsmeddelanden (visaUppföljning)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>följning</td>
    <td>boolesk</td>
    </tr>
</table>

Inkludera avancerade leveranser (med avancerad)

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

Inkludera korrektur (medFCP)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>withFCP</td>
    <td>boolesk</td>
    </tr>
</table>

Planerad under angiven period (perPlanning)

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

Presentera under angiven period (efter kalender)

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

Visa i körklart läge (showJob)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>oob</td>
    <td>boolesk</td>
    </tr>
</table>
