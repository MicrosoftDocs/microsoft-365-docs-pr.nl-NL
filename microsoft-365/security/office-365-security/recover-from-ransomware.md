---
title: Herstel na een ransomware-aanval
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft 365-beheerders kunnen leren hoe ze kunnen worden hersteld via een Ransomware-aanval.
ms.openlocfilehash: dd740b19abac9d30196c1ffd82c8a3f377b19dbf
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845538"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="46fe0-103">Herstel van een Ransomware aanval in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="46fe0-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="46fe0-104">Zelfs als u om de bescherming van uw organisatie te beschermen, kunt u nog steeds slachtoffer [van een aanval](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) doen.</span><span class="sxs-lookup"><span data-stu-id="46fe0-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="46fe0-105">Ransomware is Big Business en de aanvallen zijn uitgebreid.</span><span class="sxs-lookup"><span data-stu-id="46fe0-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="46fe0-106">Met de stappen in dit onderwerp krijgt u de beste kans om gegevens te herstellen die zijn versleuteld met de Ransomware, en om de verspreiding van de infectie binnen uw organisatie te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="46fe0-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your organization.</span></span> <span data-ttu-id="46fe0-107">Houd rekening met de volgende punten voordat u aan de slag gaat:</span><span class="sxs-lookup"><span data-stu-id="46fe0-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="46fe0-108">Er is geen garantie voor het betalen van de Ransom om toegang te krijgen tot uw bestanden.</span><span class="sxs-lookup"><span data-stu-id="46fe0-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="46fe0-109">Met de Ransom kunt u in feite een doelwit maken van een meer Ransomware.</span><span class="sxs-lookup"><span data-stu-id="46fe0-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="46fe0-110">Als u al hebt betaald, maar u hebt uw bestanden wel hersteld zonder dat u de resolutie van de aanvaller hoeft te gebruiken, belt u de Bank om te zien of ze de transactie kunnen blokkeren.</span><span class="sxs-lookup"><span data-stu-id="46fe0-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="46fe0-111">We raden u ook aan om de fraude aanval aan te melden, websites met uitlichting en Microsoft te melden zoals verderop in dit artikel wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="46fe0-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="46fe0-112">Het is heel belangrijk dat u snel aan de aanval antwoordt en de gevolgen hiervan.</span><span class="sxs-lookup"><span data-stu-id="46fe0-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="46fe0-113">Hoe meer u wacht, hoe minder waarschijnlijk u de betrokken gegevens kunt herstellen.</span><span class="sxs-lookup"><span data-stu-id="46fe0-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="46fe0-114">Stap 1: uw back-ups controleren</span><span class="sxs-lookup"><span data-stu-id="46fe0-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="46fe0-115">Als u offline back-ups hebt, kunt u de versleutelde gegevens waarschijnlijk terugzetten **nadat** u de nettolading van Ransomware (malware) van uw omgeving hebt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="46fe0-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="46fe0-116">U kunt deze stap overslaan als u geen back-ups hebt, of als de back-up ook van invloed zijn op de back-up.</span><span class="sxs-lookup"><span data-stu-id="46fe0-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="46fe0-117">Stap 2: ActiveSync en OneDrive-synchronisatie uitschakelen</span><span class="sxs-lookup"><span data-stu-id="46fe0-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="46fe0-118">Met het hoofdpunt kunt u het versleutelen van gegevensversleuteling door de Ransomware beëindigen.</span><span class="sxs-lookup"><span data-stu-id="46fe0-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="46fe0-119">Als u vermoedt dat e-mail een doel is, dient u gebruikers toegang tot postvakken tijdelijk uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="46fe0-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="46fe0-120">Exchange ActiveSync wordt door mobiele apparaten gebruikt voor het synchroniseren van gegevens tussen het apparaat en het Exchange Online-postvak.</span><span class="sxs-lookup"><span data-stu-id="46fe0-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="46fe0-121">Zie [Exchange ActiveSync voor gebruikers uitschakelen in Exchange Online voor meer informatie over](https://support.microsoft.com/help/2795303)het uitschakelen van ActiveSync voor een postvak.</span><span class="sxs-lookup"><span data-stu-id="46fe0-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="46fe0-122">Als u andere soorten toegang wilt uitschakelen voor een postvak, raadpleegt u:</span><span class="sxs-lookup"><span data-stu-id="46fe0-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="46fe0-123">[MAPI voor een postvak in-of uitschakelen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span><span class="sxs-lookup"><span data-stu-id="46fe0-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="46fe0-124">POP3-of IMAP4-toegang voor een gebruiker in-of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="46fe0-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="46fe0-125">Als u de synchronisatie van OneDrive onderbreekt, wordt de bescherming van uw cloudgegevens verhelpt tegen het bijwerken van mogelijk besmette apparaten.</span><span class="sxs-lookup"><span data-stu-id="46fe0-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="46fe0-126">Zie [synchronisatie onderbreken en hervatten in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="46fe0-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="46fe0-127">Stap 3: Verwijder de malware van de betreffende apparaten</span><span class="sxs-lookup"><span data-stu-id="46fe0-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="46fe0-128">Voer een volledige virusscan uit met de meest recente updates op alle verdachte computers en apparaten om de nettolading te detecteren en te verwijderen die is gekoppeld aan de Ransomware.</span><span class="sxs-lookup"><span data-stu-id="46fe0-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="46fe0-129">Vergeet niet om apparaten te gebruiken die gegevens synchroniseren, of het doel van toegewezen netwerkstations (deze computers en apparaten moeten ook worden gescand).</span><span class="sxs-lookup"><span data-stu-id="46fe0-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="46fe0-130">U kunt [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) of (voor oudere clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="46fe0-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="46fe0-131">Een alternatief waarmee u het programma van Ransomware en malware kunt verwijderen is het hulpprogramma voor het verwijderen van [schadelijke software (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span><span class="sxs-lookup"><span data-stu-id="46fe0-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="46fe0-132">Als deze opties niet werken, kunt u [Windows Defender offline](https://support.microsoft.com/help/17466) proberen of [problemen oplossen met het detecteren en verwijderen van malware](https://support.microsoft.com/help/4466982).</span><span class="sxs-lookup"><span data-stu-id="46fe0-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="46fe0-133">Stap 4: bestanden herstellen op een geschoonde computer of apparaat</span><span class="sxs-lookup"><span data-stu-id="46fe0-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="46fe0-134">Nadat u de vorige stap hebt uitgevoerd om de een Ransomware-nettolading uit uw omgeving te verwijderen (zodat de software niet uw bestanden kan versleutelen of verwijderen), kunt u de [geschiedenis](https://support.microsoft.com/help/17128) van bestanden in Windows 10 en Windows 8,1 of systeembeveiliging in Windows 7 gebruiken om te proberen om uw lokale bestanden en mappen te herstellen.</span><span class="sxs-lookup"><span data-stu-id="46fe0-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="46fe0-135">**Opmerkingen** :</span><span class="sxs-lookup"><span data-stu-id="46fe0-135">**Notes** :</span></span>

- <span data-ttu-id="46fe0-136">U kunt ook de back-upversies van Ransomware versleutelen of verwijderen, zodat u geen bestanden kunt herstellen met bestandsgeschiedenis of systeembeveiliging</span><span class="sxs-lookup"><span data-stu-id="46fe0-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="46fe0-137">Als dat het geval is, dan moet u gebruikmaken van back-ups op externe stations of apparaten die niet worden beïnvloed door de Ransomware of OneDrive, zoals beschreven in de volgende sectie.</span><span class="sxs-lookup"><span data-stu-id="46fe0-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="46fe0-138">Als een map wordt gesynchroniseerd met OneDrive en u niet werkt met de nieuwste versie van Windows, kunnen er enkele beperkingen gelden met de bestandsgeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="46fe0-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="46fe0-139">Stap 5: uw bestanden in OneDrive voor bedrijven herstellen</span><span class="sxs-lookup"><span data-stu-id="46fe0-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="46fe0-140">Met bestanden herstellen in OneDrive voor bedrijven kunt u uw volledige OneDrive herstellen naar een vorig tijdstip in de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="46fe0-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="46fe0-141">Zie [uw OneDrive herstellen](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="46fe0-141">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="46fe0-142">Stap 6: verwijderde e-mail herstellen</span><span class="sxs-lookup"><span data-stu-id="46fe0-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="46fe0-143">In het zeldzame geval dat de Ransomware al uw e-mail heeft verwijderd, kunt u de verwijderde items waarschijnlijk herstellen.</span><span class="sxs-lookup"><span data-stu-id="46fe0-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="46fe0-144">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="46fe0-144">For more information, see:</span></span>

- [<span data-ttu-id="46fe0-145">Verwijderde berichten herstellen in het postvak van een gebruiker</span><span class="sxs-lookup"><span data-stu-id="46fe0-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="46fe0-146">Verwijderde items herstellen in Outlook voor Windows</span><span class="sxs-lookup"><span data-stu-id="46fe0-146">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="46fe0-147">Stap 7: synchronisatie van Exchange ActiveSync en OneDrive opnieuw inschakelen</span><span class="sxs-lookup"><span data-stu-id="46fe0-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="46fe0-148">Nadat u de computers en apparaten hebt opgeschoond en de gegevens hebt hersteld, kunt u ActiveSync en OneDrive-synchronisatie opnieuw inschakelen die u eerder in [stap 2](#step-2-disable-activesync-and-onedrive-sync)hebt uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="46fe0-148">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="46fe0-149">Stap 8 (optioneel): OneDrive-synchronisatieblok keren voor specifieke bestandsextensies</span><span class="sxs-lookup"><span data-stu-id="46fe0-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="46fe0-150">Wanneer u hebt teruggezet, kunt u voorkomen dat OneDrive voor bedrijven-clients synchroniseren met de bestandstypen die door deze Ransomware werden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="46fe0-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="46fe0-151">Zie [set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="46fe0-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="46fe0-152">De aanval melden</span><span class="sxs-lookup"><span data-stu-id="46fe0-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="46fe0-153">Neem contact op met de politie</span><span class="sxs-lookup"><span data-stu-id="46fe0-153">Contact law enforcement</span></span>

<span data-ttu-id="46fe0-154">U dient contact op te nemen met uw lokale of nationale politieautoriteiten.</span><span class="sxs-lookup"><span data-stu-id="46fe0-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="46fe0-155">Als u bijvoorbeeld in de Verenigde Staten woont, kunt u contact opnemen met de [FBI Local Field Office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) of [Secret Service](http://www.secretservice.gov/).</span><span class="sxs-lookup"><span data-stu-id="46fe0-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="46fe0-156">Een rapport indienen bij de website voor het rapporteren van de fraude van uw land</span><span class="sxs-lookup"><span data-stu-id="46fe0-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="46fe0-157">Websites voor het rapporteren van de zwendel geven informatie over het voorkomen en vermijden van Scams.</span><span class="sxs-lookup"><span data-stu-id="46fe0-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="46fe0-158">Ze bieden ook mechanismen om te rapporteren als u slachtoffer van de zwendel was.</span><span class="sxs-lookup"><span data-stu-id="46fe0-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="46fe0-159">Australië: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="46fe0-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="46fe0-160">Canada: [anti-fraude centrum](http://www.antifraudcentre-centreantifraude.ca/) voor Canada</span><span class="sxs-lookup"><span data-stu-id="46fe0-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="46fe0-161">Frankrijk: [Agence nationale de la Sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="46fe0-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="46fe0-162">Duitsland: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="46fe0-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="46fe0-163">Ierland: [een Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="46fe0-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="46fe0-164">Nieuw-Zeeland: [fraude zaken](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="46fe0-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="46fe0-165">Verenigd Koninkrijk: [actie fraude](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="46fe0-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="46fe0-166">Verenigde Staten: [online beschermen](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="46fe0-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="46fe0-167">Als uw land niet wordt vermeld, vraag dan contact op met uw lokale of nationale politiediensten.</span><span class="sxs-lookup"><span data-stu-id="46fe0-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="46fe0-168">E-mailberichten bij Microsoft indienen</span><span class="sxs-lookup"><span data-stu-id="46fe0-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="46fe0-169">U kunt phishing melden met Ransomware met een van de verschillende methoden.</span><span class="sxs-lookup"><span data-stu-id="46fe0-169">You can report phishing message that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="46fe0-170">Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="46fe0-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="46fe0-171">Zie ook</span><span class="sxs-lookup"><span data-stu-id="46fe0-171">See also</span></span>

- [<span data-ttu-id="46fe0-172">Ransomware</span><span class="sxs-lookup"><span data-stu-id="46fe0-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="46fe0-173">Antwoord op Ransomware – om te betalen of niet te betalen?</span><span class="sxs-lookup"><span data-stu-id="46fe0-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="46fe0-174">Noorse hydro reageert op Ransomware-aanval met transparantie</span><span class="sxs-lookup"><span data-stu-id="46fe0-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="46fe0-175">Ransomware-detectie en het herstellen van uw bestanden in OneDrive</span><span class="sxs-lookup"><span data-stu-id="46fe0-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="46fe0-176">Microsoft Security Intelligence-rapport</span><span class="sxs-lookup"><span data-stu-id="46fe0-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="46fe0-177">Macro's in Office-bestanden in-of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="46fe0-177">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="46fe0-178">Aanbevolen instellingen voor EOP en Microsoft Defender voor Office 365-beveiliging</span><span class="sxs-lookup"><span data-stu-id="46fe0-178">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="46fe0-179">Een waardevolle-upgrade: beveiliging van volgende generatie voor Windows 10 bewijst krachtig tegen Ransomware-uitbraken in 2017</span><span class="sxs-lookup"><span data-stu-id="46fe0-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="46fe0-180">Geen mas, Samas: wat doet zich in de modus operandi van dit Ransomware?</span><span class="sxs-lookup"><span data-stu-id="46fe0-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="46fe0-181">Vergrendelings malware, Lucky om dit te voorkomen</span><span class="sxs-lookup"><span data-stu-id="46fe0-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="46fe0-182">MSRT juli 2016: Cerber Ransomware</span><span class="sxs-lookup"><span data-stu-id="46fe0-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="46fe0-183">De drie koppen van de Cerberus-like Cerber Ransomware</span><span class="sxs-lookup"><span data-stu-id="46fe0-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="46fe0-184">Troldeshe Ransomware beïnvloed door (de) da Vinci</span><span class="sxs-lookup"><span data-stu-id="46fe0-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
