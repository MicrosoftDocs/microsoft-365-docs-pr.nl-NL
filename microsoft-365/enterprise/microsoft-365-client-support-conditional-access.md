---
title: Ondersteuning voor Microsoft 365 client-apps – voorwaardelijke toegang
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: In dit artikel vindt u informatie over welke platforms, clients en PowerShell-modules voorwaardelijke toegang voor Microsoft 365 ondersteunen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fd4dcaeda27f12427f3175b7ec52e2fdb0c153da
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546510"
---
# <a name="microsoft-365-client-app-support--conditional-access"></a>Ondersteuning voor Microsoft 365 client-apps – voorwaardelijke toegang

In de moderne werknemer hebben gebruikers toegang tot de bronnen van uw organisatie met behulp van diverse apparaten en apps, waar u ook bent. Daarom is het dus niet voldoende om aan te geven wie toegang heeft tot een resource. Uw organisatie moet ook ondersteunen hoe en waar een resource in de infrastructuur van toegangsbeheer wordt geopend.

Met Azure Active Directory (Azure AD)-apparaat, locatie en meervoudige verificatie op basis van een voorwaardelijke toegang kunt u aan deze nieuwe vereiste voldoen. Voorwaardelijke toegang is een mogelijkheid van Azure AD waarmee u de toegang tot apps in uw omgeving kunt beheren op basis van specifieke voorwaarden en vanaf een centrale locatie.

Meer informatie over [Azure AD-beleid voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/).

## <a name="supported-platforms"></a>Ondersteunde platformen

 - Bureaublad van Windows 10
 - Moderne Windows 10-apps
 - Webbrowsers
 - Android
 - Apparaten
 - macOS<sup>1</sup>

Zie [systeemvereisten voor Microsoft 365](https://products.office.com/office-system-requirements)voor meer informatie over platform ondersteuning in microsoft 365.

## <a name="supported-clients"></a>Ondersteunde clients

De meest recente versies van de volgende clients ondersteunen voorwaardelijke toegang:

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure-pictogram](../media/o365-azure-64x64.png) <br> [Azure AD- <br> Portal ](https://azure.microsoft.com/features/azure-portal/) | ![Pictogram toegang](../media/o365-access-64x64.png) <br> [Toegang](https://products.office.com/access) | ![Pictogram voor bedrijfsportal](../media/o365-microsoft-64x64.png) <br> [Bedrijfs <br> Portal ](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal)  | ![Pictogram Cortana](../media/o365-cortana-64x64.png) <br> [Cortana](https://www.microsoft.com/cortana) | ![Pictogram Delve](../media/o365-delve-64x64.png) <br> [Delve](https://products.office.com/business/intelligent-search) 
| ![Dynamics 365-pictogram](../media/o365-dynamics365-64x64.png) <br> [Dynamics 365](https://dynamics.microsoft.com) | ![Pictogram Edge](../media/o365-edge-64x64.png) <br> [Allernieuwste](https://www.microsoft.com/windows/microsoft-edge) | ![Pictogram Exchange](../media/o365-exchange-64x64.png) <br> [Exchange](https://products.office.com/exchange/exchange-online) | ![Excel-pictogram](../media/o365-excel-64x64.png) <br> [Excel](https://products.office.com/excel) | ![Formulier pictogram](../media/o365-forms-64x64.png) <br> [Forms](https://flow.microsoft.com/connectors/shared_microsoftforms/microsoft-forms/) 
| ![Kaizala-pictogram](../media/o365-kaizala-64x64.png) <br> [Kaizala](https://products.office.com/en/business/microsoft-kaizala) | ![Office.com-pictogram](../media/o365-office-64x64.png) <br> [Office.com](https://www.office.com/) | ![Lens pictogram](../media/o365-lens-64x64.png) <br> [Office Lens](https://www.microsoft.com/p/office-lens/9wzdncrfj3t8?activetab=pivot%3Aoverviewtab) | ![Pictogram Office 365-beheerder](../media/o365-o365admin-64x64.png) <br> [Microsoft 365- <br> beheerder](https://products.office.com/business/manage-office-365-admin-app) | ![OneDrive voor bedrijven-pictogram](../media/o365-OneDrive-64x64.png) <br> [OneDrive<sup>1</sup>](https://products.office.com/onedrive-for-business/online-cloud-storage) 
| ![OneNote-pictogram](../media/o365-OneNote-64x64.png) <br> [OneNote](https://products.office.com/onenote) | ![Outlook-pictogram](../media/o365-outlook-64x64.png) <br> [Outlook](https://products.office.com/outlook) | ![Pictogram planner](../media/o365-planner-64x64.png) <br> [Planner](https://products.office.com/business/task-management-software) | ![PowerApps-pictogram](../media/o365-powerapps-64x64.png) <br> [PowerApps](https://powerapps.microsoft.com) | ![Pictogram Power automatisch automatiseren](../media/o365-flow-64x64.png) <br> [Automatisch aan de macht <br>](https://flow.microsoft.com)
| ![PowerBI-pictogram](../media/o365-powerbi-64x64.png) <br> [Power BI](https://powerbi.microsoft.com) | ![PowerPoint-pictogram](../media/o365-powerpoint-64x64.png) <br> [PowerPoint](https://products.office.com/powerpoint) | ![Project-pictogram](../media/o365-project-64x64.png) <br> [Project](https://products.office.com/project) | ![Publisher-pictogram](../media/o365-publisher-64x64.png) <br> [Publisher](https://products.office.com/publisher) | ![SharePoint-pictogram](../media/o365-sharepoint-64x64.png) <br> [Point](https://products.office.com/sharepoint) 
| ![Skype voor bedrijven-pictogram](../media/o365-skypeforbusiness-64x64.png) <br> [Skype voor <br> bedrijven](https://www.skype.com/business/) | ![Pictogram Sticky Notes](../media/o365-stickynotes-64x64.png) <br> [Sticky Notes](https://www.microsoft.com/p/microsoft-sticky-notes/9nblggh4qghw) | ![Pictogram stream](../media/o365-stream-64x64.png) <br> [Stream](https://stream.microsoft.com) | ![Sway-pictogram](../media/o365-sway-64x64.png) <br> [Sway](https://sway.com) | ![Pictogram teams](../media/o365-teams-64x64.png) <br> [Teams](https://products.office.com/microsoft-teams/group-chat-software) 
| ![Pictogram taak](../media/o365-todo-64x64.png) <br> [Taak](https://todo.microsoft.com) | ![Visio-pictogram](../media/o365-visio-64x64.png) <br> [Visio](https://products.office.com/visio/flowchart-software) | ![Word-pictogram](../media/o365-word-64x64.png) <br> [Word](https://products.office.com/word) | ![Pictogram Yammer](../media/o365-yammer-64x64.png) <br> [Yammer](https://products.office.com/yammer/yammer-overview)

## <a name="supported-powershell-modules"></a>Ondersteunde PowerShell-modules

| | | | | | |
|:---:|:---:|:---:|:---:|:---:|:---:|
| ![Azure-pictogram](../media/o365-azure-64x64.png) <br> [Azure AD <br> PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) | ![Pictogram Exchange](../media/o365-exchange-64x64.png) <br> [Exchange Online <br> PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) | ![SharePoint-pictogram](../media/o365-sharepoint-64x64.png) <br> [SharePoint Online- <br> PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

> [!NOTE]
> <sup>1</sup> ondersteuning voor OneDrive op macOS is binnenkort beschikbaar.

## <a name="see-also"></a>Raadpleeg ook

[Overzicht van Microsoft 365 Enterprise](microsoft-365-overview.md)
