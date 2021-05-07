---
title: Exchange Online-e-mailversleuteling met AD RMS
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
ms.custom:
- seo-marvel-apr2020
description: Informatie over het configureren Exchange Online IRM om on-premises Active Directory Rights Management Service (AD RMS) te gebruiken om te voldoen aan de vereisten van uw organisatie.
ms.openlocfilehash: d98cf5c762cd4dac0cbad6d25a3cc766d5c5310a
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162684"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>Exchange Online-e-mailversleuteling met AD RMS

Om informatielekken te voorkomen, bevat Exchange Online IRM-functionaliteit (Information Rights Management) die online en offline bescherming biedt voor e-mailberichten en bijlagen. U kunt Exchange Online IRM zo configureren dat de on-premises Active Directory Rights Management Service (AD RMS) wordt gebruikt om aan de vereisten van uw organisatie te voldoen. Dit is niet gebruikelijk. Als u geen vereiste hebt om AD RMS te gebruiken, gebruikt u [Office 365-berichtversleuteling](ome.md) in plaats daarvan. 

IRM-beveiliging kan worden toegepast door gebruikers in Microsoft Outlook of Outlook op het web en kan worden toegepast door beheerders met behulp van transportbeveiligingsregels of Outlook beveiligingsregels. Met IRM kunnen u en uw gebruikers bepalen wie gevoelige gegevens in een e-mailbericht kan openen, doorsturen, afdrukken of kopiëren.
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>Wijzigingen in de manier waarop IRM werkt met Office 365-berichtversleuteling (OME) en Azure Active Directory

Vanaf september 2017, wanneer u de nieuwe Office 365-berichtversleuteling-mogelijkheden voor uw organisatie in stelt, stelt u ook IRM in voor gebruik met Azure Rights Management (Azure RMS). U kunt IRM niet meer afzonderlijk instellen met Azure RMS. In plaats daarvan werken OME en rights management naadloos samen. Zie voor meer informatie over de nieuwe mogelijkheden [Office 365-berichtversleuteling veelgestelde vragen.](./ome-faq.yml) Als u klaar bent om aan de slag te gaan met de nieuwe OME-mogelijkheden binnen uw organisatie, zie Nieuwe Office 365-berichtversleuteling-mogelijkheden instellen die zijn gebaseerd op [Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>Hoe IRM werkt met Exchange Online en Active Directory Rights Management Services

Exchange Online IRM gebruikt on-premises Active Directory Rights Management Services (AD RMS), een informatiebeveiligingstechnologie in Windows Server 2008 en hoger. IRM-beveiliging wordt toegepast op e-mail door een AD RMS-beleidssjabloon voor rechten toe te passen op een e-mailbericht. Rechten zijn gekoppeld aan het bericht zelf, zodat de beveiliging online en offline en binnen en buiten de firewall van uw organisatie plaatsvindt.
  
Gebruikers kunnen een sjabloon toepassen op een e-mailbericht om de machtigingen te bepalen die geadresseerden voor een bericht hebben. Acties, zoals doorsturen, gegevens uit een bericht oppakken, een bericht opslaan of een bericht afdrukken, kunnen worden beheerd door een AD RMS-rechtenbeleid op het bericht toe te passen.
  
U kunt IRM zo configureren dat u een AD RMS-server gebruikt Windows Server 2008 of hoger. U kunt deze AD RMS-server gebruiken om de AD RMS-sjablonen voor rechtenbeleid voor uw cloudorganisatie te beheren. Outlook is ook afhankelijk van de AD RMS-server om gebruikers in staat te stellen IRM-beveiliging toe te passen op berichten die ze verzenden. Zie [IRM configureren voor gebruik van een on-premises AD RMS-server](configure-irm-to-use-an-on-premises-ad-rms-server.md)voor meer informatie. 
  
Nadat deze is ingeschakeld, kan IRM-beveiliging als volgt worden toegepast op berichten:
  
- **Gebruikers kunnen handmatig een sjabloon toepassen met Outlook en Outlook op internet.** Gebruikers kunnen een AD RMS-sjabloon voor rechtenbeleid toepassen op een e-mailbericht door de sjabloon te selecteren in de **lijst Machtigingen** instellen. Wanneer gebruikers een met IRM beveiligd bericht verzenden, ontvangen alle bijgevoegde bestanden die een ondersteunde indeling gebruiken, ook dezelfde IRM-beveiliging als het bericht. IRM-beveiliging wordt toegepast op bestanden die zijn gekoppeld aan Word, Excel en PowerPoint, evenals XPS-bestanden en bijgevoegde e-mailberichten. 
    
- **Beheerders kunnen transportbeveiligingsregels gebruiken om IRM-beveiliging automatisch toe te passen op Outlook en Outlook op internet.** U kunt transportbeveiligingsregels maken voor IRM-beveiligen van berichten. Configureer de actie transportbeveiligingsregel om een AD RMS-sjabloon voor rechtenbeleid toe te passen op berichten die voldoen aan de regelvoorwaarde. Nadat u IRM hebt ingeschakeld, zijn de AD RMS-sjablonen voor het rechtenbeleid van uw organisatie beschikbaar voor gebruik met de actie voor transportbeveiligingsregel Toepassen van rechten op **het bericht met**.
    
- **Beheerders kunnen beveiligingsregels Outlook maken.** Outlook beveiligingsregels worden automatisch IRM-beveiliging toegepast op berichten in Outlook 2010 (niet Outlook op het web) op basis van berichtvoorwaarden die de afdeling van de afzender omvatten, naar wie het bericht wordt verzonden en of geadresseerden zich binnen of buiten uw organisatie hebben. Zie Een [beveiligingsregel Outlook maken voor meer informatie.](/exchange/create-an-outlook-protection-rule-exchange-2013-help)
