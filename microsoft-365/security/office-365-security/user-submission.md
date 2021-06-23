---
title: Door de gebruiker gerapporteerde berichtinstellingen
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
ms.openlocfilehash: f59548a1f36e067d8b649f7fe22149362d6fe9c6
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083534"
---
# <a name="user-reported-message-settings"></a>Door de gebruiker gerapporteerde berichtinstellingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 organisaties met Exchange Online postvakken kunt u een postvak opgeven om berichten te ontvangen die gebruikers melden als schadelijk of niet schadelijk. Wanneer gebruikers berichten rapporteren met de verschillende rapportageopties, kunt u dit postvak gebruiken om berichten te onderscheppen (alleen verzenden naar het aangepaste postvak) of kopieën van berichten te ontvangen (verzenden naar het aangepaste postvak en Microsoft). Deze functie werkt met de volgende opties voor berichtrapportage:

- [De invoeging Rapportbericht](enable-the-report-message-add-in.md)
- [De invoeging Phishing melden](enable-the-report-phish-add-in.md)
- [Rapportagehulpprogramma's van derden](#third-party-reporting-tools)

Als u door de gebruiker gerapporteerde berichten naar een aangepast postvak bezorgt in plaats van rechtstreeks bij Microsoft, kunnen uw beheerders berichten selectief en handmatig rapporteren aan Microsoft met [beheerdersinzending.](admin-submission.md) Deze instellingen stonden voorheen bekend als het beleid voor gebruikersinzendingen.

  > [!NOTE]
  > Als rapportage is uitgeschakeld [in](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)webversie van Outlook, wordt deze instelling overgenomen door het inschakelen van door de gebruiker gerapporteerde berichten en kunnen gebruikers berichten opnieuw in webversie van Outlook rapporteren.

## <a name="custom-mailbox-prerequisites"></a>Vereisten voor aangepaste postvakken

Gebruik de volgende artikelen om de vereiste vereisten te configureren, zodat door de gebruiker gerapporteerde berichten naar uw aangepaste postvak gaan:

- Sla spamfilters in het aangepaste postvak over door een exchange mail flow-regel te maken om het betrouwbaarheidsniveau voor spam in te stellen. Zie [De EAC gebruiken om een e-mailstroomregel](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) te maken die de SCL van een bericht in stelt om de SCL in te stellen op **Spamfilters omzeilen.**

- [Maak een Safe bijlagebeleid](set-up-safe-attachments-policies.md) met het aangepaste postvak waarin Safe Bijlagen scannen is uitgeschakeld **(Safe Sectie** Bijlagen onbekende malwarereactie \> **uitgeschakeld).**

- [Maak een Safe koppelingenbeleid](set-up-safe-links-policies.md) met het aangepaste postvak waarin Safe Koppelingen scannen is uitgeschakeld ( Selecteer de actie voor onbekende potentieel schadelijke **URL's in** berichtensectie \> **Uit).**

- [Maak een anti-malwarebeleid](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) met het aangepaste postvak waarin automatisch verwijderen van nul uur (ZAP) voor malware is uitgeschakeld **(** Sectie Beveiligingsinstellingen Schakel automatische \> 0-uursre **purge** voor malware inschakelen is niet geselecteerd).

- [Maak een antispambeleid](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) met het aangepaste postvak waarin ZAP voor spam en ZAP voor phishing zijn uitgeschakeld ( Auto **purge-sectie** Nul uur ingeschakeld voor automatisch verwijderen \> **(ZAP)** is niet geselecteerd.

- Schakel de regel ongewenste e-mail in het aangepaste postvak uit. Gebruik [Instellingen voor ongewenste e-mail configureren Exchange Online postvakken om](configure-junk-email-settings-on-exo-mailboxes.md) de regel ongewenste e-mail uit te schakelen. Nadat het bericht is uitgeschakeld, kan EOP geen berichten naar de map  Ongewenste e-mail verplaatsen op basis van de actie Voor spamfiltering Bericht verplaatsen naar de map Ongewenste e-mail of de safelistverzameling in het postvak.

Nadat u hebt geverifieerd dat uw postvak aan alle toepasselijke vereisten voldoet, kunt u de procedures in dit artikel gebruiken om het postvak voor gebruikersinzendingen te configureren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com/>. Als u rechtstreeks naar de pagina **Inzendingen wilt** gaan, gebruikt u <https://security.microsoft.com/reportsubmission> .

- Als u de configuratie voor gebruikersinzendingen wilt wijzigen, moet u lid zijn van een van de volgende rollengroepen:

  - **Organisatiebeheer** of **Beveiligingsbeheerder** in de [machtigingen in de Microsoft 365 Defender portal.](permissions-microsoft-365-security-center.md)
  - **Organisatiebeheer** in [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)

- U hebt toegang nodig tot Exchange Online PowerShell. Als het account dat u probeert te gebruiken geen toegang heeft tot Exchange Online PowerShell, krijgt u een foutmelding die er zo uitziet wanneer u het postvak voor inzendingen opgeeft:

  > Een e-mailadres opgeven in uw domein

  Zie de volgende onderwerpen voor meer informatie over het in- of uitschakelen van toegang tot Exchange Online PowerShell:

  - [Toegang tot powershell in- Exchange Online uitschakelen](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Clienttoegangsregels in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>Gebruik de Microsoft 365 Defender portal om het postvak met gebruikersinzendingen te configureren

1. Ga in Microsoft 365 Defender portal naar  Beleidsregels & beleidsregels Bedreigingsbeleid Anderen sectie Gebruikers gerapporteerde berichtinstellingen \>  \>  \>  \> **Gebruikersinzendingen.**

2. Op de **pagina Gebruikersinzendingen** wordt bepaald of de instelling van microsoft **Outlook rapportbericht** **is uitgeschakeld** of **Aan:**

   - **Microsoft Outlook knop Rapportbericht** \> **Aan** ![ In- of uitschakelen: Selecteer deze optie als u de invoegoptie Rapportbericht, de invoegvoegoptie Phishing melden of de ingebouwde rapportage in webversie van Outlook gebruikt en configureer vervolgens de volgende ](../../media/scc-toggle-on.png) instellingen:
     - **De gerapporteerde berichten verzenden naar**: Selecteer een van de volgende opties:
       - **Microsoft:** Het postvak voor gebruikersinzendingen wordt niet gebruikt (alle gerapporteerde berichten gaan naar Microsoft).
       - **Microsoft en het postvak van mijn** organisatie: Voer in het vak dat wordt weergegeven het e-mailadres in van een bestaand Exchange Online postvak. Distributiegroepen zijn niet toegestaan. Gebruikersinzendingen gaan naar zowel Microsoft voor analyse als naar het aangepaste postvak voor uw beheer- of beveiligingsbewerkingsteam om te analyseren.
       - **Het postvak van mijn** organisatie: Voer in het vak dat wordt weergegeven het e-mailadres in van een bestaand Exchange Online postvak. Distributiegroepen zijn niet toegestaan. Gebruik deze optie als u wilt dat het bericht eerst alleen naar een beheerder of het beveiligingsbewerkingsteam gaat voor analyse. Berichten gaan niet naar Microsoft, tenzij de beheerder deze zelf doorgestuurd.

          > [!IMPORTANT]
          >
          > Amerikaanse overheidsorganisaties (GCC, GCC High en DoD) kunnen alleen het postvak van mijn organisatie **configureren.** De andere twee opties zijn uitgeschakeld.
          >
          > Als organisaties zijn geconfigureerd om alleen naar een aangepast postvak te verzenden, worden gerapporteerde berichten niet opnieuw verzonden en zijn de resultaten in de portal Gebruikers gerapporteerde berichten altijd leeg.

       Ongeacht de waarde die u hebt geselecteerd voor **De gerapporteerde** berichten verzenden naar, zijn de volgende instellingen beschikbaar:

       - **Gebruikers laten kiezen of ze hun bericht willen rapporteren aan Microsoft**
       - **Selecteer rapportageopties die beschikbaar zijn voor gebruikerssectie:** Selecteer ten minste één van de volgende opties:
         - **Vraag het mij voordat u het bericht verstuurt**
         - **Het bericht altijd rapporteren**
         - **Het bericht nooit rapporteren**

          > [!CAUTION]
          > Als u de rapportage van ongewenste e-mail hebt uitgeschakeld [in webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) met behulp van webversie van Outlook-postvakbeleid, maar u een van de vorige instellingen hebt geconfigureerd om berichten te rapporteren aan Microsoft, kunnen gebruikers berichten rapporteren aan Microsoft in webversie van Outlook met de invoegvoegmap Bericht melden of de invoeging Phishing melden.

     - **Sectie Gebruikersrapportage**
       - **Vóór** het  rapporttabblad: Voer in de hoofdvakken Titel en Bericht de beschrijvende tekst in die gebruikers zien voordat ze een bericht rapporteren met de invoegtekst Rapportbericht of de invoegtekst Phishing melden.  U kunt de variabele %type% gebruiken om het inzendingstype (ongewenste e-mail, geen ongewenste e-mail, phish, enzovoort) op te nemen.
       - **Na rapporttabblad:**  Voer in de vakken Titel en Bevestigingsbericht de beschrijvende tekst in die gebruikers zien nadat ze een bericht hebben gemeld met de invoegtekst Rapportbericht of de invoeging Phishing melden.  U kunt de variabele %type% gebruiken om het inzendingstype op te nemen.

       Als u op de pagina een optie selecteert die de gerapporteerde berichten naar Microsoft verzendt, wordt ook de volgende tekst toegevoegd aan de melding:

          > Uw e-mail wordt in de as-is verzonden naar Microsoft voor analyse. Sommige e-mailberichten kunnen persoonlijke of gevoelige informatie bevatten.

   - **Microsoft Outlook knop Rapportbericht** \> **Uit** ![ Schakel deze optie in: selecteer deze optie als u rapportagehulpmiddelen van derden gebruikt in plaats van de invoeging Rapportbericht, de invoegvoegoptie Phishing melden of de ingebouwde rapportage in webversie van Outlook en configureer vervolgens de volgende ](../../media/scc-toggle-off.png) instellingen:
     - Selecteer **Dit aangepaste postvak gebruiken om gerapporteerde inzendingen van gebruikers te ontvangen.** Typ in het vak dat wordt weergegeven het e-mailadres van een bestaand Exchange Online postvak dat e-mail kan ontvangen.

   Wanneer u klaar bent, klikt u op **Bevestigen.** Als u deze waarden wilt leeg maken, klikt u op **Herstellen**

## <a name="third-party-reporting-tools"></a>Rapportagehulpprogramma's van derden

U kunt hulpprogramma's voor berichtrapportage van derden configureren om gerapporteerde berichten naar het aangepaste postvak te verzenden. U doet dit door de knop **Microsoft Outlook bericht** in te  stellen op Uit en het postvak van mijn organisatie in te stellen op een Office 365 van uw keuze. 

De enige vereiste is dat het oorspronkelijke bericht is opgenomen als een . EML of . MSG-bijlage (niet gecomprimeerd) in het bericht dat naar het aangepaste postvak wordt verzonden (niet alleen het oorspronkelijke bericht doorsturen naar het aangepaste postvak).

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
