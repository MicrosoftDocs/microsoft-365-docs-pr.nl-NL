---
title: Niet-geverifieerde afzender
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u informatie over hoe u voorkomen dat phishingberichten uw postvak bereiken, Outlook.com en de webversie van Outlook.
ms.openlocfilehash: ed317f5673aa37b91e8c5092eb127b8df6be944e
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754830"
---
# <a name="unverified-sender"></a>Niet-geverifieerde afzender

> [!NOTE]
> Deze updates worden nu uitgerold en zijn mogelijk niet voor alle gebruikers beschikbaar. Deze functie wordt ondersteund voor Enterprise Outlook.com- en Enterprise Outlook Win32-desktopgebruikers. Het is momenteel niet beschikbaar voor gebruikers van Office 365 voor consumenten.

Om te voorkomen dat phishingberichten uw postvak bereiken, controleert Office 365 of de afzenders zijn wie ze zeggen dat ze zijn en markeren ze verdachte berichten als ongewenste e-mail.

> [!IMPORTANT]
> Wanneer een bericht is gemarkeerd als een phishing-scam, wordt in Outlook boven aan de pagina een waarschuwing weergegeven, maar kunnen alle koppelingen in het bericht nog steeds worden geopend.

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a>Hoe kan ik een verdacht bericht in mijn postvak IN identificeren?

Outlook toont indicatoren wanneer de afzender van een bericht niet kan worden geïdentificeerd of wanneer hun identiteit verschilt van wat u ziet in het adres Van.

## <a name="you-see-a--in-the-sender-image"></a>Je ziet een '?' in de afzender afbeelding

Wanneer Office 365 de identiteit van de afzender niet kan verifiëren met behulp van e-mailverificatietechnieken, wordt er een '?' weergegeven in de afzenderafbeelding.

![Bericht is niet geslaagd voor verificatie](../../media/message-did-not-pass-verification.jpg)

Niet elk bericht dat niet te verifiëren is kwaadaardig. U moet echter voorzichtig zijn met de interactie met berichten die niet worden geverifieerd als u de afzender niet herkent. Of, als je een afzender herkent die normaal gesproken geen '?' in de afzenderafbeelding heeft, maar je plotseling begint te zien, kan dat een teken zijn dat de afzender wordt vervalst.

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a>Hoe te beheren welke berichten de niet-geverifieerde afzenderbehandeling ontvangen 

Als u een Office 365-klant bent, u deze functie beheren via het Office 365 Security & Compliance Center.

- In het Security & Compliance Center kunnen beheerders van wereldwijde of beveiligingsbeheerders de functie in- of uitschakelen via antispoofingbeveiliging onder het Anti-Phish-beleid. Bovendien u de cmdlet **Set-AntiPhishPolicy** gebruiken in Exchange Online PowerShell. Zie [Anti-phishingbeveiliging in Office 365](anti-phishing-protection.md) en [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/set-antiphishpolicy)voor meer informatie.

    ![Niet-geverifieerde afzenders bewerken in de grafische interface.](../../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- Als een beheerder een false positive heeft geïdentificeerd en een afzender de niet-geverifieerde afzenderbehandeling niet mag ontvangen, kan een van de volgende acties worden ondernomen om de afzender toe te voegen aan de spoofinformatielijst voor spoofinformatie:

  - Voeg het domeinpaar toe via de Spoof Intelligence Insight. Zie [Walkthrough: inzicht in spoofinformatie voor](walkthrough-spoof-intelligence-insight.md)meer informatie.

  - Voeg het domeinpaar toe via de cmdlet **Set-PhishFilterPolicy** in Exchange Online PowerShell. Zie [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy) en Het [beleid van Office 365 ATP-antiphishing en antiphishing instellen](set-up-anti-phishing-policies.md)voor meer informatie.

Bovendien passen we de niet-geverifieerde afzenderbehandeling niet toe als het bericht via de regels voor poststroom (ook wel transportregels genoemd) of de veilige domeinlijst (antispambeleid) in de Postvak IN is bezorgd.

## <a name="how-to-manage-the-via-tag"></a>Hoe de 'via' tag te beheren 

Als u een Office 365-klant bent, u deze functie beheren via het Office 365 Security & Compliance Center, op dezelfde manier als u de niet-geverifieerde afzenderbehandeling beheert. Als u de afzender toevoegt aan de spoofintelligentielijst, wordt de 'via'-behandeling niet toegepast.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

### <a name="what-criteria-does-outlookcom-and-outlook-win32-desktop-use-to-add-the--and-the-via-properties"></a>Welke criteria gebruikt Outlook.com en Outlook Win32-bureaublad om de '?' en de 'via'-eigenschappen toe te voegen?

Voor de '?' in de afzenderafbeelding: Outlook.com vereist dat het bericht SPF- of DKIM-authenticatie doorgeeft en een dmarc-pas ontvangt, of een samengestelde verificatiepas van Office 365 Spoof Intelligence. Zie [SPF instellen in Office 365 om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md) en [DKIM gebruiken om uitgaande e-mail te valideren die vanuit uw aangepaste domein in Office 365 is verzonden.](use-dkim-to-validate-outbound-email.md)

Voor de via-tag: Als het domein in het Adres Van verschilt van het domein in de DKIM-handtekening of de SMTP-mail UIT, geeft Outlook.com het domein weer in een van deze twee velden (de voorkeur aan de DKIM-handtekening).

### <a name="how-do-i-remove-the--without-utilizing-the-spoof-intelligence-spoof-allow-list"></a>Hoe verwijder ik de '?' zonder gebruik te maken van de Spoof Intelligence spoof toestaan lijst?

Voor de '?' in de afzenderafbeelding: Als afzender moet u uw bericht verifiëren bij SPF of DKIM.

Voor de via-tag: Als afzender moet u ervoor zorgen dat het domein in de DKIM-handtekening of de SMTP MAIL FROM hetzelfde is als of een subdomein is van het domein in het Van-adres.

### <a name="do-outlookcom-and-outlook-win32-desktop-show-this-for-every-message-that-doesnt-pass-authentication"></a>Laten Outlook.com en Outlook Win32-bureaublad dit zien voor elk bericht dat niet door verificatie gaat?

Niet per se. Office 365 heeft mogelijk andere eigenschappen in het bericht om de afzender te verifiëren.

## <a name="related-topics"></a>Verwante onderwerpen

[Help uw Outlook.com e-mailaccount te beschermen](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[Hoe om te gaan met phishing in Outlook.com](https://support.microsoft.com/office/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[Ongewenste e-mail en spam filteren in de webversie van Outlook](https://support.microsoft.com/office/db786e79-54e2-40cc-904f-d89d57b7f41d)
