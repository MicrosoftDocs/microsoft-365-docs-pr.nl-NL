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
ms.openlocfilehash: b9e433e0c7d3f5f3466924b318e242e5ac29181c
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122370"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="f24ba-103">Een QR-code gebruiken om u aan te melden bij de mobiele Outlook-apps</span><span class="sxs-lookup"><span data-stu-id="f24ba-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f24ba-104">Deze Microsoft 365-functie is beschikbaar in de openbare preview-versie.</span><span class="sxs-lookup"><span data-stu-id="f24ba-104">This Microsoft 365 feature is in public preview.</span></span> <span data-ttu-id="f24ba-105">Openbare preview biedt vroegtijdige toegang tot Microsoft 365-functies.</span><span class="sxs-lookup"><span data-stu-id="f24ba-105">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="f24ba-106">Als Microsoft 365-beheerder kunt u uw gebruikers in staat stellen zich aan te melden bij de app Outlook voor Android of iOS op hun mobiele apparaten zonder dat ze hun gebruikersnaam en wachtwoord moeten invoeren.</span><span class="sxs-lookup"><span data-stu-id="f24ba-106">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="f24ba-107">Door een QR-code te scannen kunnen gebruikers zich veilig verifiëren en zich aanmelden bij Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="f24ba-107">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="f24ba-108">In de webversie van Outlook of andere Outlook-bureaubladtoepassingen zien gebruikers mogelijk meldingen met de mededeling dat ze Outlook op hun mobiele apparaat kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f24ba-108">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="f24ba-109">Deze meldingen kunnen worden beheerd door de beheerder met behulp van Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="f24ba-109">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="f24ba-110">Als gebruikers zichzelf een sms-bericht sturen om de app te downloaden op hun mobiele apparaat, wordt er een QR-code weergegeven op hun computer.</span><span class="sxs-lookup"><span data-stu-id="f24ba-110">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="f24ba-111">Ze kunnen de QR-code scannen om zich aan te melden bij Outlook op hun telefoon of tablet.</span><span class="sxs-lookup"><span data-stu-id="f24ba-111">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="f24ba-112">Deze QR-code is een token van korte duur die maar één keer kan worden ingewisseld.</span><span class="sxs-lookup"><span data-stu-id="f24ba-112">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="f24ba-113">In sommige gevallen moeten uw gebruikers zich opnieuw verifiëren op hun computer om de QR-code te genereren.</span><span class="sxs-lookup"><span data-stu-id="f24ba-113">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="f24ba-114">Exchange PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="f24ba-114">Use Exchange PowerShell</span></span>

<span data-ttu-id="f24ba-115">Deze ervaring is standaard ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f24ba-115">This experience is on by default.</span></span> <span data-ttu-id="f24ba-116">Als u deze functie wilt uitschakelen, volgt u de onderstaande stappen.</span><span class="sxs-lookup"><span data-stu-id="f24ba-116">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="f24ba-117">[Maak verbinding met Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="f24ba-117">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="f24ba-118">Met PowerShell kunt u de meldingen uitschakelen om uw gebruikers te informeren over de mobiele Outlook-apps.</span><span class="sxs-lookup"><span data-stu-id="f24ba-118">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="f24ba-119">Hiermee wordt ook voorkomen dat de aanmeldingsstroom voor QR-code wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f24ba-119">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="f24ba-120">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f24ba-120">Related topics</span></span>

[<span data-ttu-id="f24ba-121">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="f24ba-121">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
