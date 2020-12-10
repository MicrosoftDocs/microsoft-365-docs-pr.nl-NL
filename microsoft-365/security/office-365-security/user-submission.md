---
title: Beleid voor het aanmissionen van gebruikers
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen leren hoe u een postvak configureert om spam en phishing-e-mail te verzamelen die door gebruikers worden gerapporteerd.
ms.openlocfilehash: 7064e2d26722c433d33fe2f983484a40fa33c1e6
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615622"
---
# <a name="user-submissions-policy"></a>Beleid voor het aanmissionen van gebruikers

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met postvakken van Exchange Online kunt u een postvak opgeven voor het ontvangen van berichten die gebruikers als schadelijk of niet schadelijk melden. Wanneer gebruikers berichten verzenden met behulp van de verschillende rapportopties, kunt u dit postvak gebruiken om berichten te onderscheppen (alleen verzenden naar het aangepaste postvak) of kopieën van berichten ontvangen (verzenden naar het aangepaste postvak en Microsoft). Deze functie werkt met de volgende opties voor het rapporteren van berichten:

- [De invoegtoepassing bericht melden](enable-the-report-message-add-in.md)

- [Ingebouwde rapporten in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (voorheen Outlook Web app)

- [Ingebouwde rapporten in Outlook voor iOS en Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Als het rapporteren is [uitgeschakeld in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), wordt deze instelling vervangen door gebruikers die de instelling en de mogelijkheid bieden om berichten te rapporteren in de webversie van Outlook.

U kunt ook hulpmiddelen voor het rapporteren van SMS-berichten configureren voor het doorsturen van berichten naar het postvak dat u opgeeft.

Door gebruiker gerapporteerde berichten te verzenden naar een aangepast postvak in plaats van rechtstreeks aan Microsoft kunnen uw beheerders berichten selectief en handmatig rapporteren aan Microsoft via de [beheerder](admin-submission.md).

## <a name="custom-mailbox-prerequisites"></a>Vereisten voor aangepaste Postvak

Ga als volgt te werk om de vereisten te configureren die vereist zijn om door de gebruiker gerapporteerde berichten te verzenden naar uw aangepaste postvak:

- U kunt spam filteren in het aangepaste postvak door een Exchange-e-mail stroom regel te maken om het betrouwbaarheidsniveau voor ongewenste e-mail in te stellen. Zie voor meer informatie over het [maken van een e-mail stroom regel waarmee de SCL van een bericht wordt ingesteld](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) voor het instellen van de SCL op **-1**.

- Schakel het scannen van bijlagen voor malware in het aangepaste postvak uit. Gebruik [beleidsregels voor veilige bijlagen instellen in Defender voor Office 365](set-up-atp-safe-attachments-policies.md) om een veilig bijlage beleid te maken met **de instelling voor** **veilige bijlagen onbekende malware antwoord**.

- Schakel URL Scanning voor berichten in het aangepaste postvak uit. Met het beleid voor het maken van [koppelingen naar Office 365](set-up-atp-safe-links-policies.md) kunt u een beleid instellen voor veilige koppelingen met **de instelling voor** de optie **voor onbekende, mogelijk schadelijke url's in berichten**.

- Maak een anti-malwarebeleid voor het uitschakelen van malware met het automatisch wissen van 0 uur. Zie [het artikel over beveiligings & voor het maken van malware met een anti-malwarebeleid](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) **voor het** instellen van malware van **0 uur** .

- Maak een spamfilter beleid voor het uitschakelen van het automatisch wissen van Zero Hour (ZAP) voor spam en phishing in het aangepaste postvak. Zie het artikel **over** [beveiligings & om Antispambeleid te maken](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) en schakel de selectievakjes uit voor **spam ZAP** en **Phish ZAP**.

- Schakel de regel voor ongewenste e-mail uit in het aangepaste postvak. Gebruik de [instellingen voor ongewenste e-mail in Exchange Online-postvakken configureren](configure-junk-email-settings-on-exo-mailboxes.md) om de regel voor ongewenste e-mail uit te schakelen. Als dit is uitgeschakeld, kunnen berichten niet worden verplaatst naar de map Ongewenste E-mail op basis van het spamfilter verdict **-actiebericht verplaatsen naar map Ongewenste e-mail** of de verzameling veilige lijst in het postvak.

Nadat u hebt gecontroleerd of uw postvak aan alle toepasselijke voorwaarden voldoet, [gebruikt u de beveiligings & voor nalevings centrum om het postvak voor de gebruiker te configureren](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in dit artikel).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u direct naar de pagina voor het aanvragen van **gebruikers** wilt gaan, gebruikt u <https://protection.office.com/userSubmissionsReportMessage> .

- Als u de configuratie van gebruikers inzendingen wilt wijzigen, moet u lid zijn van een van de volgende rollen groepen:

  - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
  - **Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>De beveiligings & voor nalevings centrum gebruiken om het postvak voor de gebruiker te configureren

1. Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **risicobeheer** \>  \> .

2. Selecteer een van de volgende opties op de pagina **gebruikers items** die wordt weergegeven:

   1. **De functie bericht rapporteren voor Outlook inschakelen (aanbevolen)**: Selecteer deze optie als u de invoegtoepassing bericht rapporteren of de ingebouwde rapporten in de webversie van Outlook gebruikt en de volgende instellingen configureert:

      - **Het bevestigingsbericht voor eindgebruikers aanpassen**: Klik op deze link. Configureer de volgende instellingen in het vervolgmenu met **bevestigingsberichten aanpassen** dat wordt weergegeven:

      - **Voordat u gaat verzenden**: Typ in de vakken **titel** en **bevestiging** de beschrijvende tekst die gebruikers zien voordat ze een bericht rapporteren met behulp van de invoegtoepassing bericht melden. U kunt de variabele% type% gebruiken voor het inzendings type (ongewenst, geen ongewenste e-mail, phishing, enzovoort).

        Zoals u ziet, wordt de volgende tekst ook toegevoegd aan de melding wanneer u een optie selecteert waarmee de gerapporteerde berichten naar Microsoft worden verzonden:

        > Uw e-mailbericht wordt verzonden naar Microsoft voor analyse. Sommige e-mailberichten kunnen persoonlijke of gevoelige informatie bevatten.

      - **Na verzending**: Klik op ![ pictogram uitvouwen ](../../media/scc-expand-icon.png) . Voer in de vakken **titel** en **bevestigingsbericht** de beschrijvende tekst in die gebruikers zien nadat ze een bericht hebben gerapporteerd via de invoegtoepassing bericht rapporteren. U kunt de variabele% type% gebruiken om het type levering op te nemen.

      Klik op **Opslaan** wanneer u gereed bent. Als u deze waarden wilt wissen, klikt u op de pagina voor het **aanbrengen** van **gebruikers** op terug herstellen.

      - **Verstuur de gerapporteerde berichten naar**: Voer een van de volgende opties in:

        - **Microsoft (aanbevolen)**: het postvak voor de gebruiker wordt niet gebruikt (alle gerapporteerde berichten gaan naar Microsoft).

        - **Microsoft en een aangepast postvak**: in het vak dat wordt weergegeven, voert u het e-mailadres van een bestaand Exchange Online-postvak in. Distributiegroepen zijn niet toegestaan. Gebruikers inzendingen gaan naar Microsoft for Analysis en naar het aangepaste postvak voor uw beheerder of beveiligingsactiviteiten team om dit te analyseren.

        - **Aangepast postvak**: Typ in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online-postvak. Distributiegroepen zijn niet toegestaan. Gebruik deze optie als u wilt dat het bericht eerst naar een beheerder of het beveiligings werkactiviteiten team gaat voor analyse. Berichten gaan niet naar Microsoft, tenzij deze door de beheerder zelf worden doorgestuurd.

        > [!NOTE]
        > US Government-organisaties (GCC, GCC-H en DoD) kunnen alleen **aangepaste postvak** configureren. De andere twee opties zijn uitgeschakeld.

      Wanneer u klaar bent, klikt u op **bevestigen**.

      > [!CAUTION]
      > Als u de [rapportage van ongewenste e-mail in de webversie van Outlook hebt uitgeschakeld](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) met behulp van de beleidsregels voor het postvak in de webversie van Outlook, maar u de volgende instellingen voor het melden van berichten naar Microsoft hebt uitgeschakeld, kunnen gebruikers berichten rapporteren aan Microsoft in de webversie van Outlook met behulp van de invoegtoepassing berichten rapporteren.

   - **De functie voor het melden van berichten voor Outlook uitschakelen**: Selecteer deze optie als u rapportagehulpmiddelen van derden gebruikt in plaats van de invoegtoepassing berichten rapporteren of de ingebouwde rapporten in de webversie van Outlook en configureer de volgende instellingen:

      Selecteer **dit aangepaste postvak gebruiken om door de gebruiker gerapporteerde inzendingen te ontvangen**. In het vak dat wordt weergegeven, voert u het e-mailadres in van een bestaand postvak dat zich al in Office 365 bevindt. Dit moet een bestaand postvak zijn in Exchange Online, dat e-mailberichten kan ontvangen.

      Wanneer u klaar bent, klikt u op **bevestigen**.

## <a name="message-submission-format"></a>Opmaak van berichten indienen

Berichten die naar aangepaste postvakken worden verzonden, moeten een specifieke e-mail indeling voor het verzenden volgen. Het onderwerp (envelop titel) van de indiening moet de volgende indeling hebben:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

waarbij SafetyAPIAction een van de volgende gehele waarden is:

- 1: ongewenste e-mail
- 2: geen ongewenste e-mail
- 3: phishing

In het volgende voorbeeld:

- Het bericht wordt als phishing gerapporteerd.
- De netwerkbericht-ID is 49871234-6dc6-43e8-ABCD-08d797f20abe.
- Het IP-adres van de afzender is 167.220.232.101.
- Het van-adres is test@contoso.com.
- De onderwerpregel van het bericht is "phishing testen"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

Berichten die niet op deze indeling volgen, worden niet correct weergegeven in de portal voor ingediende items.
