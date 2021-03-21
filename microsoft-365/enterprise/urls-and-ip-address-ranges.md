---
title: Office 365-URL's en IP-adresbereiken
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/01/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: 'Overzicht: Office 365 vereist verbinding met internet. De volgende eindpunten moeten bereikbaar zijn voor klanten die gebruikmaken van Office 365-abonnementen, waaronder Government Community Cloud (GCC).'
hideEdit: true
ms.openlocfilehash: 1c0a2a486bf6964edc9b94fd670c96ade161cacd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925266"
---
# <a name="office-365-urls-and-ip-address-ranges"></a>Office 365-URL's en IP-adresbereiken

Office 365 vereist verbinding met internet. De volgende eindpunten moeten bereikbaar zijn voor klanten die gebruikmaken van Office 365-abonnementen, waaronder Government Community Cloud (GCC).
  
*Office 365 Worldwide (+GCC)* | [Office 365 beheerd door 21 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |

||||
|:-----|:-----|:-----|
|**Laatst bijgewerkt:** 03-01-2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Abonnement op wijzigingenlogboek](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Downloaden:** alle vereiste en optionele bestemmingen in één lijst in [JSON-indeling](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).  <br/> | **Gebruik:** onze proxy-[PAC-bestanden](managing-office-365-endpoints.md#pacfiles) <br/> |

 Begin met [Het beheren van Office 365-eindpunten](managing-office-365-endpoints.md) om onze aanbevelingen voor het beheren van netwerkverbindingen met deze gegevens te begrijpen. Eindpuntgegevens worden aan het begin van elke maand bijgewerkt zoals vereist met nieuwe IP-adressen en URL's die worden gepubliceerd 30 dagen voordat ze actief worden. Dit maakt het voor klanten die nog geen geautomatiseerde updates hebben mogelijk om hun processen te voltooien voordat er een nieuwe verbinding is vereist. Eindpuntgegevens kunnen ook gedurende de maand worden bijgewerkt indien nodig om escalaties van ondersteuningen, beveiligingsincidenten of andere directe operationele vereisten aan te pakken. De gegevens die op deze pagina worden weergegeven, zijn allemaal gegenereerd op basis van de REST-webservice. Als u gebruikmaakt van een script of netwerkapparaat voor toegang tot deze gegevens, gaat u rechtstreeks naar de [Webservice](microsoft-365-ip-web-service.md).

De onderstaande eindpuntgegevens geven een overzicht van de vereisten voor verbinding tussen de computer van een gebruiker en Office 365. Het omvat geen netwerkverbindingen van Microsoft naar een klantennetwerk, ook wel hybride of inkomende netwerkverbindingen genoemd. Zie [Aanvullende eindpunten](additional-office365-ip-addresses-and-urls.md) voor meer informatie.

De eindpunten worden ingedeeld in vier servicegebieden. De eerste drie servicegebieden kunnen afzonderlijk worden geselecteerd om verbinding te maken. Het vierde servicegebied is een gangbare afhankelijkheid (met de naam Microsoft 365 Common en Office) en moet altijd een netwerkverbinding hebben.

De getoonde gegevenskolommen zijn:

- **ID**: Het ID-nummer van de rij, ook wel een eindpuntenset genoemd. Deze ID is hetzelfde als die door de webservice wordt geretourneerd voor de eindpuntenset.

- **Category**: Toon of de eindpuntenset wordt gecategoriseerd als "Optimaliseren", "Toestaan" of "Standaard". U vindt meer informatie over deze categorieën en richtlijnen voor het beheren ervan in [Nieuwe Office 365-eindpuntcategorieën](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). In deze kolom wordt ook aangegeven welke eindpuntensets vereist zijn voor netwerkverbinding. Voor eindpuntensets die geen netwerkverbinding hoeven te hebben, geven we in dit veld notities om aan te geven welke functionaliteit ontbreekt als de eindpuntenset wordt geblokkeerd. Als u een volledig servicegebied uitsluit, vereisen de eindpuntensets die als verplicht worden genoemd geen verbinding.

- **ER**: Dit is **Ja** als de eindpuntenset wordt ondersteund via Azure ExpressRoute met Office 365-routeprefixen. De BGP-community met de weergegeven routeprefixen komt overeen met het weergegeven servicegebied. Als ER **Nee** is, betekent het dat ExpressRoute niet wordt ondersteund voor deze eindpuntenset. U dient er echter niet vanuit te gaan dat er geen routes worden genoemd voor een eindpuntenset waarvan ER **Nee** is.

- **Adressen**: Hier worden de FQDN‘s of wildcard-domeinnamen en IP-adresbereiken voor de eindpuntenset weergegeven. Houd er rekening mee dat een IP-adresbereik de CIDR-indeling heeft en mogelijk veel afzonderlijke IP-adressen bevat in het opgegeven netwerk.
 
- **Poorten**: Bevat de TCP- of UDP-poorten die worden gecombineerd met de adressen om het netwerkeindpunt te vormen. Het is mogelijk dat er een aantal dubbele waarden worden weergegeven in de IP-adresbereiken waarvoor verschillende poorten worden genoemd.

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

>[!Note]
>Zie [Het gebruik van harde IP-adressen voor Yammer wordt niet aanbevolen](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) op de Yammer-blog voor aanbevelingen over IP-adressen en URL's voor Yammer.
>

## <a name="related-topics"></a>Verwante onderwerpen

[Office 365-eindpunten beheren](managing-office-365-endpoints.md)

[Algemene Microsoft Stream-eindpunten](/stream/network-overview#general-microsoft-stream-endpoints)
  
[Microsoft 365-connectiviteit controleren](./monitor-connectivity.md)

[De basis- en gemiddelde CA-bundel op het toepassingssysteem van derden](../compliance/encryption-office-365-certificate-chains.md)
  
[Clientconnectiviteit](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Netwerken voor contentlevering](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[IP-bereiken en servicetags Microsoft Azure – Openbare cloud](https://www.microsoft.com/download/details.aspx?id=56519)

[IP-bereiken en servicetags Microsoft Azure – Cloud overheid VS](https://www.microsoft.com/download/details.aspx?id=57063)

[IP-bereiken en servicetags Microsoft Azure – Cloud Duitsland](https://www.microsoft.com/download/details.aspx?id=57064)

[IP-bereiken en servicetags Microsoft Azure – Cloud China](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft Public IP Space](https://www.microsoft.com/download/details.aspx?id=53602)

[Register met servicenaam en poortnummer van transportprotocol](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)