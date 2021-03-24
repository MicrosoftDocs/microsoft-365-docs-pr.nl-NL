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
description: In dit artikel worden de wijzigingen beschreven die worden doorgevoerd in de beveiligingsfuncties in Azure Information Protection
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77d45c8521e67c480b9e5557b05eed8ba5dd2645
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058990"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Beveiligingsfuncties in Azure Information Protection die worden uitgerold naar bestaande tenants

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Als u wilt helpen bij de eerste stap bij het beveiligen van uw gegevens, zijn vanaf juli 2018 alle in aanmerking komende tenants van Azure Information Protection standaard ingeschakeld voor de beveiligingsfuncties in Azure Information Protection. De beveiligingsfuncties in Azure Information Protection stonden voorheen bekend in Office 365 als Rights Management of Azure RMS. Als uw organisatie een Office E3-serviceplan of een hoger serviceplan heeft, krijgt u nu een voorsprong op het beveiligen van informatie via Azure Information Protection wanneer we deze functies implementeren.

## <a name="changes-beginning-july-1-2018"></a>Wijzigingen vanaf 1 juli 2018

Vanaf 1 juli 2018 zal Microsoft de beveiligingsfunctie in Azure Information Protection inschakelen voor alle organisaties met een van de volgende abonnementen:

- Office 365-berichtversleuteling wordt aangeboden als onderdeel van Office 365 E3 en E5, Microsoft E3 en E5, Office 365 A1, A3 en A5 en Office 365 G3 en G5. U hebt geen extra licenties nodig om de nieuwe beveiligingsmogelijkheden te ontvangen die worden ondersteund door Azure Information Protection.

- U kunt ook Azure Information Protection Plan 1 toevoegen aan de volgende abonnementen voor het ontvangen van de nieuwe mogelijkheden voor berichtversleuteling van Office 365: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard of Office 365 Enterprise E1.

- Elke gebruiker die gebruik maakt van Office 365-berichtversleuteling, moet een licentie hebben om onder de functie te vallen.

- Zie de servicebeschrijvingen [van Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) voor Office 365-berichtversleuteling voor de volledige lijst.

Tenantbeheerders kunnen de beveiligingsstatus controleren in de Office 365-beheerdersportal.

![Schermafbeelding waarin wordt laten zien dat rechtenbeheer in Office 365 is geactiveerd.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Waarom brengen we deze wijziging aan?

Office 365 Message Encryption maakt gebruik van de beveiligingsmogelijkheden in Azure Information Protection. In het hart van de recente verbeteringen in Office 365 Message Encryption en onze bredere investeringen in informatiebeveiliging in Microsoft 365, maken we het organisaties gemakkelijker om onze beveiligingsmogelijkheden in te stellen en te gebruiken, aangezien versleutelingstechnologieën historisch gezien moeilijk zijn in te stellen. Door de beveiligingsfuncties in Azure Information Protection standaard in te schakelen, kunt u snel aan de slag om uw gevoelige gegevens te beveiligen.

## <a name="does-this-impact-me"></a>Is dit van invloed op mij?

Als uw organisatie een in aanmerking komende Office 365-licentie heeft gekocht, wordt uw tenant beïnvloed door deze wijziging.

> [!IMPORTANT]
> Als u Active Directory Rights Management Services (AD RMS) gebruikt in uw on-premises omgeving, moet u zich onmiddellijk van deze wijziging afkeert of migreren naar Azure Information Protection voordat we deze wijziging binnen 30 dagen implementeren. Zie 'I use AD RMS, how do I opt out?' voor meer informatie over het kiezen van een opt-out. verder in dit artikel. Zie Migreren van AD RMS naar Azure Information Protection als u liever [migreert.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Kan ik Azure Information Protection gebruiken met Active Directory Rights Management Services (AD RMS)?

Nee. Dit is geen ondersteund implementatiescenario. Zonder de extra opt-outstappen te nemen, kunnen sommige computers automatisch de Azure Rights Management-service gaan gebruiken en ook verbinding maken met uw AD RMS-cluster. Dit scenario wordt niet ondersteund en heeft onbetrouwbare resultaten, dus het is belangrijk dat u zich binnen 30 dagen voordat we deze nieuwe functies uitrollen, deze wijziging niet meer wilt gebruiken. Zie 'I use AD RMS, how do I opt out?' voor meer informatie over het kiezen van een opt-out. verder in dit artikel. Zie Migreren van AD RMS naar Azure Information Protection als u liever [migreert.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Hoe weet ik of ik AD RMS gebruik?

Gebruik deze instructies van Het voorbereiden van de omgeving voor Azure Rights Management wanneer u ook [Active Directory Rights Management Services (AD RMS)](/azure/information-protection/deploy-use/prepare-environment-adrms) hebt om te controleren of u AD RMS hebt geïmplementeerd:

1. Hoewel optioneel, publiceren de meeste AD RMS-implementaties het serviceverbindingspunt (SCP) naar Active Directory, zodat domeincomputers het AD RMS-cluster kunnen ontdekken.

   Gebruik ADSI Edit om te zien of er een SCP is gepubliceerd in Active Directory: CN=Configuration [server name], CN=Services, CN=RightsManagementServices, CN=SCP

2. Als u geen SCP gebruikt, moeten Windows-computers die verbinding maken met een AD RMS-cluster, zijn geconfigureerd voor servicedetectie aan clientzijde of omleiding van licenties met behulp van het Windows-register: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation` .

Zie Servicedetectie aan clientzijde inschakelen met behulp van het [Windows-register](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) en Het serververkeer voor licenties omleiden voor meer informatie over [deze registerconfiguraties.](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Ik gebruik AD RMS, hoe kan ik mij afkeert?

Als u zich wilt afk zien van de aanstaande wijziging, gaat u als volgende stappen te werk:

1. Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell-sessie en maakt u verbinding met Exchange Online. Zie Verbinding maken [met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)voor instructies.

2. Voer de Set-IRMConfiguration cmdlet uit met de volgende syntaxis:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Wat kan ik verwachten nadat deze wijziging is aangebracht?

Zodra dit is ingeschakeld, op voorwaarde dat u zich niet hebt opgegeven, kunt u de nieuwe versie van Office 365-berichtversleuteling gaan gebruiken die is aangekondigd op [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) en maakt gebruik van de versleutelings- en beveiligingsmogelijkheden van Azure Information Protection.

![Schermafbeelding met een OME-beveiligd bericht in de webversie van Outlook.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Zie [Office 365 Message Encryption](../../compliance/ome.md)voor meer informatie over de nieuwe verbeteringen.