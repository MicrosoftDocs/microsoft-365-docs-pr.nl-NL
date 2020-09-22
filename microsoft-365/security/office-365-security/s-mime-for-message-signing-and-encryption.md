---
title: S/MIME voor versleuteling in Exchange Online-Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: Beheerders kunnen e-mail uitbreidingen (Secure/Multipurpose Internet Mail Extensions) in Exchange Online leren gebruiken voor het versleutelen van e-mailberichten en deze digitaal ondertekenen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8dce3e3fa3d24e1773f51f96e19a58d8a3b2efce
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200605"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME voor de ondertekening van berichten en versleuteling in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


S/MIME (Secure/Multipurpose Internet Mail Extensions) is een uitgebreide geaccepteerde methode (of een specifiek Protocol) voor het verzenden van digitaal ondertekende en versleutelde berichten. Met S/MIME kunt u e-mailberichten versleutelen en digitaal ondertekenen. Wanneer u S/MIME met een e-mailbericht gebruikt, kunnen de personen die het bericht ontvangen, weten dat wat ze in hun postvak in hebben, het exacte bericht is dat met de afzender is begonnen. Daarnaast helpt de persoon die berichten ontvangt om te weten dat het bericht afkomstig is van de specifieke afzender en niet van iemand die de afzender moet zijn. Om dit te doen, bieden S/MIME-beveiliging voor cryptografische beveiligingsservices zoals verificatie, integriteit van berichten en non-afwijzing van oorsprong (met behulp van digitale handtekeningen). Dit helpt ook privacy en gegevensbeveiliging te verbeteren (met versleuteling) voor elektronische berichten. Zie [S/MIME-informatie](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))voor een uitgebreide achtergrondinformatie over de geschiedenis en architectuur van s/mime in de context van e-mail.

Als Exchange Online-beheerder kunt u de beveiliging S/MIME op basis van de postvakken in uw organisatie inschakelen. Volg de richtlijnen in de onderstaande onderwerpen, samen met Exchange Online PowerShell om S/MIME in te stellen. Als u S/MIME in ondersteunde e-mailclients wilt gebruiken, moeten de gebruikers in uw organisatie certificaten hebben die zijn afgegeven voor ondertekening en versleuteling, en gegevens die worden gepubliceerd in uw on-premises Active Directory Domain Services (AD DS). De AD DS moet zich bevinden op een fysieke locatie die u bestuurt, en niet op een externe locatie of op de cloud gebaseerde service van een andere locatie op internet. Zie [overzicht van Active Directory Domain Services](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)voor meer informatie over AD DS.

## <a name="supported-scenarios-and-technical-considerations"></a>Ondersteunde scenario's en technische overwegingen

U kunt S/MIME instellen voor gebruik met een van de volgende eindpunten:

- Outlook 2010 of later
- De webversie van Outlook (voorheen Outlook Web app)
- Exchange ActiveSync (EAS)

De stappen die u volgt om S/MIME in te stellen met elk van deze eindpunten, wijken af enigszins af. In het algemeen dient u de volgende stappen uit te voeren:

1. Een certificeringsinstantie (CA) voor Windows installeren en een openbare sleutelinfrastructuur instellen voor het verlenen van S/MIME-certificaten. Certificaten die worden verstrekt door leveranciers van derden worden ook ondersteund. Zie [overzicht van Active Directory Certificate Services](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))voor meer informatie.

   **Opmerkingen**:

   - Certificaten die zijn uitgegeven door een externe certificeringsinstantie, bieden het voordeel dat ze automatisch worden vertrouwd door alle clients en apparaten. Certificaten die zijn uitgegeven door een interne, persoonlijke certificeringsinstantie, worden niet automatisch vertrouwd door clients en apparaten, en niet alle apparaten (bijvoorbeeld telefoons) kunnen worden geconfigureerd om persoonlijke certificaten te vertrouwen.

   - Overweeg om een tussenliggend certificaat te gebruiken in plaats van het basiscertificaat om certificaten te verlenen aan gebruikers. Op die manier kunt u, als u de certificaten ooit opnieuw moet intrekken en opnieuw uitgeven, de basis certificering blijft behouden.

2. Publiceer het gebruikerscertificaat in een on-premises AD DS-account in de **UserSMIMECertificate** -en **UserCertificate** -kenmerken.

3. Voor Exchange Online-organisaties synchroniseert u de gebruikerscertificaten van AD DS naar Azure Active Directory met een juiste versie van Azure AD Connect. Deze certificaten worden vervolgens gesynchroniseerd vanuit Azure Active Directory naar de map Exchange Online en worden gebruikt wanneer een bericht wordt versleuteld naar een geadresseerde.

4. Stel een virtuele certificaat verzameling in om S/MIME te valideren. Deze informatie wordt door de webversie van Outlook gebruikt bij het valideren van de handtekening van een e-mailbericht en ervoor te zorgen dat deze door een vertrouwd certificaat is ondertekend.

5. Het eindpunt van Outlook of EA'S instellen voor gebruik van S/MIME.

> [!NOTE]
> U kunt S/MIME-besturing niet installeren in de webversie van Outlook op een Mac-, iOS-, Android-of ander niet-Windows-apparaat. Zie [berichten versleutelen met S/MIME in de webversie van Outlook](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)voor meer informatie.

## <a name="setup-smime-with-outlook-on-the-web"></a>S/MIME instellen met de webversie van Outlook

Het instellen van S/MIME voor Exchange Online met de webversie van Outlook omvat de volgende belangrijke stappen:

1. [S/MIME-instellingen voor de webversie van Outlook configureren](configure-s-mime-settings-for-outlook-web-app.md)
2. [Verzameling van virtuele certificaten instellen om S/MIME te valideren](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [Gebruikerscertificaten synchroniseren met Office 365 voor S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Technologieën voor gerelateerde berichten versleutelen

Aangezien de beveiliging van een bericht belangrijker wordt, moeten beheerders de principes en concepten van beveiligde berichten begrijpen. Dit is met name belangrijk vanwege de groeiende uiteenlopende technologieën van de bescherming en de beschikbaarheid van technologieën (waaronder S/MIME). Als u meer wilt weten over S/MIME en de werking van de e-mail, raadpleegt u [S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)). Tal van versleutelings technologieën werken samen voor een betere bescherming tegen de rest en in de transit. S/MIME kan tegelijk met de volgende technologieën werken, maar is niet afhankelijk van de technologieën:

- **TLS (Transport Layer Security)** versleutelt de tunnel of route tussen e-mailservers om te voorkomen dat u kunt luisteren en luisteren.

- **Secure Sockets Layer (SSL)** versleutelt de verbinding tussen e-mailclients en microsoft 365-servers.

- **BitLocker** versleutelt de gegevens op een harde schijf in een datacenter, zodat de persoon deze niet kan lezen als iemand onbevoegd toegang krijgt.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME vergeleken met Office 365-bericht versleuteling

S/MIME vereist een certificaat-en publicatie-infrastructuur die vaak wordt gebruikt in Business-to-Business en zaken-naar-consument. De gebruiker beheert de cryptografiesleutels in S/MIME en kan kiezen of ze ze gebruiken voor elk bericht dat ze verzenden. E-mailprogramma's, zoals Outlook, zoeken naar een vertrouwde basiscertificeringsinstantie van een certificeringsinstantie om digitale ondertekening en verificatie van de handtekening uit te voeren. Office 365-bericht versleuteling is een beleidstoepassing die kan worden geconfigureerd door een beheerder, en geen afzonderlijke gebruiker, om e-mail te versleutelen die naar iedereen binnen of buiten de organisatie is verzonden. Het is een online dienst die is gebaseerd op Azure Rights Management (RMS) en die niet is gebaseerd op de infrastructuur van openbare sleutel. Office 365-bericht versleuteling biedt ook extra mogelijkheden, zoals de mogelijkheid om het e-mailadres aan te passen met het merk van uw organisatie. Zie voor meer informatie over het versleutelen van Office 365-berichten [versleutelen in Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption).

## <a name="more-information"></a>Meer informatie

[De webversie van Outlook](https://docs.microsoft.com/exchange/exchange-admin-center)

[E-mail beveiligen (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
