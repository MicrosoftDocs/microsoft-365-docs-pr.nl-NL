---
title: Een postvak opgeven voor gebruikersinzendingen van spam- en phishingberichten
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
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u een postvak configureert om spam en phishing-e-mail te verzamelen die door gebruikers worden gerapporteerd.
ms.openlocfilehash: e9550ce6357ddf19041e752c17e8bd844cba1a11
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726493"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Een postvak opgeven voor gebruikersinzendingen van spam- en phishingberichten in Exchange Online

In Microsoft 365-organisaties met Exchange Online-postvakken u een postvak opgeven om berichten te ontvangen die gebruikers melden als kwaadaardig of niet kwaadaardig. Wanneer gebruikers berichten verzenden met behulp van de verschillende rapportageopties, u dit postvak gebruiken om berichten te onderscheppen (alleen naar het aangepaste postvak verzenden) of kopieën van berichten te ontvangen (verzenden naar het aangepaste postvak en Microsoft). Deze functie werkt met de volgende opties voor berichtrapportage:

- [De invoegtoepassing Rapportbericht](enable-the-report-message-add-in.md)

- [Ingebouwde rapportage in de webversie](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) van Outlook (voorheen Outlook Web App genoemd)

  > [!NOTE]
  > Als de rapportage [is uitgeschakeld in de webversie](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)van Outlook, worden de inzendingen van gebruikers hier overschrijven en kunnen gebruikers berichten in de webversie van Outlook opnieuw rapporteren.

U ook hulpprogramma's voor berichtrapportage van derden configureren om berichten door te sturen naar het postvak dat u opgeeft.

Door gerapporteerde gebruikersberichten te leveren aan een aangepast postvak in plaats van rechtstreeks aan Microsoft, kunnen uw beheerders selectief en handmatig berichten rapporteren aan Microsoft met behulp van [admin-indiening.](admin-submission.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Inzendingen van** gebruikers wilt gaan, gebruikt u <https://protection.office.com/userSubmissionsReportMessage> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet machtigingen krijgen voordat u de procedures in dit onderwerp uitvoeren:

  - Als u de configuratie voor gebruikersinzendingen wilt wijzigen, moet u lid zijn van een van de volgende rolgroepen:

    - **Organisatiebeheer** of **beveiligingsbeheerder** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Organisatiebeheer** of **hygiënebeheer** in [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)

  - Voor alleen-lezen toegang tot gebruikersinzendingen moet u lid zijn van een van de volgende rolgroepen:

    - **Security Reader** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Alleen-weergeven organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Gebruik het Security & Compliance Center om het postvak voor gebruikersinzendingen te configureren

1. Ga in het Security & Compliance Center naar **Gebruikersinzendingen voor** \> **Policy** \> **bedreigingsbeheerbeleid.**

2. Selecteer op de pagina **Gebruikersinzendingen** die wordt weergegeven een van de volgende opties:

   a. **De functie Rapportbericht voor Outlook inschakelen (Aanbevolen)**: Selecteer deze optie als u de invoegtoepassing Rapportbericht of de ingebouwde rapportage in de webversie van Outlook gebruikt en configureer vervolgens de volgende instellingen:

      - **Het bevestigingsbericht van de eindgebruiker aanpassen**: Klik op deze link. Configureer in de flyout **bevestigingsbericht aanpassen** die wordt weergegeven de volgende instellingen:

      - **Vóór indiening**: Voer in de vakken **Bericht en** **Bevestiging** de beschrijvende tekst in die gebruikers zien voordat ze een bericht rapporteren met de invoegtoepassing Bericht rapporteren. U het variabele type %% gebruiken om het indieningstype (junk, niet junk, phish, enz.) op te nemen.

        Zoals opgemerkt, als u een optie selecteert die de gerapporteerde berichten naar Microsoft verzendt, wordt ook de volgende tekst aan de melding toegevoegd:

        > Uw e-mail wordt als nu naar Microsoft verzonden voor analyse. Sommige e-mails kunnen persoonlijke of gevoelige informatie bevatten.

      - **Na indiening**: Klik op ![ pictogram Uitvouwen ](../../media/scc-expand-icon.png) . Voer in de vakken **Bericht en** **Bevestiging** de beschrijvende tekst in die gebruikers zien nadat ze een bericht hebben gemeld met de invoegtoepassing Bericht rapporteren. U het variabele type %% gebruiken om het indieningstype op te nemen.

      Klik op **Opslaan** wanneer u gereed bent. Als u deze waarden wilt wissen, klikt u op **Terugzetten** op de pagina **Gebruikersinzendingen.**

      - **Stuur de gerapporteerde berichten naar**: Maak een van de volgende selecties:

        - **Microsoft (Aanbevolen)**: Het postvak voor gebruikersinzendingen wordt niet gebruikt (alle gerapporteerde berichten gaan naar Microsoft).

        - **Microsoft en een aangepast postvak**: Voer in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online-postvak in. Distributiegroepen zijn niet toegestaan. Gebruikersinzendingen gaan naar zowel Microsoft voor analyse als naar het aangepaste postvak dat uw beheerders- of beveiligingsteam kan analyseren.

        - **Aangepast postvak**: Voer in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online-postvak in. Distributiegroepen zijn niet toegestaan. Gebruik deze optie als u wilt dat het bericht alleen naar een beheerder of het beveiligingsteam gaat voor analyse eerst. Berichten gaan niet naar Microsoft, tenzij de beheerder het zelf doorstuurt.

        > [!NOTE]
        > Organisaties van de Amerikaanse overheid (GCC, GCC-H en DoD) kunnen alleen **aangepast postvak**configureren. De andere twee opties zijn uitgeschakeld. 

      Klik op **Bevestigen**als u klaar bent.

      > [!CAUTION]
      > Als u [de rapportage over ongewenste e-mail in de webversie](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) van Outlook hebt uitgeschakeld met het beleid voor outlook voor webpostvak, maar u een van de vorige instellingen configureert om berichten aan Microsoft te rapporteren, kunnen gebruikers berichten rapporteren aan Microsoft in de webversie van Outlook met behulp van de invoegtoepassing Rapportbericht.

   - **De functie Rapportbericht voor Outlook uitschakelen:** Selecteer deze optie als u rapportagehulpprogramma's van derden gebruikt in plaats van de invoegtoepassing Rapportbericht of de ingebouwde rapportage in de webversie van Outlook en configureer vervolgens de volgende instellingen:

      Selecteer **Dit aangepaste postvak gebruiken om door gebruikers gerapporteerde inzendingen te ontvangen.** Voer in het vak dat wordt weergegeven het e-mailadres in van een bestaand postvak dat zich al in Office 365 bevindt. Dit moet een bestaand postvak in Exchange Online zijn dat e-mail kan ontvangen.

      Klik op **Bevestigen**als u klaar bent.

## <a name="message-submission-format"></a>Indeling voor het indienen van berichten

Berichten die naar aangepaste postvakken worden verzonden, moeten een specifieke e-mailindeling volgen. Het onderwerp (enveloptitel) van de indiening moet in deze vorm zijn:

`SafetyAPIAction|NetworkMessgeId|SenderIp|FromAddress|(Message Subject)`

waren SafetyAPIAction is een van de volgende gehele waarden:

- 1: Junk
- 2: NotJunk
- 3: Phish

In het volgende voorbeeld:

- Het bericht wordt gerapporteerd als Phish.
- De Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.
- De Sender IP is 167.220.232.101.
- Het adres van Van is test@contoso.com.
- De onderwerpregel van het bericht is "test phish submission"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

Berichten die deze indeling niet volgen, worden niet goed weergegeven in de portal Inzendingen.
