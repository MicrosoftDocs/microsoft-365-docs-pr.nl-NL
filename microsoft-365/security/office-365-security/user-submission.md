---
title: Een postvak opgeven voor de verzending van spam en malafide berichten in de gebruikers
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
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u een postvak configureert om spam en phishing-e-mail te verzamelen die door gebruikers worden gerapporteerd.
ms.openlocfilehash: 6ae534278f4471f98f2d3bdd2318c687cea9f1d3
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195805"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Een postvak opgeven voor de verzending van spam en phishing-berichten in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met postvakken van Exchange Online kunt u een postvak opgeven voor het ontvangen van berichten die gebruikers als schadelijk of niet schadelijk melden. Wanneer gebruikers berichten verzenden met behulp van de verschillende rapportopties, kunt u dit postvak gebruiken om berichten te onderscheppen (alleen verzenden naar het aangepaste postvak) of kopieën van berichten ontvangen (verzenden naar het aangepaste postvak en Microsoft). Deze functie werkt met de volgende opties voor het rapporteren van berichten:

- [De invoegtoepassing bericht melden](enable-the-report-message-add-in.md)

- [Ingebouwde rapporten in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (voorheen Outlook Web app)

- [Ingebouwde rapporten in Outlook voor iOS en Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Als het rapporteren is [uitgeschakeld in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), wordt deze instelling vervangen door gebruikers die de instelling en de mogelijkheid bieden om berichten te rapporteren in de webversie van Outlook.

U kunt ook hulpmiddelen voor het rapporteren van SMS-berichten configureren voor het doorsturen van berichten naar het postvak dat u opgeeft.

Door gebruiker gerapporteerde berichten te verzenden naar een aangepast postvak in plaats van rechtstreeks aan Microsoft kunnen uw beheerders berichten selectief en handmatig rapporteren aan Microsoft via de [beheerder](admin-submission.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u direct naar de pagina voor het aanvragen van **gebruikers** wilt gaan, gebruikt u <https://protection.office.com/userSubmissionsReportMessage> .

- Als u de configuratie van gebruikers inzendingen wilt wijzigen, moet u lid zijn van een van de volgende rollen groepen:

  - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
  - **Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>De beveiligings & voor nalevings centrum gebruiken om het postvak voor de gebruiker te configureren

1. Ga in het beveiligings & compliance naar beleidsregels voor het beleid voor **risicobeheer** \> **Policy** \> **User submissions**.

2. Selecteer een van de volgende opties op de pagina **gebruikers items** die wordt weergegeven:

   a. **De functie bericht rapporteren voor Outlook inschakelen (aanbevolen)**: Selecteer deze optie als u de invoegtoepassing bericht rapporteren of de ingebouwde rapporten in de webversie van Outlook gebruikt en de volgende instellingen configureert:

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
        > US Government-organisaties (GCC, GCC-H en DoD) kunnen alleen **aangepaste postvak**configureren. De andere twee opties zijn uitgeschakeld. 

      Wanneer u klaar bent, klikt u op **bevestigen**.

      > [!CAUTION]
      > Als u de [rapportage van ongewenste e-mail in de webversie van Outlook hebt uitgeschakeld](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) met behulp van de beleidsregels voor het postvak in de webversie van Outlook, maar u de volgende instellingen voor het melden van berichten naar Microsoft hebt uitgeschakeld, kunnen gebruikers berichten rapporteren aan Microsoft in de webversie van Outlook met behulp van de invoegtoepassing berichten rapporteren.

   - **De functie voor het melden van berichten voor Outlook uitschakelen**: Selecteer deze optie als u rapportagehulpmiddelen van derden gebruikt in plaats van de invoegtoepassing berichten rapporteren of de ingebouwde rapporten in de webversie van Outlook en configureer de volgende instellingen:

      Selecteer **dit aangepaste postvak gebruiken om door de gebruiker gerapporteerde inzendingen te ontvangen**. In het vak dat wordt weergegeven, voert u het e-mailadres in van een bestaand postvak dat zich al in Office 365 bevindt. Dit moet een bestaand postvak zijn in Exchange Online, dat e-mailberichten kan ontvangen.

      Wanneer u klaar bent, klikt u op **bevestigen**.

## <a name="message-submission-format"></a>Opmaak van berichten indienen

Berichten die naar aangepaste postvakken worden verzonden, moeten een specifieke e-mail indeling voor het verzenden volgen. Het onderwerp (envelop titel) van de indiening moet de volgende indeling hebben:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

SafetyAPIAction is een van de volgende gehele waarden:

- 1: ongewenste e-mail
- 2: NotJunk
- 3: phishing

In het volgende voorbeeld:

- Het bericht wordt als phishing gerapporteerd.
- De netwerkbericht-ID is 49871234-6dc6-43e8-ABCD-08d797f20abe.
- Het IP-adres van de afzender is 167.220.232.101.
- Het van-adres is test@contoso.com.
- De onderwerpregel van het bericht is "phishing testen"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

Berichten die niet op deze indeling volgen, worden niet correct weergegeven in de portal voor ingediende items.
