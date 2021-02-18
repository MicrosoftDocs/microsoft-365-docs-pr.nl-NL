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
description: Een korte beschrijving van wat Exchange Online-beheerders moeten doen om de S/MIME-instellingen in de webversie van Outlook in Exchange Online te bekijken en te configureren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ccadfc46e42713601b115c18a119e48dcfdcbf4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290031"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="caaec-103">S/MIME-instellingen configureren in Exchange Online voor de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="caaec-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="caaec-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="caaec-104">**Applies to**</span></span>
- [<span data-ttu-id="caaec-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="caaec-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="caaec-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="caaec-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="caaec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="caaec-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="caaec-108">Als beheerder van Exchange Online kunt u de webversie van Outlook (voorheen Outlook Web App genoemd) zo instellen dat het verzenden en ontvangen van met S/MIME beveiligde berichten is toegestaan.</span><span class="sxs-lookup"><span data-stu-id="caaec-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="caaec-109">Gebruik de **cmdlets Get-SmimeConfig** en **Set-SmimeConfig** om deze functie in Exchange Online PowerShell weer te geven en te beheren.</span><span class="sxs-lookup"><span data-stu-id="caaec-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="caaec-110">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="caaec-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="caaec-111">Zie [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) en [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="caaec-111">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="caaec-112">Overwegingen voor de nieuwe Microsoft Edge (op basis van Chromium)</span><span class="sxs-lookup"><span data-stu-id="caaec-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="caaec-113">Als u S/MIME in de webversie van Outlook wilt gebruiken in de nieuwe webbrowser [Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) moet u (of een andere beheerder) het browserbeleid van Microsoft Edge met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie in de nieuwe Microsoft Edge te installeren.</span><span class="sxs-lookup"><span data-stu-id="caaec-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="caaec-114">De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="caaec-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="caaec-115">Houd er rekening mee dat voor het toepassen van dit beleid apparaten zijn vereist die lid zijn van een domein of apparaten die lid zijn van Azure AD. Voor het gebruik van S/MIME in de nieuwe browser Microsoft Edge zijn apparaten die lid zijn van een domein of apparaten die lid zijn van Azure AD, effectief vereist.</span><span class="sxs-lookup"><span data-stu-id="caaec-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="caaec-116">Zie **ExtensionInstallForcelist** voor meer informatie over het beleid [ExtensionInstallForcelist.](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)</span><span class="sxs-lookup"><span data-stu-id="caaec-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="caaec-117">Deze stap is een vereiste voor het gebruik van het nieuwe Microsoft Edge. Het vervangt niet de S/MIME-besturing die door gebruikers is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="caaec-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="caaec-118">Gebruikers wordt gevraagd om de S/MIME-besturing in de webversie van Outlook te downloaden en te installeren tijdens hun eerste gebruik van S/MIME.</span><span class="sxs-lookup"><span data-stu-id="caaec-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="caaec-119">Gebruikers kunnen ook proactief **naar S/MIME** gaan in hun instellingen voor de webversie van Outlook om de downloadkoppeling voor het besturingselement op te halen.</span><span class="sxs-lookup"><span data-stu-id="caaec-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="caaec-120">Aandachtspunten voor Chrome</span><span class="sxs-lookup"><span data-stu-id="caaec-120">Considerations for Chrome</span></span>

<span data-ttu-id="caaec-121">Als u S/MIME in de webversie van Outlook in de webbrowser Google Chrome wilt gebruiken, moet u (of een andere beheerder) het Chromium-beleid met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie te installeren in Chrome.</span><span class="sxs-lookup"><span data-stu-id="caaec-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="caaec-122">De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="caaec-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="caaec-123">Houd er rekening mee dat voor het toepassen van dit beleid computers zijn vereist die lid zijn van een domein. Voor het gebruik van S/MIME in Chrome hebt u dus computers nodig die lid zijn van een domein.</span><span class="sxs-lookup"><span data-stu-id="caaec-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="caaec-124">Zie **ExtensionInstallForcelist** voor meer informatie over het beleid [ExtensionInstallForcelist.](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)</span><span class="sxs-lookup"><span data-stu-id="caaec-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="caaec-125">Deze stap is een vereiste voor het gebruik van Chrome. Het vervangt niet de S/MIME-besturing die door gebruikers is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="caaec-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="caaec-126">Gebruikers wordt gevraagd om de S/MIME-besturing in de webversie van Outlook te downloaden en te installeren tijdens hun eerste gebruik van S/MIME.</span><span class="sxs-lookup"><span data-stu-id="caaec-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="caaec-127">Gebruikers kunnen ook proactief **naar S/MIME** gaan in hun instellingen voor de webversie van Outlook om de downloadkoppeling voor het besturingselement op te halen.</span><span class="sxs-lookup"><span data-stu-id="caaec-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="caaec-128">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="caaec-128">For more information</span></span>

[<span data-ttu-id="caaec-129">S/MIME voor het ondertekenen en versleutelen van berichten</span><span class="sxs-lookup"><span data-stu-id="caaec-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
