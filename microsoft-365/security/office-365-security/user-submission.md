---
title: Beleid voor gebruikersinzending
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen informatie krijgen over het configureren van een postvak voor het verzamelen van spam en phishing-e-mail die door gebruikers wordt gerapporteerd.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6022d2ca0e4357b422a20490fee7486affefa09c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287267"
---
# <a name="user-submissions-policy"></a>Beleid voor gebruikersinzending

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met Exchange Online-postvakken kunt u een postvak opgeven voor het ontvangen van berichten die gebruikers als schadelijk of niet schadelijk rapporteren. Wanneer gebruikers berichten verzenden met de verschillende rapportageopties, kunt u dit postvak gebruiken om berichten te onderscheppen (alleen naar het aangepaste postvak te verzenden) of kopieën van berichten te ontvangen (verzonden naar het aangepaste postvak en Microsoft). Deze functie werkt met de volgende opties voor berichtrapportage:

- [De invoegapp Bericht rapporteren](enable-the-report-message-add-in.md)

- [De invoegvoeg tekst Phishing melden](enable-the-report-phish-add-in.md)

- [Ingebouwde rapportage in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (voorheen Bekend als Outlook Web App)

- [Ingebouwde rapportage in Outlook voor iOS en Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > Als rapportage is uitgeschakeld in de webversie van [Outlook,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)zal het inschakelen van gebruikersinzendingen hier die instelling overschrijven en gebruikers weer in staat stellen berichten te rapporteren in de webversie van Outlook.

U kunt ook hulpprogramma's van derden voor berichtrapportage configureren om berichten door te sturen naar het postvak dat u opgeeft.

Als door de gebruiker gerapporteerde berichten worden verzonden naar een aangepast postvak in plaats van rechtstreeks naar Microsoft, kunnen uw beheerders berichten selectief en handmatig rapporteren aan Microsoft met behulp van [beheerdersverzending.](admin-submission.md)

## <a name="custom-mailbox-prerequisites"></a>Vereisten voor aangepaste postvakken

Gebruik de volgende artikelen om de vereiste te configureren zodat door de gebruiker gerapporteerde berichten naar uw aangepaste postvak gaan:

- Sla spamfilters op het aangepaste postvak over door een Exchange-regel voor de e-mailstroom te maken om het betrouwbaarheidsniveau voor ongewenste e-mail in te stellen. Zie Het EAC gebruiken om een regel voor de [e-mailstroom](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) te maken waarin de SCL van een bericht wordt ingesteld om de SCL in te stellen op **-1.**

- Schakel scanbijlagen uit voor malware in het aangepaste postvak. Gebruik Beleidsregels voor veilige bijlagen instellen in Defender voor [Office 365](set-up-atp-safe-attachments-policies.md) om een beleid voor veilige bijlagen te maken met de instelling **Uit** voor veilige bijlagen **onbekende malwarereactie.**

- Het scannen van URL's uitschakelen voor berichten in het aangepaste postvak. Gebruik Beleid voor veilige koppelingen instellen in Defender voor [Office 365](set-up-atp-safe-links-policies.md) om een beleid voor veilige koppelingen te maken met de instelling Uit voor De actie selecteren voor onbekende, potentieel schadelijke **URL's in berichten.** 

- Maak een antimalwarebeleid om Malware Zero-hour Auto Purge uit te schakelen. Zie [Het beveiligings- & compliancecentrum gebruiken](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) om antimalwarebeleid te maken om **Malware Zero-hour Auto Purge in** te stellen op **Uit.**

- Maak een spamfilterbeleid om Zap (Zero Hour Auto Purge) uit te schakelen voor spam en phishing in het aangepaste postvak. Zie [Het beveiligings- & compliancecentrum gebruiken](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) om antispambeleid te maken en de selectievakjes In voor Spam **ZAP** en  **Phish ZAP uit te checken.**

- Schakel de regel voor ongewenste e-mail uit in het aangepaste postvak. Gebruik [Instellingen voor ongewenste e-mail configureren in Postvakken van Exchange Online om](configure-junk-email-settings-on-exo-mailboxes.md) de regel voor ongewenste e-mail uit te schakelen. Als deze is uitgeschakeld, kan EOP geen berichten naar de  map Ongewenste e-mail verplaatsen op basis van de actie Bericht verplaatsen naar de map Ongewenste e-mail of de verzameling veilige contactpersonen in het postvak.

Nadat u hebt gecontroleerd of uw postvak aan alle toepasselijke vereisten voldoet, gebruikt u het [beveiligings- & compliancecentrum](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) om het postvak voor gebruikersinzending te configureren (in dit artikel).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **pagina gebruikersinzendingen wilt** gaan, gebruikt u <https://protection.office.com/userSubmissionsReportMessage> .

- Als u de configuratie voor gebruikersinzendingen wilt wijzigen, moet u lid zijn van een van de volgende rollengroepen:

  - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
  - **Organisatiebeheer** in [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)

- U hebt toegang nodig tot Exchange Online PowerShell. Als het account dat u probeert te gebruiken geen toegang heeft tot Exchange Online PowerShell, krijgt u een foutmelding die er zo uitziet wanneer u het postvak voor inzendingen opgeeft:

  > Een e-mailadres in uw domein opgeven

  Zie de volgende onderwerpen voor meer informatie over het in- of uitschakelen van toegang tot Exchange Online PowerShell:

  - [Toegang tot Exchange Online PowerShell in- of uitschakelen](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Regels voor clienttoegang in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a>Het beveiligings- & gebruiken om het postvak voor gebruikersinzending te configureren

1. Ga in het & Compliancecentrum naar **Gebruikersinzendingen** van het beleid \>  \> **voor bedreigingsbeheer.**

2. Selecteer een **van de volgende** opties op de pagina Gebruikers die wordt weergegeven:

   1. De functie Bericht rapporteren inschakelen voor **Outlook (aanbevolen)**: selecteer deze optie als u de invoegversie Bericht rapporteren, de invoegversie Phishing melden of de ingebouwde rapportage in de webversie van Outlook gebruikt en vervolgens de volgende instellingen configureert:

      - **Het bevestigingsbericht voor de eindgebruiker aanpassen:** klik op deze koppeling. Configureer **de volgende instellingen** in de flyout Bevestigingsbericht aanpassen die wordt weergegeven:

      - **Vóór**  inzending: voer in de vakken Titel en Bevestigingsbericht de beschrijvende tekst in die gebruikers zien voordat ze een bericht melden met behulp van de invoegapp Bericht rapporteren of de phishing-invoegvoeging melden.  U kunt de variabele %type% gebruiken om het indieningstype (ongewenste e-mail, geen ongewenste e-mail, phish, enzovoort) op te nemen.

        Als u een optie selecteert om de gerapporteerde berichten naar Microsoft te verzenden, wordt ook de volgende tekst toegevoegd aan de melding:

        > Uw e-mailbericht wordt naar Microsoft verzonden voor analyse. Sommige e-mailberichten kunnen persoonlijke of gevoelige informatie bevatten.

      - **Na de inzending**: klik ![ op pictogram Uitvbreken. ](../../media/scc-expand-icon.png) Voer in **de** vakken **Titel** en Bevestigingsbericht de beschrijvende tekst in die gebruikers zien nadat ze een bericht hebben rapporteren met behulp van de invoegapp Bericht rapporteren of de invoegvoegsel Phishing melden. U kunt het variabele %type% gebruiken om het indieningstype op te nemen.

      Klik op **Opslaan** wanneer u gereed bent. Als u deze waarden wilt verwijderen, klikt **u op** Terugzetten op de **pagina Gebruikersinzendingen.**

      - **Verzend de gerapporteerde berichten naar:** Maak een van de volgende selecties:

        - **Microsoft (Aanbevolen)**: Het postvak voor gebruikersinzendingen wordt niet gebruikt (alle gerapporteerde berichten gaan naar Microsoft).

        - **Microsoft en een aangepast postvak:** voer in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online-postvak in. Distributiegroepen zijn niet toegestaan. Gebruikersinzendingen gaan naar zowel Microsoft voor analyse als naar het aangepaste postvak dat u moet analyseren door uw beheerder of het team voor beveiligingsbewerkingen.

        - **Aangepast postvak:** typ in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online-postvak. Distributiegroepen zijn niet toegestaan. Gebruik deze optie als u wilt dat het bericht alleen naar een beheerder of het beveiligingsteam wordt gestuurd voor analyse. Berichten worden alleen naar Microsoft verzonden als de beheerder het bericht zelf doorgestuurd.

        > [!NOTE]
        > Amerikaanse overheidsorganisaties (GCC, GCC-H en DoD) kunnen alleen aangepaste postvakken **configureren.** De andere twee opties zijn uitgeschakeld.

      Klik op Bevestigen wanneer u klaar **bent.**

      > [!CAUTION]
      > Als u rapportage van ongewenste e-mail in de webversie van Outlook hebt uitgeschakeld met postvakbeleidsregels van de [webversie](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) van Outlook, maar u een van de vorige instellingen configureert om berichten te rapporteren aan Microsoft, kunnen gebruikers berichten rapporteren aan Microsoft in de webversie van Outlook met behulp van de invoegversie Bericht rapporteren of Phishing melden.

   - De functie Bericht rapporteren uitschakelen voor **Outlook:** selecteer deze optie als u rapportagehulpprogramma's van derden gebruikt in plaats van de invoegversie Bericht rapporteren, de invoegversie Phishing melden of de ingebouwde rapportage in de webversie van Outlook. Configureer vervolgens de volgende instellingen:

      Selecteer **Dit aangepaste postvak gebruiken om door de gebruiker gemelde inzendingen te ontvangen.** Voer in het vak dat wordt weergegeven het e-mailadres in van een bestaand postvak dat al in Office 365 staat. Dit moet een bestaand postvak in Exchange Online zijn dat e-mail kan ontvangen.

      Klik op Bevestigen wanneer u klaar **bent.**

## <a name="message-submission-format"></a>Indeling berichtinzending

Berichten die naar aangepaste postvakken worden verzonden, moeten een specifieke indeling voor e-mail voor indiening volgen. Het onderwerp (Enveloptitel) van de inzending moet de volgende indeling hebben:

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

waarbij SafetyAPIAction een van de volgende gehele getallen is:

- 1: Ongewenste e-mail
- 2: Geen ongewenste e-mail
- 3: Phishing

In het volgende voorbeeld:

- Het bericht wordt als phishingbericht gerapporteerd.
- De netwerkbericht-id is 49871234-6dc6-43e8-abcd-08d797f20abe.
- Het IP-adres van de afzender is 167.220.232.101.
- Het van-adres wordt test@contoso.com.
- De onderwerpregel van het bericht is 'test phishing-inzending'

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

Berichten die niet volgens deze indeling worden weergegeven, worden niet correct weergegeven in de portal Voorzendingen.
