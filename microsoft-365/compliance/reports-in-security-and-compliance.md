---
title: Rapporten in het beveiligings- & compliancecentrum
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: Gebruik het Beveiligings- & compliancecentrum om verschillende rapporten te krijgen voor uw SharePoint Online en Exchange Online organisatie, plus Azure Active Directory rapporten.
ms.openlocfilehash: 3e72ecab68ece31c44d99f85806492e788f4cd7c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162114"
---
# <a name="reports-in-the-security--compliance-center"></a>Rapporten in het beveiligings- & compliancecentrum

U kunt de pagina **Rapporten weergeven** in het beveiligings- & compliancecentrum gebruiken om snel toegang te krijgen tot auditrapporten voor uw SharePoint Online en Exchange Online organisaties. U kunt ook toegang Azure Active Directory aanmeldingsrapporten, gebruikersactiviteitsrapporten en het Azure AD-auditlogboek op de pagina **Rapporten** weergeven. Dit komt omdat uw betaalde Microsoft 365 een gratis abonnement voor Microsoft Azure. De eerste keer dat u toegang probeert te krijgen tot deze Azure-rapporten, moet u een een-time registratieproces voltooien. 
  
> [!TIP]
> Zie Activiteitenrapporten in het [Microsoft 365-beheercentrum voor](../admin/activity-reports/activity-reports.md)meer rapporten over activiteiten in uw organisatie. 
  
 **Before you begin**
  
U hebt de volgende machtigingen nodig om rapporten weer te geven in het & Compliancecentrum.
  
- U moet de rol Beveiligingslezer krijgen toegewezen in het Exchange-beheercentrum (EAC) om rapporten weer te geven in het Beveiligings- & Compliancecentrum. Deze rol is standaard toegewezen aan de rollengroepen Organisatiebeheer en Beveiligingslezer in het EAC.
    
- U moet de rol View-Only DLP-compliancebeheer in het beveiligings- & compliancecentrum toegewezen krijgen om DLP-rapporten weer te geven in het Beveiligings- & Compliancecentrum. Deze rol is standaard toegewezen aan de rollengroepen Compliancebeheerder, Organisatiebeheer, Beveiligingsbeheerder en Beveiligingslezer in het beveiligingscentrum & Compliancecentrum.

- Daarnaast moet u de rol View-Only geadresseerden in het EAC krijgen toegewezen om DLP-rapporten in het EAC weer te geven. Deze rol is standaard toegewezen aan de rollengroepen Compliancebeheer, Organisatiebeheer en View-Only organisatiebeheer in het EAC.
  
 **De pagina Rapporten weergeven openen in het beveiligings- & compliancecentrum:**
  
1. Ga naar [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).
    
2. Meld u aan met de referenties voor een gebruikersaccount in uw organisatie.
    
Op de **pagina Rapporten** weergeven kunt u de volgende typen rapporten bekijken: 
  
- [Controlerapporten](#auditing-reports)
- [Controlerapport van toezicht](#supervisory-review-report)
- [Rapporten voor preventie van gegevensverlies](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>Controlerapporten

In de volgende tabel worden de rapporten  in de sectie **Controle** op de pagina Rapporten weergeven in het beveiligings- & compliancecentrum beschreven. 
  
|**Rapport**|**Beschrijving**|
|:-----|:-----|
|**auditlogboekrapport** <br/> |U kunt in het auditlogboek zoeken naar activiteiten van gebruikers en beheerders in uw organisatie. Het rapport bevat vermeldingen gebruikers- en beheerdersactiviteit in Exchange Online, SharePoint Online, OneDrive voor Bedrijven en Azure Active Directory, de adreslijstservice voor Office 365. Zie Het [auditlogboek](search-the-audit-log-in-security-and-compliance.md)doorzoeken in het Office 365.  <br/> |
|**Azure AD-rapporten** <br/> |Als u ongebruikelijke of verdachte aanmeldingsactiviteiten in uw organisatie wilt zoeken, kunt u aanmeldings- en activiteitenrapporten gebruiken in Microsoft Azure. U kunt ook gebeurtenissen weergeven in het Auditlogboek van Azure AD. Als u rapporten in Azure wilt weergeven, klikt u op **Azure AD-rapporten weergeven.** Zie voor meer informatie: <br/><br/>[Gebruik uw gratis Azure Active Directory abonnement in Office 365.](use-your-free-azure-ad-subscription-in-office-365.md) <br/> [Bekijk uw toegangs- en gebruiksrapporten.](/azure/active-directory/reports-monitoring/overview-reports)  <br/> |
|**Exchange controlerapporten** <br/> | U kunt de controlefunctionaliteit in Microsoft 365 gebruiken om wijzigingen bij te houden die zijn aangebracht in uw Exchange Online door de beheerders van uw organisatie. Wijzigingen die zijn aangebracht in Exchange Online organisatie door een beheerder van het Microsoft-datacenter of door een gedelegeerde beheerder, worden ook geregistreerd. Voor Exchange Online is auditregistratie van beheerders standaard ingeschakeld, zodat u niets hoeft te doen om de logboekregistratie in te stellen. Exchange Online biedt ook logboekregistratie voor postvakken om de toegang tot postvakken bij te houden door iemand anders dan de eigenaar van het postvak. U moet de logboekregistratie voor postvakken inschakelen voor elk postvak dat u niet-eigenaartoegang wilt bijhouden.  <br/>  Voor zowel beheerders- als postvakauditlogboekregistratie kunt u auditrapporten uitvoeren om de controlelogboekgegevens weer te laten zien. U kunt ook auditlogboeken voor postvakken en beheerders exporteren, die binnen 24 uur naar u worden verzonden in een XML-bestand dat is gekoppeld aan een e-mailbericht. <br/><br/>Zie voor meer informatie over het exporteren van auditlogboeken:  <br/><br/> [Auditlogboeken voor postvakken exporteren](/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) <br/> [Het auditlogboek voor datacenterbeheerders weergeven en exporteren](/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) <br/> [Zoeken in de rollengroepwijzigingen of auditlogboeken van beheerders](/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) <br/>   [Exchange controlerapporten](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).  <br/> |
   
## <a name="supervisory-review-report"></a>Controlerapport van toezicht

Met het controlerapport ziet u de status van alle beleidsregels voor toezichtsbeoordeling in uw organisatie. Zie Beleidsregels voor toezichtsbeoordeling [configureren voor uw organisatie voor meer informatie.](./communication-compliance-configure.md)
  
## <a name="data-loss-prevention-reports"></a>Rapporten voor preventie van gegevensverlies

DLP-rapporten (Data Loss Prevention) bevatten informatie over het DLP-beleid en de regels die zijn toegepast op inhoud die gevoelige gegevens in uw organisatie bevatten. U kunt het rapport ook zo configureren dat er informatie wordt weergegeven over DLP-acties die zijn gebaseerd op uw DLP-beleid en -regels. Zie Het rapport weergeven voor preventie van gegevensverlies voor [meer informatie.](view-the-dlp-reports.md)