---
title: S/MIME-instellingen configureren-Exchange Online voor Outlook op het web
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Een korte beschrijving van wat Exchange Online-beheerders nodig hebben om de S/MIME-instellingen in de webversie van Outlook in Exchange Online weer te geven en te configureren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe561c3a66cf2e7bdb76aabe10ffc875d85f2d77
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203333"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="d5832-103">S/MIME-instellingen configureren in Exchange Online voor de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="d5832-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d5832-104">Als beheerder van Exchange Online kunt u de webversie van Outlook (voorheen Outlook Web app) instellen voor het verzenden en ontvangen van e-mailberichten die/of MIME-beveiliging zijn.</span><span class="sxs-lookup"><span data-stu-id="d5832-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="d5832-105">Met de cmdlet **Get-SmimeConfig** en **set-SmimeConfig** kunt u deze functie weergeven en beheren in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5832-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="d5832-106">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5832-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="d5832-107">Zie [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) en [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)voor gedetailleerde syntaxis-en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="d5832-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="d5832-108">Aandachtspunten voor nieuwe Microsoft Edge (op basis van chroom)</span><span class="sxs-lookup"><span data-stu-id="d5832-108">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="d5832-109">Als u S/MIME in de webversie van Outlook wilt gebruiken in de nieuwe webbrowser van [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) , moet u (of een andere beheerder) het browser beleid Microsoft Edge met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie te installeren in de nieuwe Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="d5832-109">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="d5832-110">De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="d5832-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="d5832-111">En houd er rekening mee dat het toepassen van dit beleid vereist domein aanmerkt of Azure AD-bijgevoegde apparaten, dus als u S/MIME in de nieuwe Microsoft Edge-browser wilt gebruiken, moet u domeinnaam of Azure AD-gekoppelde apparaten gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d5832-111">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="d5832-112">Zie [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)voor meer informatie over het **ExtensionInstallForcelist** -beleid.</span><span class="sxs-lookup"><span data-stu-id="d5832-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="d5832-113">Deze stap is een vereiste voor het gebruik van nieuwe Microsoft Edge. het vervangt niet het S/MIME-besturingselement dat door gebruikers is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="d5832-113">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="d5832-114">Gebruikers wordt gevraagd om de S/MIME-besturing te downloaden en te installeren in de webversie van Outlook, wanneer ze het eerst gebruiken met S/MIME.</span><span class="sxs-lookup"><span data-stu-id="d5832-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="d5832-115">Gebruikers kunnen ook proactief naar **S/MIME** in de webversie van Outlook gaan om de downloadkoppeling voor het besturingselement te downloaden.</span><span class="sxs-lookup"><span data-stu-id="d5832-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="d5832-116">Aandachtspunten voor Chrome</span><span class="sxs-lookup"><span data-stu-id="d5832-116">Considerations for Chrome</span></span>

<span data-ttu-id="d5832-117">Als u S/MIME in de webversie van Outlook wilt gebruiken in de webversie van Google Chrome, moet u (of een andere beheerder) het Chrome-beleid met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie te installeren in Chrome.</span><span class="sxs-lookup"><span data-stu-id="d5832-117">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="d5832-118">De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="d5832-118">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="d5832-119">En houd er rekening mee dat bij het toepassen van dit beleid toegevoegde domein-computers zijn vereist, zodat de domeinnamen voor domeinnamen in Chrome naar behoren worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="d5832-119">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="d5832-120">Zie [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)voor meer informatie over het **ExtensionInstallForcelist** -beleid.</span><span class="sxs-lookup"><span data-stu-id="d5832-120">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="d5832-121">Deze stap is een vereiste voor het gebruik van Chrome. het vervangt niet het S/MIME-besturingselement dat door gebruikers is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="d5832-121">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="d5832-122">Gebruikers wordt gevraagd om de S/MIME-besturing te downloaden en te installeren in de webversie van Outlook, wanneer ze het eerst gebruiken met S/MIME.</span><span class="sxs-lookup"><span data-stu-id="d5832-122">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="d5832-123">Gebruikers kunnen ook proactief naar **S/MIME** in de webversie van Outlook gaan om de downloadkoppeling voor het besturingselement te downloaden.</span><span class="sxs-lookup"><span data-stu-id="d5832-123">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="d5832-124">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="d5832-124">For more information</span></span>

[<span data-ttu-id="d5832-125">S/MIME voor het ondertekenen en versleutelen van berichten</span><span class="sxs-lookup"><span data-stu-id="d5832-125">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
