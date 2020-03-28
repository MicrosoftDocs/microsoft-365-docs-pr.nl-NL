---
title: Herstellen van een ransomware aanval
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Office 365-beheerders kunnen leren hoe ze kunnen herstellen van een ransomware-aanval.
ms.openlocfilehash: 6d57142bac6dad22d38cc26a9353b528a9f8eb10
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032874"
---
# <a name="recover-from-a-ransomware-attack-in-office-365"></a><span data-ttu-id="6e2a6-103">Herstellen van een ransomware-aanval in Office 365</span><span class="sxs-lookup"><span data-stu-id="6e2a6-103">Recover from a ransomware attack in Office 365</span></span>

<span data-ttu-id="6e2a6-104">Zelfs als u alle voorzorgsmaatregelen neemt om uw Office 365-organisatie te beschermen, u nog steeds het slachtoffer worden van een [ransomware-aanval.](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)</span><span class="sxs-lookup"><span data-stu-id="6e2a6-104">Even if you take every precaution to protect your Office 365 organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="6e2a6-105">Ransomware is big business, en de aanvallen zijn te verifiëren geavanceerde.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="6e2a6-106">De stappen in dit onderwerp geeft u de beste kans om gegevens die werd versleuteld door de ransomware te herstellen, en zal helpen stoppen met de verspreiding van de infectie in uw Office 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your Office 365 organization.</span></span> <span data-ttu-id="6e2a6-107">Voordat u aan de slag gaat, moet u de volgende items overwegen:</span><span class="sxs-lookup"><span data-stu-id="6e2a6-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="6e2a6-108">Er is geen garantie dat het betalen van het losgeld toegang tot uw bestanden zal terugkeren.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="6e2a6-109">In feite, het betalen van het losgeld kan je een doelwit voor meer ransomware.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="6e2a6-110">Als u al hebt betaald, maar u uw bestanden met succes hebt kunnen herstellen zonder dat u de resolutie van de aanvaller hoeft te gebruiken, moet u uw bank bellen om te zien of ze de transactie kunnen blokkeren.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="6e2a6-111">We raden u ook aan de ransomware-aanval te melden aan de rechtshandhaving, scam rapportage websites en Microsoft zoals later beschreven in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="6e2a6-112">Het is heel belangrijk dat je snel reageert op de aanval en de gevolgen ervan.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="6e2a6-113">Hoe langer u wacht, hoe kleiner de kans dat u de getroffen gegevens herstellen.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="6e2a6-114">Stap 1: Uw back-ups verifiëren</span><span class="sxs-lookup"><span data-stu-id="6e2a6-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="6e2a6-115">Als u offline back-ups hebt, u waarschijnlijk de versleutelde gegevens herstellen **nadat** u de ransomware payload (malware) uit uw omgeving hebt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="6e2a6-116">Als u geen back-ups hebt, of als uw back-ups ook werden beïnvloed door de ransomware, u deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="6e2a6-117">Stap 2: ActiveSync en OneDrive-synchronisatie uitschakelen</span><span class="sxs-lookup"><span data-stu-id="6e2a6-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="6e2a6-118">Het belangrijkste punt hier is om de verspreiding van data-encryptie te stoppen door de ransomware.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="6e2a6-119">Als u vermoedt dat e-mail een doelwit is, moet u de toegang van gebruikers tot postvakken tijdelijk uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="6e2a6-120">Exchange ActiveSync wordt door mobiele apparaten gebruikt om gegevens te synchroniseren tussen het apparaat en het Exchange Online-postvak.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="6e2a6-121">Zie [ActiveSync uitschakelen voor gebruikers in Office 365](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365)als u ActiveSync voor een postvak wilt uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Office 365](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).</span></span>

<span data-ttu-id="6e2a6-122">Zie als:</span><span class="sxs-lookup"><span data-stu-id="6e2a6-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="6e2a6-123">[MAPI in- of uitschakelen voor een postvak](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span><span class="sxs-lookup"><span data-stu-id="6e2a6-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="6e2a6-124">POP3- of IMAP4-toegang voor een gebruiker in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="6e2a6-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="6e2a6-125">Als u OneDrive-synchronisatie pauzeert, u voorkomen dat uw cloudgegevens worden bijgewerkt door mogelijk geïnfecteerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="6e2a6-126">Zie [Synchronisatie onderbreken en hervatten in OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="6e2a6-127">Stap 3: Verwijder de malware van de getroffen apparaten</span><span class="sxs-lookup"><span data-stu-id="6e2a6-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="6e2a6-128">Voer een volledige antivirusscan uit met de nieuwste updates op alle verdachte computers en apparaten om de payload te detecteren en te verwijderen die is gekoppeld aan de ransomware.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="6e2a6-129">Vergeet niet apparaten die gegevens synchroniseren, of het doel van toegewezen netwerkstations (die computers en apparaten moeten ook worden gescand).</span><span class="sxs-lookup"><span data-stu-id="6e2a6-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="6e2a6-130">U [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) of (voor oudere clients) Microsoft Security [Essentials](https://www.microsoft.com/download/details.aspx?id=5201)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="6e2a6-131">Een alternatief dat u ook zal helpen ransomware of malware te verwijderen is de [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span><span class="sxs-lookup"><span data-stu-id="6e2a6-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="6e2a6-132">Als deze opties niet werken, u [Windows Defender Offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) proberen of problemen met het detecteren en verwijderen van malware [oplossen.](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware)</span><span class="sxs-lookup"><span data-stu-id="6e2a6-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="6e2a6-133">Stap 4: Bestanden herstellen op een opgeschoonde computer of apparaat</span><span class="sxs-lookup"><span data-stu-id="6e2a6-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="6e2a6-134">Nadat u de vorige stap hebt voltooid om de ransomware-payload uit uw omgeving te verwijderen (waardoor de ransomware uw bestanden niet kan versleutelen of verwijderen), u [bestandsgeschiedenis](https://support.microsoft.com/help/17128/windows-8-file-history) gebruiken in Windows 10 en Windows 8.1 of Systeembeveiliging in Windows 7 om te proberen uw lokale bestanden en mappen te herstellen.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128/windows-8-file-history) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="6e2a6-135">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="6e2a6-135">**Notes**:</span></span>

- <span data-ttu-id="6e2a6-136">Sommige ransomware zal ook versleutelen of verwijderen van de back-up versies, dus je niet gebruiken Bestandsgeschiedenis of systeembeveiliging om bestanden te herstellen.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="6e2a6-137">Als dat gebeurt, moet u back-ups gebruiken op externe schijven of apparaten die niet zijn beïnvloed door de ransomware of OneDrive, zoals beschreven in de volgende sectie.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="6e2a6-138">Als een map is gesynchroniseerd met OneDrive en u de nieuwste versie van Windows niet gebruikt, zijn er mogelijk enkele beperkingen met bestandsgeschiedenis.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="6e2a6-139">Stap 5: Uw bestanden herstellen in uw OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="6e2a6-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="6e2a6-140">Met Bestanden herstellen in OneDrive voor Bedrijven u uw volledige OneDrive in de afgelopen 30 dagen naar een eerder tijdstip herstellen.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="6e2a6-141">Zie [Uw OneDrive herstellen](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-141">For more information, see [Restore your OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="6e2a6-142">Stap 6: Verwijderde e-mail herstellen</span><span class="sxs-lookup"><span data-stu-id="6e2a6-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="6e2a6-143">In het zeldzame geval dat de ransomware al uw e-mail verwijderd, u waarschijnlijk herstellen van de verwijderde items.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="6e2a6-144">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="6e2a6-144">For more information, see:</span></span>

- [<span data-ttu-id="6e2a6-145">Verwijderde berichten herstellen in het postvak van een gebruiker</span><span class="sxs-lookup"><span data-stu-id="6e2a6-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="6e2a6-146">Verwijderde items herstellen in Outlook voor Windows</span><span class="sxs-lookup"><span data-stu-id="6e2a6-146">Recover deleted items in Outlook for Windows</span></span>](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="6e2a6-147">Stap 7: Exchange ActiveSync en OneDrive-synchronisatie opnieuw inschakelen</span><span class="sxs-lookup"><span data-stu-id="6e2a6-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="6e2a6-148">Nadat u uw computers en apparaten hebt opgemaakt en uw gegevens hebt hersteld, u activesync en OneDrive-synchronisatie die u eerder hebt uitgeschakeld in [stap 2](#step-2-disable-activesync-and-onedrive-sync)opnieuw inschakelen.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-148">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="6e2a6-149">Stap 8 (optioneel): OneDrive-synchronisatie blokkeren voor specifieke bestandsextensies</span><span class="sxs-lookup"><span data-stu-id="6e2a6-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="6e2a6-150">Nadat u bent hersteld, u voorkomen dat Klanten van OneDrive voor Bedrijven de bestandstypen synchroniseren die door deze ransomware zijn getroffen.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="6e2a6-151">Zie [Set-SPOTenantSyncClientRestriction voor](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction) meer informatie</span><span class="sxs-lookup"><span data-stu-id="6e2a6-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="6e2a6-152">De aanval melden</span><span class="sxs-lookup"><span data-stu-id="6e2a6-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="6e2a6-153">Neem contact op met de politie</span><span class="sxs-lookup"><span data-stu-id="6e2a6-153">Contact law enforcement</span></span>

<span data-ttu-id="6e2a6-154">Neem contact op met uw lokale of federale wetshandhavingsinstanties.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="6e2a6-155">Als u zich bijvoorbeeld in de Verenigde Staten bevindt, u contact opnemen met het [lokale fieldoffice](https://www.fbi.gov/contact-us/field)van de FBI, [IC3](http://www.ic3.gov/complaint/default.aspx) of [de geheime dienst.](http://www.secretservice.gov/)</span><span class="sxs-lookup"><span data-stu-id="6e2a6-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="6e2a6-156">Een rapport indienen bij de website van uw land voor het melden van oplichting</span><span class="sxs-lookup"><span data-stu-id="6e2a6-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="6e2a6-157">Scam rapportage websites bieden informatie over hoe te voorkomen en te voorkomen oplichting.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="6e2a6-158">Ze bieden ook mechanismen om te melden als je slachtoffer was van oplichting.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="6e2a6-159">Australië: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="6e2a6-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="6e2a6-160">Canada: [Canadees Centrum voor fraudebestrijding](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="6e2a6-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="6e2a6-161">Frankrijk: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="6e2a6-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="6e2a6-162">Duitsland: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="6e2a6-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="6e2a6-163">Ierland: [An Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="6e2a6-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="6e2a6-164">Nieuw-Zeeland: [Consumentenzaken Oplichting](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="6e2a6-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="6e2a6-165">Verenigd Koninkrijk: [Actiefraude](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="6e2a6-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="6e2a6-166">Verenigde Staten: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="6e2a6-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="6e2a6-167">Als uw land niet op de lijst staat, vraag het dan aan uw lokale of federale wetshandhavingsinstanties.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="6e2a6-168">E-mailberichten verzenden naar Microsoft</span><span class="sxs-lookup"><span data-stu-id="6e2a6-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="6e2a6-169">U phishing-berichten die ransomware bevatten met behulp van een van de verschillende methoden.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-169">You can report phishing message that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="6e2a6-170">Zie [Berichten en bestanden rapporteren aan Microsoft voor](report-junk-email-messages-to-microsoft.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6e2a6-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6e2a6-171">Zie ook</span><span class="sxs-lookup"><span data-stu-id="6e2a6-171">See also</span></span>

- [<span data-ttu-id="6e2a6-172">Ransomware Ransomware</span><span class="sxs-lookup"><span data-stu-id="6e2a6-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="6e2a6-173">Ransomware reactie-te betalen of niet te betalen?</span><span class="sxs-lookup"><span data-stu-id="6e2a6-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="6e2a6-174">Norsk Hydro reageert op ransomware aanval met transparantie</span><span class="sxs-lookup"><span data-stu-id="6e2a6-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="6e2a6-175">Ransomware detectie en het herstellen van uw bestanden in OneDrive</span><span class="sxs-lookup"><span data-stu-id="6e2a6-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="6e2a6-176">Microsoft Security Intelligence-rapport</span><span class="sxs-lookup"><span data-stu-id="6e2a6-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="6e2a6-177">Macro's in Office-bestanden in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="6e2a6-177">Enable or disable macros in Office files</span></span>](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="6e2a6-178">Aanbevolen instellingen voor EOP- en Office 365 ATP-beveiliging</span><span class="sxs-lookup"><span data-stu-id="6e2a6-178">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="6e2a6-179">Een waardige upgrade: Next-gen beveiliging op Windows 10 blijkt veerkrachtig tegen ransomware uitbraken in 2017</span><span class="sxs-lookup"><span data-stu-id="6e2a6-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="6e2a6-180">Geen mas, Samas: Wat zit er in de modus operandi van deze ransomware?</span><span class="sxs-lookup"><span data-stu-id="6e2a6-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="6e2a6-181">Locky malware, geluk om het te vermijden</span><span class="sxs-lookup"><span data-stu-id="6e2a6-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="6e2a6-182">MSRT juli 2016: Cerber ransomware</span><span class="sxs-lookup"><span data-stu-id="6e2a6-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="6e2a6-183">De drie hoofden van de Cerberus-achtige Cerber ransomware</span><span class="sxs-lookup"><span data-stu-id="6e2a6-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="6e2a6-184">Troldesh ransomware beïnvloed door (de) Da Vinci code</span><span class="sxs-lookup"><span data-stu-id="6e2a6-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
