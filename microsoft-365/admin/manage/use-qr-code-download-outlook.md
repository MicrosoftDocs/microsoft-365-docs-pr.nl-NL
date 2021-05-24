---
title: Een QR-code gebruiken om u aan te melden bij de Outlook mobiele apps
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
description: Meer informatie over het gebruik van een QR-code om uw mobiele Outlook te verifiëren en te downloaden.
ms.openlocfilehash: 2c1853a6ea1dd1a5d2ad30b975d1dbd23b942040
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635996"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="02c4b-103">Een QR-code gebruiken om u aan te melden bij de Outlook mobiele apps</span><span class="sxs-lookup"><span data-stu-id="02c4b-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02c4b-104">Deze functie is alleen beschikbaar voor organisaties die Targeted Release hebben ingeschakeld in het Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="02c4b-104">This feature is only available to organizations that have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="02c4b-105">Zie De opties Standaard of Targeted release instellen voor meer informatie over hoe deze [werkt.](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="02c4b-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="02c4b-106">We breiden de komende weken uit naar meer organisaties via een openbare preview.</span><span class="sxs-lookup"><span data-stu-id="02c4b-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="02c4b-107">Openbare preview biedt vroegtijdige toegang tot Microsoft 365 functies.</span><span class="sxs-lookup"><span data-stu-id="02c4b-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="02c4b-108">Als Microsoft 365-beheerder kunt u uw gebruikers inschakelen om zich aan te melden bij Outlook voor Android- of iOS-app op hun mobiele apparaten zonder hun gebruikersnaam en wachtwoord in te voeren.</span><span class="sxs-lookup"><span data-stu-id="02c4b-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="02c4b-109">Door een QR-code te scannen, kunnen gebruikers zich veilig verifiëren en zich aanmelden bij Outlook mobiel.</span><span class="sxs-lookup"><span data-stu-id="02c4b-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="02c4b-110">In Outlook op het web of andere bureaubladtoepassingen Outlook kunnen gebruikers meldingen zien waarin wordt hen ervan op de hoogte worden gemaakt dat ze Outlook kunnen gebruiken op hun mobiele apparaat.</span><span class="sxs-lookup"><span data-stu-id="02c4b-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="02c4b-111">Deze meldingen kunnen worden beheerd door de beheerder met Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02c4b-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="02c4b-112">Als gebruikers ervoor kiezen om zichzelf een Sms te sturen om de app te downloaden op hun mobiele apparaat, wordt er een QR-code weergegeven op hun computer.</span><span class="sxs-lookup"><span data-stu-id="02c4b-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="02c4b-113">Ze kunnen de QR-code scannen om zich aan te melden Outlook hun telefoon of tablet.</span><span class="sxs-lookup"><span data-stu-id="02c4b-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="02c4b-114">Deze QR-code is een teken van korte duur dat slechts één keer kan worden ingewisseld.</span><span class="sxs-lookup"><span data-stu-id="02c4b-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="02c4b-115">In sommige gevallen moeten uw gebruikers zich opnieuw verifiëren op hun computer om de QR-code te genereren.</span><span class="sxs-lookup"><span data-stu-id="02c4b-115">In some cases, your users must re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="02c4b-116">PowerShell Exchange gebruiken</span><span class="sxs-lookup"><span data-stu-id="02c4b-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="02c4b-117">Deze functie is standaard ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="02c4b-117">This feature is on by default.</span></span> <span data-ttu-id="02c4b-118">Als u deze functie wilt uitschakelen, volgt u de onderstaande stappen.</span><span class="sxs-lookup"><span data-stu-id="02c4b-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="02c4b-119">[Verbinding maken powershell Exchange gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="02c4b-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="02c4b-120">Met PowerShell kunt u de meldingen uitschakelen die uw gebruikers informeren over de Outlook mobiele apps.</span><span class="sxs-lookup"><span data-stu-id="02c4b-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="02c4b-121">Hierdoor wordt ook voorkomen dat de aanmeldingsstroom voor QR-code wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="02c4b-121">This also prevents the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a><span data-ttu-id="02c4b-122">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="02c4b-122">Related content</span></span>

<span data-ttu-id="02c4b-123">[De opties Standaard of Targeted Release](release-options-in-office-365.md) (artikel)\ instellen</span><span class="sxs-lookup"><span data-stu-id="02c4b-123">[Set up the Standard or Targeted release options](release-options-in-office-365.md) (article)\</span></span>
<span data-ttu-id="02c4b-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) (artikel)</span><span class="sxs-lookup"><span data-stu-id="02c4b-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) (article)</span></span>