---
title: Beveiligingsfuncties in azure Information Protection waarover wordt gerollend voor bestaande tenants
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In dit artikel wordt uitgelegd welke wijzigingen worden doorgevoerd in de beveiligingsfuncties in azure Information Protection
ms.openlocfilehash: 070b0d1af0576391ce5f22a827975d1541646454
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203597"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Beveiligingsfuncties in azure Information Protection waarover wordt gerollend voor bestaande tenants

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Om u te helpen bij de eerste stap bij het beschermen van uw informatie 2018, moet u, voor de bescherming van uw gegevens, alle Azure-informatiebescherming in aanmerking komen de beveiligingsfuncties in azure Information Protection zijn standaard ingeschakeld. De beveiligingsfuncties in azure Information Protection werden voorheen bekend in Office 365 als Rights Management of Azure RMS. Als uw organisatie een abonnement heeft op Office E3 service of een hoger serviceplan, krijgt u nu een Head te beschermen tegen de bescherming van gegevens via Azure Information Protection wanneer we deze functies willen invullen.

## <a name="changes-beginning-july-1-2018"></a>Wijzigingen vanaf 1 juli 2018

Vanaf 1 juli 2018 zal Microsoft de beschermings functie voor Azure Information Protection inschakelen voor alle organisaties met een van de volgende abonnementen:

- Office 365-bericht versleuteling wordt aangeboden als onderdeel van Office 365 E3 en E5, Microsoft E3 en E5, Office 365 a1, a3, en Office 365 G3 en G5. U hebt geen extra licenties nodig om de nieuwe beschermingsfuncties mogelijk te maken door Azure Information Protection.

- U kunt ook Azure Information Protection abonnement 1 toevoegen aan de volgende abonnementen om de nieuwe functies voor bericht versleuteling van Office 365 te ontvangen: Exchange Online abonnement 1, Exchange Online plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard, of Office 365 Enterprise E1.

- Voor de voordelen van Office 365-bericht versleuteling moet een licentie voor het gebruik van de functie gelden.

- Zie de [Exchange Online-servicebeschrijvingen](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) voor Office 365-bericht versleuteling voor de volledige lijst.

Tenant beheerders kunnen de beveiligingsstatus controleren in de Office 365-beheerportal.

![Schermafbeelding van het activeren van Rights Management in Office 365.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Waarom wordt deze wijziging aangebracht?

Office 365-bericht versleuteling maakt gebruik van de beschermingsfuncties in azure Information Protection. Met de kern van de recente verbeteringen aan Office 365-bericht versleuteling en onze bredere investeringen aan informatiebescherming in Microsoft 365, maken we het eenvoudiger om onze organisatie onze beveiligingsmogelijkheden te activeren en te gebruiken, zoals historisch, en de versleutelings technologieën zijn moeilijk te configureren. Als u de beveiligingsfuncties in azure Information Protection standaard inschakelt, kunt u snel aan de slag om uw gevoelige gegevens te beschermen.

## <a name="does-this-impact-me"></a>Is dit van invloed op mij?

Als uw organisatie een in aanmerking komend Office 365-licentie heeft gekocht, wordt uw Tenant beïnvloed door deze wijziging.

 **BELANGRIJKE!** Als u gebruikmaakt van Active Directory Rights Management Services (AD RMS) in uw on-premises omgeving, moet u deze wijziging direct afmelden of migreren naar Azure Information Protection voordat u deze wijziging binnen de komende 30 dagen uitrolt. Zie voor meer informatie over het gebruik van uitbellen de optie Ik gebruik AD RMS, hoe kan ik me afmelden? " verderop in dit artikel. Als u liever migreert, raadpleegt u [migratie van AD RMS naar Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Kan ik Azure Information Protection gebruiken met Active Directory Rights Management Services (AD RMS)?

Nee. Dit is geen ondersteund implementatiescenario. Zonder gebruik te maken van de aanvullende stappen voor het aftappen, kunnen sommige computers automatisch de Azure Rights Management-service starten en ook verbinding maken met uw AD RMS-cluster. Dit scenario wordt niet ondersteund en bevat onbetrouwbare resultaten, dus het is belangrijk dat u deze wijziging binnen 30 dagen aflevert voordat we deze nieuwe functies rollen. Zie voor meer informatie over het gebruik van uitbellen de optie Ik gebruik AD RMS, hoe kan ik me afmelden? " verderop in dit artikel. Als u liever migreert, raadpleegt u [migratie van AD RMS naar Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Hoe weet ik of ik AD RMS gebruik?

Volg deze instructies [voor het voorbereiden van de omgeving voor Azure Rights Management wanneer u ook Active Directory Rights Management Services (AD RMS) hebt](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) om te controleren of u AD RMS hebt geïmplementeerd:

1. Hoewel deze optie optioneel is, kunnen de meeste AD RMS-implementaties het SCP (serviceverbindingspunt) publiceren naar Active Directory, zodat domeincomputers het AD RMS-cluster kunnen detecteren.

Gebruik ADSI Edit om te zien of er een SCP is gepubliceerd in Active Directory: CN = Configuration [servernaam], CN = Services, CN = RightsManagementServices, CN = SCP

2. Als u niet werkt met een SCP, moet Windows-computers die verbinding maken met een AD RMS-cluster, worden geconfigureerd voor de client serviceontdekking of de licentie omleiding via het Windows-register: HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MSIPC\ServiceLocation of HKEY_LOCAL_MACHINE \SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation

Zie voor meer informatie over deze register configuraties [de serviceontdekking van de client inschakelen met behulp van het Windows-register en het](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) [omleiden van licentieserver verkeer](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Ik gebruik AD RMS, hoe kan ik me afmelden?

Voer de volgende stappen uit als u zich wilt afmelden bij de komende wijziging:

1. Start een Windows PowerShell-sessie en maak verbinding met Exchange Online via een werk-of schoolaccount met algemene beheerdersmachtigingen in uw organisatie. Zie [verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)voor instructies.

2. Voer de cmdlet Set-IRMConfiguration uit met de volgende syntaxis:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Wat kan ik verwachten nadat deze wijziging is doorgevoerd?

Als deze functie is ingeschakeld, kunt u de nieuwe versie van Office 365-bericht versleuteling gebruiken, dat werd aangekondigd op [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) en de versleutelings-en beschermingsfuncties van Azure Information Protection benutten.

![Schermafbeelding van een OME beveiligd bericht in de webversie van Outlook.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Zie voor meer informatie over de nieuwe verbeteringen de [bericht versleuteling van Office 365](../../compliance/ome.md).
