---
title: IRM configureren voor gebruik van een on-premises AD RMS-server
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: Informatie over het configureren van IRM (Information Rights Management) in Exchange Online om een AD RMS-server (Active Directory Rights Management Service) te gebruiken.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c42d793639a9efaf94e3222a172ea192d1e03d3
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227233"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>IRM configureren voor gebruik van een on-premises AD RMS-server

Voor gebruik met on-premises implementaties gebruikt IRM (Information Rights Management) in Exchange Online Active Directory Rights Management Services (AD RMS), een informatiebeveiligingstechnologie in Windows Server 2008 en hoger. IRM-beveiliging wordt toegepast op e-mail door een AD RMS-beleidssjabloon voor rechten toe te passen op een e-mailbericht. Rechten zijn gekoppeld aan het bericht zelf, zodat de beveiliging online en offline en binnen en buiten de firewall van uw organisatie plaatsvindt.

In dit onderwerp ziet u hoe u IRM configureert voor het gebruik van een AD RMS-server. Zie de veelgestelde vragen over het gebruik van de nieuwe Office 365-berichtversleuteling voor Azure Active Directory en Azure Rights Management [Office 365-berichtversleuteling.](./ome-faq.yml)

Zie Information Rights Management in Exchange Online voor meer informatie over IRM [in Exchange Online.](information-rights-management-in-exchange-online.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Geschatte tijd om deze taak te voltooien: 30 minuten

- U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie de vermelding 'Information Rights Management' in het onderwerp Berichtbeleid en [compliancemachtigingen](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions) om te zien welke machtigingen u nodig hebt.

- De AD RMS-server moet worden uitgevoerd Windows Server 2008 of hoger. Zie Een [AD RMS-cluster installeren](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11))voor meer informatie over het implementeren van AD RMS.

- Zie Voor meer informatie over het installeren en configureren Windows PowerShell en verbinding maken met de service, Verbinding maken om Exchange Online [Remote PowerShell te gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell)

- Zie Sneltoetsen voor het Exchange beheercentrum in Exchange Online voor informatie over sneltoetsen die van toepassing kunnen zijn op de procedures [in dit onderwerp.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Hebt u problemen? Vraag om hulp in de Exchange forums. Ga naar de forums [op Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)of [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="how-do-you-do-this"></a>Hoe doet u dit?
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>Stap 1: De AD RMS-console gebruiken om een vertrouwde publicatiedomein (TPD) te exporteren vanaf een AD RMS-server

De eerste stap is het exporteren van een vertrouwd publicatiedomein (TPD) van de on-premises AD RMS-server naar een XML-bestand. De TPD bevat de volgende instellingen die nodig zijn voor het gebruik van RMS-functies:

- Het serverlicentiecertificaat (SLC) dat wordt gebruikt voor het ondertekenen en versleutelen van certificaten en licenties

- De URL's die worden gebruikt voor licenties en publiceren

- De AD RMS-sjablonen voor rechtenbeleid die zijn gemaakt met de specifieke SLC voor die TPD

Wanneer u de TPD importeert, wordt deze opgeslagen en beveiligd in Exchange Online.

1. Open de Active Directory Rights Management Services console en vouw het AD RMS-cluster uit.

2. Vouw in de consolestructuur Het **vertrouwensbeleid uit** en klik vervolgens **op Vertrouwde publicatiedomeinen.**

3. Selecteer in het deelvenster Resultaten het certificaat voor het domein dat u wilt exporteren.

4. Klik in **het deelvenster** Acties op **Vertrouwde publicatiedomein exporteren.**

5. Klik in **het vak Publicatiedomeinbestand** op **Opslaan als** om het bestand op te slaan op een specifieke locatie op de lokale computer. Typ een bestandsnaam, geef de bestandsnaamextensie op `.xml` en klik op **Opslaan.**

6. Typ in **de** vakken **Wachtwoord** en Wachtwoord bevestigen een sterk wachtwoord dat wordt gebruikt om het vertrouwde publicatiedomeinbestand te versleutelen. U moet dit wachtwoord opgeven wanneer u de TPD importeert in uw e-mailorganisatie in de cloud.

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>Stap 2: Gebruik de Exchange Management Shell om de TPD te importeren in Exchange Online

Nadat de TPD is geëxporteerd naar een XML-bestand, moet u het importeren in Exchange Online. Wanneer een TPD wordt geïmporteerd, worden de AD RMS-sjablonen van uw organisatie ook geïmporteerd. Wanneer de eerste TPD wordt geïmporteerd, wordt deze de standaard TPD voor uw cloudorganisatie. Als u een andere TPD  importeert, kunt u de standaardschakelknop gebruiken om deze de standaard TPD te maken die beschikbaar is voor gebruikers.

Als u de TPD wilt importeren, moet u de volgende opdracht uitvoeren in Windows PowerShell:

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

U kunt de waarden voor de _parameters ExtranetLicensingUrl_ en _IntranetLicensingUrl_ in de Active Directory Rights Management Services verkrijgen. Selecteer het AD RMS-cluster in de consolestructuur. De licentie-URL's worden weergegeven in het resultatenvenster. Deze URL's worden gebruikt door e-mail clients wanneer inhoud moet worden ontsleuteld en wanneer Exchange Online moet bepalen welke TPD moet worden gebruikt.

Wanneer u deze opdracht uit te voeren, wordt u gevraagd om een wachtwoord. Voer het wachtwoord in dat u hebt opgegeven toen u de TPD exporteerde vanaf uw AD RMS-server.

Met de volgende opdracht wordt bijvoorbeeld de TPD met de naam Geëxporteerde TPD geïmporteerd met het XML-bestand dat u hebt geëxporteerd vanaf uw AD RMS-server en opgeslagen op het bureaublad van het Administrator-account. De parameter Naam wordt gebruikt om een naam op te geven voor de TPD.

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

Zie [Import-RMSTrustedPublishingDomain (Importeren-RMSTrustedPublishingDomain)](/powershell/module/exchange/import-rmstrustedpublishingdomain)voor gedetailleerde syntaxis- en parametergegevens.

#### <a name="how-do-you-know-this-step-worked"></a>Hoe weet u dat deze stap heeft gewerkt?

Als u wilt controleren of u de TPD hebt geïmporteerd, kunt u de **cmdlet Get-RMSTrustedPublishingDomain** uitvoeren om TPD's op te halen in uw Exchange Online organisatie. Zie de voorbeelden in [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain)voor meer informatie.

### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>Stap 3: Gebruik de Exchange Management Shell om een AD RMS-beleidssjabloon voor rechten te distribueren

Nadat u de TPD hebt geïmporteerd, moet u ervoor zorgen dat een AD RMS-beleidssjabloon voor rechten is verdeeld. Een gedistribueerde sjabloon is zichtbaar webversie van Outlook (voorheen bekend als Outlook Web App) gebruikers, die de sjablonen vervolgens kunnen toepassen op een e-mailbericht.

Voer de volgende opdracht uit als u een lijst wilt retourneren met alle sjablonen in de standaard-TPD:

```powershell
Get-RMSTemplate -Type All | fl
```

Als de waarde van de parameter  _Type_  `Archived` is, is de sjabloon niet zichtbaar voor gebruikers. Alleen gedistribueerde sjablonen in de standaard-TPD zijn beschikbaar in webversie van Outlook.

Voer de volgende opdracht uit om een sjabloon te distribueren:

```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

Met de volgende opdracht wordt bijvoorbeeld de sjabloon Bedrijfs vertrouwelijk geïmporteerd.

```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

Zie [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) en [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate)voor gedetailleerde syntaxis- en parametergegevens.

**De sjabloon Niet doorsturen**

Wanneer u de standaard-TPD uit uw on-premises organisatie importeert in Exchange Online, wordt een AD RMS-beleidssjabloon met de naam Niet doorsturen geïmporteerd.  Deze sjabloon wordt standaard gedistribueerd wanneer u de standaard-TPD importeert. U kunt de cmdlet **Set-RMSTemplate** niet gebruiken om de sjabloon Niet doorsturen **te** wijzigen.

Wanneer de **sjabloon Niet doorsturen** is toegepast op een bericht, kunnen alleen de geadresseerden die in het bericht zijn geadresseerd, het bericht lezen. Bovendien kunnen geadresseerden het volgende niet doen:

- Het bericht doorsturen naar een andere persoon.

- Inhoud uit het bericht kopiëren.

- Druk het bericht af.

> [!IMPORTANT]
> De **sjabloon Niet** doorsturen kan niet voorkomen dat gegevens in een bericht worden gekopieerd met schermopnameprogramma's, camera's of gebruikers die de gegevens handmatig transcriberen

U kunt extra AD RMS-sjablonen voor rechtenbeleid maken op de AD RMS-server in uw on-premises organisatie om te voldoen aan uw IRM-beveiligingsvereisten. Als u aanvullende AD RMS-sjablonen voor rechtenbeleid maakt, moet u de TPD opnieuw exporteren van de on-premises AD RMS-server en de TPD vernieuwen in de cloud-e-mailorganisatie.

#### <a name="how-do-you-know-this-step-worked"></a>Hoe weet u dat deze stap heeft gewerkt?

Voer de **cmdlet Get-RMSTemplate** uit om de eigenschappen van de sjabloon te controleren om te controleren of u de sjabloon hebt gedistribueerd en of de beleidssjabloon VOOR AD RMS-rechten is gedistribueerd. Zie de voorbeelden in [Get-RMSTemplate voor meer informatie.](/powershell/module/exchange/get-rmstemplate)

### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>Stap 4: Gebruik de Exchange Management Shell om IRM in te stellen

Nadat u de TPD hebt geïmporteerd en een AD RMS-beleidssjabloon voor rechten hebt verdeeld, kunt u de volgende opdracht uitvoeren om IRM in te stellen voor uw e-mailorganisatie in de cloud.

```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

Zie [Set-IRMConfiguration (Set-IRMConfiguration)](/powershell/module/exchange/set-irmconfiguration)voor gedetailleerde syntaxis- en parametergegevens.

#### <a name="how-do-you-know-this-step-worked"></a>Hoe weet u dat deze stap heeft gewerkt?

Als u wilt controleren of IRM is ingeschakeld, moet u de [cmdlet Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) uitvoeren om de IRM-configuratie in de Exchange Online controleren.

## <a name="how-do-you-know-this-task-worked"></a>Hoe weet u dat deze taak heeft gewerkt?
<a name="sectionSection2"> </a>

Ga als volgt te werk om te controleren of u de TPD hebt geïmporteerd en IRM hebt ingeschakeld:

- Gebruik de **cmdlet Test-IRMConfiguration** om de IRM-functionaliteit te testen. Zie 'Voorbeeld 1' in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration)voor meer informatie.

- Stel een nieuw bericht op in webversie van Outlook IRM-beveiligen door de optie Machtigingen instellen in het uitgebreide menu  ![ (Pictogram Meer opties) te ](../media/ITPro-EAC-MoreOptionsIcon.gif) selecteren.
