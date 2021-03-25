---
title: Problemen met onboarding en foutberichten oplossen
description: Problemen met onboarding en foutmelding oplossen tijdens het voltooien van de installatie van Microsoft Defender voor Eindpunt.
keywords: probleemoplossing, probleemoplossing, Azure Active Directory, onboarding, foutbericht, foutberichten, Microsoft Defender voor eindpunt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 1b769c1b3e4201802ea6150358568bf57894d305
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185803"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a><span data-ttu-id="e4a55-104">Problemen met abonnementen en portaltoegang oplossen</span><span class="sxs-lookup"><span data-stu-id="e4a55-104">Troubleshoot subscription and portal access issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e4a55-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e4a55-105">**Applies to:**</span></span>
- [<span data-ttu-id="e4a55-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="e4a55-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e4a55-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4a55-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e4a55-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e4a55-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e4a55-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e4a55-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

<span data-ttu-id="e4a55-110">Op deze pagina vindt u gedetailleerde stappen om problemen op te lossen die kunnen optreden bij het instellen van uw Microsoft Defender voor Eindpunt-service.</span><span class="sxs-lookup"><span data-stu-id="e4a55-110">This page provides detailed steps to troubleshoot issues that might occur when setting up your Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="e4a55-111">Als u een foutbericht ontvangt, geeft het Microsoft Defender-beveiligingscentrum een gedetailleerde uitleg over wat het probleem is en worden relevante koppelingen verstrekt.</span><span class="sxs-lookup"><span data-stu-id="e4a55-111">If you receive an error message, Microsoft Defender Security Center will provide a detailed explanation on what the issue is and relevant links will be supplied.</span></span>

## <a name="no-subscriptions-found"></a><span data-ttu-id="e4a55-112">Geen abonnementen gevonden</span><span class="sxs-lookup"><span data-stu-id="e4a55-112">No subscriptions found</span></span>

<span data-ttu-id="e4a55-113">Als u tijdens het openen van  het Microsoft Defender-beveiligingscentrum een bericht krijgt dat er geen abonnementen zijn gevonden, betekent dit dat de Azure Active Directory (Azure AD) die wordt gebruikt om zich aan te melden bij de gebruiker bij de portal, geen Microsoft Defender voor Eindpunt-licentie heeft.</span><span class="sxs-lookup"><span data-stu-id="e4a55-113">If while accessing Microsoft Defender Security Center you get a **No subscriptions found** message, it means the Azure Active Directory (Azure AD) used to log in the user to the portal, does not have a Microsoft Defender for Endpoint license.</span></span>

<span data-ttu-id="e4a55-114">Mogelijke redenen:</span><span class="sxs-lookup"><span data-stu-id="e4a55-114">Potential reasons:</span></span>
- <span data-ttu-id="e4a55-115">De Windows E5- en Office E5-licenties zijn afzonderlijke licenties.</span><span class="sxs-lookup"><span data-stu-id="e4a55-115">The Windows E5 and Office E5 licenses are separate licenses.</span></span>
- <span data-ttu-id="e4a55-116">De licentie is aangeschaft, maar niet ingericht voor dit Azure AD-exemplaar.</span><span class="sxs-lookup"><span data-stu-id="e4a55-116">The license was purchased but not provisioned to this Azure AD instance.</span></span>
    - <span data-ttu-id="e4a55-117">Het kan een probleem zijn met het inrichten van licenties.</span><span class="sxs-lookup"><span data-stu-id="e4a55-117">It could be a license provisioning issue.</span></span>
    - <span data-ttu-id="e4a55-118">Het kan zijn dat u de licentie per ongeluk hebt ingericht op een andere Microsoft Azure AD dan de licentie die voor verificatie in de service wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e4a55-118">It could be you inadvertently provisioned the license to a different Microsoft Azure AD than the one used for authentication into the service.</span></span>

<span data-ttu-id="e4a55-119">In beide gevallen moet u contact opnemen met microsoft-ondersteuning bij algemene ondersteuning van Microsoft Defender voor [endpoint-](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) of [volumelicentieondersteuning.](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)</span><span class="sxs-lookup"><span data-stu-id="e4a55-119">For both cases, you should contact Microsoft support at [General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) or [Volume license support](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx).</span></span>

![Afbeelding van geen gevonden abonnementen](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a><span data-ttu-id="e4a55-121">Uw abonnement is verlopen</span><span class="sxs-lookup"><span data-stu-id="e4a55-121">Your subscription has expired</span></span>

<span data-ttu-id="e4a55-122">Als u tijdens het openen van het Microsoft Defender-beveiligingscentrum een bericht krijgt **dat** uw abonnement is verlopen, is uw onlineserviceabonnement verlopen.</span><span class="sxs-lookup"><span data-stu-id="e4a55-122">If while accessing Microsoft Defender Security Center you get a **Your subscription has expired** message, your online service subscription has expired.</span></span> <span data-ttu-id="e4a55-123">Microsoft Defender for Endpoint-abonnement heeft, net als elk ander onlineserviceabonnement, een vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="e4a55-123">Microsoft Defender for Endpoint subscription, like any other online service subscription, has an expiration date.</span></span> 

<span data-ttu-id="e4a55-124">U kunt ervoor kiezen om de licentie op elk moment te verlengen of uit te breiden.</span><span class="sxs-lookup"><span data-stu-id="e4a55-124">You can choose to renew or extend the license at any point in time.</span></span> <span data-ttu-id="e4a55-125">Bij toegang tot de portal  na de vervaldatum wordt een bericht van uw abonnement dat is verlopen, weergegeven met een optie om het offboarding-pakket van het apparaat te downloaden, mocht u ervoor kiezen om de licentie niet te verlengen.</span><span class="sxs-lookup"><span data-stu-id="e4a55-125">When accessing the portal after the expiration date a **Your subscription has expired** message will be presented with an option to download the device offboarding package, should you choose to not renew the license.</span></span>

> [!NOTE]
> <span data-ttu-id="e4a55-126">Om veiligheidsredenen verloopt het pakket dat wordt gebruikt voor Offboard-apparaten 30 dagen na de datum waarop het is gedownload.</span><span class="sxs-lookup"><span data-stu-id="e4a55-126">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="e4a55-127">Verlopen offboarding-pakketten die naar een apparaat zijn verzonden, worden geweigerd.</span><span class="sxs-lookup"><span data-stu-id="e4a55-127">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="e4a55-128">Wanneer u een offboarding-pakket downloadt, wordt u op de hoogte gesteld van de vervaldatum van de pakketten en wordt het ook opgenomen in de pakketnaam.</span><span class="sxs-lookup"><span data-stu-id="e4a55-128">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

![Afbeelding van verlopen abonnement](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a><span data-ttu-id="e4a55-130">U bent niet gemachtigd om toegang te krijgen tot de portal</span><span class="sxs-lookup"><span data-stu-id="e4a55-130">You are not authorized to access the portal</span></span>

<span data-ttu-id="e4a55-131">Als u een U bent niet gemachtigd om toegang te krijgen tot de **portal,** moet u er rekening mee houden dat Microsoft Defender voor Eindpunt een beveiligingscontrole, incidentonderzoek en antwoordproduct is en dat de toegang tot de portal daarom wordt beperkt en gecontroleerd door de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="e4a55-131">If you receive a **You are not authorized to access the portal**, be aware that Microsoft Defender for Endpoint is a security monitoring, incident investigation and response product, and as such, access to it is restricted and controlled by the user.</span></span>
<span data-ttu-id="e4a55-132">Zie Gebruikerstoegang toewijzen [**aan de portal voor meer informatie.**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="e4a55-132">For more information, see, [**Assign user access to the portal**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span></span>

![Afbeelding van niet geautoriseerde toegang tot portal](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a><span data-ttu-id="e4a55-134">Gegevens zijn momenteel niet beschikbaar in sommige secties van de portal</span><span class="sxs-lookup"><span data-stu-id="e4a55-134">Data currently isn't available on some sections of the portal</span></span>
<span data-ttu-id="e4a55-135">Als in het portaldashboard en andere secties een foutbericht wordt weergegeven, zoals 'Gegevens zijn momenteel niet beschikbaar':</span><span class="sxs-lookup"><span data-stu-id="e4a55-135">If the portal dashboard and other sections show an error message such as "Data currently isn't available":</span></span>

![Afbeelding van gegevens die momenteel niet beschikbaar zijn](images/atp-data-not-available.png)

<span data-ttu-id="e4a55-137">U moet de subdomeinen en `securitycenter.windows.com` alle subdomeinen daar onder toestaan.</span><span class="sxs-lookup"><span data-stu-id="e4a55-137">You'll need to allow the `securitycenter.windows.com` and all subdomains under it.</span></span> <span data-ttu-id="e4a55-138">Bijvoorbeeld `*.securitycenter.windows.com`.</span><span class="sxs-lookup"><span data-stu-id="e4a55-138">For example, `*.securitycenter.windows.com`.</span></span>


## <a name="portal-communication-issues"></a><span data-ttu-id="e4a55-139">Problemen met portalcommunicatie</span><span class="sxs-lookup"><span data-stu-id="e4a55-139">Portal communication issues</span></span>
<span data-ttu-id="e4a55-140">Als u problemen ondervindt met toegang tot de portal, ontbrekende gegevens of beperkte toegang tot gedeelten van de portal, moet u controleren of de volgende URL's zijn toegestaan en worden geopend voor communicatie.</span><span class="sxs-lookup"><span data-stu-id="e4a55-140">If you encounter issues with accessing the portal, missing data, or restricted access to portions of the portal, you'll need to verify that the following URLs are allowed and open for communication.</span></span>

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.securitycenter.windows.com` 
- `https://automatediracs-eus-prd.securitycenter.windows.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com` 
- `https://securitycenter.windows.com` 
- `https://static2.sharepointonline.com` 



