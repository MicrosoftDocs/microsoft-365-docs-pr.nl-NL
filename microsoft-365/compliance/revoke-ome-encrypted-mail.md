---
title: E-mail intrekken die is versleuteld met geavanceerde berichtversleuteling
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Als beheerder en als afzender van berichten kunt u bepaalde e-mailberichten intrekken die zijn versleuteld met Office 365 Advanced Message Encryption.
ms.openlocfilehash: 340a9e73dba50e28223ee561db749a089c649df6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "52162273"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>E-mail intrekken die is versleuteld met geavanceerde berichtversleuteling

E-mailte intrekken wordt aangeboden als onderdeel van Office 365 Advanced Message Encryption. Office 365 Advanced Message Encryption is opgenomen in [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing) en Office 365 Education A5. Als uw organisatie een abonnement heeft dat geen Office 365 Advanced Message Encryption bevat, kunt u dit kopen met de Microsoft 365 E5 Compliance SKU-invoegactie voor Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing) of de Office 365 Advanced Compliance SKU-invoegactie voor Microsoft 365 E3, Microsoft 365 E3 (Non-profitmedewerkersprijzen) of Office 365 SKU's.

Dit artikel maakt deel uit van een grotere reeks artikelen over [Office 365-berichtversleuteling.](ome.md)

Als een bericht is versleuteld met Office 365 Advanced Message Encryption en u een Microsoft 365-beheerder bent of als u de afzender van het bericht bent, kunt u het bericht onder bepaalde voorwaarden intrekken. Beheerders trekken berichten in met PowerShell. Als afzender trekt u een bericht in dat u rechtstreeks vanuit Outlook op internet hebt verzonden. In dit artikel worden de omstandigheden beschreven waaronder intrekking mogelijk is en hoe u dit kunt doen.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Versleutelde e-mailberichten die u kunt intrekken

Beheerders en afzenders van berichten kunnen versleutelde e-mailberichten intrekken als de geadresseerde een versleutelde e-mail met een koppeling heeft ontvangen. Als de geadresseerde een native inline-ervaring heeft ontvangen in een ondersteunde Outlook client, kunt u het bericht niet intrekken.

Of een geadresseerde een koppelingservaring of een inline-ervaring ontvangt, is afhankelijk van het identiteitstype van de geadresseerde: Office 365- en Microsoft-accountontvangers (bijvoorbeeld outlook.com-gebruikers) krijgen een inline-ervaring in ondersteunde Outlook-clients. Alle andere typen geadresseerden, zoals Gmail- en Yahoo-geadresseerden, krijgen een op koppeling gebaseerde ervaring.

Beheerders en afzenders van berichten kunnen berichten intrekken die zijn versleuteld met behulp van versleuteling die rechtstreeks vanaf Outlook op internet wordt toegepast. Bijvoorbeeld berichten die zijn versleuteld met de optie Alleen versleutelen.

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Schermafbeelding met de optie Alleen versleutelen in Outlook web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Gebruikerservaring voor ingetrokken versleutelde e-mailberichten

Wanneer een e-mailbericht is ingetrokken, ontvangt de geadresseerde een foutmelding wanneer deze toegang heeft tot de versleutelde e-mail via de Office 365-berichtversleuteling-portal: 'Het bericht is ingetrokken door de afzender'.

![Schermafbeelding van een ingetrokken versleutelde e-mail.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>Een versleuteld bericht dat u hebt verzonden intrekken

U kunt een e-mail intrekken die u hebt verzonden naar één geadresseerde die een sociaal account gebruikt, zoals gmail.com of yahoo.com. Met andere woorden, u kunt een e-mailbericht intrekken dat is verzonden naar één geadresseerde die de koppelingservaring heeft ontvangen.

U kunt geen e-mail intrekken die u hebt verzonden naar een geadresseerde die een werk- of schoolaccount gebruikt van Office 365 of Microsoft 365 of een gebruiker die een Microsoft-account gebruikt, bijvoorbeeld een outlook.com-account. 

Als u een versleuteld bericht dat u hebt verzonden, wilt intrekken, moet u deze stappen voltooien

1. Blader Outlook op internet in **de** map Verzonden naar het bericht dat u wilt intrekken.

   Als de e-mail kan worden herkeerbaar, ziet u de koppeling Externe toegang verwijderen boven aan het bericht.

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Schermafbeelding met versleutelde e-mail die u wilt intrekken in Outlook web.":::

2. Klik **op Externe toegang verwijderen om** het bericht in te trekken.

   In het bericht wordt weergegeven dat de status ervan is ingetrokken.

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Schermafbeelding met ingetrokken versleuteld bericht in Outlook web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>Een versleuteld bericht intrekken als beheerder

Microsoft 365 beheerders volgen deze algemene stappen om een in aanmerking komende versleutelde e-mail in te trekken:

- Ontvang de bericht-id van het e-mailbericht.
- Controleer of u het bericht kunt intrekken.
- De e-mail intrekken.

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Stap 1. De bericht-id van het e-mailbericht verkrijgen

Voordat u een versleutelde e-mail kunt intrekken, verzamelt u de bericht-id van de e-mail. De MessageId heeft meestal de notatie:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Er zijn meerdere manieren om de bericht-id te vinden van het e-mailbericht dat u wilt intrekken. In deze sectie worden een aantal opties beschreven, maar u kunt elke methode gebruiken die de id bevat.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>De bericht-id van de e-mail die u wilt intrekken identificeren met Behulp van Bericht traceren in het Beveiligings &amp; compliancecentrum

1. Zoek naar de e-mail per afzender of geadresseerde met [behulp van Nieuwe bericht traceren in & Compliance center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).

2. Wanneer u de e-mail hebt gevonden, selecteert u deze om het detailvenster **Bericht traceren weer te** geven. Vouw **Meer informatie uit om** de bericht-id te zoeken.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>De bericht-id identificeren van de e-mail die u wilt intrekken met behulp Office berichtenversleutelingsrapporten in het Beveiligings &amp; compliancecentrum

1. Ga in het &amp; Beveiligings compliancecentrum naar het **rapport Berichtversleuteling.** Zie E-mailbeveiligingsrapporten weergeven in het Beveiligings compliancecentrum voor meer informatie over dit [ &amp; rapport.](../security/defender-365-security/view-email-security-reports.md)

2. Kies de **tabel Details weergeven** en identificeer het bericht dat u wilt intrekken.

3. Dubbelklik op het bericht om details weer te geven die de bericht-id bevatten.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Stap 2. Controleren of de e-mail kan worden herkeerbaar

Als u wilt controleren of u een bericht kunt intrekken, controleert u of het veld Intrekkingsstatus zichtbaar is in het rapport Versleuteling in de tabel **Details** in het Beveiligings &amp; compliancecentrum.

Als u wilt controleren of u een bepaald e-mailbericht kunt intrekken met Windows PowerShell, moet u deze stappen voltooien.

1. Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online. Zie Verbinding maken [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)voor instructies.

2. Voer de Get-OMEMessageStatus als volgt uit:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   Deze opdracht retourneert het onderwerp van het bericht en of het bericht kan worden herkeerbaar. Bijvoorbeeld:

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>Stap 3. De e-mail intrekken

Zodra u de bericht-id van de e-mail kent die u wilt intrekken en u hebt geverifieerd dat het bericht kan worden herroepen, kunt u de e-mail intrekken met behulp van het Beveiligings compliancecentrum of &amp; Windows PowerShell.

Het bericht intrekken via het Beveiligings &amp; compliancecentrum

1. Maak met een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie verbinding met het beveiligings- & Compliancecentrum.

2. Kies in **het versleutelingsrapport** in **de tabel Details** voor het bericht de optie Bericht **intrekken.**

Als u een e-mail wilt intrekken met Windows PowerShell, gebruikt u Set-OMEMessageRevocation cmdlet.

1. Gebruik een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie en Verbinding maken [powershell Exchange Online gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Voer de Set-OMEMessageRevocation als volgt uit:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. Als u wilt controleren of de e-mail is ingetrokken, Get-OMEMessageStatus de cmdlet als volgt uit:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    Als intrekking is gelukt, geeft de cmdlet het volgende resultaat:  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Meer informatie over Office 365 Advanced Message Encryption

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Office 365 Advanced Message Encryption - e-mailverloop](ome-advanced-expiration.md)

- [Beschrijving van berichtbeleid en complianceservice](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)