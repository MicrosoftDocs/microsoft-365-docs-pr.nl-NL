---
title: Vereisten voor Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Voor MSP's (Managed Service Providers) krijgt u een lijst met vereisten voor het gebruik van Microsoft 365 Lighthouse.
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395186"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>Vereisten voor Microsoft 365 Lighthouse

> [!NOTE]
> De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn alleen beschikbaar voor partners die voldoen aan de vereisten in dit artikel. Als uw organisatie geen Microsoft 365 Lighthouse, zie [Registreren voor Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse is een beheerportal waarmee beheerde serviceproviders (MSP's) apparaten, gegevens en gebruikers op grote schaal kunnen beveiligen en beheren voor klanten van kleine en middelgrote bedrijven (SMB).  

MSP's moeten zijn geregistreerd in het Cloud Solution Provider (CSP)-programma als indirecte wederverkoper of direct bill-partner om de Microsoft 365 Lighthouse.  

Bovendien moet elke MSP-klant tenant in aanmerking komen voor Microsoft 365 Lighthouse voldoen aan de volgende vereisten: 
 
- Gedelegeerde beheerdersbevoegdheden (DAP) voor de MSP 
- Ten minste één Microsoft 365 Business Premium licentie 
- Minder dan 500 gebruikers met een licentie  

## <a name="requirements-for-enablingdevice-management"></a>Vereisten voor het inschakelen van apparaatbeheer   

Als u tenantapparaten van klanten wilt weergeven op de pagina's voor apparaatbeheer, moet een MSP:    

- Schrijf alle klantapparaten in Microsoft Endpoint Manager (MEM).Zie Apparaten registreren [in Microsoft Intune.](/mem/intune/enrollment/)
- Wijs compliancebeleid toe aan alle apparaten van klanten.Zie Een compliancebeleid maken [in](/mem/intune/protect/create-compliance-policy)Microsoft Intune. 

## <a name="requirements-for-enabling-usermanagement"></a>Vereisten voor het inschakelen van gebruikersbeheer 

Als klantgegevens worden weergegeven in rapporten op gebruikersbeheerpagina's, waaronder Risicovolle gebruikers, Meervoudige verificatie en Wachtwoord opnieuw instellen, moeten klantten over licenties voor Azure Active Directory Premium P1 of hoger hebben. Azure AD Premium P1 is inbegrepen bij Microsoft 365 Business Premium.   

## <a name="requirements-for-enablingthreat-management"></a>Vereisten voor het inschakelen van bedreigingsbeheer 

Als u tenantapparaten en bedreigingen van klanten wilt weergeven op de pagina's voor bedreigingsbeheer, moet u alle tenantapparaten van klanten registreren in Microsoft Endpoint Manager (MEM) en deze beveiligen door Microsoft Defender Antivirus.  

Zie Apparaten registreren [in Microsoft Intune.](/mem/intune/enrollment/)  

Microsoft Defender Antivirus maakt deel uit van het Windows besturingssysteem en is standaard ingeschakeld op apparaten met Windows 10.  

> [!NOTE] 
> Als u een niet-Microsoft-antivirusoplossing gebruikt en niet Microsoft Defender Antivirus, Microsoft Defender Antivirus automatisch uitgeschakeld. Wanneer u de antivirusoplossing van niet-Microsoft verwijdert, Microsoft Defender Antivirus automatisch geactiveerd om uw apparaten Windows te beschermen tegen bedreigingen.    

## <a name="related-content"></a>Verwante inhoud   

[Beveiliging Microsoft 365 Lighthouse portal configureren](m365-lighthouse-configure-portal-security.md) (artikel)\
[Microsoft 365 Lighthouse pagina overzicht van apparaat compliance](m365-lighthouse-device-compliance-page-overview.md) (artikel)\
[Microsoft 365 Lighthouse Paginaoverzicht gebruikers](m365-lighthouse-users-page-overview.md) (artikel)\
[Microsoft 365 Lighthouse overzicht van de pagina Bedreigingsbeheer](m365-lighthouse-threat-management-page-overview.md) (artikel)\
[Microsoft 365 Lighthouse veelgestelde vragen](m365-lighthouse-faq.yml)   (artikel)

