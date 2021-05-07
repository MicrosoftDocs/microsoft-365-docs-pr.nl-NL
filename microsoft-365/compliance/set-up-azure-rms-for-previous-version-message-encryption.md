---
title: Een Azure Rights Management instellen voor de vorige versie van berichtversleuteling
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: De vorige versie van Office 365-berichtversleuteling is afhankelijk van Microsoft Azure Rights Management (voorheen Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161974"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>Een Azure Rights Management instellen voor de vorige versie van berichtversleuteling

In dit onderwerp worden de stappen beschreven die u moet volgen om Azure Rights Management (RMS), onderdeel van Azure Information Protection, te activeren en in te stellen voor gebruik met de vorige versie van Office 365-berichtversleuteling (OME).

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Dit artikel is alleen van toepassing op de vorige versie van OME

Als u uw organisatie nog niet hebt verplaatst naar de nieuwe OME-mogelijkheden, maar u OME al hebt geïmplementeerd, is de informatie in dit artikel van toepassing op uw organisatie. Microsoft raadt u aan een plan te maken om over te gaan naar de nieuwe OME-mogelijkheden zodra dit redelijk is voor uw organisatie. Zie Nieuwe functies voor Office 365-berichtversleuteling instellen voor [instructies.](set-up-new-message-encryption-capabilities.md) Als u eerst wilt weten hoe de nieuwe mogelijkheden werken, bekijkt [u Office 365-berichtversleuteling.](ome.md) De rest van dit artikel verwijst naar OME-gedrag vóór de release van de nieuwe OME-mogelijkheden.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Vereisten voor het gebruik van de vorige versie van Office 365-berichtversleuteling
<a name="warmprereqs"> </a>

Office 365-berichtversleuteling (OME), inclusief IRM, is afhankelijk van Azure Rights Management (Azure RMS). Azure RMS is de beveiligingstechnologie die wordt gebruikt door Azure Information Protection. Als u OME wilt gebruiken, moet uw organisatie een abonnement Exchange Online of Exchange Online Protection dat op zijn beurt een Azure Rights Management bevat.
  
- Als u niet zeker weet wat uw abonnement bevat, bekijkt u Exchange Online servicebeschrijvingen voor [berichtenbeleid, herstel en naleving.](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

- Als u Azure Rights Management hebt, maar deze niet is ingesteld voor Exchange Online of Exchange Online Protection, wordt in dit artikel uitgelegd hoe u Azure Rights Management activeert en beschrijft u de beste manier om OME in te stellen voor het werken met Azure Rights Management.

- Als u OME al hebt ingesteld voor gebruik met Azure Rights Management voor Exchange Online of Exchange Online Protection, kunt u, afhankelijk van hoe u het hebt ingesteld, direct aan de slag met OME en de nieuwe mogelijkheden. In dit artikel wordt uitgelegd hoe u kunt bepalen of u OME correct hebt ingesteld, wat u moet doen als u de instelling wilt wijzigen en wat er gebeurt als u ervoor kiest de instelling niet te wijzigen. Als u bijvoorbeeld de nieuwe mogelijkheden wilt gebruiken, moet u Azure RMS met OME gebruiken. U kunt de nieuwe mogelijkheden niet gebruiken met een on-premises Active Directory RMS.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Activeer Azure Rights Management voor de vorige versie van OME in Office 365

U moet Azure Rights Management activeren zodat de gebruikers in uw organisatie informatiebeveiliging kunnen toepassen op berichten die ze verzenden en berichten en bestanden kunnen openen die zijn beveiligd door de Azure Rights Management service. Zie Activeren van Azure Rights Management voor [instructies.](/azure/information-protection/activate-service) Nadat u de activering hebt voltooid, keert u hier terug en gaat u verder met de taken in dit artikel.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>De vorige versie van OME instellen om Azure RMS te gebruiken door vertrouwde publicatiedomeinen (TPD's) te importeren

Een TPD is een XML-bestand dat informatie bevat over de instellingen voor rechtenbeheer van uw organisatie. De TPD bevat bijvoorbeeld informatie over het certificaat van de licentiegever voor de server (SLC) dat wordt gebruikt voor het ondertekenen en versleutelen van certificaten en licenties, de URL's die worden gebruikt voor licenties en publiceren, en meer. U importeert de TPD in uw organisatie met Windows PowerShell.
  
> [!IMPORTANT]
> Voorheen kon u ervoor kiezen om TPD's uit de Active Directory Rights Management-service (AD RMS) in uw organisatie te importeren. Dit voorkomt echter dat u de nieuwe OME-mogelijkheden gebruikt en wordt niet aanbevolen. Als uw organisatie op dit moment op deze manier is geconfigureerd, raadt Microsoft u aan een plan te maken om te migreren van uw on-premises Active Directory RMS naar Azure Information Protection in de cloud. Zie Migreren van AD RMS naar Azure Information Protection voor [meer informatie.](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) U kunt de nieuwe OME-mogelijkheden pas gebruiken als u de migratie naar Azure Information Protection hebt voltooid.
  
 **TPD's importeren vanuit Azure RMS**
  
1. [Verbinding maken om Exchange Online Externe PowerShell te gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Kies de URL voor het delen van sleutels die overeenkomt met de geografische locatie van uw organisatie:

|**Locatie**|**Url voor het delen van sleutels**|
|:-----|:-----|
|Noord-Amerika  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Europese Unie  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Azië  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Zuid-Amerika  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 voor de overheid (Government Community Cloud)  <br/> Deze RMS-locatie voor het delen van sleutels is gereserveerd voor klanten die een Office 365 voor SKU's van de overheid hebben gekocht.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. Configureer de locatie voor het delen van sleutels door [de cmdlet Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) als volgt uit te stellen: 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   Als u bijvoorbeeld de locatie voor het delen van sleutels wilt configureren als uw organisatie zich in Noord-Amerika bevindt:

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. Voer de [cmdlet Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) uit met de schakelknop -RMSOnline om de TPD te importeren uit Azure Rights Management: 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   Waarbij  *TPDName*  de naam is die u wilt gebruiken voor de TPD. Bijvoorbeeld 'Contoso North American TPD'. 

5. Als u wilt controleren of u uw organisatie hebt geconfigureerd voor het gebruik van de Azure Rights Management-service, moet u de [cmdlet Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) als volgt uitvoeren met de -RMSOnline-schakelknop:

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   Deze cmdlet controleert onder andere de connectiviteit met de Azure Rights Management service, downloadt de TPD en controleert de geldigheid.

6. Voer de [cmdlet Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) als volgt uit om Azure Rights Management-sjablonen uit te schakelen in Outlook web en Outlook: 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. Voer de cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) als volgt uit om Azure Rights Management in te stellen voor uw e-mailorganisatie in de cloud en deze te configureren voor Azure Rights Management voor Office 365-berichtversleuteling:

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. Als u wilt controleren of u de TPD hebt geïmporteerd en Azure Rights Management hebt ingeschakeld, gebruikt u de Test-IRMConfiguration cmdlet om de functionaliteit Azure Rights Management testen. Zie 'Voorbeeld 1' in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration)voor meer informatie.

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>Ik heb de vorige versie van OME ingesteld met Active Directory Rights Management niet Azure Information Protection, wat moet ik doen?
<a name="importTPDs"> </a>

U kunt uw bestaande Office 365-berichtversleuteling e-mailstroomregels blijven gebruiken met Active Directory Rights Management, maar u kunt de nieuwe OME-mogelijkheden niet configureren of gebruiken. In plaats daarvan moet u migreren naar Azure Information Protection. Zie Migreren van AD RMS naar Azure Information Protection voor informatie over migratie en wat dit betekent voor [uw organisatie.](/information-protection/deploy-use/prepare-environment-adrms)
  
## <a name="next-steps"></a>Volgende stappen
<a name="importTPDs"> </a>

Als u de configuratie van Azure Rights Management hebt voltooid en u de nieuwe OME-mogelijkheden wilt inschakelen, gaat u naar Nieuwe Office 365-berichtversleuteling-functies instellen die bovenop Azure Information Protection zijn [gebouwd.](./set-up-new-message-encryption-capabilities.md)
  
Nadat u uw organisatie hebt ingesteld voor het gebruik van de nieuwe OME-mogelijkheden, kunt u regels voor e-mailstroom definiëren om e-mailberichten te beveiligen met nieuwe [OME-mogelijkheden.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="related-topics"></a>Verwante onderwerpen
<a name="importTPDs"> </a>

[Versleuteling in Office 365](encryption.md)
  
[Technische naslaginformatie over versleuteling in Office 365](technical-reference-details-about-encryption.md)
  
[Wat is Azure Rights Management?](/information-protection/understand-explore/what-is-azure-rms)