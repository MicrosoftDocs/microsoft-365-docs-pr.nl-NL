---
title: Een beleid voor het type gevoelige informatie maken met Office 365-berichtversleuteling
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Meer informatie over het maken van een beleid voor het type gevoelige informatie voor uw organisatie met Office 365-berichtversleuteling.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad570f64122aecd245b912b1b6545a5950e838cc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162169"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a><span data-ttu-id="b215b-103">Een beleid voor het type gevoelige informatie voor uw organisatie maken met behulp van berichtversleuteling</span><span class="sxs-lookup"><span data-stu-id="b215b-103">Create a sensitive information type policy for your organization using Message Encryption</span></span>

<span data-ttu-id="b215b-104">U kunt de regels Exchange e-mailstroom of DLP (Data Loss Prevention) gebruiken om een beleid voor gevoelige informatie te maken met Office 365-berichtversleuteling.</span><span class="sxs-lookup"><span data-stu-id="b215b-104">You can use either Exchange mail flow rules or Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="b215b-105">Als u een Exchange e-mailstroomregel wilt maken, kunt u het EAC -beheercentrum (EAC) of PowerShell Exchange gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b215b-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="b215b-106">Het beleid maken met behulp van e-mailstroomregels in het EAC</span><span class="sxs-lookup"><span data-stu-id="b215b-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="b215b-107">Meld u aan bij het Exchange-beheercentrum (EAC) en ga naar **E-mailstroomregels.**  >  </span><span class="sxs-lookup"><span data-stu-id="b215b-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="b215b-108">Maak op de pagina Regels een regel die van toepassing is op Office 365-berichtversleuteling.</span><span class="sxs-lookup"><span data-stu-id="b215b-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="b215b-109">U kunt een regel maken op basis van voorwaarden, zoals de aanwezigheid van bepaalde trefwoorden of gevoelige informatietypen in het bericht of de bijlage.</span><span class="sxs-lookup"><span data-stu-id="b215b-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="b215b-110">Het beleid maken met behulp van e-mailstroomregels in PowerShell</span><span class="sxs-lookup"><span data-stu-id="b215b-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="b215b-111">Gebruik een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie, start een Windows PowerShell en maak verbinding met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b215b-111">Use a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="b215b-112">Zie Verbinding maken [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="b215b-112">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b215b-113">Gebruik de Set-IRMConfiguration en New-TransportRule cmdlets om het beleid te maken.</span><span class="sxs-lookup"><span data-stu-id="b215b-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="b215b-114">Voorbeeld van een e-mailstroomregel die is gemaakt met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b215b-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="b215b-115">Voer de volgende opdrachten uit in PowerShell om een Exchange-mailstroomregel te maken die automatisch e-mailberichten versleutelt die buiten uw organisatie worden verzonden met de optie alleen-versleutelen als de e-mailberichten of hun bijlagen de volgende typen gevoelige informatie bevatten:</span><span class="sxs-lookup"><span data-stu-id="b215b-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the encrypt-only option if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="b215b-116">ABA-routeringsnummer</span><span class="sxs-lookup"><span data-stu-id="b215b-116">ABA routing number</span></span>
- <span data-ttu-id="b215b-117">Creditcardnummer</span><span class="sxs-lookup"><span data-stu-id="b215b-117">Credit card Number</span></span>
- <span data-ttu-id="b215b-118">Nummer van Het Bureau voor drugshandhaving (DEA)</span><span class="sxs-lookup"><span data-stu-id="b215b-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="b215b-119">V.S. / VK</span><span class="sxs-lookup"><span data-stu-id="b215b-119">U.S. / U.K.</span></span> <span data-ttu-id="b215b-120">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="b215b-120">passport number</span></span>
- <span data-ttu-id="b215b-121">Amerikaans bankrekeningnummer</span><span class="sxs-lookup"><span data-stu-id="b215b-121">U.S. bank account number</span></span>
- <span data-ttu-id="b215b-122">U.S. Individual Taxpayer Identification Number (ITIN)</span><span class="sxs-lookup"><span data-stu-id="b215b-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="b215b-123">U.S. Social Security Number (SSN)</span><span class="sxs-lookup"><span data-stu-id="b215b-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="b215b-124">Zie Set-IRMConfiguration and New-TransportRule [(Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) and [New-TransportRule)](/powershell/module/exchange/new-transportrule)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b215b-124">For more information, see [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) and [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="b215b-125">Hoe geadresseerden bijlagen openen</span><span class="sxs-lookup"><span data-stu-id="b215b-125">How recipients access attachments</span></span>

<span data-ttu-id="b215b-126">Nadat Microsoft een bericht versleutelt, hebben geadresseerden onbeperkte toegang tot bijlagen wanneer ze hun versleutelde e-mail openen en openen.</span><span class="sxs-lookup"><span data-stu-id="b215b-126">After Microsoft encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="b215b-127">Voorbereidingen treffen voor deze wijziging</span><span class="sxs-lookup"><span data-stu-id="b215b-127">To prepare for this change</span></span>

<span data-ttu-id="b215b-128">Mogelijk wilt u alle toepasselijke documentatie en trainingsmateriaal voor eindgebruikers bijwerken om personen in uw organisatie voor te bereiden op deze wijziging.</span><span class="sxs-lookup"><span data-stu-id="b215b-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="b215b-129">Deel deze Office 365-berichtversleuteling resources met uw gebruikers:</span><span class="sxs-lookup"><span data-stu-id="b215b-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="b215b-130">Versleutelde berichten verzenden, weergeven en beantwoorden in Outlook pc</span><span class="sxs-lookup"><span data-stu-id="b215b-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="b215b-131">Microsoft 365 Essentials Video: Office Berichtversleuteling</span><span class="sxs-lookup"><span data-stu-id="b215b-131">Microsoft 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="b215b-132">Deze wijzigingen weergeven in het auditlogboek</span><span class="sxs-lookup"><span data-stu-id="b215b-132">View these changes in the audit log</span></span>

<span data-ttu-id="b215b-133">Microsoft 365 deze activiteit controleert en deze beschikbaar stelt voor beheerders.</span><span class="sxs-lookup"><span data-stu-id="b215b-133">Microsoft 365 audits this activity and makes it available to administrators.</span></span> <span data-ttu-id="b215b-134">De bewerking is 'New-TransportRule' en een fragment van een voorbeeldauditinvoer uit het auditlogboek zoeken in & compliancecentrum is hieronder:</span><span class="sxs-lookup"><span data-stu-id="b215b-134">The operation is 'New-TransportRule' and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="b215b-135">Het beleid voor gevoelige informatietypen uitschakelen of aanpassen</span><span class="sxs-lookup"><span data-stu-id="b215b-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="b215b-136">Nadat u de Exchange-mailstroomregel hebt gemaakt, [](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) kunt u de regel uitschakelen of bewerken door naar E-mailstroomregels in het Exchange-beheercentrum (EAC) te gaan en de regel ' Uitgaande gevoelige e-mailberichten  >   versleutelen *(standaardregel)* uit te schakelen'.</span><span class="sxs-lookup"><span data-stu-id="b215b-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule "*Encrypt outbound sensitive emails (out of box rule)*".</span></span>