---
title: DataModel-målgrupp
description: Läs mer om datamodellen
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 53da6c4e-d4fb-4677-acff-744e3eb10960
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 1%

---

# Målgrupp (nms:audiens)

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
                  <td>aamMappingId</td>
                  <td>Audience Manager-mappnings-ID</td>
                  <td>sträng (100)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>amcDataSource (amcDataSourceBase)</td>
                  <td>AMC-datakälla</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audiensData</td>
                  <td>Förhandsgranska markerad population</td>
                  <td>samling </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>publikDataSchema</td>
                  <td>Datamodell</td>
                  <td>sträng (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audiensMetadata</td>
                  <td>Målgruppsmetadata</td>
                  <td>sträng (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>collectLineNumber</td>
                  <td>Använd ett radnummer som ID</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>count</td>
                  <td>Antal</td>
                  <td>heltal </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countDate</td>
                  <td>Räkningsdatum</td>
                  <td>datum </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countPreview</td>
                  <td>CountPreview</td>
                  <td>artikel </td>
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
                  <td>desc</td>
                  <td>Beskrivning</td>
                  <td>sträng (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>doNotPersist</td>
                  <td>Historikera inte det här jobbet</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>errorLimit</td>
                  <td>Fel innan avbruten</td>
                  <td>heltal </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>expirationDate</td>
                  <td>Förfaller den</td>
                  <td>datum </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Geografisk enhet</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasSchema</td>
                  <td>HasSchema</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isAMC</td>
                  <td>Adobe Marketing Cloud</td>
                  <td>boolesk </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>Är extern resurs</td>
                  <td>boolesk </td>
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
                  <td>rejectFilename</td>
                  <td>Avvisningsfil</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sharedAudience</td>
                  <td>Namn på den delade målgruppen</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>källa</td>
                  <td>Source</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sourceId</td>
                  <td>SOURCE ID</td>
                  <td>heltal </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>Målgrupp</td>
                  <td>sträng (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>type</td>
                  <td>Typ</td>
                  <td>uppräkning (sträng) (100)</td>
                  <td>
                     <ul>
                        <li>Fråga - fråga - fråga</li>
                        <li>Lista - lista - lista</li>
                        <li>Fil - fil - fil</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>där</td>
                  <td>Frågedefinition</td>
                  <td>artikel </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>arbetsflöde (arbetsflöde)</td>
                  <td>Arbetsflöde</td>
                  <td>link </td>
                  <td> </td>
               </tr>
            </table>

## Filter

Efter filtreringsdimension (byFilteringResource)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>filteringResource</td>
    <td>string</td>
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

Efter typ (byType)

<table>
    <tr>
    <th>Namn</th>
    <th>Typ</th>
    </tr>
    <tr>
    <td>type</td>
    <td>uppräkning</td>
    </tr>
    <tr>
    <td>isAMC</td>
    <td>string</td>
    </tr>
</table>
