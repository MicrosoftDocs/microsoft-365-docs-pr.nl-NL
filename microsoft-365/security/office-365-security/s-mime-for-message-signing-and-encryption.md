---
title: S/MIME voor versleuteling in Exchange Online - Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: Beheerders kunnen meer te weten komen over het gebruik van S/MIME (Secure/Multipurpose Internet Mail Extensions) in Exchange Online om e-mails te versleutelen en digitaal te ondertekenen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95bbab5161f9e4133223a247f8937c68f29c0590
ms.sourcegitcommit: 7a59d83a8660c2344ebdb92e0ea0171c9c2d9498
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44811012"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME voor het ondertekenen van berichten en versleuteling in Exchange Online

S/MIME (Secure/Multipurpose Internet Mail Extensions) is een algemeen aanvaarde methode (of beter gezegd, een protocol) voor het verzenden van digitaal ondertekende en versleutelde berichten. Met S/MIME u e-mails versleutelen en digitaal ondertekenen. Wanneer u S/MIME met een e-mailbericht gebruikt, helpt dit de mensen die dat bericht ontvangen er zeker van te zijn dat wat ze in hun postvak IN zien het exacte bericht is dat is begonnen met de afzender. Het zal ook helpen mensen die berichten ontvangen om er zeker van te zijn dat het bericht afkomstig is van de specifieke afzender en niet van iemand die zich voordoet als de afzender. Hiervoor biedt S/MIME cryptografische beveiligingsservices zoals authenticatie, berichtintegriteit en niet-verwerping van oorsprong (met behulp van digitale handtekeningen). Het helpt ook de privacy- en gegevensbeveiliging (met behulp van encryptie) voor elektronische berichten te verbeteren. Zie [Inzicht in S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))voor een meer volledige achtergrond over de geschiedenis en architectuur van S/MIME in de context van e-mail.

Als Exchange Online-beheerder u s/MIME-gebaseerde beveiliging inschakelen voor de postvakken in uw organisatie. Gebruik de richtlijnen in de onderwerpen die hier zijn gekoppeld samen met Exchange Online PowerShell om S/MIME in te stellen. Als u S/MIME wilt gebruiken in ondersteunde e-mailclients, moeten de gebruikers in uw organisatie certificaten hebben uitgegeven voor ondertekenings- en versleutelingsdoeleinden en gegevens die zijn gepubliceerd op uw on-premises Active Directory Domain Service (AD DS). Uw AD DS moet zich bevinden op computers op een fysieke locatie die u bestuurt en niet op een externe faciliteit of cloudservice ergens op het internet. Zie Overzicht van [Active Directory Domain Services](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)voor meer informatie over AD DS.

## <a name="supported-scenarios-and-technical-considerations"></a>Ondersteunde scenario's en technische overwegingen

U S/MIME instellen om met een van de volgende eindpunten te werken:

- Outlook 2010 of hoger

- Outlook op de web (voorheen bekend als Outlook Web App)

- Exchange ActiveSync (EAS)

De stappen die u volgt om S/MIME in te stellen met elk van deze eindpunten zijn iets anders. Over het algemeen moet u de volgende stappen uitvoeren:

1. Installeer een op Windows gebaseerde certificeringsinstantie en stel een openbare sleutelinfrastructuur in om S/MIME-certificaten uit te geven. Certificaten die zijn uitgegeven door externe certificaatproviders worden ook ondersteund. Zie Overzicht van [Active Directory Certificate Services](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))voor meer informatie.

2. Publiceer het gebruikerscertificaat in een on-premises AD DS-account in de kenmerken **UserSMIMECertificate** en/of **UserCertificate.**

3. Synchroniseer voor Exchange Online-organisaties de gebruikerscertificaten van AD DS naar Azure Active Directory met behulp van een geschikte versie van Azure AD Connect. Deze certificaten worden vervolgens gesynchroniseerd van Azure Active Directory naar Exchange Online-map en worden gebruikt bij het versleutelen van een bericht naar een ontvanger.

4. Stel een virtuele certificaatverzameling in om S/MIME te valideren. Deze informatie wordt gebruikt door de webversie van Outlook bij het valideren van de handtekening van een e-mail en ervoor te zorgen dat deze is ondertekend door een vertrouwd certificaat.

5. Stel het eindpunt van Outlook of EAS in om S/MIME te gebruiken.

> [!NOTE]
> U S/MIME-besturingselementen niet installeren in het web van Outlook op Mac, iOS, Android of andere niet-Windows-apparaten. Zie [Berichten versleutelen met S/MIME in de webversie van Outlook voor](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)meer informatie.

## <a name="setup-smime-with-outlook-on-the-web"></a>S/MIME instellen met de webversie van Outlook

Het instellen van S/MIME voor Exchange Online met de webversie van Outlook omvat de volgende belangrijke stappen:

1. [S/MIME-instellingen voor de webversie van Outlook configureren](configure-s-mime-settings-for-outlook-web-app.md)

2. [Verzameling van virtuele certificaten instellen om S/MIME te valideren](set-up-virtual-certificate-collection-to-validate-s-mime.md)

3. [Gebruikerscertificaten synchroniseren met Office 365 voor S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Gerelateerde technologie voor het versleutelen van berichten

Naarmate berichtbeveiliging belangrijker wordt, moeten beheerders de principes en concepten van veilige berichten begrijpen. Dit inzicht is vooral belangrijk vanwege de groeiende verscheidenheid aan beschermingsgerelateerde technologieën (waaronder S/MIME) die beschikbaar zijn. Zie Inzicht in [S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))voor meer informatie over S/MIME en hoe deze werkt in de context van e-mail. Een verscheidenheid aan versleutelingstechnologieën werkt samen om bescherming te bieden voor berichten in rust en onderweg. S/MIME kan gelijktijdig werken met de volgende technologieën, maar is er niet van afhankelijk:

- **Transport Layer Security (TLS)** versleutelt de tunnel of de route tussen e-mailservers om pottenkijkers en afluisteren te voorkomen.

- **Secure Sockets Layer (SSL)** versleutelt de verbinding tussen e-mailclients en Microsoft 365-servers.

- **BitLocker** versleutelt de gegevens op een harde schijf in een datacenter, zodat als iemand ongeautoriseerde toegang krijgt, deze niet kan worden gelezen.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME vergeleken met Office 365-berichtversleuteling

S/MIME vereist een certificaat- en publicatie-infrastructuur die vaak wordt gebruikt in business-to-business- en business-to-consumer-situaties. De gebruiker beheert de cryptografische sleutels in S/MIME en kan kiezen of deze worden gebruikt voor elk bericht dat ze verzenden. E-mailprogramma's zoals Outlook zoeken op een vertrouwde locatie van de rootcertificaatautoriteit om de handtekening digitaal te ondertekenen en te verifiëren. Office 365 Message Encryption is een beleidsgebaseerde versleutelingsservice die kan worden geconfigureerd door een beheerder en niet door een individuele gebruiker, om e-mail te versleutelen die naar iemand binnen of buiten de organisatie wordt verzonden. Het is een online service die is gebouwd op Azure Rights Management (RMS) en niet afhankelijk is van een infrastructuur met openbare sleutels. Office 365 Message Encryption biedt ook extra mogelijkheden, zoals de mogelijkheid om de e-mail aan te passen aan het merk van de organisatie. Zie [Versleuteling in Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption)voor meer informatie over Office 365-berichtversleuteling.

## <a name="more-information"></a>Meer informatie

[Webversie van Outlook](https://docs.microsoft.com/exchange/exchange-admin-center)

[Beveiligde e-mail (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
