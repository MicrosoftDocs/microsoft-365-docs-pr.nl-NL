---
title: Melding van ongewenste e-mail uitschakelen in de webversie van Outlook
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: Als Office 365-beheerder u de mogelijkheid uitschakelen waarop mensen e-mail als ongewenste e-mail kunnen melden.
ms.openlocfilehash: 0bca03786d0335c24e48340e588510f09d6f6a7e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812062"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="9628a-103">Melding van ongewenste e-mail uitschakelen in de webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="9628a-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="9628a-104">U ongewenste, phishing- en niet-ongewenste berichten naar Microsoft verzenden voor analyse met behulp van de webopties voor ongewenste e-mail (voorheen bekend als Outlook Web App), zoals beschreven in De rapportageopties voor [ongewenste e-mail melden en phishing in het web van Outlook.](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)</span><span class="sxs-lookup"><span data-stu-id="9628a-104">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web (formerly known as Outlook Web App) junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span> <span data-ttu-id="9628a-105">Als u deze opties niet wilt gebruiken, kunnen beheerders deze uitschakelen via de cmdlet [Set-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="9628a-105">If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) cmdlet.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9628a-106">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="9628a-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="9628a-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="9628a-107"><a name="sectionSection0"> </a></span></span>

- <span data-ttu-id="9628a-108">Geschatte tijd om te voltooien: 5 minuten</span><span class="sxs-lookup"><span data-stu-id="9628a-108">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="9628a-109">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="9628a-109">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="9628a-110">Zie het item 'Outlook in het webpostvakbeleid' in [Exchange Online-machtigingen](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions)om te zien welke machtigingen u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="9628a-110">To see what permissions you need, see the "Outlook on the web mailbox policies" entry in [Exchange Online permissions](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions).</span></span>

- <span data-ttu-id="9628a-111">Zie Verbinding maken met [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9628a-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="9628a-112">Ongewenste e-mail, phishing en geen ongewenste rapportage aan Microsoft uitschakelen</span><span class="sxs-lookup"><span data-stu-id="9628a-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="9628a-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="9628a-113"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="9628a-114">Voer eerst de volgende opdracht uit om de namen van uw beschikbare Outlook in het webpostvakbeleid op te halen:</span><span class="sxs-lookup"><span data-stu-id="9628a-114">First, run the following command to get the names of your available Outlook on the web mailbox policies:</span></span>

```
Get-OwaMailboxPolicy | Format-Table Name
```

<span data-ttu-id="9628a-115">Gebruik vervolgens de volgende syntaxis om ongewenste e-mail in te schakelen of uit te schakelen en geen ongewenste rapportage aan Microsoft in de webversie van Outlook:</span><span class="sxs-lookup"><span data-stu-id="9628a-115">Next, use the following syntax to enable or disable junk and not junk reporting to Microsoft in Outlook on the web:</span></span>

```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

<span data-ttu-id="9628a-116">In dit voorbeeld wordt rapportage uitgeschakeld in het standaardpostvakbeleid van Outlook-webapp:</span><span class="sxs-lookup"><span data-stu-id="9628a-116">This example turns off reporting in the default Outlook web app mailbox policy:</span></span>

```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

<span data-ttu-id="9628a-117">Zie [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) en [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)voor gedetailleerde syntaxis- en parametergegevens.</span><span class="sxs-lookup"><span data-stu-id="9628a-117">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="9628a-118">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="9628a-118">How do you know this worked?</span></span>
<span data-ttu-id="9628a-119"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="9628a-119"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="9628a-120">**Voer Get-OWAMailboxPolicy** uit om de parameterwaarden te controleren en open Outlook op het web voor een getroffen gebruiker (die het beleid van Outlook op het webpostvak op hen heeft toegepast) en controleer of de opties voor het melden van ongewenste, phishing en niet-ongewenste berichten niet beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="9628a-120">Run **Get-OWAMailboxPolicy** to check the parameter values, and then open Outlook on the web for an affected user (who has the Outlook on the web mailbox policy applied to them) and verify that the options to report junk, phishing, and not junk are not available.</span></span> <span data-ttu-id="9628a-121">U berichten nog steeds markeren als ongewenste e-mail, phishing en niet als ongewenste e-mail, maar u ze niet melden.</span><span class="sxs-lookup"><span data-stu-id="9628a-121">You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span>
