---
title: Veiligheidstips in- of uitschakelen in Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
ms.collection:
- M365-security-compliance
description: Geeft Office 365- en EOP-beheerders aan hoe ze veiligheidstips in e-mailberichten kunnen in- en uitschakelen.
ms.openlocfilehash: ae8a3bc9811aa54b0c5ae4cc8a0e2eb9aa80aef0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811305"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a><span data-ttu-id="3788e-103">Veiligheidstips in- of uitschakelen in Office 365</span><span class="sxs-lookup"><span data-stu-id="3788e-103">Enable or disable safety tips in Office 365</span></span>

<span data-ttu-id="3788e-104">Exchange Online Protection (EOP) voegt een veiligheidstip toe aan e-mailberichten die het levert.</span><span class="sxs-lookup"><span data-stu-id="3788e-104">Exchange Online Protection (EOP) adds, or stamps, a safety tip to email messages that it delivers.</span></span> <span data-ttu-id="3788e-105">Deze veiligheidstips bieden ontvangers een snelle, visuele manier om te bepalen of een bericht afkomstig is van een veilige, geverifieerde afzender, als het bericht is gemarkeerd als spam door Office 365, als het bericht iets verdachts bevat, zoals een phishing-scam, of als externe afbeeldingen geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="3788e-105">These safety tips provide recipients with a quick, visual way to determine if a message is from a safe, verified sender, if the message has been marked as spam by Office 365, if the message contains something suspicious such as a phishing scam, or if external images have been blocked.</span></span> <span data-ttu-id="3788e-106">Beheerders van Office 365 en EOP-zelfstandige bestanden kunnen een instelling voor spambeleid bewerken om veiligheidstips in of uit te schakelen die worden weergegeven in e-mail in Outlook en andere bureaublad-e-mailclients.</span><span class="sxs-lookup"><span data-stu-id="3788e-106">Office 365 and EOP-standalone admins can edit a spam policy setting to enable or disable safety tips from being displayed in email in Outlook and other desktop email clients.</span></span>

<span data-ttu-id="3788e-107">Office 365 maakt standaard veiligheidstips voor uw organisatie en we raden u aan deze standaard in staat te stellen om spam- en phishingaanvallen te bestrijden.</span><span class="sxs-lookup"><span data-stu-id="3788e-107">Office 365 enables safety tips by default for your organization and we recommend that you leave them enabled to help combat spam and phishing attacks.</span></span> <span data-ttu-id="3788e-108">U veiligheidstips voor de webversie van Outlook niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="3788e-108">You can't disable safety tips for Outlook on the web.</span></span>

<span data-ttu-id="3788e-109">Zie [Veiligheidstips in e-mailberichten in Office 365](safety-tips-in-office-365.md) voor voorbeelden en informatie over de informatie die in veiligheidstips wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3788e-109">To see examples and to learn about the information displayed in safety tips, see [Safety tips in email messages in Office 365.](safety-tips-in-office-365.md)</span></span>

<span data-ttu-id="3788e-110">In dit onderwerp:</span><span class="sxs-lookup"><span data-stu-id="3788e-110">In this topic:</span></span>

- [<span data-ttu-id="3788e-111">Veiligheidstips inschakelen of uitschakelen met behulp van &amp; het Office 365 Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="3788e-111">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>](enable-or-disable-safety-tips.md#SandCCsafetytip)

- [<span data-ttu-id="3788e-112">Veiligheidstips inschakelen of uitschakelen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="3788e-112">To enable or disable safety tips by using PowerShell</span></span>](enable-or-disable-safety-tips.md#pshellsafetytip)

## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="3788e-113">Veiligheidstips inschakelen of uitschakelen met behulp van &amp; het Office 365 Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="3788e-113">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>
<span data-ttu-id="3788e-114"><a name="SandCCsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="3788e-114"><a name="SandCCsafetytip"> </a></span></span>

1. <span data-ttu-id="3788e-115">Ga naar [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="3788e-115">Go to [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="3788e-116">Meld u aan bij Office 365 met uw werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="3788e-116">Sign in to Office 365 with your work or school account.</span></span>

3. <span data-ttu-id="3788e-117">Kies **Beleid voor bedreigingsbeheer** \> **.**</span><span class="sxs-lookup"><span data-stu-id="3788e-117">Choose **Threat Management** \> **Policy**.</span></span>

4. <span data-ttu-id="3788e-118">Kies op de pagina **Beleid** **anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="3788e-118">On the **Policy** page, choose **Anti-Spam**.</span></span>

    ![Deze screenshot laat zien hoe je naar de &amp; pagina Anti-spam-instellingen in het Security Compliance Center komen.](../../media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)

5. <span data-ttu-id="3788e-120">Kies op de pagina **Anti-spam-instellingen** het tabblad **Aangepast.**</span><span class="sxs-lookup"><span data-stu-id="3788e-120">On the **Anti-spam settings** page choose the **Custom** tab.</span></span>

    ![Deze schermafbeelding toont de locatie van het tabblad Aangepast op &amp; de pagina Anti-spam-instellingen in het Security Compliance Center.](../../media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)

6. <span data-ttu-id="3788e-122">Kies indien nodig de aangepaste **instellingenschakelaar** om aangepaste instellingen in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="3788e-122">If necessary, choose the **Custom settings** switch to turn on custom settings.</span></span> <span data-ttu-id="3788e-123">Als de aangepaste instellingen-switch is ingesteld op **Uit,** u het beleid voor spamfilters niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="3788e-123">If the custom settings switch is set to **Off**, you won't be able to modify spam filter policies.</span></span>

    ![Deze schermafbeelding toont aangepaste anti-spamfilterbeleidsinstellingen uitgeschakeld.](../../media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)

7. <span data-ttu-id="3788e-125">Vouw het spambeleid uit dat u wilt wijzigen en kies **het beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="3788e-125">Expand the spam policy you want to modify and then choose **Edit policy**.</span></span> <span data-ttu-id="3788e-126">Kies bijvoorbeeld de pijl-omlaag naast **het standaardspamfilterbeleid**.</span><span class="sxs-lookup"><span data-stu-id="3788e-126">For example, choose the down arrow next to **Default spam filter policy**.</span></span> <span data-ttu-id="3788e-127">Of, als u wilt, u een nieuw beleid maken door **een beleid toevoegen**te kiezen.</span><span class="sxs-lookup"><span data-stu-id="3788e-127">Or, if you want, you can create a new policy by choosing **Add a policy**.</span></span>

8. <span data-ttu-id="3788e-128">Spam- **en bulkacties** uitbreiden.</span><span class="sxs-lookup"><span data-stu-id="3788e-128">Expand **Spam and bulk** actions.</span></span>

9. <span data-ttu-id="3788e-129">Als u veiligheidstips wilt inschakelen, schakelt u onder **Veiligheidstips**het selectievakje **Aan** in.</span><span class="sxs-lookup"><span data-stu-id="3788e-129">To enable safety tips, under **Safety Tips**, check the **On** checkbox.</span></span> <span data-ttu-id="3788e-130">Schakel het selectievakje **Aan** uit om veiligheidstips uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="3788e-130">To disable safety tips, clear the **On** checkbox.</span></span>

10. <span data-ttu-id="3788e-131">Selecteer **Save**.</span><span class="sxs-lookup"><span data-stu-id="3788e-131">Choose **Save**.</span></span>

## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a><span data-ttu-id="3788e-132">Veiligheidstips inschakelen of uitschakelen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="3788e-132">To enable or disable safety tips by using PowerShell</span></span>
<span data-ttu-id="3788e-133"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="3788e-133"><a name="pshellsafetytip"> </a></span></span>

<span data-ttu-id="3788e-134">Beheerders kunnen Exchange Online PowerShell gebruiken om veiligheidstips in te schakelen of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="3788e-134">Admins can use Exchange Online PowerShell to enable or disable safety tips.</span></span> <span data-ttu-id="3788e-135">Gebruik de cmdlet Set-HostedContentFilterPolicy om veiligheidstips in een spamfilterbeleid in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="3788e-135">Use the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips in a spam filter policy.</span></span>

1. <span data-ttu-id="3788e-136">Maak verbinding met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3788e-136">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="3788e-137">Zie Verbinding [maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)voor informatie.</span><span class="sxs-lookup"><span data-stu-id="3788e-137">For information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3788e-138">Voer de cmdlet Set-HostedContentFilterPolicy uit om veiligheidstips in te schakelen of uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="3788e-138">Run the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips:</span></span>

   ```powershell
   Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true | $false>
   ```

<span data-ttu-id="3788e-139">Waar:</span><span class="sxs-lookup"><span data-stu-id="3788e-139">Where:</span></span>

- <span data-ttu-id="3788e-140">*beleidsnaam* is de naam van het beleid dat u wilt wijzigen, bijvoorbeeld **standaard**.</span><span class="sxs-lookup"><span data-stu-id="3788e-140">*policy name*  is the name of the policy you want to modify, for example **default**.</span></span>

- <span data-ttu-id="3788e-141">`$true`maakt veiligheidstips voor het spamfilterbeleid mogelijk.</span><span class="sxs-lookup"><span data-stu-id="3788e-141">`$true` enables safety tips for the spam filter policy.</span></span>

- <span data-ttu-id="3788e-142">`$false`schakelt veiligheidstips uit voor het spamfilterbeleid.</span><span class="sxs-lookup"><span data-stu-id="3788e-142">`$false` disables safety tips for the spam filter policy.</span></span>

<span data-ttu-id="3788e-143">Als u bijvoorbeeld veiligheidstips voor het standaardspamfilterbeleid wilt uitschakelen, voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="3788e-143">For example, to disable safety tips for the default spam filter policy, run the following command:</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
```

<span data-ttu-id="3788e-144">Zie [Beleid voor inhoudsopties instellen voor](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)meer informatie over deze cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3788e-144">For more information about this cmdlet, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy).</span></span>

## <a name="still-need-help"></a><span data-ttu-id="3788e-145">Nog steeds hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="3788e-145">Still need help?</span></span>
<span data-ttu-id="3788e-146"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="3788e-146"><a name="pshellsafetytip"> </a></span></span>

<span data-ttu-id="3788e-147">Als u veiligheidstips hebt uitgeschakeld, maar ze nog steeds in uw e-mailberichten ziet, controleert u deze dingen:</span><span class="sxs-lookup"><span data-stu-id="3788e-147">If you disabled safety tips but are still seeing them in your email messages, check these things:</span></span>

- <span data-ttu-id="3788e-148">U veiligheidstips voor de webversie van Outlook niet uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="3788e-148">You can't disable safety tips for Outlook on the web.</span></span> <span data-ttu-id="3788e-149">Probeer dezelfde e-mail weer te geven in een andere client, zoals Outlook.</span><span class="sxs-lookup"><span data-stu-id="3788e-149">Try viewing the same email in another client, such as Outlook.</span></span>

- <span data-ttu-id="3788e-150">Veiligheidstips zijn standaard beschikbaar voor iedereen die EOP gebruikt, dit geldt ook voor iedereen die Office 365 heeft.</span><span class="sxs-lookup"><span data-stu-id="3788e-150">Safety tips are on by default for every one who uses EOP, this includes everyone who has Office 365.</span></span> <span data-ttu-id="3788e-151">Als u wilt voorkomen dat veiligheidstips in e-mail worden weergegeven, moet u deze uitschakelen met behulp van een spamfilterbeleid zoals beschreven in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="3788e-151">In order to disable safety tips from showing up in email, you must disable them by using a spam filter policy as described in this topic.</span></span> <span data-ttu-id="3788e-152">Zodra u het beleid hebt ingesteld, moet u ervoor zorgen dat het is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="3788e-152">Once you've set up the policy, ensure that it is enabled.</span></span> <span data-ttu-id="3788e-153">Zie [Uw spamfilterbeleid](configure-your-spam-filter-policies.md)configureren voor informatie over het inschakelen van het beleid voor spamfilters .</span><span class="sxs-lookup"><span data-stu-id="3788e-153">For information on enabling spam filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="3788e-154">Zie [Office 365 Email Anti-Spam Protection](anti-spam-protection.md)voor meer manieren om spam en phishing te bestrijden.</span><span class="sxs-lookup"><span data-stu-id="3788e-154">For more ways to combat spam and phishing, see [Office 365 Email Anti-Spam Protection](anti-spam-protection.md).</span></span>
