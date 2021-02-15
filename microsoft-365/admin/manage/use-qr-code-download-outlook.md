---
title: Een QR-code gebruiken om u aan te melden bij de mobiele Outlook-apps
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Informatie over het gebruik van een QR-code voor verificatie en het downloaden van Outlook Mobile.
ms.openlocfilehash: 1e5207a2792b557689a306fa1474a2c5fac81ed9
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242352"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="cd85e-103">Een QR-code gebruiken om u aan te melden bij de mobiele Outlook-apps</span><span class="sxs-lookup"><span data-stu-id="cd85e-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd85e-104">Deze functie is alleen beschikbaar voor organisaties die Targeted Release hebben ingeschakeld in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="cd85e-104">This feature is only available to organizations who have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="cd85e-105">Zie De Standard Release- of Targeted Release-opties instellen voor meer informatie over hoe dit [werkt.](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="cd85e-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="cd85e-106">De komende weken zullen we via een openbare preview naar meer organisaties worden uitgebreid.</span><span class="sxs-lookup"><span data-stu-id="cd85e-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="cd85e-107">Openbare preview biedt vroegtijdige toegang tot Microsoft 365-functies.</span><span class="sxs-lookup"><span data-stu-id="cd85e-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="cd85e-108">Als Microsoft 365-beheerder kunt u uw gebruikers in staat stellen zich aan te melden bij de App Outlook voor Android of iOS op hun mobiele apparaten zonder dat ze hun gebruikersnaam en wachtwoord moeten invoeren.</span><span class="sxs-lookup"><span data-stu-id="cd85e-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="cd85e-109">Door een QR-code te scannen kunnen gebruikers zich veilig verifiëren en zich aanmelden bij Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="cd85e-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="cd85e-110">In de webversie van Outlook of andere Outlook-bureaubladtoepassingen zien gebruikers mogelijk meldingen met de mededeling dat ze Outlook op hun mobiele apparaat kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cd85e-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="cd85e-111">Deze meldingen kunnen worden beheerd door de beheerder met behulp van Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="cd85e-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="cd85e-112">Als gebruikers zichzelf een sms-bericht sturen om de app te downloaden op hun mobiele apparaat, wordt er een QR-code weergegeven op hun computer.</span><span class="sxs-lookup"><span data-stu-id="cd85e-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="cd85e-113">Ze kunnen de QR-code scannen om zich aan te melden bij Outlook op hun telefoon of tablet.</span><span class="sxs-lookup"><span data-stu-id="cd85e-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="cd85e-114">Deze QR-code is een token van korte duur die maar één keer kan worden ingewisseld.</span><span class="sxs-lookup"><span data-stu-id="cd85e-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="cd85e-115">In sommige gevallen moeten uw gebruikers zich opnieuw verifiëren op hun computer om de QR-code te genereren.</span><span class="sxs-lookup"><span data-stu-id="cd85e-115">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="cd85e-116">Exchange PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="cd85e-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="cd85e-117">Deze functie is standaard ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="cd85e-117">This feature is on by default.</span></span> <span data-ttu-id="cd85e-118">Als u deze functie wilt uitschakelen, volgt u de onderstaande stappen.</span><span class="sxs-lookup"><span data-stu-id="cd85e-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="cd85e-119">[Maak verbinding met Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="cd85e-119">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="cd85e-120">Met PowerShell kunt u de meldingen uitschakelen om uw gebruikers te informeren over de mobiele Outlook-apps.</span><span class="sxs-lookup"><span data-stu-id="cd85e-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="cd85e-121">Hiermee wordt ook voorkomen dat de aanmeldingsstroom voor QR-code wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="cd85e-121">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="cd85e-122">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="cd85e-122">Related topics</span></span>

[<span data-ttu-id="cd85e-123">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="cd85e-123">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
