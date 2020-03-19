---
title: Beheerdersinzendingen in Office 365, O365-inzendingen, Office 365-spamprobleem, O365 vals negatief, phish indienen in Office 365, e-mail indienen voor scannen, verdachte e-mail in Office 365, een e-mail scannen, Microsoft laten scannen op phish, Microsoft laten scannen op spam, verzenden e-mail, e-mail indienen, dodgy e-mail, slechte acteur mail, verdacht, niet-vertrouwde e-mail, phish e-mails melden aan Microsoft, phish e-mails melden aan Microsoft, meld scam e-mail aan Microsoft, meld malware in e-mail naar Microsoft, spam e-mail in inbox office 365, virus in e-mail office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Meer informatie over het verzenden van verdachte e-mails, vermoedelijke phishingmails, spam en andere mogelijk schadelijke berichten, URL's en bestanden van uw Office 365-tenant aan Microsoft voor het scannen.
ms.openlocfilehash: b123aef485628728df9db27875117b47295975ad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808814"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a>Verdachte spam, phish, URL's en bestanden indienen bij Microsoft voor Office 365-scannen

Beheerders kunnen e-mails verzenden met behulp van bestands- of netwerkbericht-id, URL's en bestanden voor het scannen door Microsoft in Office 365.
De bijgewerkte inzendingen sectie bevat nog steeds door de gebruiker gerapporteerde berichten en beschikbaar voor alle klanten met behulp van EOP.

Wanneer u een e-mail indient, krijgt u informatie over alle beleidsregels die de inkomende e-mail mogelijk in uw tenant hebben toegestaan, evenals het onderzoeken van URL's en bijlagen in de e-mail. Beleid waarmee een e-mail mogelijk is, omvat de lijst met veilige afzenders van een individuele gebruiker en beleid op tenantniveau, zoals exchange-mailstroomregels (ook wel transportregels genoemd).

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a>Verdachte inhoud doorsturen naar Microsoft voor Office 365-scannen

Als u inhoud wilt verzenden naar Microsoft, klikt u op de knop **Nieuwe indiening** in de linkerbovenhoek van de inzendingenpagina. Er verschijnt een fly-out aan de rechterkant van de pagina met de optie om een e-mail, URL of bestand in te dienen.

### <a name="submit-a-questionable-email-to-microsoft"></a>Een twijfelachtige e-mail verzenden naar Microsoft

![Voorbeeld van e-mailindiening](../../media/submission-flyout-email.PNG)

1. Als u een e-mail wilt verzenden, selecteert u **e-mail** en geeft u de **e-mailbericht-id** op of uploadt u het e-mailbestand.

2. Geef de ontvanger(s) op tegen wie u de beleidscontrole wilt uitvoeren. De beleidscontrole bepaalt of de e-mail het scannen heeft omzeild vanwege beleid op gebruikers- of tenantniveau.

3. Geef op of de e-mail al dan niet geblokkeerd had moeten zijn. Als de e-mail had moeten worden geblokkeerd, geeft u aan of deze had moeten worden geblokkeerd als spam, phishing of malware. Als u niet zeker weet welk type het zou kunnen zijn, gebruik dan uw beste oordeel.

   - Als het filter is omzeild vanwege beleid bij indiening, ziet u informatie over dat beleid.

   - Als het filter niet is omzeild vanwege een of meer beleidsregels, wordt de scan binnen enkele minuten voltooid. U ziet aanvullende informatie over de indiening door op de statuskoppeling te klikken. Dit omvat de resultaten van de beleidscontrole en het herscannen. Houd er rekening mee dat de e-mail niet opnieuw wordt uitgevoerd via de volledige filterstack van Office 365 ATP, maar een gedeeltelijke herscan uitvoert op basis van bepaalde kenmerken van de e-mail, URL of het bestand.

4. Klik op **Verzenden.**

### <a name="send-a-suspect-url-to-microsoft"></a>Een verdachte URL naar Microsoft verzenden

![Voorbeeld van e-mailindiening](../../media/submission-url-flyout.png)

1. Als u een URL wilt indienen, selecteert u **URL** van de flyout. Typ de volledige URL in inclusief het protocol **(https://).**

   Als u hebt geselecteerd **Moet zijn gefilterd,** geef dan op of de URL phishing of malware is.

2. Klik op **Verzenden.**

### <a name="submit-a-suspected-file-to-microsoft"></a>Een verdacht bestand indienen bij Microsoft

![Voorbeeld van e-mailindiening](../../media/submission-file-flyout.PNG)

1. Als u een bestand wilt indienen, selecteert u **Bestand** uit de flyout en uploadt u het bestand dat u wilt scannen.

2. Klik op **Verzenden.**

## <a name="related-topics"></a>Verwante onderwerpen

[Office 365 Advanced Threat Protection Plan 2](office-365-ti.md)

[Beschermen tegen bedreigingen in Office 365](protect-against-threats.md)

[Rapporten weergeven voor geavanceerde bedreigingsbeveiliging van Office 365](view-reports-for-atp.md)
