---
title: De nieuwe mogelijkheden van Message Encryption instellen
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Meer informatie over de nieuwe mogelijkheden voor berichtversleuteling van Office 365 waarmee beveiligde e-mailcommunicatie mogelijk wordt met personen binnen en buiten uw organisatie.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cf37826c3e1e349947ab83fe211f9406a765e5ea
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162688"
---
# <a name="set-up-new-message-encryption-capabilities"></a>De nieuwe mogelijkheden van Message Encryption instellen

Met de nieuwe mogelijkheden voor berichtversleuteling van Office 365 kunnen organisaties beveiligde e-mail delen met iedereen, op elk apparaat. Gebruikers kunnen beveiligde berichten uitwisselen met andere Microsoft 365-organisaties en niet-klanten met Outlook.com, Gmail en andere e-mailservices.

Volg de onderstaande stappen om ervoor te zorgen dat de nieuwe OME-mogelijkheden beschikbaar zijn in uw organisatie.

## <a name="verify-that-azure-rights-management-is-active"></a>Controleren of Azure Rights Management actief is

De nieuwe mogelijkheden vaan OME maken gebruik van de beveiligingsfuncties in [Azure Rights Management Services (Azure RMS)](/azure/information-protection/what-is-information-protection), de technologie die door [Azure Information Protection](/azure/information-protection/what-is-azure-rms) wordt gebruikt om e-mailberichten en documenten te beveiligen via versleuteling en toegangscontrole.

De enige vereiste voor het gebruik van de nieuwe OME-mogelijkheden is dat [Azure Rights Management](/azure/information-protection/what-is-azure-rms) moet worden geactiveerd op de tenant van uw organisatie. Als dat zo is, activeert Microsoft 365 automatisch de nieuwe OME-mogelijkheden en hoeft u niets te doen.

Azure RMS wordt ook automatisch geactiveerd voor de meeste abonnementen die hiervoor in aanmerking komen, dus u hoeft hiervoor waarschijnlijk ook niets te doen. Zie [Azure Rights Management activeren](/azure/information-protection/activate-service) voor meer informatie.

>[!IMPORTANT]
>Als u de Active Directory Rights Management-service (AD RMS) gebruikt met Exchange Online, moet u [migreren naar Azure Information Protection](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) voordat u de nieuwe OME-mogelijkheden kunt gebruiken. OME is niet compatibel met AD RMS.  

Zie voor meer informatie:

- [Welke abonnementen heb ik nodig om de nieuwe OME-mogelijkheden te kunnen gebruiken?](ome-faq.yml#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities-) om te controleren of uw abonnement Azure Information Protection (met Azure RMS-functionaliteit) omvat.
- [Azure Information Protection](https://azure.microsoft.com/services/information-protection/) voor informatie over de aankoop van een in aanmerking komend abonnement.  

### <a name="manually-activating-azure-rights-management"></a>Azure Rights Management handmatig activeren

Als u Azure RMS heeft uitgeschakeld, of als het niet automatisch geactiveerd is, dan kunt u het handmatig activeren in het:

- **Beheercentrum van Microsoft 365**: zie [Azure Rights Management activeren vanuit het beheercentrum](/azure/information-protection/activate-office365) voor instructies.
- **Azure-portaal**: zie [Azure Rights Management activeren vanuit het Azure-portaal](/azure/information-protection/activate-azure) voor instructies.

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Beheer van de tenantsleutel van Azure Information Protection configureren

Deze stap is optioneel. Microsoft toestaan de hoofdsleutel voor Azure Information Protection te beheren, is de standaardinstelling en aanbevolen praktijk voor de meeste organisaties. Als dit het geval is, hoeft u niets te doen.

Er zijn diverse redenen, zoals compliancevereisten, waardoor u mogelijk uw eigen hoofdsleutel moet genereren en beheren (ook wel 'bring your own key' of BYOK). Als dit het geval is, raden we u aan de vereiste stappen uit te voeren voordat u de nieuwe OME-mogelijkheden instelt. Zie [Azure Information Protection-tenantsleutels plannen en implementeren](/information-protection/plan-design/plan-implement-tenant-key) voor meer informatie.

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>Nieuwe OME-configuratie controleren in Exchange Online PowerShell

U kunt controleren of uw Microsoft 365-tenant correct is geconfigureerd voor het gebruik van de nieuwe OME-mogelijkheden in [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell).
  
1. [Maak verbinding met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) met een account met algemene beheerdersmachtigingen in uw Microsoft 365-tenant.

2. Voer de cmdlet Get-OrganizationConfig uit.

     U ziet nu een waarde $True voor de parameter AzureRMSLicensingEnabled, wat aangeeft dat OME is geconfigureerd in uw tenant. Als dat niet zo is, gebruikt u Set-IRMConfiguration om de waarde van AzureRMSLicensingEnabled in te stellen op $True om OME in te schakelen.

3. Voer de cmdlet Test-IRMConfiguration uit met de volgende syntaxis:

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **Voorbeeld**:

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - Een e-mailadres van afzender opgeven is optioneel, maar indien u dit doet moet het systeem extra controles uitvoeren. Gebruik het e-mailadres van een gebruiker in uw Microsoft 365-tenant.

     Uw resultaten zouden vergelijkbaar moeten zijn met:

     ```text
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - De naam van uw organisatie vervangt *Contoso*.

   - De standaard sjabloonnamen kunnen afwijken van de namen die hierboven worden weergegeven. Zie [Sjablonen voor Azure Information Protection configureren en beheren](/azure/information-protection/configure-policy-templates) voor meer informatie.

4. Voer de cmdlet Remove-PSSession uit om de verbinding met de Rights Management-service te verbreken.

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a>Volgende stappen: e-mailstroomregels definiëren om nieuwe OME-mogelijkheden te gebruiken

Als er eerder e-mailstroomregels werden geconfigureerd om e-mail in uw organisatie te versleutelen, moet u de bestaande regels bijwerken om de nieuwe OME-mogelijkheden te kunnen gebruiken. Voor nieuwe implementaties moet u nieuwe e-mailstroomregels aanmaken.

>[!IMPORTANT]
>Als u bestaande e-mailstroomregels niet bijwerkt, blijven uw gebruikers versleutelde e-mail ontvangen die de vorige HTML-bijlageindeling gebruikt, in plaats van de nieuwe, probleemloze OME-ervaring.

E-mailstroomregels bepalen onder welke voorwaarden e-mailberichten moeten worden versleuteld, evenals voorwaarden voor het verwijderen van die versleuteling. Wanneer u een actie voor een regel in stelt, worden alle berichten die voldoen aan de voorwaarden voor de regel versleuteld bij verzending.
  
Zie [Regels voor de e-mailstroom definiëren om e-mailberichten in Office 365 te versleutelen in Office 365 voor](define-mail-flow-rules-to-encrypt-email.md) voor stappen om e-mailstroomregels voor OME aan te maken.

Bestaande regels bijwerken om de nieuwe OME-mogelijkheden te gebruiken:

1. Ga in het Microsoft 365-beheercentrum naar **Beheercentrum > Exchange**.
2. Ga in het Exchange-beheercentrum naar **E-mailstroom > Regels**.
3. Doe voor elke regel **het volgende**:
    - Selecteer **Het beveiligingsbeleid voor berichten wijzigen**.
    - Selecteer **Office 365-berichtversleuteling en rechtenbescherming toepassen**.
    - Selecteer een RMS-sjabloon in de lijst.
    - Selecteer **Opslaan**.
    - Selecteer **OK**.