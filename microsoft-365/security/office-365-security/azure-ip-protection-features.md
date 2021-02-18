---
title: Beveiligingsfuncties in Azure Information Protection die worden uitgerold naar bestaande tenants
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In dit artikel wordt uitgelegd welke wijzigingen worden doorgevoerd in de beveiligingsfuncties in Azure Information Protection
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fe85a46e3f20cda62cd8a52bd5df92257f8fee57
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286667"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Beveiligingsfuncties in Azure Information Protection die worden uitgerold naar bestaande tenants

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Om u te helpen bij de eerste stap bij het beveiligen van uw gegevens, zijn vanaf juli 2018 alle in aanmerking komende tenants voor Azure Information Protection standaard ingeschakeld voor de beveiligingsfuncties in Azure Information Protection. De beveiligingsfuncties in Azure Information Protection werden voorheen in Office 365 bekend als Rights Management of Azure RMS. Als uw organisatie een Office E3-serviceplan of een hoger serviceplan heeft, krijgt u bij het implementeren van deze functies de eerste keer te maken met het beveiligen van gegevens via Azure Information Protection.

## <a name="changes-beginning-july-1-2018"></a>Wijzigingen vanaf 1 juli 2018

Vanaf 1 juli 2018 zal Microsoft de beveiligingsmogelijkheden in Azure Information Protection inschakelen voor alle organisaties met een van de volgende abonnementen:

- Office 365-berichtversleuteling wordt aangeboden als onderdeel van Office 365 E3 en E5, Microsoft E3 en E5, Office 365 A1, A3 en A5, en Office 365 G3 en G5. U hebt geen extra licenties nodig om de nieuwe beveiligingsmogelijkheden te ontvangen die mogelijk worden gemaakt door Azure Information Protection.

- U kunt Azure Information Protection Plan 1 ook toevoegen aan de volgende abonnementen voor het ontvangen van de nieuwe office 365-berichtversleutelingsfuncties: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard of Office 365 Enterprise E1.

- Elke gebruiker die gebruik maakt van Office 365-berichtversleuteling, moet een licentie hebben om de functie te kunnen gebruiken.

- Zie de beschrijvingen van de [Exchange Online-service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) voor Office 365-berichtversleuteling voor de volledige lijst.

Tenantbeheerders kunnen de beveiligingsstatus controleren in de Office 365-beheerdersportal.

![Schermafbeelding die laat zien dat Rights Management in Office 365 is geactiveerd.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Waarom brengen we deze wijziging aan?

Office 365-berichtversleuteling maakt gebruik van de beveiligingsmogelijkheden in Azure Information Protection. Het hart van de recente verbeteringen in Office 365-berichtversleuteling en onze bredere investeringen in informatiebeveiliging in Microsoft 365 maken we het organisaties gemakkelijker om onze beveiligingsfuncties in te stellen en te gebruiken, aangezien versleutelingstechnologieën historisch gezien moeilijk zijn ingesteld. Door de beveiligingsfuncties in Azure Information Protection standaard in te schakelen, kunt u snel aan de slag om uw gevoelige gegevens te beschermen.

## <a name="does-this-impact-me"></a>Is dit van invloed op mij?

Als uw organisatie een in aanmerking komende Office 365-licentie heeft gekocht, heeft deze wijziging gevolgen voor uw tenant.

> [!IMPORTANT]
> Als u AD RMS (Active Directory Rights Management Services) gebruikt in uw on-premises omgeving, moet u deze wijziging onmiddellijk stoppen of migreren naar Azure Information Protection voordat we deze wijziging binnen de komende 30 dagen implementeren. Zie 'I use AD RMS, how do I opt out? verder in dit artikel. Zie Migreren van AD RMS naar Azure Information Protection als u liever [migreert.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Kan ik Azure Information Protection gebruiken met Active Directory Rights Management Services (AD RMS)?

Nee. Dit is geen ondersteund implementatiescenario. Zonder de extra opt-outstappen uit te voeren, kunnen sommige computers automatisch gebruikmaken van de Azure Rights Management-service en ook verbinding maken met uw AD RMS-cluster. Dit scenario wordt niet ondersteund en heeft onbetrouwbare resultaten, dus het is belangrijk dat u deze wijziging binnen 30 dagen voordat we deze nieuwe functies uitrollen, uitrolt. Zie 'I use AD RMS, how do I opt out? verder in dit artikel. Zie Migreren van AD RMS naar Azure Information Protection als u liever [migreert.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Hoe weet ik of ik AD RMS gebruik?

Gebruik deze instructies voor het voorbereiden van de omgeving voor Azure Rights Management wanneer u ook [Active Directory Rights Management Services (AD RMS)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) hebt om te controleren of U AD RMS hebt geïmplementeerd:

1. Hoewel optioneel, publiceren de meeste AD RMS-implementaties het serviceverbindingspunt (SCP) naar Active Directory, zodat domeincomputers het AD RMS-cluster kunnen ontdekken.

   AdsI Edit gebruiken om te zien of er een SCP is gepubliceerd in Active Directory: CN=Configuration [servernaam], CN=Services, CN=RightsManagementServices, CN=SCP

2. Als u geen SCP gebruikt, moeten Windows-computers die verbinding maken met een AD RMS-cluster, worden geconfigureerd voor servicedetectie op de client of voor licentieomleiding via het Windows-register: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation`

Zie Inschakelen van servicedetectie aan de clientzijde met behulp van het [Windows-register](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) en Het omleiden van [licentieserververkeer](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)voor meer informatie over deze registerconfiguraties.

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Ik gebruik AD RMS. Hoe kan ik dit niet doen?

Als u zich wilt afstappen van de komende wijziging, moet u deze stappen doorlopen:

1. Start een Windows PowerShell-sessie met een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie en maak verbinding met Exchange Online. Zie Connect [to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)voor instructies.

2. Voer de Set-IRMConfiguration cmdlet uit met de volgende syntaxis:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Wat kan ik verwachten nadat deze wijziging is aangebracht?

Zodra dit is ingeschakeld, kunt u, als u zich niet hebt uitgemeld, aan de slag met de nieuwe versie van Office 365-berichtversleuteling, die is aangekondigd bij [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) en die gebruik maakt van de versleutelings- en beveiligingsmogelijkheden van Azure Information Protection.

![Schermafbeelding van een ome-beveiligd bericht in de webversie van Outlook.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Zie Office 365-berichtversleuteling voor meer informatie [over de nieuwe verbeteringen.](../../compliance/ome.md)
