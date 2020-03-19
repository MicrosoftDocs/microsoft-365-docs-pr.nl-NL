---
title: Beveiligingsfuncties in Azure Information Protection die worden uitgerold naar bestaande Office 365-tenants
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
description: Om te helpen bij de eerste stap bij het beveiligen van uw gegevens, hebben alle in aanmerking komende Azure Information Protection-tenants vanaf juli 2018 de beveiligingsfuncties in Azure Information Protection standaard ingeschakeld. De beveiligingsfuncties in Azure Information Protection stonden voorheen in Office 365 bekend als Rights Management of Azure RMS. Als uw organisatie een Office E3-serviceplan of een hoger serviceplan heeft, krijgt u nu een voorsprong op het beveiligen van informatie via Azure Information Protection wanneer we deze functies uitrollen.
ms.openlocfilehash: de3b233d4baac380608d3a209c2ffea274c20d5b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808803"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-office-365-tenants"></a>Beveiligingsfuncties in Azure Information Protection die worden uitgerold naar bestaande Office 365-tenants

Om te helpen bij de eerste stap bij het beveiligen van uw gegevens, hebben alle in aanmerking komende Azure Information Protection-tenants vanaf juli 2018 de beveiligingsfuncties in Azure Information Protection standaard ingeschakeld. De beveiligingsfuncties in Azure Information Protection stonden voorheen in Office 365 bekend als Rights Management of Azure RMS. Als uw organisatie een Office E3-serviceplan of een hoger serviceplan heeft, krijgt u nu een voorsprong op het beveiligen van informatie via Azure Information Protection wanneer we deze functies uitrollen.

## <a name="changes-beginning-july-1-2018"></a>Wijzigingen vanaf 1 juli 2018

Vanaf 1 juli 2018 schakelt Microsoft de beveiligingsmogelijkheid in Azure Information Protection in voor alle Office 365-tenants die een van de volgende abonnementen hebben:

- Office 365-berichtversleuteling wordt aangeboden als onderdeel van Office 365 E3 en E5, Microsoft E3 en E5, Office 365 A1, A3 en A5 en Office 365 G3 en G5. U hebt geen extra licenties nodig om de nieuwe beveiligingsmogelijkheden te ontvangen die worden aangedreven door Azure Information Protection.

- U azure-informatiebeschermingsplan 1 ook toevoegen aan de volgende abonnementen om de nieuwe mogelijkheden voor berichtenversleuteling van Office 365 te ontvangen: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Office 365 Business Essentials, Office 365 Business Premium of Office 365 Enterprise E1.

- Elke gebruiker die profiteert van Office 365-berichtversleuteling moet een licentie hebben om onder de functie te vallen.

- Zie de beschrijvingen van de [Exchange Online-service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) voor Office 365-berichtversleuteling voor de volledige lijst.

Tenantbeheerders kunnen de beveiligingsstatus controleren in de Office 365-beheerdersportal.

![Schermafbeelding waarop wordt weergegeven dat het beheer van rechten in Office 365 is geactiveerd.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>Waarom maken we deze verandering?

Office 365-berichtversleuteling maakt gebruik van de beveiligingsmogelijkheden in Azure Information Protection. In het hart van de recente verbeteringen in Office 365 Message Encryption en onze bredere investeringen in informatiebescherming in Microsoft 365, maken we het voor organisaties gemakkelijker om onze beveiligingsmogelijkheden in te schakelen en te gebruiken, zoals historisch gezien versleuteling technologieën zijn moeilijk op te zetten. Door de beveiligingsfuncties in Azure Information Protection standaard in te schakelen, u snel aan de slag om uw gevoelige gegevens te beschermen.

## <a name="does-this-impact-me"></a>Heeft dit invloed op mij?

Als uw Office 365-organisatie een in aanmerking komende Office 365-licentie heeft aangeschaft, heeft uw tenant gevolgen voor deze wijziging.

 **Belangrijk!** Als u AD RMS (Active Directory Rights Management Services) gebruikt in uw on-premises omgeving, moet u zich onmiddellijk afmelden voor deze wijziging of migreren naar Azure Information Protection voordat we deze wijziging binnen de komende 30 dagen uitrollen. Zie 'Ik gebruik AD RMS, hoe kan ik me afmelden voor informatie over hoe u zich afmeldt?' later in dit artikel. Zie [Migreren van AD RMS naar Azure Information Protection als](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) u liever migreert.

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Kan ik Azure Information Protection gebruiken met AD RMS (Active Directory Rights Management Services)?

Nee. Dit is geen ondersteund implementatiescenario. Zonder de extra opt-outstappen te nemen, kunnen sommige computers automatisch de Azure Rights Management-service gebruiken en ook verbinding maken met uw AD RMS-cluster. Dit scenario wordt niet ondersteund en heeft onbetrouwbare resultaten, dus het is belangrijk dat u zich afziet van deze wijziging binnen de komende 30 dagen voordat we deze nieuwe functies uitrollen. Zie 'Ik gebruik AD RMS, hoe kan ik me afmelden voor informatie over hoe u zich afmeldt?' later in dit artikel. Zie [Migreren van AD RMS naar Azure Information Protection als](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) u liever migreert.

## <a name="how-do-i-know-if-im-using-ad-rms"></a>Hoe weet ik of ik AD RMS gebruik?

Gebruik deze instructies van [De omgeving voorbereiden op Azure Rights Management wanneer u ook AD RMS (Active Directory Rights Management Services) hebt](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) om te controleren of u AD RMS hebt geïmplementeerd:

1. Hoewel optioneel, publiceren de meeste AD RMS-implementaties het serviceverbindingspunt (SCP) naar Active Directory, zodat domeincomputers het AD RMS-cluster kunnen ontdekken.

Adsi-bewerking gebruiken om te zien of u een SCP hebt gepubliceerd in Active Directory: CN=Configuration [servernaam], CN=Services, CN=RightsManagementServices, CN=SCP

2. Als u geen SCP gebruikt, moeten Windows-computers die verbinding maken met een AD RMS-cluster zijn geconfigureerd voor het ontdekken van clientservices of het omleiden van licenties met behulp van het Windows-register: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocatie of HKEY_ LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation

Zie [Detectie van clientservices inschakelen met het Windows-register](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) en [het omleiden van licentieserververkeer](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)voor meer informatie over deze registerconfiguraties.

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Ik gebruik AD RMS, hoe kan ik me afmelden?

Voer de volgende stappen uit om je af te melden voor de komende wijziging:

1. Start een Windows PowerShell-sessie met een werk- of schoolaccount met globale beheerdersmachtigingen in uw Office 365-organisatie en maak verbinding met Exchange Online. Zie Verbinding [maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)voor instructies.

2. Voer de cmdlet Set-IRMConfiguration uit met de volgende syntaxis:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Wat kan ik verwachten nadat deze wijziging is aangebracht?

Zodra dit is ingeschakeld, u, op voorwaarde dat u zich niet hebt afgemeld, de nieuwe versie van Office 365-berichtenversleuteling gebruiken die is aangekondigd op [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) en gebruikmaakt van de versleutelings- en beveiligingsmogelijkheden van Azure Information Protection.

![Schermafbeelding waarop een beveiligd OME-bericht wordt weergegeven in de webversie van Outlook.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

Zie [Office 365-berichtversleuteling](../../compliance/ome.md)voor meer informatie over de nieuwe verbeteringen.
