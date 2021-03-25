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
description: Beheerders kunnen informatie krijgen over het gebruik van S/MIME (Secure/Multipurpose Internet Mail Extensions) in Exchange Online om e-mailberichten te versleutelen en digitaal te ondertekenen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d189bf7f52dd6f9fb11dc360c17d5fe15729c9fa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204316"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME voor het ondertekenen en versleutelen van berichten in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


S/MIME (Secure/Multipurpose Internet Mail Extensions) is een veelgebruikte methode (of preciezer, een protocol) voor het verzenden van digitaal ondertekende en versleutelde berichten. Met S/MIME kunt u e-mailberichten versleutelen en digitaal ondertekenen. Wanneer u S/MIME gebruikt met een e-mailbericht, kunnen de personen die dat bericht ontvangen er zeker van zijn dat wat ze in hun Postvak IN zien het exacte bericht is dat is begonnen met de afzender. Het helpt ook mensen die berichten ontvangen om er zeker van te zijn dat het bericht afkomstig is van de specifieke afzender en niet van iemand die zich voordoet als de afzender. Hiervoor biedt S/MIME cryptografische beveiligingsservices, zoals verificatie, berichtintegriteit en niet-afwijzing van origin (met behulp van digitale handtekeningen). Het helpt ook de privacy en gegevensbeveiliging te verbeteren (met behulp van versleuteling) voor elektronische berichten. Zie [S/MIME](/previous-versions/tn-archive/aa995740(v=exchg.65))begrijpen voor een meer volledige achtergrond over de geschiedenis en architectuur van S/MIME in de context van e-mail.

Als Exchange Online-beheerder kunt u beveiliging op basis van S/MIME inschakelen voor de postvakken in uw organisatie. Gebruik de richtlijnen in de onderwerpen die hier zijn gekoppeld, samen met Exchange Online PowerShell om S/MIME in te stellen. Als u S/MIME wilt gebruiken in ondersteunde e-mail clients, moeten de gebruikers in uw organisatie certificaten hebben uitgegeven voor ondertekenings- en versleutelingsdoeleinden en gegevens die zijn gepubliceerd naar uw on-premises Active Directory Domain Service (AD DS). Uw AD DS moet zich bevinden op computers op een fysieke locatie die u bestuurt en niet op een externe faciliteit of cloudservice ergens op internet. Zie Overzicht van [Active Directory Domain Services](/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)voor meer informatie over AD DS.

## <a name="supported-scenarios-and-technical-considerations"></a>Ondersteunde scenario's en technische overwegingen

U kunt S/MIME instellen voor gebruik met een van de volgende eindpunten:

- Outlook 2010 of hoger
- De webversie van Outlook (voorheen Bekend als Outlook Web App)
- Exchange ActiveSync (EAS)

De stappen die u volgt om S/MIME in te stellen bij elk van deze eindpunten, verschillen enigszins. Over het algemeen moet u de volgende stappen doen:

1. Installeer een windows-certificeringsinstantie (CA) en stel een openbare sleutelinfrastructuur in om S/MIME-certificaten uit te geven. Certificaten die zijn uitgegeven door externe certificaatproviders, worden ook ondersteund. Zie Overzicht [van Active Directory Certificate Services voor meer informatie.](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))

   **Opmerkingen**:

   - Certificaten die zijn uitgegeven door een externe certificeringsinstantie, hebben het voordeel dat ze automatisch worden vertrouwd door alle clients en apparaten. Certificaten die worden uitgegeven door een interne, persoonlijke certificeringsinstantie, worden niet automatisch vertrouwd door clients en apparaten en niet alle apparaten (bijvoorbeeld telefoons) kunnen worden geconfigureerd voor het vertrouwen van persoonlijke certificaten.

   - Overweeg een tussenliggend certificaat te gebruiken in plaats van het hoofdcertificaat om certificaten uit te geven aan gebruikers. Als u op die manier certificaten wilt intrekken en opnieuw moet uitgeven, is het hoofdcertificaat nog steeds intact.

2. Publiceer het gebruikerscertificaat in een on-premises AD DS-account in de **userSMIMECertificate-** en/of **UserCertificate-kenmerken.**

3. Synchroniseer voor Exchange Online-organisaties de gebruikerscertificaten van AD DS naar Azure Active Directory met behulp van een geschikte versie van Azure AD Connect. Deze certificaten worden vervolgens gesynchroniseerd vanuit Azure Active Directory naar Exchange Online-adreslijst en worden gebruikt bij het versleutelen van een bericht naar een geadresseerde.

4. Een virtuele certificaatverzameling instellen om S/MIME te valideren. Deze gegevens worden gebruikt door de webversie van Outlook bij het valideren van de handtekening van een e-mailbericht en het garanderen dat deze is ondertekend door een vertrouwd certificaat.

5. Stel het eindpunt van Outlook of EAS in om S/MIME te gebruiken.

> [!NOTE]
> U kunt S/MIME-besturingselement niet installeren in de webversie van Outlook op Mac, iOS, Android of andere niet-Windows-apparaten. Zie Berichten [versleutelen met S/MIME in de webversie van Outlook](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)voor meer informatie.

## <a name="set-up-smime-with-outlook-on-the-web"></a>S/MIME instellen met de webversie van Outlook

Voor het instellen van S/MIME voor Exchange Online met de webversie van Outlook zijn de volgende belangrijke stappen vereist:

1. [S/MIME-instellingen voor de webversie van Outlook configureren](configure-s-mime-settings-for-outlook-web-app.md)
2. [Verzameling van virtuele certificaten instellen om S/MIME te valideren](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [Gebruikerscertificaten synchroniseren met Office 365 voor S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Technologieën voor berichtversleuteling

Naarmate berichtbeveiliging belangrijker wordt, moeten beheerders de principes en concepten van veilige berichten begrijpen. Dit begrip is vooral belangrijk vanwege de groeiende verscheidenheid aan beveiligingsgerelateerde technologieën (waaronder S/MIME) die beschikbaar zijn. Zie S/MIME begrijpen voor meer informatie over S/MIME en hoe het werkt in de context van [e-mail.](/previous-versions/tn-archive/aa995740(v=exchg.65)) Diverse versleutelingstechnologieën werken samen om berichten in rust en onderweg te beschermen. S/MIME kan tegelijk werken met de volgende technologieën, maar is niet afhankelijk van deze technologieën:

- **Met Transport Layer Security (TLS)** versleutelt u de tunnel of de route tussen e-mailservers om te voorkomen dat er wordt gesluimd en afgeluisterd.

- **Secure Sockets Layer (SSL)** versleutelt de verbinding tussen e-mail clients en Microsoft 365-servers.

- **BitLocker** versleutelt de gegevens op een harde schijf in een datacenter, zodat als iemand onbevoegde toegang krijgt, deze niet kan lezen.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME vergeleken met Office 365-berichtversleuteling

S/MIME vereist een certificaat- en publicatie-infrastructuur die vaak wordt gebruikt in situaties van business-to-business en business-to-consumer. De gebruiker bepaalt de cryptografische sleutels in S/MIME en kan kiezen of deze worden gebruikt voor elk bericht dat ze verzenden. E-mailprogramma's, zoals Outlook, zoeken op een vertrouwde locatie van de hoofdcertificaatinstantie om digitale ondertekening en verificatie van de handtekening uit te voeren. Office 365 Message Encryption is een op beleid gebaseerde versleutelingsservice die kan worden geconfigureerd door een beheerder, en niet door een afzonderlijke gebruiker, om e-mail te versleutelen die naar iedereen binnen of buiten de organisatie wordt verzonden. Het is een onlineservice die is gebaseerd op Azure Rights Management (RMS) en niet afhankelijk is van een openbare-sleutelinfrastructuur. Office 365 Message Encryption biedt ook extra mogelijkheden, zoals de mogelijkheid om de e-mail aan te passen met het merk van de organisatie. Zie Versleuteling in Office 365 voor meer informatie over Berichtversleuteling [voor Office 365.](../../compliance/encryption.md)

## <a name="more-information"></a>Meer informatie

[Webversie van Outlook](/exchange/exchange-admin-center)

[Secure Mail (2000)](/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))