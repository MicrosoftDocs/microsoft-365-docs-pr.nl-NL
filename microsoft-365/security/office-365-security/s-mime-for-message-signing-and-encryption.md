---
title: S/MIME voor versleuteling in Exchange Online - Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: Beheerders vinden meer informatie over het gebruik van S/MIME (Secure/Multipurpose Internet Mail Extensions) in Exchange Online om e-mails te versleutelen en digitaal te ondertekenen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 35266b4ceefe161b907ddbc955fd234b716792a6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288571"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME voor het ondertekenen van berichten en versleuteling in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


S/MIME (Secure/Multipurpose Internet Mail Extensions) is een algemeen geaccepteerde methode (of preciezer een protocol) voor het verzenden van digitaal ondertekende en versleutelde berichten. Met S/MIME kunt u e-mails versleutelen en deze digitaal ondertekenen. Wanneer u S/MIME gebruikt met een e-mailbericht, kunnen de personen die dat bericht ontvangen, er zeker van zijn dat wat ze in hun Postvak IN zien, exact het bericht is dat is gestart met de afzender. Het helpt personen die berichten ontvangen ook om er zeker van te zijn dat het bericht afkomstig is van de specifieke afzender en niet van iemand die zich voordoet als de afzender. S/MIME biedt hiervoor cryptografische beveiligingsservices zoals verificatie, berichtintegriteit en niet-weerlegbaarheid van herkomst (met digitale handtekeningen). Daarnaast wordt de privacy en gegevensbeveiliging (via versleuteling) verbeterd voor elektronische berichten. Zie [S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))voor een volledigere achtergrond over de geschiedenis en architectuur van S/MIME in de context van e-mail.

Als Exchange Online-beheerder kunt u beveiliging op basis van S/MIME inschakelen voor de postvakken in uw organisatie. Gebruik de richtlijnen in de hier gekoppelde onderwerpen, samen met Exchange Online PowerShell voor het instellen van S/MIME. Als u S/MIME wilt gebruiken in ondersteunde e-mail clients, moeten voor de gebruikers in uw organisatie certificaten zijn uitgegeven voor ondertekenings- en versleutelingsdoeleinden en gegevens die zijn gepubliceerd naar uw on-premises Active Directory Domain Service (AD DS). Uw AD DS moet zich bevinden op computers op een fysieke locatie die u controleert en niet ergens op internet in een afgelegen gebouw of cloudservice. Zie Overzicht van Active Directory Domain Services voor meer informatie [over AD DS.](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)

## <a name="supported-scenarios-and-technical-considerations"></a>Ondersteunde scenario's en technische overwegingen

U kunt S/MIME instellen voor gebruik met een van de volgende eindpunten:

- Outlook 2010 of hoger
- Webversie van Outlook (voorheen Outlook Web App genoemd)
- Exchange ActiveSync (EAS)

De stappen die u volgt voor het instellen van S/MIME bij elk van deze eindpunten, kunnen enigszins afwijken. Over het algemeen moet u de volgende stappen volgen:

1. Installeer een Windows-certificeringsinstantie (CA) en stel een openbare sleutelinfrastructuur in om S/MIME-certificaten uit te geven. Certificaten die door externe certificaatproviders zijn uitgegeven, worden ook ondersteund. Zie Overzicht van [Active Directory-certificaatservices voor meer informatie.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))

   **Opmerkingen**:

   - Certificaten die zijn uitgegeven door een externe certificeringsinstantie, hebben het voordeel dat ze automatisch worden vertrouwd door alle clients en apparaten. Certificaten die worden uitgegeven door een interne, persoonlijke certificeringsinstantie, worden niet automatisch vertrouwd door clients en apparaten en niet alle apparaten (bijvoorbeeld telefoons) kunnen worden geconfigureerd voor het vertrouwen van persoonlijke certificaten.

   - Overweeg om een tussenliggend certificaat te gebruiken in plaats van het basiscertificaat om certificaten aan gebruikers uit te geven. Op die manier blijft het basiscertificaat intact als u certificaten ooit moet intrekken en opnieuw moet intrekken.

2. Publiceer het gebruikerscertificaat in een on-premises AD DS-account in de **kenmerken UserSMIMECertificate** en/of **UserCertificate.**

3. Synchroniseer voor Exchange Online-organisaties de gebruikerscertificaten vanuit AD DS naar Azure Active Directory met behulp van een geschikte versie van Azure AD Connect. Deze certificaten worden vervolgens vanuit Azure Active Directory gesynchroniseerd met de Exchange Online-adreslijst en worden gebruikt bij het versleutelen van een bericht naar een ontvanger.

4. Een virtuele certificaatverzameling instellen om S/MIME te valideren. Deze gegevens worden door de webversie van Outlook gebruikt bij het valideren van de handtekening van een e-mailbericht en om ervoor te zorgen dat deze is ondertekend door een vertrouwd certificaat.

5. Het Outlook- of EAS-eindpunt instellen voor het gebruik van S/MIME.

> [!NOTE]
> U kunt S/MIME-besturing niet installeren in de webversie van Outlook op Mac- of iOS-, Android- of andere niet-Windows-apparaten. Zie Berichten versleutelen [met S/MIME in de webversie van Outlook voor meer informatie.](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)

## <a name="set-up-smime-with-outlook-on-the-web"></a>S/MIME instellen met de webversie van Outlook

Voor het instellen van S/MIME voor Exchange Online met de webversie van Outlook moet u de volgende belangrijke stappen volgen:

1. [S/MIME-instellingen voor de webversie van Outlook configureren](configure-s-mime-settings-for-outlook-web-app.md)
2. [Verzameling van virtuele certificaten instellen om S/MIME te valideren](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [Gebruikerscertificaten synchroniseren met Office 365 voor S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Verwante berichtversleutelingstechnologieën

Naarmate de berichtbeveiliging belangrijker wordt, moeten beheerders de principes en concepten voor beveiligde berichten begrijpen. Dit inzicht is vooral belangrijk vanwege de groeiende verscheidenheid aan beveiligingstechnologieën (met inbegrip van S/MIME) die beschikbaar zijn. Zie S/MIME voor meer informatie over [S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))en hoe het werkt in de context van e-mail. Verschillende versleutelingstechnologieën werken samen om berichten in rust en in transit te beschermen. S/MIME kan tegelijk met de volgende technologieën werken, maar is daar niet van afhankelijk:

- **Met Transport Layer Security (TLS)** versleutelt u de tunnel of de route tussen e-mailservers om te voorkomen dat uw tunneling wordt verwijderd en wordt overgeslagen.

- **Met Secure Sockets Layer (SSL)** wordt de verbinding tussen e-mail clients en Microsoft 365-servers versleuteld.

- **BitLocker** versleutelt de gegevens op een harde schijf in een datacenter, zodat ze de gegevens niet kunnen lezen als iemand onbevoegde toegang krijgt.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME vergeleken met Office 365-berichtversleuteling

S/MIME vereist een certificaat- en publicatie-infrastructuur die vaak wordt gebruikt in business-to-business- en business-to-consumer-situaties. De gebruiker bepaalt de cryptografische sleutels in S/MIME en kan kiezen of ze ze voor elk bericht dat ze verzenden gebruiken. E-mailprogramma's zoals Outlook zoeken op een vertrouwde locatie van een basiscertificaatinstantie om digitale ondertekening en verificatie van de handtekening uit te voeren. Office 365-berichtversleuteling is een op beleid gebaseerde versleutelingsservice die kan worden geconfigureerd door een beheerder en niet door een individuele gebruiker, om e-mail te versleutelen die wordt verzonden naar iedereen binnen of buiten de organisatie. Het is een onlineservice die is gebouwd op Azure Rights Management (RMS) en die niet afhankelijk is van een openbare sleutelinfrastructuur. Office 365-berichtversleuteling biedt ook extra mogelijkheden, zoals de mogelijkheid om de e-mail aan te passen aan het merk van de organisatie. Zie Versleuteling in Office 365 voor meer informatie over [Office 365-berichtversleuteling.](../../compliance/encryption.md)

## <a name="more-information"></a>Meer informatie

[Webversie van Outlook](https://docs.microsoft.com/exchange/exchange-admin-center)

[Secure Mail (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
