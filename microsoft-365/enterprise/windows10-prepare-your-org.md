---
title: Uw organisatie voorbereiden op Windows 10 Enterprise
description: Biedt een richtlijnen op hoog niveau voor de stappen die u nodig hebt om Windows 10 Enterprise op pc's te implementeren als onderdeel van Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-documentatie, Windows 10 Enterprise, implementatie
author: JoeDavies-MSFT
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
f1.keywords:
- NOCSH
ms.author: josephd
ms.openlocfilehash: 9b83082a4dc859c10db03608de2edebdbb633cbe
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805470"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>Stap 1: Uw organisatie voorbereiden op Windows 10 Enterprise

*Dit artikel is van toepassing op zowel de E3- als E5-versies van Microsoft 365 Enterprise*

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Houd voor het upgraden van uw apparaten naar Windows 10 Enterprise rekening met het volgende:

- **Uw domeinen moeten worden toegevoegd en geverifieerd** <br>
  Met een Microsoft 365-abonnement krijgt u een standaarddomeinnaam die eindigt in onmicrosoft.com (bijvoorbeeld contoso.onmicrosoft.com). De meeste organisaties geven de voorkeur aan een of meer van de domeinen die ze bezitten, zodat hun e-mailadressen eindigen in hun eigen domeinnaam (zoals username@contoso.com). Als u uw eigen domein wilt gebruiken, moet u het toevoegen aan Microsoft 365 en controleren of u de eigenaar bent. We raden u aan uw domeinen nu toe te voegen en te verifiëren, zodat ze klaar zijn om te gaan wanneer u Microsoft 365-services instelt, zoals e-mail en Skype voor Bedrijven.
- **U hoeft op dit moment geen gebruikers toe te voegen** <br>
  Om Microsoft 365-services te gebruiken of Microsoft 365-producten te installeren, hebben gebruikers accounts in Microsoft 365 nodig en hebben ze productlicenties nodig. Hoe u gebruikers toevoegt aan Microsoft 365, is afhankelijk van het aantal gebruikers en of u momenteel Active Directory on-premises hebt. Als u geen Active Directory hebt (of u Active Directory hebt, maar deze niet wilt synchroniseren met Microsoft 365), u gebruikers rechtstreeks toevoegen aan Microsoft 365 en licenties toewijzen, afzonderlijk of in bulk. <br>
  Als u Active Directory on-premises hebt, u [deze synchroniseren met Microsoft 365](identity-add-user-accounts.md#identity-sync) om gebruikersaccounts te maken in Azure AD, de clouddirectory die wordt gebruikt door Microsoft 365. Met deze methode u accounts maken voor gebruikers en voor beveiligingsgroepen die u gebruikt om machtigingen voor resources te beheren (zoals SharePoint Online-siteverzamelingen of -documenten). Als u uw Active Directory synchroniseert met Microsoft 365, worden geen licenties toegewezen aan de gebruikers.
- **U hoeft op dit moment geen licentie voor gebruikers te hebben** <br>
  Voordat gebruikers Microsoft 365-services kunnen gebruiken of software kunnen installeren vanuit de Microsoft 365-portal, hebben ze productlicenties nodig. Als globale of gebruikersbeheerbeheerder u direct productlicenties toewijzen in Microsoft 365, individueel of in bulk. U ook [groepslicenties](identity-use-group-management.md#identity-group-license) gebruiken om automatisch licenties toe te wijzen wanneer gebruikers aan een bepaalde groep worden toegevoegd. 
- **U installeert Office 365 ProPlus apart** <br>
  Het verkrijgen van een Microsoft 365-licentie installeert Office 365 ProPlus niet automatisch op uw clientcomputers. Zie [Fase 4: Office 365 ProPlus](office365proplus-infrastructure.md) voor meer informatie. 

## <a name="set-windows-diagnostics-data-level"></a>Gegevensniveau van Windows-diagnostische gegevens instellen

Microsoft gebruikt diagnostische gegevens om Windows-apparaten veilig te houden door malwaretrends en andere bedreigingen te identificeren en om ons te helpen de kwaliteit van Windows- en Microsoft-services te verbeteren. U moet ervoor zorgen dat de diagnoseservice is ingeschakeld op een minimumniveau van Basic op alle eindpunten in uw organisatie. *Standaard is deze service ingeschakeld en ingesteld op het niveau Verbeterd.* Het is echter een goede gewoonte om te controleren en ervoor te zorgen dat ze sensorgegevens ontvangen. Als u niveaus instelt via beleid, worden instellingen op apparaatniveau overschreven. 

**Diagnostische gegevensniveaus voor windows 10-besturingssysteem**

U diagnostische gegevensinstellingen van uw besturingssysteem configureren met behulp van de beheerhulpprogramma's die u al gebruikt, zoals groepsbeleid, MDM of Windows Provisioning. U uw instellingen ook handmatig wijzigen met behulp van Register Editor. Als u uw diagnostische gegevensniveaus instelt via een beheerbeleid, worden instellingen voor apparaatniveau overschreven.

Gebruik de juiste waarde in de onderstaande tabel wanneer u het beheerbeleid configureert.

| Niveau | Verzamelde gegevens | Value |
|:--- |:--- |:--- |
| Beveiliging | Alleen beveiligingsgegevens. | 0 |
| Basic | Beveiligingsgegevens en basisgegevens van het systeem en de kwaliteit. | 1 |
| Verbeterde | Beveiligingsgegevens, basissysteem- en kwaliteitsgegevens en verbeterde inzichten en geavanceerde betrouwbaarheidsgegevens. | 2 |
| Volledige | Beveiligingsgegevens, basissysteem- en kwaliteitsgegevens, verbeterde inzichten en geavanceerde betrouwbaarheidsgegevens en volledige diagnostische gegevens. | 3 |

U diagnostische gegevens inschakelen via een van deze methoden:

* **Microsoft Intune** - Als u Van plan bent Om Intune te gebruiken om uw apparaten te beheren, u een configuratiebeleid maken om diagnostische gegevens in te schakelen door het <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SysteemallowTelemetry-systeembeleid</a> te configureren. Zie Instellingen en functies beheren [op uw apparaten met Het Beleid van Microsoft Intune voor](https://aka.ms/intuneconfigpolicies)meer informatie over het instellen van configuratiebeleid.
* **Registereditor** - U de registereditor gebruiken om diagnostische gegevens handmatig in te schakelen op elk apparaat in uw organisatie. U afwisselend een script schrijven om het register te bewerken. Als er al een beheerbeleid bestaat, zoals groepsbeleid of MDM, wordt deze registerinstelling overschreven.
* **Groepsbeleid** : als u niet van plan bent apparaten in te schrijven voor Intune, u een groepsbeleidsobject gebruiken om het diagnostische gegevensniveau van uw organisatie in te stellen.
* **Opdrachtprompt** : u instellen dat gegevens en service van Windows 10-diagnostische gegevens automatisch worden gestart met de opdrachtprompt. Deze methode is het beste als u de service op slechts een paar apparaten test. Als u de service inschakelt om automatisch met deze opdracht te starten, wordt het diagnostische gegevensniveau niet geconfigureerd. Als u geen diagnostisch gegevensniveau hebt geconfigureerd met beheertools, werkt de service met het standaard niveau Verbeterd.

Zie [Diagnostische gegevens van Windows configureren in uw organisatie](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) voor meer informatie over diagnostische gegevens van Windows en hoe u deze inschakelen op basis van de gekozen methode.

Als tussencontrolepunt ziet u de [exitcriteria](windows10-exit-criteria.md#crit-windows10-step1) die overeenkomen met deze stap.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![Stap 2](../media/stepnumbers/Step2.png)| [Windows 10 Enterprise implementeren voor bestaande apparaten als een in-place upgrade](windows10-deploy-inplaceupgrade.md) |






