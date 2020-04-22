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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
description: Om u te helpen bij de eerste stap in het beveiligen van uw gegevens, hebben alle azure information protection-geschikte tenants vanaf juli 2018 standaard de beveiligingsfuncties in Azure Information Protection ingeschakeld. De beveiligingsfuncties in Azure Information Protection stonden voorheen bekend in Office 365 als Rights Management of Azure RMS. Als uw organisatie een Office E3-serviceplan of een hoger serviceplan heeft, krijgt u nu een voorsprong bij het beveiligen van informatie via Azure Information Protection wanneer we deze functies uitrollen.
ms.openlocfilehash: 3efdeefd2008a5ff9f730b879190d1edc015803a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638270"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Beveiligingsfuncties in Azure Information Protection die worden uitgerold naar bestaande tenants

Om u te helpen bij de eerste stap in het beveiligen van uw gegevens, hebben alle azure information protection-geschikte tenants vanaf juli 2018 standaard de beveiligingsfuncties in Azure Information Protection ingeschakeld. De beveiligingsfuncties in Azure Information Protection stonden voorheen bekend in Office 365 als Rights Management of Azure RMS. Als uw organisatie een Office E3-serviceplan of een hoger serviceplan heeft, krijgt u nu een voorsprong bij het beveiligen van informatie via Azure Information Protection wanneer we deze functies uitrollen.

## <a name="changes-beginning-july-1-2018"></a>Wijzigingen vanaf 1 juli 2018

Vanaf 1 juli 2018 schakelt Microsoft de beveiligingsmogelijkheid in Azure Information Protection in voor alle organisaties met een van de volgende abonnementsplannen:

- Office 365-berichtversleuteling wordt aangeboden als onderdeel van Office 365 E3 en E5, Microsoft E3 en E5, Office 365 A1, A3 en A5 en Office 365 G3 en G5. U hebt geen extra licenties nodig om de nieuwe beveiligingsmogelijkheden te ontvangen die worden aangedreven door Azure Information Protection.

- U azure information protection plan 1 ook toevoegen aan de volgende plannen om de nieuwe Office 365 Message Encryption-mogelijkheden te ontvangen: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard of Office 365 Enterprise E1.

- Elke gebruiker die profiteert van Office 365-berichtversleuteling moet een licentie hebben om onder de functie te vallen.

- Zie de beschrijvingen van de [Exchange Online-service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) voor Office 365-berichtversleuteling voor de volledige lijst.

Tenantbeheerders kunnen de beveiligingsstatus controleren in de Office 365-beheerdersportal.

![Schermafbeelding van de toepassing in Office 365 is geactiveerd.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Waarom maken we deze verandering?

Office 365-berichtversleuteling maakt gebruik van de beveiligingsmogelijkheden in Azure Information Protection. In het hart van de recente verbeteringen aan Office 365-berichtversleuteling en onze bredere investeringen in informatiebescherming in Microsoft 365, maken we het voor organisaties gemakkelijker om onze beveiligingsmogelijkheden in te schakelen en te gebruiken, omdat encryptietechnologieën historisch gezien moeilijk zijn in te stellen. Door standaard de beveiligingsfuncties in Azure Information Protection in te schakelen, u snel aan de slag om uw gevoelige gegevens te beschermen.

## <a name="does-this-impact-me"></a>Heeft dit invloed op mij?

Als uw organisatie een in aanmerking komende Office 365-licentie heeft aangeschaft, heeft uw tenant invloed op deze wijziging.

 **Belangrijk!** Als u Active Directory Rights Management Services (AD RMS) gebruikt in uw on-premises omgeving, moet u zich onmiddellijk afmelden voor deze wijziging of migreren naar Azure Information Protection voordat we deze wijziging binnen de komende 30 dagen uitrollen. Zie 'Ik gebruik AD RMS, hoe kan ik me afmelden?' later in dit artikel. Zie Migreren van AD RMS naar Azure Information Protection als u liever migreert [van AD RMS naar Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Kan ik Azure Information Protection gebruiken met Active Directory Rights Management Services (AD RMS)?

Nee. Dit is geen ondersteund implementatiescenario. Zonder de extra opt-outstappen te nemen, kunnen sommige computers automatisch de Azure Rights Management-service gebruiken en ook verbinding maken met uw AD RMS-cluster. Dit scenario wordt niet ondersteund en heeft onbetrouwbare resultaten, dus het is belangrijk dat u zich binnen 30 dagen afziet van deze wijziging voordat we deze nieuwe functies uitrollen. Zie 'Ik gebruik AD RMS, hoe kan ik me afmelden?' later in dit artikel. Zie Migreren van AD RMS naar Azure Information Protection als u liever migreert [van AD RMS naar Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Hoe weet ik of ik AD RMS gebruik?

Gebruik deze instructies van [Het voorbereiden van de omgeving voor Azure Rights Management wanneer u ook Active Directory Rights Management Services (AD RMS)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) hebt om te controleren of u AD RMS hebt geïmplementeerd:

1. Hoewel de meeste AD RMS-implementaties optioneel zijn, publiceren ze het serviceverbindingspunt (SCP) naar Active Directory, zodat domeincomputers het AD RMS-cluster kunnen ontdekken.

Adsi Bewerken gebruiken om te zien of een SCP is gepubliceerd in Active Directory: CN=Configuration [servernaam], CN=Services, CN=RightsManagementServices, CN=SCP

2. Als u geen SCP gebruikt, moeten Windows-computers die verbinding maken met een AD RMS-cluster zijn geconfigureerd voor detectie van clientservices of omleiding van licenties met behulp van het Windows-register: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocatie of HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation

Zie [Servicedetectie clientzijde inschakelen met behulp van het Windows-register](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) en [Licentieserververkeer omleiden](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)voor meer informatie over deze registerconfiguraties.

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Ik gebruik AD RMS, hoe kan ik me afmelden?

Voer de volgende stappen uit om u af te melden voor de komende wijziging:

1. Met behulp van een werk- of schoolaccount met algemene beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell-sessie en maakt u verbinding met Exchange Online. Zie Verbinding [maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)voor instructies .

2. Voer de cmdlet Set-IRMConfiguration uit met de volgende syntaxis:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Wat kan ik verwachten nadat deze wijziging is aangebracht?

Zodra dit is ingeschakeld, op voorwaarde dat u zich niet hebt afgemeld, u beginnen met het gebruik van de nieuwe versie van Office 365-berichtversleuteling die is aangekondigd op [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) en gebruikmaakt van de versleutelings- en beveiligingsmogelijkheden van Azure Information Protection.

![Schermafbeelding van een OME-beveiligd bericht in de webversie van Outlook.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Zie [Office 365-berichtversleuteling](../../compliance/ome.md)voor meer informatie over de nieuwe verbeteringen.
