---
title: Een postvak opgeven voor het inzenden van spam- en phishingberichten door gebruikers
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
description: Beheerders kunnen leren hoe u een postvak configureert om spam- en phishing-e-mail te verzamelen die door gebruikers wordt gerapporteerd.
ms.openlocfilehash: 2a1872aff88cd1cc21c6a6e3258671c303b55e17
ms.sourcegitcommit: 4ce28ad4d17d336106c1720d65349f19f9e90e04
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294191"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Een postvak opgeven voor het indienen van spam- en phishingberichten door gebruikers in Exchange Online

In Microsoft 365-organisaties met Exchange Online-postvakken u een postvak opgeven om berichten te ontvangen die gebruikers als kwaadaardig of niet kwaadaardig rapporteren. Wanneer gebruikers berichten verzenden met behulp van de verschillende rapportageopties, u dit postvak gebruiken om berichten te onderscheppen (alleen naar het aangepaste postvak verzenden) of kopieën van berichten ontvangen (verzenden naar het aangepaste postvak en Microsoft). Deze functie werkt met de volgende opties voor berichtrapportage:

- [De invoegtoepassing Rapportbericht](enable-the-report-message-add-in.md)

- [Ingebouwde rapportage in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (voorheen bekend als Outlook Web App)

  > [!NOTE]
  > Als de rapportage is [uitgeschakeld in de webversie van Outlook,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)overschrijft het inschakelen van gebruikers hier die instelling en kunnen gebruikers berichten opnieuw rapporteren in de webversie van Outlook.

U ook hulpprogramma's voor berichtrapportage van derden configureren om berichten door te sturen naar het postvak dat u opgeeft.

Door door de gebruiker gerapporteerde berichten naar een aangepast postvak te leveren in plaats van rechtstreeks aan Microsoft, kunnen uw beheerders selectief en handmatig berichten aan Microsoft rapporteren met behulp van [het indienen van beheerders.](admin-submission.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Inzendingen van gebruiker** wilt gaan, gebruikt u <https://protection.office.com/userSubmissionsReportMessage> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Als u het postvak wilt configureren voor gebruikersinzendingen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.** Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Het beveiligingscentrum & compliancecenter gebruiken om het postvak voor inzendingen van gebruikers te configureren

1. Ga in het Security & Compliance Center naar Inzendingen voor gebruikers van **het beleid voor** \> **Policy** \> **bedreigingen.**

2. Selecteer op de pagina **Gebruikersinzendingen** die wordt weergegeven een van de volgende opties:

   a. **De functie Rapportbericht voor Outlook inschakelen (Aanbevolen):** Selecteer deze optie als u de invoegtoepassing Rapportbericht of de ingebouwde rapportage in de webversie van Outlook gebruikt en configureer vervolgens de volgende instellingen:

      - **Het bevestigingsbericht voor eindgebruikers aanpassen:** Klik op deze koppeling. Configureer de volgende instellingen in de flyout **van bevestigingsbericht aanpassen:**

      - **Vóór indiening**: Voer in de vakken **Titel-** en **Bevestigingsbericht** de beschrijvende tekst in die gebruikers zien voordat ze een bericht rapporteren met de invoegtoepassing Rapportbericht. U het variabele %type% gebruiken om het onderwerpingstype op te nemen (junk, not junk, phish, enz.).

        Als u een optie selecteert die de gerapporteerde berichten naar Microsoft verzendt, wordt ook de volgende tekst aan de melding toegevoegd:

        > Uw e-mail wordt ter analyse naar Microsoft verzonden. Sommige e-mails kunnen persoonlijke of gevoelige informatie bevatten.

      - **Na indiening**: Klik op ![ Pictogram Uitvouwen ](../../media/scc-expand-icon.png) . Voer in de vakken **Titel-** en **Bevestigingsbericht** de beschrijvende tekst in die gebruikers zien nadat ze een bericht hebben gemeld met de invoegtoepassing Rapportbericht. U het variabele %type% gebruiken om het onderwerptype op te nemen.

      Klik op **Opslaan** wanneer u gereed bent. Als u deze waarden wilt wissen, klikt u op **Terugherstellen** op de pagina **Gebruikersinzendingen.**

      - **Stuur de gerapporteerde berichten naar**: Maak een van de volgende selecties:

        - **Microsoft (Aanbevolen)**: Het postvak voor inzendingen van gebruikers wordt niet gebruikt (alle gerapporteerde berichten gaan naar Microsoft).

        - **Microsoft en een aangepast postvak**: voer in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online-postvak in. Distributiegroepen zijn niet toegestaan. Inzendingen van gebruikers gaan naar zowel Microsoft voor analyse als naar het aangepaste postvak dat uw beheer- of beveiligingsteam kan analyseren.

        - **Aangepast postvak**: Voer in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online-postvak in. Distributiegroepen zijn niet toegestaan. Gebruik deze optie als u wilt dat het bericht alleen eerst naar het beheer- of beveiligingsteam gaat voor analyse. Berichten gaan niet naar Microsoft, tenzij de beheerder deze doorstuurt.

        Klik op **Bevestigen**als u klaar bent.

     > [!CAUTION]
     > Als u de melding van [ongewenste e-mail in de webversie](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) van Outlook hebt uitgeschakeld met behulp van het beleid voor webpostvak, maar u een van de vorige instellingen configureert om berichten aan Microsoft te rapporteren, kunnen gebruikers berichten rapporteren aan Microsoft in de webversie van Outlook met de invoegtoepassing Bericht rapport.

   - **De functie Rapportbericht voor Outlook uitschakelen:** Selecteer deze optie als u rapportagehulpprogramma's van derden gebruikt in plaats van de invoegtoepassing Rapportbericht of de ingebouwde rapportage in de webversie van Outlook en configureer vervolgens de volgende instellingen:

      Selecteer **Dit aangepaste postvak gebruiken om gerapporteerde inzendingen van gebruikers te ontvangen.** Voer in het vak dat wordt weergegeven het e-mailadres in van een bestaand postvak dat al in Office 365 staat. Dit moet een bestaand postvak in Exchange Online zijn dat e-mail kan ontvangen.

      Klik op **Bevestigen**als u klaar bent.

## <a name="message-submission-format"></a>Indeling voor het indienen van berichten

Berichten die naar aangepaste postvakken worden verzonden, moeten een specifieke e-mailindeling voor indiening volgen. Het onderwerp (enveloptitel) van de indiening moet in dit formaat zijn:

`{(int)safetyApiAction}|{networkId}|{senderIp}|{fromAddress}|({subject.Substring(0, Math.Min(subjectLen, subject.Length))})`

waren SafetyApiAction is:

- Junk = 1
- NotJunk = 2
- Phish = 3

In het volgende voorbeeld:

- Het bericht wordt gemeld als Phish.
- De Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.
- Het IP-adres van de afzender is 167.220.232.101.
- Het Adres van test@contoso.com.
- Het onderwerp e-mail van het bericht is "test phish indiening"

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

Berichten die deze indeling niet volgen, worden niet goed weergegeven in de portal Inzendingen.
