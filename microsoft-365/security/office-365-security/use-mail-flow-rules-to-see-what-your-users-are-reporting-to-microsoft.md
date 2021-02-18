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
description: Beheerders kunnen informatie krijgen over het gebruik van regels voor de e-mailstroom (ook wel transportregels genoemd) om kopieën te ontvangen van berichten die gebruikers rapporteren aan Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 40e87fec3bfd8ed4402713ca7ec45499bb50c68e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287603"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="2d2d6-103">Regels voor e-mailstromen gebruiken om te zien wat je gebruikers melden bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="2d2d6-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2d2d6-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="2d2d6-104">**Applies to**</span></span>
- [<span data-ttu-id="2d2d6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2d2d6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2d2d6-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2d2d6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="2d2d6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d2d6-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="2d2d6-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken zijn er verschillende manieren waarop gebruikers berichten kunnen rapporteren aan Microsoft voor analyse, zoals beschreven in rapportberichten en bestanden [bij Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="2d2d6-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="2d2d6-109">U kunt een e-mailstroomregel (ook wel transportregel genoemd) maken die zoekt naar berichten die gebruikers rapporteren aan Microsoft en u kunt BCC-geadresseerden zo configureren dat kopieën van deze gerapporteerde berichten worden ontvangen.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-109">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="2d2d6-110">U kunt de regel voor de e-mailstroom maken in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Postvakken van Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="2d2d6-110">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2d2d6-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="2d2d6-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2d2d6-112">U moet machtigingen toegewezen krijgen in Exchange Online of Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-112">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="2d2d6-113">U hebt met name de rol **Transportregels** nodig, die standaard is toegewezen aan de rollengroepen **Organisatiebeheer,** **Compliancebeheer** (globale beheerders) en **Recordbeheer.**</span><span class="sxs-lookup"><span data-stu-id="2d2d6-113">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="2d2d6-114">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="2d2d6-114">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="2d2d6-115">Machtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2d2d6-115">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="2d2d6-116">Machtigingen in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="2d2d6-116">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="2d2d6-117">De lijst met leden in rollengroepen wijzigen met het EAC</span><span class="sxs-lookup"><span data-stu-id="2d2d6-117">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="2d2d6-118">Als u het Exchange-beheercentrum wilt openen in Exchange Online, gaat u naar [het Exchange-beheercentrum in Exchange Online.](https://docs.microsoft.com/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="2d2d6-118">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="2d2d6-119">Zie het Exchange-beheercentrum in de zelfstandige EOP om het Exchange-beheercentrum [te openen in de zelfstandige EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="2d2d6-119">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="2d2d6-120">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2d2d6-121">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2d2d6-122">Zie de volgende onderwerpen voor meer informatie over regels voor de e-mailstroom in Exchange Online en de zelfstandige EOP:</span><span class="sxs-lookup"><span data-stu-id="2d2d6-122">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="2d2d6-123">E-mailstroomregels (transportregels) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2d2d6-123">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="2d2d6-124">Voorwaarden en uitzonderingen voor e-mailstroomregel (predicaten) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2d2d6-124">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="2d2d6-125">Acties voor e-mailstroomregel in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2d2d6-125">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="2d2d6-126">Het EAC gebruiken om een regel voor de e-mailstroom te maken voor het ontvangen van kopieën van gerapporteerde berichten</span><span class="sxs-lookup"><span data-stu-id="2d2d6-126">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="2d2d6-127">Ga in het EAC naar **Regels voor e-mailstroom.** \> </span><span class="sxs-lookup"><span data-stu-id="2d2d6-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="2d2d6-128">Klik **op het** pictogram Toevoegen en selecteer een nieuwe regel ![ ](../../media/ITPro-EAC-AddIcon.png) **maken.**</span><span class="sxs-lookup"><span data-stu-id="2d2d6-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="2d2d6-129">Configureer **de volgende instellingen** op de pagina Nieuwe regel die wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="2d2d6-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="2d2d6-130">**Naam:** voer een unieke, beschrijvende naam voor de regel in.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-130">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="2d2d6-131">Bijvoorbeeld BCC-berichten gerapporteerd bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-131">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="2d2d6-132">Klik **op Meer opties.**</span><span class="sxs-lookup"><span data-stu-id="2d2d6-132">Click **More Options**.</span></span>

   - <span data-ttu-id="2d2d6-133">Pas deze regel  toe **als:** Selecteer het adres van de geadresseerde bevat een van deze woorden: Voer in het dialoogvenster Woorden of woordgroepen opgeven dat wordt weergegeven een van de volgende waarden in, klik op Pictogram toevoegen en herhaal dit totdat u alle waarden hebt \>    ![ ](../../media/ITPro-EAC-AddIcon.png) ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-133">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     <span data-ttu-id="2d2d6-134">Als u een item wilt bewerken, selecteert u dit en klikt u op **het pictogram** ![ ](../../media/ITPro-EAC-EditIcon.png) Bewerken.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="2d2d6-135">Als u een vermelding wilt verwijderen, selecteert u deze en klikt u **op pictogram** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="2d2d6-136">Klik op OK wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="2d2d6-136">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="2d2d6-137">**Ga als volgt te** werk: **selecteer Geadresseerden toevoegen** aan het vak \> **BCC.**</span><span class="sxs-lookup"><span data-stu-id="2d2d6-137">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="2d2d6-138">Zoek en selecteer de geadresseerden die u wilt toevoegen in het dialoogvenster dat wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-138">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="2d2d6-139">Klik op OK wanneer u **klaar bent.**</span><span class="sxs-lookup"><span data-stu-id="2d2d6-139">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="2d2d6-140">U kunt extra selecties maken om de regel te controleren, de regel te testen, de regel te activeren tijdens een bepaalde periode en andere instellingen.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-140">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="2d2d6-141">Het is raadzaam de regel te testen voordat u deze afdwingt.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-141">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="2d2d6-142">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-142">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="2d2d6-143">PowerShell gebruiken om een regel voor de e-mailstroom te maken om kopieën van gerapporteerde berichten te ontvangen</span><span class="sxs-lookup"><span data-stu-id="2d2d6-143">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="2d2d6-144">In dit voorbeeld wordt een nieuwe regel voor de e-mailstroom gemaakt met de naam BCC-berichten gerapporteerd bij Microsoft, die zoekt naar e-mailberichten die aan Microsoft zijn gerapporteerd aan de hand van de methoden die in dit artikel worden beschreven, en die de gebruikers laura@contoso.com en julia@contoso.com toevoegt als BCC-geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-144">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="2d2d6-145">Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-145">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2d2d6-146">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="2d2d6-146">How do you know this worked?</span></span>

<span data-ttu-id="2d2d6-147">Als u wilt controleren of u een regels voor de e-mailstroom hebt geconfigureerd om kopieën van gerapporteerde berichten te ontvangen, gaat u op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="2d2d6-147">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="2d2d6-148">Ga in het EAC naar Regels voor **e-mailstroom** selecteer de regel en klik op het pictogram \>  \> Bewerken bewerken en \> controleer  ![ de ](../../media/ITPro-EAC-EditIcon.png) instellingen.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-148">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="2d2d6-149">Voer in PowerShell de volgende opdracht uit om de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="2d2d6-149">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="2d2d6-150">Stuur een testmelding naar een van de e-mailadressen van de rapportage en controleer de resultaten.</span><span class="sxs-lookup"><span data-stu-id="2d2d6-150">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
