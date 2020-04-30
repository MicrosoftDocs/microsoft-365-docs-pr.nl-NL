---
title: Regels voor e-mailstromen gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze regels voor e-mailstromen (ook wel transportregels genoemd) kunnen gebruiken om kopieën te ontvangen van berichten die gebruikers aan Microsoft rapporteren.
ms.openlocfilehash: 2b1e82ece936551c48e5617955f546cf851a8913
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939497"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="7c652-103">Regels voor e-mailstromen gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren</span><span class="sxs-lookup"><span data-stu-id="7c652-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="7c652-104">Gebruikers kunnen berichten op meerdere manieren aan Microsoft rapporteren voor analyse zoals beschreven in [Berichten en bestanden rapporteren aan Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="7c652-104">There are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="7c652-105">U een regel voor e-mailstroom (ook wel een transportregel genoemd) maken die zoekt naar berichten die gebruikers aan Microsoft rapporteren, en u BCC-ontvangers configureren om kopieën van deze gerapporteerde berichten te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="7c652-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="7c652-106">U de regel voor e-mailstroom maken in het Exchange-beheercentrum (EAC) en PowerShell (Exchange Online PowerShell voor Microsoft 365-klanten. Exchange Online Protection PowerShell voor zelfstandige EOP-klanten).</span><span class="sxs-lookup"><span data-stu-id="7c652-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7c652-107">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="7c652-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7c652-108">U moet machtigingen in Exchange Online of EOP krijgen voordat u deze procedures uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="7c652-108">You need to be assigned permissions in Exchange Online or EOP before you can do these procedures.</span></span> <span data-ttu-id="7c652-109">U moet in het bijzonder de rol **Transportregels** toegewezen krijgen, die standaard is toegewezen aan de rollen **Organisatiebeheer,** **Compliancebeheer**en **Records Management.**</span><span class="sxs-lookup"><span data-stu-id="7c652-109">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="7c652-110">Zie [Rolgroepen beheren in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)voor meer informatie .</span><span class="sxs-lookup"><span data-stu-id="7c652-110">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="7c652-111">Zie [Exchange-beheercentrum in Exchange Online-](https://docs.microsoft.com/Exchange/exchange-admin-center) of [Exchange-beheercentrum in Exchange Online Protection als](exchange-admin-center-in-exchange-online-protection-eop.md)u de EAC wilt openen.</span><span class="sxs-lookup"><span data-stu-id="7c652-111">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="7c652-112">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c652-112">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="7c652-113">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c652-113">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7c652-114">Zie de volgende onderwerpen voor meer informatie over regels voor e-mailstromen in Exchange Online en zelfstandige EOP:</span><span class="sxs-lookup"><span data-stu-id="7c652-114">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="7c652-115">Regels voor e-mailstroom (transportregels) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7c652-115">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="7c652-116">Voorwaarden en uitzonderingen voor e-mailstroomregels (predicaten) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7c652-116">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="7c652-117">Acties voor e-mailstroomregel in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7c652-117">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="7c652-118">De EAC gebruiken om een e-mailstroomregel te maken om kopieën van gerapporteerde berichten te ontvangen</span><span class="sxs-lookup"><span data-stu-id="7c652-118">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="7c652-119">Ga in de EAC naar **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="7c652-119">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="7c652-120">Klik **op** ![](../../media/ITPro-EAC-AddIcon.png) Pictogram Toevoegen toevoegen en selecteer **vervolgens Een nieuwe regel maken**.</span><span class="sxs-lookup"><span data-stu-id="7c652-120">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="7c652-121">Configureer op de pagina **Nieuwe regel** die wordt geopend de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="7c652-121">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="7c652-122">**Naam:** Voer een unieke, beschrijvende naam voor de regel in.</span><span class="sxs-lookup"><span data-stu-id="7c652-122">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="7c652-123">Bijvoorbeeld, BCC Berichten Gerapporteerd aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7c652-123">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="7c652-124">Klik **op Meer opties**.</span><span class="sxs-lookup"><span data-stu-id="7c652-124">Click **More Options**.</span></span>

   - <span data-ttu-id="7c652-125">**Deze regel toepassen als**: **Selecteer Het geadresseerdeadres** \> **bevat een van deze woorden:** Voer in het dialoogvenster](../../media/ITPro-EAC-AddIcon.png)Woorden of zinnen **opgeven** dat wordt weergegeven een van de volgende waarden in, klik op Pictogram **toevoegen** ![en herhaal totdat u alle waarden hebt ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="7c652-125">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="7c652-126">Als u een item wilt **Edit** ![bewerken, selecteert](../../media/ITPro-EAC-EditIcon.png)u het item en klikt u op pictogram Bewerken bewerken .</span><span class="sxs-lookup"><span data-stu-id="7c652-126">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="7c652-127">Als u een item wilt **Remove** ![verwijderen,](../../media/ITPro-EAC-DeleteIcon.png)selecteert u het item en klikt u op Pictogram Verwijderen .</span><span class="sxs-lookup"><span data-stu-id="7c652-127">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="7c652-128">Klik op **OK**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="7c652-128">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="7c652-129">**Ga als volgt**te werk : Selecteer **Geadresseerden** \> toevoegen **aan het vak BCC**.</span><span class="sxs-lookup"><span data-stu-id="7c652-129">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="7c652-130">Zoek en selecteer in het dialoogvenster dat wordt weergegeven de geadresseerden die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="7c652-130">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="7c652-131">Klik op **OK**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="7c652-131">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="7c652-132">U extra selecties maken om de regel te controleren, de regel te testen, de regel te activeren gedurende een bepaalde periode en andere instellingen.</span><span class="sxs-lookup"><span data-stu-id="7c652-132">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="7c652-133">We raden u aan de regel te testen voordat u deze afdwingt.</span><span class="sxs-lookup"><span data-stu-id="7c652-133">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="7c652-134">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="7c652-134">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="7c652-135">PowerShell gebruiken om een e-mailstroomregel te maken om kopieën van gerapporteerde berichten te ontvangen</span><span class="sxs-lookup"><span data-stu-id="7c652-135">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="7c652-136">In dit voorbeeld wordt een nieuwe regel voor e-mailstroom gemaakt met de naam BCC-berichten die aan Microsoft worden gerapporteerd en die wordt gerapporteerd met behulp van de methoden die in dit onderwerp zijn beschreven, en worden de gebruikers laura@contoso.com en julia@contoso.com toegevoegd als BCC-ontvangers.</span><span class="sxs-lookup"><span data-stu-id="7c652-136">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="7c652-137">Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="7c652-137">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7c652-138">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="7c652-138">How do you know this worked?</span></span>

<span data-ttu-id="7c652-139">Ga een van de volgende stappen uit om te controleren of u een e-mailstroomregels hebt geconfigureerd om kopieën van gerapporteerde berichten te ontvangen:</span><span class="sxs-lookup"><span data-stu-id="7c652-139">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="7c652-140">Ga in de EAC naar **EAC-regels** \> **Rules** \> en selecteer](../../media/ITPro-EAC-EditIcon.png)de regel \> klik op Pictogram Bewerken **bewerken** ![en controleer de instellingen.</span><span class="sxs-lookup"><span data-stu-id="7c652-140">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="7c652-141">Voer in PowerShell de volgende opdracht uit om de instellingen te verifiëren:</span><span class="sxs-lookup"><span data-stu-id="7c652-141">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="7c652-142">Stuur een testbericht naar een van de rapportage-e-mailadressen en verifieer de resultaten.</span><span class="sxs-lookup"><span data-stu-id="7c652-142">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
