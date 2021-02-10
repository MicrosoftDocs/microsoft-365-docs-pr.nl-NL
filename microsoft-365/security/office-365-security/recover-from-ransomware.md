---
title: Herstel na een ransomware-aanval
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.article: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365-beheerders kunnen meer informatie krijgen over het herstellen van een ransomware-aanval.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b834adb3d9ba5f85984e09b4bb1e4b48673c32f2
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166901"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="6a01c-103">Herstel van een ransomware-aanval in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6a01c-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6a01c-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="6a01c-104">**Applies to**</span></span>
- [<span data-ttu-id="6a01c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6a01c-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="6a01c-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="6a01c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="6a01c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a01c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="6a01c-108">Zelfs als u alle voorzorgsmaatregelen treffen om uw organisatie te beschermen, kunt u nog steeds het slachtoffer worden van een [aanval van ransomware.](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)</span><span class="sxs-lookup"><span data-stu-id="6a01c-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="6a01c-109">Ransomware is een grote onderneming en de aanvallen zijn zeer geavanceerd.</span><span class="sxs-lookup"><span data-stu-id="6a01c-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="6a01c-110">Met de stappen in dit artikel krijgt u de beste kans om gegevens te herstellen en de interne verspreiding van de instopstop te stoppen.</span><span class="sxs-lookup"><span data-stu-id="6a01c-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="6a01c-111">Kijk eens naar de volgende items voordat u aan de slag gaat:</span><span class="sxs-lookup"><span data-stu-id="6a01c-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="6a01c-112">Er is geen garantie dat het betalen van de garantie weer toegang krijgt tot uw bestanden.</span><span class="sxs-lookup"><span data-stu-id="6a01c-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="6a01c-113">In feite kan het betalen van de kosten ervoor zorgen dat u een doel wordt voor meer ransomware.</span><span class="sxs-lookup"><span data-stu-id="6a01c-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="6a01c-114">Als u al hebt betaald, maar u dit hebt hersteld zonder de oplossing van de aanvaller te gebruiken, moet u contact opnemen met uw bank om te kijken of deze de transactie kan blokkeren.</span><span class="sxs-lookup"><span data-stu-id="6a01c-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="6a01c-115">U wordt ook aangeraden de ransomware-aanval te melden aan de advocatenkantoor, websites voor het melden van oplichtingspraktijken en Microsoft, zoals verderhand in dit artikel wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="6a01c-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="6a01c-116">Het is belangrijk dat u snel reageert op de aanval en de gevolgen ervan.</span><span class="sxs-lookup"><span data-stu-id="6a01c-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="6a01c-117">Hoe langer u wacht, hoe minder waarschijnlijk het is dat u de betrokken gegevens kunt herstellen.</span><span class="sxs-lookup"><span data-stu-id="6a01c-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="6a01c-118">Stap 1: Uw back-ups controleren</span><span class="sxs-lookup"><span data-stu-id="6a01c-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="6a01c-119">Als u offlineback-ups hebt, kunt u  de versleutelde gegevens waarschijnlijk herstellen nadat u de ransomware(malware) uit uw omgeving hebt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="6a01c-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="6a01c-120">Als u geen back-ups hebt of als uw back-ups ook door ransomware zijn beïnvloed, kunt u deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="6a01c-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="6a01c-121">Stap 2: Exchange ActiveSync en OneDrive-synchronisatie uitschakelen</span><span class="sxs-lookup"><span data-stu-id="6a01c-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="6a01c-122">Het belangrijkste punt hier is om de verspreiding van gegevensversleuteling door de ransomware te stoppen.</span><span class="sxs-lookup"><span data-stu-id="6a01c-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="6a01c-123">Als u vermoedt dat e-mail een doel is van de ransomware-versleuteling, schakelt u de gebruikerstoegang tot postvakken tijdelijk uit.</span><span class="sxs-lookup"><span data-stu-id="6a01c-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="6a01c-124">Exchange ActiveSync synchroniseert gegevens tussen apparaten en Postvakken van Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6a01c-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="6a01c-125">Zie Exchange ActiveSync uitschakelen voor gebruikers in Exchange Online als u Exchange ActiveSync wilt uitschakelen [voor een postvak.](https://support.microsoft.com/help/2795303)</span><span class="sxs-lookup"><span data-stu-id="6a01c-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="6a01c-126">Als u andere soorten toegang tot een postvak wilt uitschakelen, gaat u naar:</span><span class="sxs-lookup"><span data-stu-id="6a01c-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="6a01c-127">[MAPI voor een postvak in- of uitschakelen.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)</span><span class="sxs-lookup"><span data-stu-id="6a01c-127">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="6a01c-128">POP3- of IMAP4-toegang voor een gebruiker in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="6a01c-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="6a01c-129">Door OneDrive-synchronisatie te onderbreken, beschermt u uw cloudgegevens tegen updates door mogelijk geïnfecteerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="6a01c-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="6a01c-130">Zie Synchronisatie onderbreken en hervatten [in OneDrive voor meer informatie.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)</span><span class="sxs-lookup"><span data-stu-id="6a01c-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="6a01c-131">Stap 3: Verwijder de malware van de betreffende apparaten</span><span class="sxs-lookup"><span data-stu-id="6a01c-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="6a01c-132">Voer een volledige, actuele antivirusscan uit op alle verdachte computers en apparaten om de nettolading te detecteren en te verwijderen die is gekoppeld aan de ransomware.</span><span class="sxs-lookup"><span data-stu-id="6a01c-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="6a01c-133">Vergeet niet apparaten te scannen die gegevens synchroniseren, of de doelen van de netwerkstations.</span><span class="sxs-lookup"><span data-stu-id="6a01c-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="6a01c-134">U kunt [Windows Defender of](https://www.microsoft.com/windows/comprehensive-security) (voor oudere clients) Microsoft Security [Essentials gebruiken.](https://www.microsoft.com/download/details.aspx?id=5201)</span><span class="sxs-lookup"><span data-stu-id="6a01c-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="6a01c-135">Een alternatief voor het verwijderen van ransomware of malware is het [Malicious Software Removal Tool (MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)</span><span class="sxs-lookup"><span data-stu-id="6a01c-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="6a01c-136">Als deze opties niet werken, kunt u [Windows Defender Offline](https://support.microsoft.com/help/17466) proberen of problemen oplossen met het detecteren en verwijderen van [malware.](https://support.microsoft.com/help/4466982)</span><span class="sxs-lookup"><span data-stu-id="6a01c-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="6a01c-137">Stap 4: Bestanden herstellen op een opgeschoonde computer of apparaat</span><span class="sxs-lookup"><span data-stu-id="6a01c-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="6a01c-138">Nadat u de vorige stap hebt voltooid om de nettolading van ransomware uit uw omgeving te verwijderen (waardoor ransomware uw bestanden niet kan versleutelen of verwijderen), kunt u Bestandsgeschiedenis [in](https://support.microsoft.com/help/17128) Windows 10 en Windows 8.1 of Systeembeveiliging in Windows 7 gebruiken om te proberen uw lokale bestanden en mappen te herstellen.</span><span class="sxs-lookup"><span data-stu-id="6a01c-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="6a01c-139">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="6a01c-139">**Notes**:</span></span>

- <span data-ttu-id="6a01c-140">Sommige ransomware versleutelen of verwijderen ook de back-upversies, zodat u de bestandsgeschiedenis of systeembeveiliging niet kunt gebruiken om bestanden te herstellen.</span><span class="sxs-lookup"><span data-stu-id="6a01c-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="6a01c-141">Als dat gebeurt, moet u back-ups gebruiken op externe stations of apparaten die niet zijn beïnvloed door ransomware of OneDrive, zoals wordt beschreven in de volgende sectie.</span><span class="sxs-lookup"><span data-stu-id="6a01c-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="6a01c-142">Als een map wordt gesynchroniseerd met OneDrive en u niet de nieuwste versie van Windows gebruikt, zijn er mogelijk enkele beperkingen bij het gebruik van Bestandsgeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="6a01c-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="6a01c-143">Stap 5: Uw bestanden herstellen in uw OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="6a01c-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="6a01c-144">Met Bestanden herstellen in OneDrive voor Bedrijven kunt u uw gehele OneDrive herstellen naar het vorige tijdstip in de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="6a01c-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="6a01c-145">Zie Uw [OneDrive herstellen voor meer informatie.](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)</span><span class="sxs-lookup"><span data-stu-id="6a01c-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="6a01c-146">Stap 6: Verwijderde e-mail herstellen</span><span class="sxs-lookup"><span data-stu-id="6a01c-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="6a01c-147">In het zeldzame geval dat de ransomware al uw e-mailberichten heeft verwijderd, kunt u de verwijderde items waarschijnlijk herstellen.</span><span class="sxs-lookup"><span data-stu-id="6a01c-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="6a01c-148">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="6a01c-148">For more information, see:</span></span>

- [<span data-ttu-id="6a01c-149">Verwijderde berichten herstellen in het postvak van een gebruiker</span><span class="sxs-lookup"><span data-stu-id="6a01c-149">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="6a01c-150">Verwijderde items herstellen in Outlook voor Windows</span><span class="sxs-lookup"><span data-stu-id="6a01c-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="6a01c-151">Stap 7: Exchange ActiveSync en OneDrive-synchronisatie opnieuw inschakelen</span><span class="sxs-lookup"><span data-stu-id="6a01c-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="6a01c-152">Nadat u uw computers en apparaten hebt opgeschoond en de gegevens hebt hersteld, kunt u Exchange ActiveSync- en OneDrive-synchronisatie die u eerder in stap 2 hebt uitgeschakeld, [opnieuw inschakelen.](#step-2-disable-exchange-activesync-and-onedrive-sync)</span><span class="sxs-lookup"><span data-stu-id="6a01c-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="6a01c-153">Stap 8 (optioneel): OneDrive-synchronisatie blokkeren voor specifieke bestandsextensies</span><span class="sxs-lookup"><span data-stu-id="6a01c-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="6a01c-154">Nadat u het bestand hebt hersteld, kunt u voorkomen dat OneDrive voor Bedrijven-clients de bestandstypen synchroniseren die door deze ransomware zijn beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="6a01c-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="6a01c-155">Zie [Set-SPOTenantSyncClientRestriction voor meer informatie](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="6a01c-155">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="6a01c-156">De aanval melden</span><span class="sxs-lookup"><span data-stu-id="6a01c-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="6a01c-157">Contact opnemen met de wet</span><span class="sxs-lookup"><span data-stu-id="6a01c-157">Contact law enforcement</span></span>

<span data-ttu-id="6a01c-158">Neem contact op met de plaatselijke of federale advocatenkantoorsinstanties.</span><span class="sxs-lookup"><span data-stu-id="6a01c-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="6a01c-159">Als u zich bijvoorbeeld in de Verenigde Staten hebt, kunt u contact opnemen met het lokale field [office VAN DE(s)](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) of de geheime [service.](http://www.secretservice.gov/)</span><span class="sxs-lookup"><span data-stu-id="6a01c-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="6a01c-160">Een rapport verzenden naar de rapportagewebsite van uw land</span><span class="sxs-lookup"><span data-stu-id="6a01c-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="6a01c-161">Websites voor oplichtingsrapportage bevatten informatie over hoe u oplichtingspraktijken kunt voorkomen en vermijden.</span><span class="sxs-lookup"><span data-stu-id="6a01c-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="6a01c-162">Ze bieden ook mechanismen om te melden als u het slachtoffer bent geworden van oplichtingspraktijken.</span><span class="sxs-lookup"><span data-stu-id="6a01c-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="6a01c-163">Australië: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="6a01c-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="6a01c-164">Canada: [Canadees antifraudecentrum](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="6a01c-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="6a01c-165">Frankrijk: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="6a01c-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="6a01c-166">Duitsland: [Vonamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="6a01c-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="6a01c-167">Ierland: [Een Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="6a01c-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="6a01c-168">Nieuw-Zeeland: [Oplichtingspraktijken in consumentenzaken](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="6a01c-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="6a01c-169">Verenigd Koninkrijk: [Actiefraude](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="6a01c-169">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="6a01c-170">Verenigde Staten: [In Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="6a01c-170">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="6a01c-171">Als uw land niet in de lijst staat, vraagt u dit aan uw lokale of federale advocatenkantoorsinstanties.</span><span class="sxs-lookup"><span data-stu-id="6a01c-171">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="6a01c-172">E-mailberichten verzenden bij Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a01c-172">Submit email messages to Microsoft</span></span>

<span data-ttu-id="6a01c-173">U kunt phishing-berichten die ransomware bevatten op een van de verschillende manieren melden.</span><span class="sxs-lookup"><span data-stu-id="6a01c-173">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="6a01c-174">Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="6a01c-174">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6a01c-175">Zie ook</span><span class="sxs-lookup"><span data-stu-id="6a01c-175">See also</span></span>

- [<span data-ttu-id="6a01c-176">Ransomware</span><span class="sxs-lookup"><span data-stu-id="6a01c-176">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="6a01c-177">Antwoord op ransomware: al dan niet te betalen?</span><span class="sxs-lookup"><span data-stu-id="6a01c-177">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="6a01c-178">Norsk Er is een reactie op de aanval van ransomware met transparantie</span><span class="sxs-lookup"><span data-stu-id="6a01c-178">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="6a01c-179">Ransomware-detectie en het herstellen van uw bestanden in OneDrive</span><span class="sxs-lookup"><span data-stu-id="6a01c-179">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="6a01c-180">Microsoft Security Intelligence-rapport</span><span class="sxs-lookup"><span data-stu-id="6a01c-180">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="6a01c-181">Macro's in Office-bestanden in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="6a01c-181">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="6a01c-182">Aanbevolen instellingen voor EOP- en Microsoft Defender voor Office 365-beveiliging</span><span class="sxs-lookup"><span data-stu-id="6a01c-182">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

- [<span data-ttu-id="6a01c-183">Een goede upgrade: De beveiliging van de volgende generatie in Windows 10 is bestand tegen ransomware-virussen in 2017</span><span class="sxs-lookup"><span data-stu-id="6a01c-183">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="6a01c-184">No mas, Samas: What's in this ransomware's modus operandi?</span><span class="sxs-lookup"><span data-stu-id="6a01c-184">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="6a01c-185">Locky malware, geluk om dit te vermijden</span><span class="sxs-lookup"><span data-stu-id="6a01c-185">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="6a01c-186">MSRT juli 2016: Cerber ransomware</span><span class="sxs-lookup"><span data-stu-id="6a01c-186">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="6a01c-187">De drie koppen van de Cerberus-like Cerber ransomware</span><span class="sxs-lookup"><span data-stu-id="6a01c-187">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="6a01c-188">Troldesh-ransomware die zijn beïnvloed door (de) Da Wordt-code</span><span class="sxs-lookup"><span data-stu-id="6a01c-188">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
