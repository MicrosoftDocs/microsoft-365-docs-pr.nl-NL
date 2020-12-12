---
title: Regels voor e-mailstromen gebruiken om te zien wat je gebruikers melden bij Microsoft
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
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie over het gebruik van e-mail stroom regels (ook wel transport-regels genoemd) gebruiken om kopieën te ontvangen van berichten die gebruikers naar Microsoft melden.
ms.openlocfilehash: 0f3046c9d1962366ffd75353347b6cf7b72afd14
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659847"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="ad2bb-103">Regels voor e-mailstromen gebruiken om te zien wat je gebruikers melden bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="ad2bb-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ad2bb-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken zijn er meerdere manieren waarop gebruikers berichten kunnen rapporteren aan Microsoft voor analyse zoals beschreven in [berichten en bestanden aan Microsoft rapporteren](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ad2bb-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="ad2bb-105">U kunt een e-mail stroom regel (ook wel een transportregel genoemd) maken waarmee berichten die gebruikers naar Microsoft rapporteren, kunnen worden weergegeven en dat er kopieën van deze gerapporteerde berichten kunnen worden ontvangen.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="ad2bb-106">U kunt de e-mail stroom regel maken in het Exchange Admin Center (SBV) en PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="ad2bb-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ad2bb-107">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="ad2bb-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ad2bb-108">Voordat u de procedures in dit artikel kunt uitvoeren, moet u beschikken over machtigingen voor Exchange Online of Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-108">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="ad2bb-109">Specifiek hebt u de rol van **transport regels** nodig, dat is toegewezen aan **Organisatiebeheer**, **nalevings beheer** (globale beheerders) en rollen groepen voor **recordbeheer** .</span><span class="sxs-lookup"><span data-stu-id="ad2bb-109">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="ad2bb-110">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="ad2bb-110">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="ad2bb-111">Machtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ad2bb-111">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="ad2bb-112">Machtigingen in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="ad2bb-112">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="ad2bb-113">Werken met de lijst met wijzigingen in de lijst met leden van rollen groepen</span><span class="sxs-lookup"><span data-stu-id="ad2bb-113">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="ad2bb-114">Zie [Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)om het SBV te openen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="ad2bb-115">Als u het Exchange-Beheercentrum in standalone EOP wilt openen, raadpleegt u [Exchange Admin Center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="ad2bb-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="ad2bb-116">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ad2bb-117">Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ad2bb-118">Zie de volgende onderwerpen voor meer informatie over regels voor e-mail stroom in Exchange Online en zelfstandige EOP:</span><span class="sxs-lookup"><span data-stu-id="ad2bb-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="ad2bb-119">Regels voor e-mail stroom (transportregels) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ad2bb-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="ad2bb-120">Voorwaarden voor de e-mail stroom regels en uitzonderingen (predikaten) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ad2bb-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="ad2bb-121">Acties voor e-mail stroom regels in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ad2bb-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="ad2bb-122">Gebruik de functie SBV om een e-mail stroom regel te maken om kopieën van gerapporteerde berichten te ontvangen</span><span class="sxs-lookup"><span data-stu-id="ad2bb-122">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="ad2bb-123">Ga in het Exchange-Beheercentrum naar de regels voor de **e-mail stroom** \> .</span><span class="sxs-lookup"><span data-stu-id="ad2bb-123">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="ad2bb-124">Klik **op** ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en selecteer vervolgens **een nieuwe regel maken**.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-124">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="ad2bb-125">Configureer de volgende instellingen op de pagina **nieuwe regel** die wordt geopend:</span><span class="sxs-lookup"><span data-stu-id="ad2bb-125">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="ad2bb-126">**Naam**: Typ een unieke, beschrijvende naam voor de regel.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-126">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="ad2bb-127">BCC-berichten die naar Microsoft zijn gerapporteerd, bijvoorbeeld</span><span class="sxs-lookup"><span data-stu-id="ad2bb-127">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="ad2bb-128">Klik op **meer opties**.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-128">Click **More Options**.</span></span>

   - <span data-ttu-id="ad2bb-129">**Deze regel toepassen als**: Selecteer het adres van **de ontvanger** \> **bevat een of meer van deze woorden**: Typ een van de volgende waarden in het dialoogvenster **woorden of woordgroepen opgeven** dat wordt weergegeven, klik op  ![ pictogram toevoegen ](../../media/ITPro-EAC-AddIcon.png) en herhaal dit tot u alle waarden hebt ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-129">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="ad2bb-130">Als u een vermelding wilt bewerken, selecteert u  deze en klikt u op ![ pictogram bewerken bewerken ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="ad2bb-130">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="ad2bb-131">Als u een vermelding wilt verwijderen, selecteert u deze **en klikt u** op het ![ pictogram verwijderen ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="ad2bb-131">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="ad2bb-132">Wanneer u klaar bent, klikt u op **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-132">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="ad2bb-133">**Ga als volgt** te werk: Selecteer **geadresseerden toevoegen** \> **aan het vak BCC**.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-133">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="ad2bb-134">In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u de geadresseerden die u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-134">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="ad2bb-135">Wanneer u klaar bent, klikt u op **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-135">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="ad2bb-136">U kunt extra keuzes maken om de regel te controleren, de regel te testen, de regel te activeren gedurende een specifieke periode en andere instellingen.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-136">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="ad2bb-137">U wordt aangeraden de regel te testen voordat u deze afdwingt.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-137">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="ad2bb-138">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-138">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="ad2bb-139">PowerShell gebruiken om een e-mail stroom regel te maken om kopieën van gerapporteerde berichten te ontvangen</span><span class="sxs-lookup"><span data-stu-id="ad2bb-139">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="ad2bb-140">In dit voorbeeld wordt een nieuwe e-mail stroom regel met de naam BCC-berichten gerapporteerd aan Microsoft waarmee wordt gezocht naar e-mailberichten die bij Microsoft worden gerapporteerd met behulp van de methoden die in dit artikel worden beschreven, en voegt u de gebruikers laura@contoso.com en julia@contoso.com toe als BCC-geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-140">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="ad2bb-141">Zie [Nieuwe-Transportregel](https://docs.microsoft.com/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-141">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ad2bb-142">Hoe weet u of dit heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="ad2bb-142">How do you know this worked?</span></span>

<span data-ttu-id="ad2bb-143">Voer een van de volgende stappen uit om te controleren of u een e-mail stroom regels hebt geconfigureerd om kopieën van gerapporteerde berichten te ontvangen:</span><span class="sxs-lookup"><span data-stu-id="ad2bb-143">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="ad2bb-144">Ga in het Exchange-Beheercentrum naar **e-mail stroom** \> **regels** \> , selecteer de regel Klik op bewerkings \> pictogram **bewerken** ![ ](../../media/ITPro-EAC-EditIcon.png) en controleer de instellingen.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-144">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="ad2bb-145">In PowerShell voert u de volgende opdracht uit om de instellingen te controleren:</span><span class="sxs-lookup"><span data-stu-id="ad2bb-145">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="ad2bb-146">Verzend een testbericht naar een van de e-mailadressen van de rapporten en controleer de resultaten.</span><span class="sxs-lookup"><span data-stu-id="ad2bb-146">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
