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
ms.openlocfilehash: 2931171d8e2dcd26593904385aec872c8967abf4
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213350"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a>Een postvak opgeven voor het indienen van spam- en phishingberichten door gebruikers in Exchange Online

In Microsoft 365-organisaties met Exchange Online-postvakken u een postvak opgeven om berichten te ontvangen die gebruikers als kwaadaardig of niet kwaadaardig rapporteren. Wanneer gebruikers berichten verzenden met behulp van de verschillende rapportageopties, u dit postvak gebruiken om berichten te onderscheppen (alleen naar het aangepaste postvak verzenden) of kopieën van berichten ontvangen (verzenden naar het aangepaste postvak en Microsoft). Deze functie werkt met de volgende opties voor berichtrapportage:

- [De invoegtoepassing Rapportbericht](enable-the-report-message-add-in.md)

- [Ingebouwde rapportage in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (voorheen bekend als Outlook Web App)

U ook hulpprogramma's voor berichtrapportage van derden configureren om berichten door te sturen naar het postvak dat u opgeeft.

Door door de gebruiker gerapporteerde berichten naar een aangepast postvak te leveren in plaats van rechtstreeks aan Microsoft, kunnen uw beheerders selectief en handmatig berichten aan Microsoft rapporteren met behulp van [het indienen van beheerders.](admin-submission.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Inzendingen van gebruiker** wilt gaan, gebruikt u <https://protection.office.com/userSubmissionsReportMessage> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie Verbinding maken met Exchange [Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)als u verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Als u het postvak wilt configureren voor gebruikersinzendingen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.** Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Het beveiligingscentrum & compliancecenter gebruiken om het postvak voor inzendingen van gebruikers te configureren

1. Ga in het Security & Compliance Center naar Inzendingen voor gebruikers van **het beleid voor** \> **Policy** \> **bedreigingen.**

2. Selecteer op de pagina **Gebruikersinzendingen** die wordt weergegeven een van de volgende opties:

   - **De functie Rapportbericht voor Outlook inschakelen (Aanbevolen):** Selecteer deze optie als u de invoegtoepassing Rapportbericht of de ingebouwde rapportage in de webversie van Outlook gebruikt en configureer vervolgens de volgende instellingen:

     - **Het bevestigingsbericht voor eindgebruikers aanpassen:** Klik op deze koppeling. Configureer de volgende instellingen in de flyout **van bevestigingsbericht aanpassen:**

       - **Vóór indiening**: Voer in de vakken **Titel-** en **Bevestigingsbericht** de beschrijvende tekst in die gebruikers zien voordat ze een bericht rapporteren met de invoegtoepassing Rapportbericht. U het variabele %type% gebruiken om het onderwerpingstype op te nemen (junk, not junk, phish, enz.).

         Zoals opgemerkt, wordt ook de volgende tekst aan de kennisgeving toegevoegd:

         > Uw e-mail wordt ter analyse naar Microsoft verzonden. Sommige e-mails kunnen persoonlijke of gevoelige informatie bevatten.

       - **Na indiening**: Klik op ![ Pictogram Uitvouwen ](../../media/scc-expand-icon.png) . Voer in de vakken **Titel-** en **Bevestigingsbericht** de beschrijvende tekst in die gebruikers zien nadat ze een bericht hebben gemeld met de invoegtoepassing Rapportbericht. U het variabele %type% gebruiken om het onderwerptype op te nemen.

      Klik op **Opslaan** wanneer u gereed bent. Als u deze waarden wilt wissen, klikt u op **Terugherstellen** op de pagina **Gebruikersinzendingen.**

   - **Stuur de gerapporteerde berichten naar**: Maak een van de volgende selecties:

     - **Microsoft (Aanbevolen)**: Het postvak voor inzendingen van gebruikers wordt niet gebruikt (alle gerapporteerde berichten gaan naar Microsoft).

     - **Microsoft en een aangepast postvak**: voer in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online-postvak in. Distributiegroepen zijn niet toegestaan.

     - **Aangepast postvak**: Voer in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online-postvak in. Distributiegroepen zijn niet toegestaan.

     Klik op **Bevestigen**als u klaar bent.

     ![Gerapporteerde berichten verzenden naar Microsoft en een aangepast postvak](../../media/user-submission-enable-outlook-report-message.png)

   - **De functie Rapportbericht voor Outlook uitschakelen:** Selecteer deze optie als u rapportagehulpprogramma's van derden gebruikt in plaats van de invoegtoepassing Rapportbericht of de ingebouwde rapportage in de webversie van Outlook en configureer vervolgens de volgende instellingen:

     Selecteer **Dit aangepaste postvak gebruiken om gerapporteerde inzendingen van gebruikers te ontvangen.** Voer in het vak dat wordt weergegeven het e-mailadres van een bestaand postvak of het e-mailadres van het postvak dat u wilt maken in.

     Klik op **Bevestigen**als u klaar bent.

     ![Gerapporteerde berichten verzenden naar een aangepast postvak met hulpprogramma's van derden](../../media/user-submission-disable-outlook-report-message.png)
