---
title: Beleid voor gebruikersinzendingen
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
description: Beheerders kunnen leren hoe ze een postvak configureren voor het verzamelen van spam en phishing-e-mail die door gebruikers worden gerapporteerd.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4827ce149632d0e37dbe9c3dc5fc8325dbfa8afa
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929873"
---
# <a name="user-submissions-policy"></a>Beleid voor gebruikersinzendingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 organisaties met Exchange Online postvakken kunt u een postvak opgeven om berichten te ontvangen die gebruikers melden als schadelijk of niet schadelijk. Wanneer gebruikers berichten verzenden met de verschillende rapportageopties, kunt u dit postvak gebruiken om berichten te onderscheppen (alleen naar het aangepaste postvak te verzenden) of kopieën van berichten te ontvangen (verzenden naar het aangepaste postvak en Microsoft). Deze functie werkt met de volgende opties voor berichtrapportage:

- [De invoeging Rapportbericht](enable-the-report-message-add-in.md)

- [De invoeging Phishing melden](enable-the-report-phish-add-in.md)

- [Rapportagehulpprogramma's van derden](#third-party-reporting-tools)

Als u door de gebruiker gerapporteerde berichten naar een aangepast postvak bezorgt in plaats van rechtstreeks bij Microsoft, kunnen uw beheerders berichten selectief en handmatig rapporteren aan Microsoft met [beheerdersinzending.](admin-submission.md)

  > [!NOTE]
  > Als rapportage is uitgeschakeld [in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)op internet, wordt deze instelling overgenomen door gebruikersinzendingen in te stellen en kunnen gebruikers berichten opnieuw rapporteren in Outlook op internet.

## <a name="custom-mailbox-prerequisites"></a>Vereisten voor aangepaste postvakken

Gebruik de volgende artikelen om de vereiste vereisten te configureren, zodat door de gebruiker gerapporteerde berichten naar uw aangepaste postvak gaan:

- Sla spamfilters in het aangepaste postvak over door een exchange mail flow-regel te maken om het betrouwbaarheidsniveau voor spam in te stellen. Zie [De EAC gebruiken om een e-mailstroomregel](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) te maken die de SCL van een bericht in stelt om de SCL in te stellen op **Spamfilters omzeilen.**

- Schakel het scannen van bijlagen voor malware in het aangepaste postvak uit. Gebruik Het beleid Safe Bijlagen [instellen in Defender](set-up-safe-attachments-policies.md) voor Office 365 om een Safe-bijlagebeleid  te maken met de instelling Uit voor Safe Bijlagen onbekende **malwarereactie.**

- Schakel HET SCANNEN VAN URL's in berichten in het aangepaste postvak uit. Gebruik [Beleidsregels voor Safe koppelingen instellen in Defender](set-up-safe-links-policies.md) voor Office 365 om een Safe-koppelingsbeleid te maken met de instelling Uit voor Selecteer de actie voor onbekende potentieel schadelijke **URL's in berichten.** 

- Maak een anti-malwarebeleid om Malware Zero-hour Auto Purge uit te schakelen. Zie De portal Microsoft 365 Defender gebruiken om [antispambeleid](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) te maken om **Malware Zero-hour Auto Purge in te** stellen op **Uit.**

- Maak een spamfilterbeleid om automatisch verwijderen (ZAP) van nul uur uit te schakelen voor spam en phishing in het aangepaste postvak. Zie De portal Microsoft 365 Defender gebruiken om [antispambeleid](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) te maken en de selectievakjes Aan voor **Spam ZAP** en  **Phish ZAP uit te sluiten.**

- Schakel de regel ongewenste e-mail in het aangepaste postvak uit. Gebruik [Instellingen voor ongewenste e-mail configureren Exchange Online postvakken om](configure-junk-email-settings-on-exo-mailboxes.md) de regel ongewenste e-mail uit te schakelen. Nadat EOP is uitgeschakeld, kan EOP berichten niet verplaatsen naar  de map Ongewenste e-mail op basis van de actie Bericht verplaatsen naar de map Ongewenste e-mail of de safelistverzameling in het postvak.

Nadat u hebt geverifieerd dat uw postvak aan alle toepasselijke vereisten voldoet, implementeert u de procedure die is opgegeven in De portal Microsoft 365 Defender gebruiken om het postvak voor gebruikersinzendingen [te configureren.](#use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com/>. Als u rechtstreeks naar de pagina **Inzendingen wilt** gaan, gebruikt u <https://security.microsoft.com/reportsubmission> .

- Als u de configuratie voor gebruikersinzendingen wilt wijzigen, moet u lid zijn van een van de volgende rollengroepen:

  - **Organisatiebeheer** of **Beveiligingsbeheerder** in de [Microsoft 365 Defender-portal](permissions-in-the-security-and-compliance-center.md).
  - **Organisatiebeheer** in [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)

- U hebt toegang nodig tot Exchange Online PowerShell. Als het account dat u probeert te gebruiken geen toegang heeft tot Exchange Online PowerShell, krijgt u een foutmelding die er zo uitziet wanneer u het postvak voor inzendingen opgeeft:

  > Een e-mailadres opgeven in uw domein

  Zie de volgende onderwerpen voor meer informatie over het in- of uitschakelen van toegang tot Exchange Online PowerShell:

  - [Toegang tot powershell in- Exchange Online uitschakelen](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Clienttoegangsregels in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>Gebruik de Microsoft 365 Defender-portal om het postvak met gebruikersinzendingen te configureren

1. Ga in Microsoft 365 Defender-portal naar **Beleidsregels &** beleidsregels Bedreigingsbeleid \>  \> **Gebruiker gerapporteerde berichtinstellingen** \> **Gebruikersinzendingen**.

2. Selecteer een **van de** volgende opties op de pagina Gebruikersinzendingen die wordt weergegeven:

      1. De functie Rapportbericht inschakelen voor **Outlook (aanbevolen) :** Selecteer deze optie als u de invoegfunctie Rapportbericht, de invoegvoegoptie Phishing melden of de ingebouwde rapportage in Outlook op het web gebruikt en vervolgens de volgende instellingen configureert:

    - **Het bevestigingsbericht van de eindgebruiker aanpassen:** Klik op deze koppeling. Configureer **de volgende instellingen** in het flyout Bevestigingsbericht aanpassen dat wordt weergegeven:

        - **Vóór**  de  inzending: Voer in de vakken Titel en bevestigingsbericht de beschrijvende tekst in die gebruikers zien voordat ze een bericht rapporteren met de invoegtekst Rapportbericht of de invoegtekst Phishing melden. U kunt de variabele %type% gebruiken om het inzendingstype (ongewenste e-mail, geen ongewenste e-mail, phish, enzovoort) op te nemen.

          Zoals vermeld, als u een optie selecteert die de gerapporteerde berichten naar Microsoft verzendt, wordt ook de volgende tekst toegevoegd aan de melding:

          > Uw e-mail wordt in de as-is verzonden naar Microsoft voor analyse. Sommige e-mailberichten kunnen persoonlijke of gevoelige informatie bevatten.

        - **Na de inzending:** Klik ![ op Pictogram Uitvv. ](../../media/scc-expand-icon.png) Voer in  **de** vakken Titel en bevestigingsbericht de beschrijvende tekst in die gebruikers zien nadat ze een bericht hebben rapporteerd met de invoegvoegtekst Rapportbericht of de invoegtekst Phishing melden. U kunt de variabele %type% gebruiken om het inzendingstype op te nemen.

      Klik op **Opslaan** wanneer u gereed bent. Als u deze waarden wilt verwijderen, klikt **u op Terugzetten** op de **pagina Gebruikersinzendingen.**
    
    - **De rapportageopties voor eindgebruikers aanpassen:** Klik op deze koppeling. Voer in **de flyout Rapportageopties** voor eindgebruikers aanpassen de beschrijvende tekst in voor rapportageopties voor ongewenste e-mail. 
    
      Selecteer **onder Opties om aan te geven wanneer** berichten worden gerapporteerd ten minste één van de volgende opties:
        - **Vraag het mij voordat u een rapport verstuurt**
        - **Rapporten automatisch verzenden**
        - **Nooit rapporten verzenden**
       
      Klik op **Opslaan** wanneer u gereed bent.

        - **De gerapporteerde berichten verzenden naar**: Maak een van de volgende selecties:

        - **Microsoft (Aanbevolen)**: Het postvak voor gebruikersinzendingen wordt niet gebruikt (alle gerapporteerde berichten gaan naar Microsoft).

        - **Zowel Microsoft als een aangepast postvak:** Voer in het vak dat wordt weergegeven het e-mailadres in van een bestaand Exchange Online postvak. Distributiegroepen zijn niet toegestaan. Gebruikersinzendingen gaan naar zowel Microsoft voor analyse als naar het aangepaste postvak voor uw beheer- of beveiligingsbewerkingsteam om te analyseren.

        - **Alleen aangepast postvak:** Voer in het vak dat wordt weergegeven het e-mailadres in van een bestaand Exchange Online postvak. Distributiegroepen zijn niet toegestaan. Gebruik deze optie als u wilt dat het bericht eerst alleen naar een beheerder of het beveiligingsbewerkingsteam gaat voor analyse. Berichten gaan niet naar Microsoft, tenzij de beheerder deze zelf doorgestuurd.

          > [!NOTE]
          > Amerikaanse overheidsorganisaties (GCC, GCC-H en DoD) kunnen alleen Aangepast postvak **configureren.** De andere twee opties zijn uitgeschakeld.

          > [!NOTE]
          > Als organisaties zijn geconfigureerd om alleen naar een aangepast postvak te verzenden, worden gerapporteerde berichten niet opnieuw verzonden en zijn de resultaten in de portal Gebruikers gerapporteerde berichten altijd leeg.

      Wanneer u klaar bent, klikt u op **Bevestigen.**

      > [!CAUTION]
      > Als u de rapportage van ongewenste e-mail hebt uitgeschakeld [in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) op het web met behulp van beleidsregels voor Outlook op het webpostvak, maar u een van de vorige instellingen configureert om berichten te rapporteren aan Microsoft, kunnen gebruikers berichten rapporteren aan Microsoft in Outlook op het web met de invoeging Rapportbericht of de invoeging Phishing melden.


    2. De functie Rapportbericht uitschakelen voor **Outlook:** Selecteer deze optie als u rapportagehulpmiddelen van derden gebruikt in plaats van de invoegfunctie Rapportbericht, de invoegfunctie Phishing melden of de ingebouwde rapportage in Outlook op het web en configureer vervolgens de volgende instellingen:

       Selecteer **Dit aangepaste postvak gebruiken om gerapporteerde inzendingen van gebruikers te ontvangen.** Voer in het vak dat wordt weergegeven het e-mailadres in van een bestaand postvak dat al in Office 365. Dit moet een bestaand postvak zijn in Exchange Online dat e-mail kan ontvangen.

       Wanneer u klaar bent, klikt u op **Bevestigen.**

## <a name="third-party-reporting-tools"></a>Rapportagehulpprogramma's van derden

U kunt hulpprogramma's voor berichtrapportage van derden configureren om gerapporteerde berichten naar het aangepaste postvak te verzenden. De enige vereiste is dat het oorspronkelijke bericht is opgenomen als een bijlage in het bericht dat naar het aangepaste postvak wordt verzonden (niet alleen het oorspronkelijke bericht doorsturen naar het aangepaste postvak).

De vereisten voor berichtopmaak worden beschreven in de volgende sectie. De opmaak is optioneel, maar als de opmaak niet de voorgeschreven notatie volgt, worden de rapporten altijd als phish verzonden.

## <a name="message-submission-format"></a>Berichtinzendingsindeling

Als u de oorspronkelijke bijgevoegde berichten correct wilt identificeren, hebben berichten die naar het aangepaste postvak worden verzonden, specifieke opmaak nodig. Als de berichten deze indeling niet gebruiken, worden de oorspronkelijke bijgevoegde berichten altijd geïdentificeerd als phishing-inzendingen.

Voor een correcte identificatie van de oorspronkelijke bijgevoegde berichten moeten berichten die naar het aangepaste postvak worden verzonden, de volgende syntaxis gebruiken voor het onderwerp (enveloptitel):

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

waarbij SafetyAPIAction een van de volgende gehele getallen is:

- 1: Ongewenste e-mail
- 2: Geen ongewenste e-mail
- 3: Phishing

In dit voorbeeld worden de volgende waarden gebruikt:

- Het bericht wordt gerapporteerd als phishing.
- De netwerkbericht-id is 49871234-6dc6-43e8-abcd-08d797f20abe.
- De IP-afzender is 167.220.232.101.
- Het van-adres is test@contoso.com.
- De onderwerpregel van het bericht is 'test phishing-inzending'

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

Berichten die deze indeling niet volgen, worden niet correct weergegeven in de portal Inzendingen.
