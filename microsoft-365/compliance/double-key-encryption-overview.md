---
title: Overzicht van dubbele sleutelversleuteling en veelgestelde vragen
description: Veelgestelde vragen over Dubbele sleutelversleuteling voor Microsoft 365.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 12/11/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: ed07361f8c433a318342ae3c8ad750549992c285
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162072"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>Veelgestelde vragen over dubbele sleutelversleuteling

Hebt u een vraag over hoe Dubbele sleutelversleuteling werkt? Controleer hier of er een antwoord is.

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>Wat is Dubbele sleutelversleuteling voor Microsoft 365 (DKE)?

Met dubbele sleutelversleuteling voor Microsoft 365 kunnen klanten hun zeer gevoelige gegevens beveiligen om te voldoen aan gespecialiseerde vereisten. Het helpt klanten om de volledige controle over hun versleutelingssleutels te behouden. Er worden twee sleutels gebruikt om gegevens te beveiligen. één sleutel in uw besturingselement en een tweede sleutel die veilig is opgeslagen in Microsoft Azure. Als u gegevens wilt weergeven die zijn beveiligd met dubbele sleutelversleuteling, hebt u toegang tot beide sleutels nodig. Aangezien Microsoft slechts één van deze sleutels kan openen, blijven beveiligde gegevens ontoegankelijk voor Microsoft, zodat u volledige controle hebt over de privacy en beveiliging van uw gegevens.  

U kunt de service Dubbele sleutelversleuteling hosten die wordt gebruikt om uw sleutel op te vragen op een locatie naar keuze (on-premises sleutelbeheerserver of in de cloud). U onderhoudt de service net zoals elke andere toepassing. Met dubbele sleutelversleuteling kunt u de toegang tot de service Dubbele sleutelversleuteling bepalen. U kunt uw zeer gevoelige gegevens on-premises opslaan of verplaatsen naar de cloud. U kunt erop vertrouwen dat u toegang van derden wilt voorkomen, omdat u de volledige controle over uw sleutel hebt. Met dubbele sleutelversleuteling kunt u uw gegevens en sleutel op dezelfde locatie opslaan.

Met DKE kunt u voldoen aan wettelijke vereisten in verschillende voorschriften en standaarden, zoals de Algemene verordening gegevensbescherming (AVG), de Health Insurance Portability and Accountability Act (HIPAA), de Gramm-Leach-Bliley Act (GLBA), de Russische wetgeving voor gegevens lokalisatie – Federale wetgeving nee. 242-FZ, de Federale Privacywet 1988 van Australië en de Nieuw-Zeelandse Privacywet 1993.

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>Kan ik Double Key Encryption gebruiken met Microsoft Office ingebouwde gevoeligheidslabels?

U moet de geïntegreerde labelingclient voor Azure Information Protection gebruiken om documenten te beveiligen met dubbele sleutelversleuteling. Op dit moment kunt u geen Microsoft Office ingebouwde gevoeligheidslabels gebruiken.

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>Welke Microsoft 365-apps kan ik gebruiken met DKE?

U kunt DKE-labels gebruiken om documenten te beveiligen met de bureaubladversies van Word, Excel en PowerPoint op Windows. Controleer of u *.12711 of hoger (bureaubladversies van Word, PowerPoint en Excel) gebruikt op Windows.

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>Hoe verschilt Double Key Encryption van de bestaande HYOK-oplossing (Hold Your Own Key).

Met dubbele sleutelversleuteling worden uw gegevens versleuteld met twee toetsen. Uw versleutelingssleutel is in uw beheer en de tweede sleutel wordt opgeslagen in Microsoft Azure, zodat u uw versleutelde gegevens naar de cloud kunt verplaatsen. HYOK beschermt uw inhoud met slechts één sleutel en de sleutel is altijd on-premises.  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>Kunnen versleutelde documenten met dubbele sleutel extern worden gedeeld?

U kunt versleutelde documenten met dubbele sleutel delen met gebruikers in een afzonderlijke tenant, zolang deze gebruikers het volgende doen:

- Hebt u de vereiste machtiging om toegang te krijgen tot uw sleutel in uw Double Key Encryption-service.

- Heb de vereiste machtiging om toegang te krijgen tot uw sleutel in Microsoft Azure.

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>Wat gebeurt er met documenten die zijn beveiligd met HYOK?

Het implementeren van dubbele sleutelversleuteling heeft geen invloed op uw bestaande HYOK-installatie. U wordt echter aangeraden dubbele sleutelversleuteling parallel met HYOK te gebruiken.

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>Kan ik Double Key Encryption uitvoeren in mijn niet-Microsoft air-gapped omgeving?

DKE biedt geen ondersteuning voor deze omgevingen, omdat de service toegang nodig heeft tot Microsoft Azure.

## <a name="where-can-i-store-double-key-encrypted-documents"></a>Waar kan ik versleutelde documenten met dubbele sleutel opslaan?

U kunt versleutelde documenten met dubbele sleutel on-premises of in de cloud opslaan. In de cloud kunt u versleutelde inhoud verplaatsen naar SharePoint Online en OneDrive voor Bedrijven. Aangezien Microsoft geen toegang heeft tot uw persoonlijke sleutel, blijven de versleutelde gegevens ondoorzichtig voor Microsoft. Dit betekent ook dat u de versleutelde documenten niet online kunt bekijken in Office Web Apps.

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>In welke regio's en talen is Dubbele sleutelversleuteling beschikbaar? Is Double Key Encryption wereldwijd beschikbaar?

DKE-labels zijn gelokaliseerd in dezelfde talen als andere gevoeligheidslabels in Microsoft Information Protection. Double Key Encryption is wereldwijd beschikbaar.

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>Kan ik een niet-DKE-label converteren naar een DKE-label?

Nee. U kunt geen DKE toevoegen aan een label nadat u deze hebt aan een label. In plaats daarvan moet u **Dubbele sleutelversleuteling gebruiken** kiezen en de URL van uw Double Key Encryption-service opgeven wanneer u het label maakt.

## <a name="how-do-i-roll-my-dke-keys"></a>Hoe rol ik mijn DKE-toetsen?

Zie Operations for your Azure Information Protection tenant key (Operations for your Azure Information Protection tenant key ) voor instructies over het rollen (ook wel draaien of opnieuw toetsen maken genoemd) van de sleutel die u in Azure [opgeslagen.](/azure/information-protection/operations-customer-managed-tenant-key)

Zie [Tenant- en sleutelinstellingen](double-key-encryption.md#tenant-and-key-settings) voor informatie over het maken van een nieuwe sleutel voor de DKE-service.

Wanneer u een sleutel maakt, stelt u een naam en een GUID in. Als u vervolgens een sleutel draait, houdt u de oude record bij de naam en GUID, maar voegt u een nieuwe record toe met dezelfde naam, maar een andere GUID. De nieuwe sleutel wordt ingesteld als actief, zodat de OPENBARE sleutel-API deze gaat retourneren voor nieuwe versleuteling. Beide sleutels zijn beschikbaar voor ontsleuteling, zodat nieuwe inhoud en oude inhoud kunnen worden ontsleuteld.