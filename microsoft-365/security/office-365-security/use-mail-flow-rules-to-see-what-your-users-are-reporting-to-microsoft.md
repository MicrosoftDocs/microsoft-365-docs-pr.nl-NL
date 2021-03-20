---
title: Regels voor e-mailstromen gebruiken om te zien wat je gebruikers melden bij Microsoft
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
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze regels voor e-mailstroom (ook wel transportregels genoemd) kunnen gebruiken om kopieën te ontvangen van berichten die gebruikers rapporteren aan Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 34857c368fc910eeb43f6a78c490b9ad7568db1c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918628"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="d3b3d-103">Regels voor e-mailstromen gebruiken om te zien wat je gebruikers melden bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="d3b3d-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d3b3d-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d3b3d-104">**Applies to**</span></span>
- [<span data-ttu-id="d3b3d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d3b3d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d3b3d-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d3b3d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d3b3d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3b3d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="d3b3d-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken zijn er verschillende manieren voor gebruikers om berichten te rapporteren aan Microsoft voor analyse, zoals beschreven in Berichten en bestanden rapporteren aan [Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="d3b3d-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="d3b3d-109">U kunt een regel voor de e-mailstroom maken (ook wel transportregel genoemd) die zoekt naar berichten die gebruikers rapporteren aan Microsoft en u kunt BCC-geadresseerden zo configureren dat kopieën van deze gerapporteerde berichten worden ontvangen.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-109">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="d3b3d-110">U kunt de regel voor de e-mailstroom maken in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).</span><span class="sxs-lookup"><span data-stu-id="d3b3d-110">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d3b3d-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="d3b3d-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d3b3d-112">U moet machtigingen krijgen toegewezen in Exchange Online of Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-112">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="d3b3d-113">U hebt met name de rol **Transportregels** nodig, die standaard is toegewezen aan de rollengroepen **Organisatiebeheer,** **Compliancebeheer** (globale beheerders) en **Recordsbeheer.**</span><span class="sxs-lookup"><span data-stu-id="d3b3d-113">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="d3b3d-114">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="d3b3d-114">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="d3b3d-115">Machtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d3b3d-115">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="d3b3d-116">Machtigingen in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="d3b3d-116">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="d3b3d-117">De lijst met leden in rollengroepen wijzigen met het EAC</span><span class="sxs-lookup"><span data-stu-id="d3b3d-117">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="d3b3d-118">Zie [Exchange-beheercentrum in Exchange Online](/Exchange/exchange-admin-center)om het EAC in Exchange Online te openen.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-118">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="d3b3d-119">Zie [Exchange-beheercentrum in](exchange-admin-center-in-exchange-online-protection-eop.md)zelfstandige EOP om de EAC in zelfstandige EOP te openen.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-119">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="d3b3d-120">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d3b3d-121">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d3b3d-122">Zie de volgende onderwerpen voor meer informatie over e-mailstroomregels in Exchange Online en zelfstandige EOP:</span><span class="sxs-lookup"><span data-stu-id="d3b3d-122">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="d3b3d-123">Regels voor e-mailstroom (transportregels) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d3b3d-123">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="d3b3d-124">Voorwaarden en uitzonderingen voor e-mailstroomregel (predicaten) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d3b3d-124">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="d3b3d-125">Acties voor e-mailstroomregel in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d3b3d-125">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="d3b3d-126">De EAC gebruiken om een e-mailstroomregel te maken om kopieën van gerapporteerde berichten te ontvangen</span><span class="sxs-lookup"><span data-stu-id="d3b3d-126">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="d3b3d-127">Ga in het EAC naar **E-mailstroomregels.** \> </span><span class="sxs-lookup"><span data-stu-id="d3b3d-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="d3b3d-128">Klik **op Pictogram** Toevoegen toevoegen en selecteer vervolgens Een nieuwe regel ![ ](../../media/ITPro-EAC-AddIcon.png) **maken.**</span><span class="sxs-lookup"><span data-stu-id="d3b3d-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="d3b3d-129">Configureer **de volgende instellingen** op de pagina Nieuwe regel die wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="d3b3d-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="d3b3d-130">**Naam:** Voer een unieke, beschrijvende naam in voor de regel.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-130">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="d3b3d-131">Bijvoorbeeld BCC-berichten die zijn gerapporteerd bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-131">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="d3b3d-132">Klik **op Meer opties.**</span><span class="sxs-lookup"><span data-stu-id="d3b3d-132">Click **More Options**.</span></span>

   - <span data-ttu-id="d3b3d-133">Pas deze regel  toe **als**: Selecteer Het adres van de geadresseerde bevat een van deze woorden: Voer in het dialoogvenster Woorden of woordgroepen opgeven een van de volgende waarden in, klik op Pictogram toevoegen toevoegen en herhaal dit totdat u alle waarden hebt \>    ![ ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-133">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     <span data-ttu-id="d3b3d-134">Als u een item wilt bewerken, selecteert u deze en klikt **u** op ![ Pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) bewerken.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="d3b3d-135">Als u een item wilt verwijderen, selecteert u deze en klikt **u op Pictogram** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="d3b3d-136">Wanneer u klaar bent, klikt u op **OK.**</span><span class="sxs-lookup"><span data-stu-id="d3b3d-136">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="d3b3d-137">**Ga als volgt** te werk: Selecteer **Geadresseerden toevoegen** aan het vak \> **BCC.**</span><span class="sxs-lookup"><span data-stu-id="d3b3d-137">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="d3b3d-138">Zoek en selecteer de geadresseerden die u wilt toevoegen in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-138">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="d3b3d-139">Wanneer u klaar bent, klikt u op **OK.**</span><span class="sxs-lookup"><span data-stu-id="d3b3d-139">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="d3b3d-140">U kunt extra selecties maken om de regel te controleren, de regel te testen, de regel te activeren tijdens een bepaalde periode en andere instellingen.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-140">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="d3b3d-141">Het is raadzaam om de regel te testen voordat u deze afdwingt.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-141">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="d3b3d-142">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-142">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="d3b3d-143">PowerShell gebruiken om een e-mailstroomregel te maken om kopieën van gerapporteerde berichten te ontvangen</span><span class="sxs-lookup"><span data-stu-id="d3b3d-143">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="d3b3d-144">In dit voorbeeld wordt een nieuwe regel voor de e-mailstroom gemaakt met de naam BCC-berichten die zijn gerapporteerd bij Microsoft en die zoekt naar e-mailberichten die aan Microsoft zijn gerapporteerd met de methoden die in dit artikel worden beschreven, en die de gebruikers laura@contoso.com en julia@contoso.com als BCC-geadresseerden toevoegt.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-144">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="d3b3d-145">Zie [Nieuwe-Transportregel](/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-145">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d3b3d-146">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="d3b3d-146">How do you know this worked?</span></span>

<span data-ttu-id="d3b3d-147">Als u wilt controleren of u een e-mailstroomregels hebt geconfigureerd om kopieën van gerapporteerde berichten te ontvangen, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="d3b3d-147">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="d3b3d-148">Ga in het EAC naar **E-mailstroomregels** en selecteer de regel op Pictogram Bewerken \>  \> bewerken en \> controleer de  ![ ](../../media/ITPro-EAC-EditIcon.png) instellingen.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-148">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="d3b3d-149">Voer in PowerShell de volgende opdracht uit om de instellingen te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="d3b3d-149">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="d3b3d-150">Verzend een testberichten naar een van de rapportage-e-mailadressen en controleer de resultaten.</span><span class="sxs-lookup"><span data-stu-id="d3b3d-150">Send a test messages to one of the reporting email addresses and verify the results.</span></span>