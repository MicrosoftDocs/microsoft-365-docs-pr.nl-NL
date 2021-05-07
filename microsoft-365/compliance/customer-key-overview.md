---
title: Serviceversleuteling met klantsleutel
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: In dit artikel leert u hoe serviceversleuteling werkt met de klantsleutel in Microsoft 365.
ms.openlocfilehash: 21291dc45cd634cd5b6a88c4e58972c17486724f
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162483"
---
# <a name="service-encryption-with-customer-key"></a>Serviceversleuteling met klantsleutel

Microsoft 365 biedt basislijnversleuteling, volumeversleuteling die is ingeschakeld via BitLocker en Distributed Key Manager (DKM). Microsoft 365 biedt een extra versleutelingslaag op de toepassingslaag voor uw inhoud. Deze inhoud bevat gegevens uit Exchange Online, Skype voor Bedrijven, SharePoint Online, OneDrive voor Bedrijven en Teams bestanden. Deze toegevoegde versleutelingslaag wordt serviceversleuteling genoemd.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Hoe serviceversleuteling, BitLocker en Klantsleutel samenwerken

Serviceversleuteling zorgt ervoor dat inhoud in rust wordt versleuteld op de servicelaag. Uw gegevens worden altijd in rust versleuteld in de Microsoft 365 **service met BitLocker en DKM.** Zie de 'Beveiligings-, privacy- en compliancegegevens' en Hoe Exchange Online uw e-mailgeheimen [beveiligt](exchange-online-secures-email-secrets.md)voor meer informatie. Klantsleutel biedt extra bescherming tegen het weergeven van gegevens door onbevoegde systemen of personeel en vormt een aanvulling op de BitLocker schijfversleuteling in Microsoft-datacenters. Serviceversleuteling is niet bedoeld om te voorkomen dat microsoft-personeel toegang heeft tot klantgegevens. Het primaire doel is klanten te helpen bij het voldoen aan wettelijke of nalevingsverplichtingen voor het beheren van hoofdsleutels. Klanten machtigen O365-services expliciet om hun versleutelingssleutels te gebruiken om cloudservices met toegevoegde waarde te leveren, zoals eDiscovery, anti-malware, antispam, zoekindexering, enzovoort.

Klantsleutel is gebaseerd op serviceversleuteling en u kunt versleutelingssleutels leveren en bedienen. Microsoft 365 gebruikt deze sleutels om uw gegevens in rust te versleutelen, zoals beschreven in de [Voorwaarden voor Online Services (OST).](https://www.microsoft.com/licensing/product-licensing/products.aspx) Met De klantsleutel kunt u voldoen aan nalevingsverplichtingen omdat u de versleutelingssleutels controleert die Microsoft 365 gegevens versleutelen en ontsleutelen.
  
Klantsleutel verbetert de mogelijkheid van uw organisatie om te voldoen aan de vereisten voor naleving die belangrijke afspraken met de cloudserviceprovider specificeren. Met De klantsleutel geeft u de hoofdversleutelingssleutels voor uw Microsoft 365 op het toepassingsniveau. Hierdoor oefent u de controle over de sleutels van uw organisatie uit. Als u besluit de service te verlaten, trekt u de toegang tot de hoofdsleutels van uw organisatie in. Voor alle Microsoft 365 services is het inroepen van toegang tot de sleutels de eerste stap op het pad naar gegevensverhaling. Als u de toegang tot de sleutels inroept, zijn de gegevens onleesbaar voor de service.

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>Klantsleutel versleutelt gegevens in rust in Office 365

Met behulp van de door u op te geven sleutels versleutelt Klantsleutel op toepassingsniveau:

- SharePoint Online, OneDrive voor Bedrijven en Teams bestanden.
- Bestanden die zijn geüpload naar OneDrive voor Bedrijven.
- Exchange Online inhoud van het postvak, inclusief inhoud van e-mail, agenda-items en de inhoud in e-mailbijlagen.
- Tekstgesprekken uit Skype voor Bedrijven.

We bieden momenteel geen klantcontrole over de versleutelingssleutels voor Skype-vergadering Broadcast en Skype-vergadering inhoud uploaden. In plaats daarvan wordt deze inhoud versleuteld samen met alle andere inhoud in Office 365.

### <a name="customer-key-with-hybrid-deployments"></a>Klantcode met hybride implementaties

Klantsleutel versleutelt alleen gegevens in rust in de cloud. Klantcode werkt niet om uw on-premises postvakken en bestanden te beveiligen. U kunt uw on-premises gegevens versleutelen met een andere methode, zoals BitLocker.

## <a name="about-the-data-encryption-policy-dep"></a>Informatie over het beleid voor gegevensversleuteling (DEP)

Een gegevensversleutelingsbeleid definieert de versleutelingshiërarchie om gegevens te versleutelen met behulp van elk van de sleutels die u verstrekt, evenals de beschikbaarheidssleutel die door Microsoft is beveiligd. U maakt DEP's met PowerShell-cmdlets, die voor elke service verschillen, en wijst deze DEP's toe om toepassingsgegevens te versleutelen. Bijvoorbeeld:

**Exchange Online en Skype voor Bedrijven** U kunt maximaal 50 DEP's per tenant maken. U koppelt DEP's aan uw klantsleutels in Azure Key Vault en wijst vervolgens DEP's toe aan afzonderlijke postvakken. Wanneer u een DEP aan een postvak toewijst:

- het postvak is gemarkeerd voor een postvak verplaatsen. Op basis van prioriteiten in Microsoft 365 zoals hier wordt [beschreven, verplaatst u aanvragen in de Microsoft 365 service.](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)

- De versleuteling vindt plaats terwijl het postvak wordt verplaatst. Sta 72 uur toe dat het postvak wordt versleuteld met de nieuwe DEP. Als de postvakken niet zijn versleuteld na 72 uur te hebben gewacht vanaf het moment dat u de DEP hebt toegewezen, neem dan contact op met Microsoft.

Later kunt u het DEP vernieuwen of een ander DEP toewijzen aan het postvak, zoals beschreven in Klantsleutel beheren [voor Office 365.](customer-key-manage.md) Elk postvak moet over de juiste licenties zijn om een DEP toe te wijzen. Zie Voordat u Klantcode in stelt voor meer informatie over [licenties.](customer-key-set-up.md#before-you-set-up-customer-key)

> [!NOTE]
> De DEP kan worden toegepast op een gedeeld postvak, een postvak in een openbare map en een Microsoft 365-groepspostvak voor tenants die voldoen aan de licentievereiste voor gebruikerspostvakken, hoewel sommige van deze postvakken geen toegewezen licentie kunnen zijn (postvak voor openbare mappen en Microsoft 365 groepspostvak) of een licentie nodig hebben voor het vergroten van de opslag (gedeeld postvak).

**SharePoint Online, OneDrive voor Bedrijven en Teams bestanden** Als u de functie multi-geo gebruikt, kunt u maximaal één DEP per geo maken voor uw organisatie. U kunt verschillende klantsleutels voor elke geo gebruiken. Als u de functie multi-geo niet gebruikt, kunt u slechts één DEP per tenant maken. Wanneer u de DEP toewijst, wordt de versleuteling automatisch gestart, maar kan het enige tijd duren om de versleuteling te voltooien. Raadpleeg de details in [Klantsleutel instellen.](customer-key-set-up.md)

## <a name="leaving-the-service"></a>De service verlaten

Klantsleutel helpt u bij het voldoen aan nalevingsverplichtingen doordat u uw sleutels kunt intrekken wanneer u de service Microsoft 365 verlaten. Wanneer u uw sleutels int als onderdeel van het verlaten van de service, wordt de beschikbaarheidssleutel verwijderd, wat resulteert in cryptografische verwijdering van uw gegevens. Cryptografische verwijdering verkleint het risico op gegevensmanie, wat belangrijk is voor het voldoen aan zowel beveiligings- als nalevingsverplichtingen. Zie Uw sleutels intrekken en het proces voor het verwijderen van gegevens starten voor informatie over het proces voor het verwijderen van gegevens en het intrekken van [sleutels.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

### <a name="encryption-ciphers-used-by-customer-key"></a>Versleutelingscodes die door klantsleutel worden gebruikt

Klantsleutel gebruikt diverse versleutelingscodes om sleutels te versleutelen, zoals wordt weergegeven in de volgende cijfers.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Versleutelingssleutels die worden gebruikt om sleutels voor Exchange Online en Skype voor Bedrijven

![Versleutelingscodes voor Exchange Online klantsleutel](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Versleutelingscodes die worden gebruikt om sleutels te versleutelen voor SharePoint Online OneDrive voor Bedrijven en Teams bestanden

![Versleutelingscodes voor SharePoint Online Customer Key](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Verwante artikelen

- [Klantsleutel instellen](customer-key-set-up.md)

- [Klantcode beheren](customer-key-manage.md)

- [Een klantsleutel of een beschikbaarheidssleutel rollen of draaien](customer-key-availability-key-roll.md)

- [Meer informatie over de beschikbaarheidssleutel](customer-key-availability-key-understand.md)

- [Klanten-lockbox](customer-lockbox-requests.md)

- [Serviceversleuteling](office-365-service-encryption.md)