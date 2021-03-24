---
title: S/MIME-instellingen configureren - Exchange Online voor de webversie van Outlook
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Een korte beschrijving van wat Exchange Online-beheerders moeten doen om de S/MIME-instellingen in de webversie van Outlook in Exchange Online weer te geven en te configureren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6eacc6a264682474054d0d3546b831039bee9a0c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058946"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="e22ae-103">S/MIME-instellingen configureren in de webversie van Exchange Online voor Outlook</span><span class="sxs-lookup"><span data-stu-id="e22ae-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e22ae-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="e22ae-104">**Applies to**</span></span>
- [<span data-ttu-id="e22ae-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e22ae-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e22ae-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e22ae-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e22ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e22ae-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e22ae-108">Als beheerder van Exchange Online kunt u de webversie van Outlook (voorheen Bekend als Outlook Web App) zo instellen dat u met S/MIME beveiligde berichten kunt verzenden en ontvangen.</span><span class="sxs-lookup"><span data-stu-id="e22ae-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="e22ae-109">Gebruik de **cmdlets Get-SmimeConfig** en **Set-SmimeConfig** om deze functie weer te geven en te beheren in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e22ae-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="e22ae-110">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e22ae-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="e22ae-111">Zie [Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) en [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="e22ae-111">For detailed syntax and parameter information, see [Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="e22ae-112">Aandachtspunten voor nieuwe Microsoft Edge (op Chromium gebaseerde)</span><span class="sxs-lookup"><span data-stu-id="e22ae-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="e22ae-113">Als u S/MIME wilt gebruiken in de webversie van Outlook in de nieuwe [Microsoft Edge-webbrowser,](https://www.microsoft.com/windows/microsoft-edge) moet u (of een andere beheerder) het Microsoft Edge-browserbeleid **extensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie in de nieuwe Microsoft Edge te installeren.</span><span class="sxs-lookup"><span data-stu-id="e22ae-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="e22ae-114">De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="e22ae-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="e22ae-115">En houd er rekening mee dat voor het toepassen van dit beleid domeingevoegde of Azure AD-apparaten zijn vereist, dus voor het gebruik van S/MIME in de nieuwe Microsoft Edge-browser zijn apparaten met domein- of Azure AD-apparaten effectief vereist.</span><span class="sxs-lookup"><span data-stu-id="e22ae-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="e22ae-116">Zie [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)voor meer informatie over het **beleid van ExtensionInstallForcelist.**</span><span class="sxs-lookup"><span data-stu-id="e22ae-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="e22ae-117">Deze stap is een vereiste voor het gebruik van nieuwe Microsoft Edge. het S/MIME-besturingselement dat door gebruikers is geïnstalleerd, wordt niet vervangen.</span><span class="sxs-lookup"><span data-stu-id="e22ae-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="e22ae-118">Gebruikers worden gevraagd het besturingselement S/MIME te downloaden en te installeren in de webversie van Outlook tijdens het eerste gebruik van S/MIME.</span><span class="sxs-lookup"><span data-stu-id="e22ae-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="e22ae-119">Of gebruikers kunnen proactief naar **S/MIME** gaan in de webinstellingen van Outlook om de downloadkoppeling voor het besturingselement te downloaden.</span><span class="sxs-lookup"><span data-stu-id="e22ae-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="e22ae-120">Aandachtspunten voor Chrome</span><span class="sxs-lookup"><span data-stu-id="e22ae-120">Considerations for Chrome</span></span>

<span data-ttu-id="e22ae-121">Als u S/MIME wilt gebruiken in de webversie van Outlook in de webbrowser van Google Chrome, moet u (of een andere beheerder) het Chromium-beleid met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie in Chrome te installeren.</span><span class="sxs-lookup"><span data-stu-id="e22ae-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="e22ae-122">De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="e22ae-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="e22ae-123">En houd er rekening mee dat voor het toepassen van dit beleid domeincomputers zijn vereist, dus voor het gebruik van S/MIME in Chrome zijn computers met domeinen effectief vereist.</span><span class="sxs-lookup"><span data-stu-id="e22ae-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="e22ae-124">Zie [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)voor meer informatie over het **beleid van ExtensionInstallForcelist.**</span><span class="sxs-lookup"><span data-stu-id="e22ae-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="e22ae-125">Deze stap is een vereiste voor het gebruik van Chrome. het S/MIME-besturingselement dat door gebruikers is geïnstalleerd, wordt niet vervangen.</span><span class="sxs-lookup"><span data-stu-id="e22ae-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="e22ae-126">Gebruikers worden gevraagd het besturingselement S/MIME te downloaden en te installeren in de webversie van Outlook tijdens het eerste gebruik van S/MIME.</span><span class="sxs-lookup"><span data-stu-id="e22ae-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="e22ae-127">Of gebruikers kunnen proactief naar **S/MIME** gaan in de webinstellingen van Outlook om de downloadkoppeling voor het besturingselement te downloaden.</span><span class="sxs-lookup"><span data-stu-id="e22ae-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="e22ae-128">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="e22ae-128">For more information</span></span>

[<span data-ttu-id="e22ae-129">S/MIME voor het ondertekenen en versleutelen van berichten</span><span class="sxs-lookup"><span data-stu-id="e22ae-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)