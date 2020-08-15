---
title: Multi-geografische Exchange
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Meer informatie over mogelijkheden voor meervoudige geo in Exchange Online, zoals beperkingen van functies en Postvak plaatsing.
ms.openlocfilehash: ca7203c72f23fd03512bf23eaa5a4687e4bac1b5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689266"
---
# <a name="multi-geo-capabilities-in-exchange-online"></a>Mogelijkheden voor meervoudige geo in Exchange Online

In een omgeving met meerdere geografische locaties kunt u de locatie van de inhoud van het postvak van Exchange Online (gegevens in de rest) per gebruiker selecteren.

U kunt postvakken op geografische geografische locaties plaatsen door het volgende te doen:

- U maakt een nieuw postvak van Exchange Online rechtstreeks op een geografische locatie.

- Wanneer u een bestaand Exchange Online-postvak naar een satelliet locatie verplaatst, wijzigt u de gewenste gegevenslocatie van de gebruiker.

- Een postvak van een on-premises Exchange-organisatie rechtstreeks op de geografische locatie van een satelliet te plaatsen.

## <a name="mailbox-placement-and-moves"></a>Postvak plaatsing en verhuizing

Nadat Microsoft de stappen voor meervoudige geo-configuratie heeft voltooid, voldoet Exchange Online met het **PreferredDataLocation** -kenmerk voor gebruikersobjecten in azure AD.

Met Exchange Online wordt de eigenschap **PreferredDataLocation** van Azure AD gesynchroniseerd met de eigenschap **MailboxRegion** in de Exchange Online-adreslijstservice. Met de waarde van **MailboxRegion** wordt de geografische locatie bepaald waar gebruikerspostvakken en bijbehorende archief postvakken worden geplaatst. Het is niet mogelijk om het primaire postvak van een gebruiker en de archief postvakken te configureren zodat ze zich in verschillende geografische locaties bevinden. Per gebruikersobject kan slechts één geo-locatie worden geconfigureerd.

- Wanneer **PreferredDataLocation** is geconfigureerd voor een gebruiker met een bestaand postvak, wordt het postvak in een wachtrij voor herverdeling opgeslagen en wordt automatisch naar de opgegeven geografische locatie verplaatst.

- Wanneer **PreferredDataLocation** is geconfigureerd voor een gebruiker zonder een bestaand postvak, wordt dit bij het inrichten van het postvak ingericht in de opgegeven geografische locatie.

- Wanneer u **PreferredDataLocation** niet opgeeft voor een gebruiker, wordt deze bij het inrichten van het postvak op de centrale geo-locatie ingericht.

- Als de **PreferredDataLocation** -code onjuist is (bijvoorbeeld een type nan in plaats van de waarde), wordt het postvak ingericht op de locatie van de centrale geografische locatie.

**Opmerking**: met de functie voor meervoudige geo-en Skype voor bedrijven online ondergebrachte vergaderingen gebruikt u de **PreferredDataLocation** -eigenschap op gebruikersobjecten om services te zoeken. Als u **PreferredDataLocation** -waarden configureert voor gebruikersobjecten voor het hosten van vergaderingen, worden het postvak voor die gebruikers automatisch verplaatst naar de opgegeven geo-locatie nadat meerdere geo-geo is ingeschakeld op de microsoft 365-Tenant.

## <a name="feature-limitations-for-multi-geo-in-exchange-online"></a>Functie beperkingen voor meerdere geografische functies in Exchange Online

- Functies voor beveiliging en naleving (bijvoorbeeld controle en eDiscovery) die beschikbaar zijn in het Exchange-Beheercentrum (SBV) zijn niet beschikbaar in meerdere geo-organisaties. In plaats daarvan moet u het [Microsoft 365-beveiligings & compliance](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) gebruiken om functies voor beveiliging en compliance te configureren.

- Outlook voor Mac-gebruikers ondervinden mogelijk een tijdelijk verlies van toegang tot zijn of haar online archiefmap wanneer u hun postvak naar een andere geografische locatie verplaatst. Deze voorwaarde doet zich voor als de primaire en de archief postvakken van de gebruiker zich in verschillende geografische locaties bevinden, aangezien het verplaatsen van een e-mailbericht op verschillende momenten mogelijk is.

- Gebruikers kunnen geen *postvakmappen* delen op geografische locaties in de webversie van Outlook (voorheen Outlook Web app of OWA). Een gebruiker in de Europese Unie kan bijvoorbeeld de webversie van Outlook niet gebruiken voor het openen van een gedeelde map in een postvak dat zich in de Verenigde Staten bevindt. De gebruikers van de webversie van Outlook kunnen echter wel *andere postvakken* openen in verschillende geografische locaties via een apart browservenster, zoals wordt beschreven in [het postvak van een andere gebruiker openen in een afzonderlijk browservenster in Outlook Web app](https://support.office.com/article/A909AD30-E413-40B5-A487-0EA70B763081#__toc372210362).

  **Opmerking**: het delen van een postvak in in de geo-map wordt ondersteund in Outlook voor Windows.

- Openbare mappen worden ondersteund in meerdere geo-organisaties. De openbare mappen moeten echter wel op de centrale geografische locatie staan. U kunt geen openbare mappen verplaatsen naar satelliet locaties.

- In een omgeving met meerdere geografische omgevingen wordt de controle van de postvakken van cross geo niet ondersteund. Als een gebruiker bijvoorbeeld machtigingen toewijst voor toegang tot een gedeeld postvak op een andere geografische locatie, worden postvak acties die door die gebruiker zijn uitgevoerd, niet aangemeld in het auditlogboek van het postvak van het gedeelde Postvak. Zie voor meer informatie [Postvak controle beheren](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing?view=o365-worldwide).
