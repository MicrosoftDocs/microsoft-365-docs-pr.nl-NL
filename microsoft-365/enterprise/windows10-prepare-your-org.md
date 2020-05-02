---
title: Uw organisatie voorbereiden op Windows 10 Enterprise
description: Biedt een advies op hoog niveau over de stappen die u nodig hebt om Windows 10 Enterprise op pc's te implementeren als onderdeel van Microsoft 365 Enterprise.
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
ms.openlocfilehash: 43793a1780542b1825c693030dd9d4dbff4ee3d7
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002341"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>Stap 1: Uw organisatie voorbereiden op Windows 10 Enterprise

*Dit artikel is van toepassing op zowel de E3- als de E5-versies van Microsoft 365 Enterprise*

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Voordat u uw apparaten upgradet naar Windows 10 Enterprise, moet u rekening houden met het volgende:

- **Uw domeinen moeten worden toegevoegd en geverifieerd** <br>
  Met een Microsoft 365-abonnement krijgt u een standaarddomeinnaam die eindigt op onmicrosoft.com (bijvoorbeeld contoso.onmicrosoft.com). De meeste organisaties geven de voorkeur aan een of meer van de domeinen die ze bezitten te gebruiken, zodat hun e-mailadressen eindigen in hun eigen domeinnaam (zoals username@contoso.com). Als u uw eigen domein wilt gebruiken, moet u het toevoegen aan Microsoft 365 en controleren of u de eigenaar bent. We raden u aan uw domeinen nu toe te voegen en te verifiëren, zodat ze klaar zijn voor gebruik wanneer u Microsoft 365-services instelt, zoals e-mail en Skype voor Bedrijven.
- **U hoeft op dit moment geen gebruikers toe te voegen** <br>
  Om Microsoft 365-services te gebruiken of Microsoft 365-producten te installeren, hebben gebruikers accounts in Microsoft 365 nodig en hebben ze productlicenties nodig. Hoe u gebruikers toevoegt aan Microsoft 365, is afhankelijk van het aantal gebruikers en of u momenteel Active Directory on-premises hebt. Als u geen Active Directory hebt (of als u Active Directory hebt maar deze niet wilt synchroniseren met Microsoft 365), u gebruikers rechtstreeks aan Microsoft 365 toevoegen en licenties toewijzen, afzonderlijk of in bulk. <br>
  Als u Active Directory on-premises hebt, u [deze synchroniseren met Microsoft 365](identity-add-user-accounts.md#identity-sync) om gebruikersaccounts te maken in Azure AD, de cloudmap die wordt gebruikt door Microsoft 365. Met deze methode u accounts maken voor gebruikers en voor beveiligingsgroepen die u gebruikt om machtigingen voor bronnen (zoals SharePoint Online-siteverzamelingen of -documenten) te beheren. Als u uw Active Directory synchroniseert met Microsoft 365, worden geen licenties toegewezen aan de gebruikers.
- **U hoeft op dit moment geen licentiegebruikers te geven** <br>
  Voordat gebruikers Microsoft 365-services kunnen gebruiken of software van de Microsoft 365-portal kunnen installeren, hebben ze productlicenties nodig. Als globale of gebruikersbeheerbeheerder u productenlicenties in Microsoft 365 rechtstreeks individueel of in bulk toewijzen. U ook [groepslicenties](identity-use-group-management.md#identity-group-license) gebruiken om automatisch licenties toe te wijzen wanneer gebruikers aan een bepaalde groep worden toegevoegd. 
- **U installeert Microsoft 365 Apps voor bedrijven afzonderlijk** <br>
  Het verkrijgen van een Microsoft 365-licentie installeert microsoft 365 Apps voor bedrijven niet automatisch op uw clientcomputers. Zie [Fase 4: Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md) voor meer informatie. 

## <a name="set-windows-diagnostics-data-level"></a>Gegevensniveau voor Diagnostische gegevens van Windows instellen

Microsoft gebruikt diagnostische gegevens om Windows-apparaten veilig te houden door malwaretrends en andere bedreigingen te identificeren en om ons te helpen de kwaliteit van Windows- en Microsoft-services te verbeteren. U moet ervoor zorgen dat de diagnostische service is ingeschakeld op een minimumniveau van Basic op alle eindpunten in uw organisatie. *Standaard is deze service ingeschakeld en ingesteld op het niveau Verbeterd.* Het is echter een goede gewoonte om te controleren en ervoor te zorgen dat ze sensorgegevens ontvangen. Als u niveaus instelt via het beleid, worden instellingen op apparaatniveau overschreven. 

**Diagnostische gegevensniveaus van windows 10-besturingssysteem**

U diagnostische gegevensinstellingen van uw besturingssysteem configureren met behulp van de beheerhulpprogramma's die u al gebruikt, zoals Groepsbeleid, MDM of Windows Provisioning. U uw instellingen ook handmatig wijzigen met behulp van registereditor. Als u uw diagnostische gegevensniveaus instelt via een beheerbeleid, worden alle instellingen op apparaatniveau overschreven.

Gebruik de juiste waarde in de onderstaande tabel wanneer u het beheerbeleid configureert.

| Niveau | Verzamelde gegevens | Value |
|:--- |:--- |:--- |
| Beveiliging | Alleen beveiligingsgegevens. | 0 |
| Basic | Beveiligingsgegevens en basissysteem- en kwaliteitsgegevens. | 1 |
| Verbeterde | Beveiligingsgegevens, basissysteem- en kwaliteitsgegevens en verbeterde inzichten en geavanceerde betrouwbaarheidsgegevens. | 2 |
| Volledige | Beveiligingsgegevens, basissysteem- en kwaliteitsgegevens, verbeterde inzichten en geavanceerde betrouwbaarheidsgegevens en volledige diagnostische gegevens. | 3 |

U diagnostische gegevens inschakelen via een van deze methoden:

* **Microsoft Intune** - Als u van plan bent Intune te gebruiken om uw apparaten te beheren, u een configuratiebeleid maken om diagnostische gegevens in te schakelen door het systeembeleid <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">van SystemAllowTelemetry</a> te configureren.
* **Registereditor** - U de registereditor gebruiken om diagnostische gegevens handmatig in te schakelen op elk apparaat in uw organisatie. U afwisselend een script schrijven om het register te bewerken. Als er al een beheerbeleid bestaat, zoals Groepsbeleid of MDM, wordt deze registerinstelling overschreven.
* **Groepsbeleid** : als u niet van plan bent apparaten in te schrijven in Intune, u een groepsbeleidsobject gebruiken om het diagnostische gegevensniveau van uw organisatie in te stellen.
* **Opdrachtprompt** : u diagnostische gegevens en service van Windows 10 automatisch starten met de opdrachtprompt. Deze methode is het beste als u de service op slechts een paar apparaten test. Als u de service automatisch inschakelt met deze opdracht, wordt het diagnostische gegevensniveau niet geconfigureerd. Als u geen diagnostisch gegevensniveau hebt geconfigureerd met beheerhulpprogramma's, werkt de service met het standaardniveau Verbeterd niveau.

Zie [Diagnostische gegevens van Windows configureren in uw organisatie](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) voor meer informatie over diagnostische gegevens van Windows en hoe u deze inschakelen op basis van de methode die u kiest.

Als tussentijds controlepunt kunt u de [afsluitcriteria](windows10-exit-criteria.md#crit-windows10-step1) voor deze stap bekijken.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![Stap 2](../media/stepnumbers/Step2.png)| [Windows 10 Enterprise implementeren voor bestaande apparaten als een upgrade op zijn plaats](windows10-deploy-inplaceupgrade.md) |






