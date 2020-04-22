---
title: S/MIME voor het ondertekenen en versleutelen van berichten in Exchange Online
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
description: Beheerders kunnen meer informatie krijgen over het gebruik van S/MIME in Exchange Online.
ms.openlocfilehash: 294fd22ff81e9ddaabf0664afb34a37c008a6d09
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634326"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME voor het ondertekenen en versleutelen van berichten in Exchange Online

S/MIME (Secure/Multipurpose Internet Mail Extensions) is een algemeen aanvaarde methode (of beter gezegd, een protocol) voor het verzenden van digitaal ondertekende en versleutelde berichten. Met S/MIME u e-mails versleutelen en digitaal ondertekenen. Wanneer u S/MIME gebruikt met een e-mailbericht, helpt het de mensen die dat bericht ontvangen om er zeker van te zijn dat wat ze in hun inbox zien, het exacte bericht is dat met de afzender is gestart. Het zal ook mensen helpen die berichten ontvangen om er zeker van te zijn dat het bericht afkomstig is van de specifieke afzender en niet van iemand die zich voordoet als afzender. Om dit te doen, voorziet S/MIME in cryptografische beveiligingsservices zoals authenticatie, berichtintegriteit en niet-verwerping van oorsprong (met behulp van digitale handtekeningen). Het helpt ook bij het verbeteren van de privacy en de gegevensbeveiliging (met behulp van encryptie) voor elektronische messaging. Zie [Begrijpen s/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))voor een meer complete achtergrond over de geschiedenis en architectuur van S/MIME in de context van e-mail.

Als Exchange Online-beheerder u s/mime-gebaseerde beveiliging inschakelen voor de postvakken in uw organisatie. Gebruik de richtlijnen in de onderwerpen die hier zijn gekoppeld, samen met Exchange Online PowerShell om S/MIME in te stellen. Als u S/MIME wilt gebruiken in ondersteunde e-mailclients, moeten de gebruikers in uw organisatie certificaten hebben uitgegeven voor ondertekenings- en versleutelingsdoeleinden en gegevens die worden gepubliceerd naar uw on-premises Active Directory Domain Service (AD DS). Uw AD DS moet zich bevinden op computers op een fysieke locatie die u beheert en niet op een externe faciliteit of cloudservice ergens op het internet. Zie Overzicht van [Active Directory Domain Services](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)voor meer informatie over AD DS.

## <a name="supported-scenarios-and-technical-considerations"></a>Ondersteunde scenario's en technische overwegingen

U S/MIME instellen om met een van de volgende eindpunten te werken:

- Outlook 2010 of hoger

- Webversie van Outlook (voorheen bekend als Outlook Web App)

- Exchange ActiveSync (EAS)

De stappen die u volgt om S/MIME in te stellen met elk van deze eindpunten zijn iets anders. Over het algemeen moet u de volgende stappen uitvoeren:

1. Installeer een in Windows gevestigde certificeringsinstantie en stel een openbare sleutelinfrastructuur in om S/MIME-certificaten uit te geven. Certificaten die worden uitgegeven door externe certificaataanbieders worden ook ondersteund. Zie Overzicht [van Active Directory Certificate Services](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))voor meer informatie.

2. Publiceer het gebruikerscertificaat in een on-premises AD DS-account in de gebruikerskenmerken **Van MIMECertificaat** en/of **UserCertificate.**

3. Voor Exchange Online-organisaties synchroniseert u de gebruikerscertificaten van AD DS naar Azure Active Directory met behulp van een geschikte versie van Azure AD Connect. Deze certificaten worden vervolgens gesynchroniseerd van Azure Active Directory naar Exchange Online-map en worden gebruikt bij het versleutelen van een bericht naar een ontvanger.

4. Stel een virtuele certificaatverzameling in om S/MIME te valideren. Deze informatie wordt door De Web van Outlook gebruikt wanneer het valideren van de handtekening van een e-mail en ervoor te zorgen dat het door een vertrouwd certificaat werd ondertekend.

5. Stel het Outlook- of EAS-eindpunt in om S/MIME te gebruiken.

> [!NOTE]
> U s/mime-besturingselement niet installeren in Outlook op de web op Mac, iOS, Android of andere niet-Windows-apparaten. Zie [Berichten versleutelen met S/MIME in de webversie van Outlook voor](https://support.office.com/article/878c79fc-7088-4b39-966f-14512658f480)meer informatie.

## <a name="setup-smime-with-outlook-on-the-web"></a>S/MIME instellen met de webversie van Outlook

Het instellen van S/MIME voor Exchange Online met de webversie van Outlook omvat de volgende belangrijke stappen:

1. [S/MIME-instellingen voor de webversie van Outlook configureren](configure-s-mime-settings-for-outlook-web-app.md)

2. [Verzameling van virtuele certificaten instellen om S/MIME te valideren](set-up-virtual-certificate-collection-to-validate-s-mime.md)

3. [Gebruikerscertificaten synchroniseren met Office 365 voor S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Gerelateerde versleutelingstechnologieën voor berichten

Naarmate de beveiliging van berichten belangrijker wordt, moeten beheerders de principes en concepten van veilige berichten begrijpen. Dit inzicht is vooral belangrijk vanwege de groeiende verscheidenheid aan beschermingsgerelateerde technologieën (waaronder S/MIME) die beschikbaar zijn. Zie [Begrijpen s/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))voor meer informatie over S/MIME en hoe het werkt in de context van e-mail. Een verscheidenheid aan versleutelingstechnologieën werkt samen om berichten in rust en onderweg te beschermen. S/MIME kan gelijktijdig met de volgende technologieën werken, maar is er niet van afhankelijk:

- **Transport Layer Security (TLS)** versleutelt de tunnel of de route tussen e-mailservers om pottenkijkers en afluisteren te voorkomen.

- **Secure Sockets Layer (SSL)** versleutelt de verbinding tussen e-mailclients en Microsoft 365-servers.

- **BitLocker** versleutelt de gegevens op een harde schijf in een datacenter, zodat als iemand ongeautoriseerde toegang krijgt, deze niet kan lezen.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME vergeleken met Office 365-berichtversleuteling

S/MIME vereist een certificaat- en publicatie-infrastructuur die vaak wordt gebruikt in business-to-business- en business-to-consumer situaties. De gebruiker beheert de cryptografische sleutels in S/MIME en kan kiezen of hij ze wil gebruiken voor elk bericht dat ze verzenden. E-mailprogramma's zoals Outlook zoeken in een locatie van de vertrouwde basiscertificaatinstantie om digitale ondertekening en verificatie van de handtekening uit te voeren. Office 365-berichtversleuteling is een op beleid gebaseerde versleutelingsservice die kan worden geconfigureerd door een beheerder en niet door een individuele gebruiker, om e-mail te versleutelen die naar iedereen binnen of buiten de organisatie wordt verzonden. Het is een online service die is gebouwd op Azure Rights Management (RMS) en niet afhankelijk is van een openbare sleutelinfrastructuur. Office 365-berichtversleuteling biedt ook extra mogelijkheden, zoals de mogelijkheid om de e-mail aan te passen aan het merk van de organisatie. Zie [Versleuteling in Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption)voor meer informatie over Office 365-berichtversleuteling.

## <a name="more-information"></a>Meer informatie

[De webversie van Outlook](https://docs.microsoft.com/exchange/exchange-admin-center)

[Secure Mail (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
