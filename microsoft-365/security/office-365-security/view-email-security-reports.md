---
title: Bekijk e-mailbeveiligingsrapporten in het Security & Compliance Center, Gecompromitteerde gebruikers, Encryptie, Dreigingsbeschermingsstatus, malwaredetectie, Topmalware, spamdetectie, verzonden en ontvangen e-mail, gerapporteerde berichten van de gebruiker, leesrapporten, detectie, beveiligingsgegevens, beveiligingsinformatie
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/16/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Meer informatie over het vinden en gebruiken van e-mailbeveiligingsrapporten voor uw organisatie. E-mailbeveiligingsrapporten zijn beschikbaar in het Security & Compliance Center.
ms.openlocfilehash: d99186e4f3a2831eb794d31a33fa4d56af2cc7a4
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529071"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="4388f-104">E-mailbeveiligingsrapporten bekijken in het Beveiligings- en compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="4388f-104">View email security reports in the Security & Compliance Center</span></span>

<span data-ttu-id="4388f-105">Er zijn verschillende rapporten beschikbaar in het [Security & Compliance Center](https://protection.office.com) om u te helpen zien hoe e-mailbeveiligingsfuncties, zoals antispam, anti-malware en versleutelingsfuncties in Office 365 uw organisatie beschermen.</span><span class="sxs-lookup"><span data-stu-id="4388f-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Office 365 are protecting your organization.</span></span> <span data-ttu-id="4388f-106">Als u over de [benodigde machtigingen](#what-permissions-are-needed-to-view-these-reports)beschikt, u deze rapporten bekijken in het Security & Compliance Center door naar **het dashboard rapporten** \> **Dashboard**te gaan.</span><span class="sxs-lookup"><span data-stu-id="4388f-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span>

![Rapporten dashboard in het Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

<span data-ttu-id="4388f-108">Uw e-mailbeveiligingsrapporten bevatten het volgende:</span><span class="sxs-lookup"><span data-stu-id="4388f-108">Your email security reports include the following:</span></span>

- <span data-ttu-id="4388f-109">[URL Threat Protection report](#url-threat-protection-report-new) **(NIEUW!**)</span><span class="sxs-lookup"><span data-stu-id="4388f-109">[URL Threat Protection report](#url-threat-protection-report-new) (**NEW!**)</span></span>
- [<span data-ttu-id="4388f-110">Rapport Gecompromitteerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="4388f-110">Compromised Users report</span></span>](#compromised-users-report)
- [<span data-ttu-id="4388f-111">Versleutelingsrapport</span><span class="sxs-lookup"><span data-stu-id="4388f-111">Encryption report</span></span>](#encryption-report)
- [<span data-ttu-id="4388f-112">Statusrapport risicobeveiliging</span><span class="sxs-lookup"><span data-stu-id="4388f-112">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="4388f-113">Malware detecties rapport</span><span class="sxs-lookup"><span data-stu-id="4388f-113">Malware Detections report</span></span>](#malware-detections-report)
- [<span data-ttu-id="4388f-114">Rapport Top malware</span><span class="sxs-lookup"><span data-stu-id="4388f-114">Top Malware report</span></span>](#top-malware-report)
- [<span data-ttu-id="4388f-115">Rapport Topafzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="4388f-115">Top Senders and Recipients report</span></span>](#top-senders-and-recipients-report)
- [<span data-ttu-id="4388f-116">Rapport spoofdetecties</span><span class="sxs-lookup"><span data-stu-id="4388f-116">Spoof Detections report</span></span>](#spoof-detections-report)
- [<span data-ttu-id="4388f-117">Spam detecties rapport</span><span class="sxs-lookup"><span data-stu-id="4388f-117">Spam Detections report</span></span>](#spam-detections-report)
- [<span data-ttu-id="4388f-118">Verzonden en ontvangen e-mailrapport</span><span class="sxs-lookup"><span data-stu-id="4388f-118">Sent and received email report</span></span>](#sent-and-received-email-report)
- [<span data-ttu-id="4388f-119">Rapport met door de gebruiker gerapporteerde berichten</span><span class="sxs-lookup"><span data-stu-id="4388f-119">User-reported messages report</span></span>](#user-reported-messages-report)

## <a name="url-threat-protection-report-new"></a><span data-ttu-id="4388f-120">URL Threat Protection report **(NIEUW!**)</span><span class="sxs-lookup"><span data-stu-id="4388f-120">URL Threat Protection report (**NEW!**)</span></span>

<span data-ttu-id="4388f-121">Het URL Threat Protection-rapport is beschikbaar voor iedereen met:</span><span class="sxs-lookup"><span data-stu-id="4388f-121">The URL Threat Protection report is available to anyone with:</span></span>

- <span data-ttu-id="4388f-122">Een invoegtoepassing Exchange Online Protection *en* geavanceerde bedreigingsbeveiliging (abonnement 1 *of* plan 2)</span><span class="sxs-lookup"><span data-stu-id="4388f-122">An Exchange Online Protection, *and* Advanced Threat Protection add-on (Plan 1 *or* Plan 2)</span></span>
- <span data-ttu-id="4388f-123">Een Microsoft 365 E5-abonnement</span><span class="sxs-lookup"><span data-stu-id="4388f-123">A Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="4388f-124">Dit is een 'click-centric' rapport dat twee geaggregeerde weergaven heeft.</span><span class="sxs-lookup"><span data-stu-id="4388f-124">This is a 'click-centric' report that has two aggregated views.</span></span>

1. <span data-ttu-id="4388f-125">De eerste weergave is door *URL klik-bescherming actie*, die is gericht op het weergeven van het aantal URL-klikken door gebruikers binnen de tenant, en het resultaat van de klik.</span><span class="sxs-lookup"><span data-stu-id="4388f-125">The first view is by *URL click-protection action*, which is focused on showing the number of URL clicks by users within the tenant, and the result of the click.</span></span> <span data-ttu-id="4388f-126">Een klik hier geeft aan dat de gebruiker heeft geklikt via de blokpagina naar de kwaadaardige website (dit kan worden uitgeschakeld door de beheerder binnen een Safe Links beleid).</span><span class="sxs-lookup"><span data-stu-id="4388f-126">A click here indicates that the user has clicked through the block page to the malicious website (this can be disabled by the administrator within a Safe Links policy).</span></span>

2. <span data-ttu-id="4388f-127">De tweede weergave is *URL-klik per toepassing,* waarbij het aantal URL's wordt weergegeven dat u vandaag in verschillende toepassingen klikt die veilige koppelingen ondersteunen, zoals in een e-mailclient of in Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="4388f-127">The second view is *URL click by applications*, which shows the number of URLs click in different applications that support Safe Links today, such as in an email client or in Microsoft Word.</span></span> <span data-ttu-id="4388f-128">Gegevens in beide geaggregeerde weergaven worden eens in de 4 uur vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="4388f-128">Data in both aggregated views are refreshed once every 4 hours.</span></span>

<span data-ttu-id="4388f-129">De detailstabel van het URL Threat Protection-rapport biedt een bijna realtime weergave van alle klikken die binnen de tenant plaatsvinden, en bevat onderzoeksinformatie zoals *gebruikersnaam,* *URL,* de *netwerkbericht-id* (als de URL is aangeklikt vanuit een e-mail) en andere waardevolle informatie die nuttig is voor onderzoeken en analyses.</span><span class="sxs-lookup"><span data-stu-id="4388f-129">The details table of the URL Threat Protection report provides a near-real-time view of all clicks that happen within the tenant, and it includes investigative information such as *username*, *URL*, the *network message ID* (if the URL was clicked from an email), and other valuable pieces of information useful for investigations and analyses.</span></span>

<span data-ttu-id="4388f-130">Standaard worden in het rapport alleen gegevens weergegeven over klikken van URL's die zijn geblokkeerd door Veilige koppelingen, maar het is ook mogelijk om informatie voor alle URL-klikken te bekijken door het selectievakje *Toegestane URL's* in de filters te selecteren.</span><span class="sxs-lookup"><span data-stu-id="4388f-130">By default, the report only shows data on clicks from URLs that were blocked by Safe Links, but it is also possible to see information for all URL clicks through selecting *Allowed URLs* checkbox in the filters.</span></span>

<span data-ttu-id="4388f-131">In dit rapport worden geen gegevens van klikken van gebruikers waarop het toegepaste beleid Voor veilige koppelingen is toegepast, is de optie *Klikken van gebruikers niet bijgehouden.*</span><span class="sxs-lookup"><span data-stu-id="4388f-131">This report will not have data of clicks from users where the Safe Links policy applied has the *Do not track user clicks* option selected.</span></span>

![Afbeelding van het URL Threat Protection Report in actie.](../../media/tp-URLThreatProRpt1.PNG)

## <a name="compromised-users-report"></a><span data-ttu-id="4388f-133">Rapport Gecompromitteerde gebruikers</span><span class="sxs-lookup"><span data-stu-id="4388f-133">Compromised Users report</span></span>

<span data-ttu-id="4388f-134">In dit rapport, dat beschikbaar is voor iedereen met Exchange Online Protection, wordt het aantal gebruikersaccounts weergegeven dat is gemarkeerd als verdachte of beperkte gebruikers, gegevens die bijzonder nuttig zijn omdat accounts een van de statussen invoeren die aangeven dat het gebruikersaccount problematisch kan zijn of zelfs gecompromitteerd.</span><span class="sxs-lookup"><span data-stu-id="4388f-134">This report, available to anyone with Exchange Online Protection, shows the number of user accounts marked as Suspicious or Restricted users, data particularly useful as accounts enter either of the states that indicate the user account may be problematic, or even compromised.</span></span> <span data-ttu-id="4388f-135">Bij veelvuldig gebruik kan het rapport Gecompromitteerde gebruiker pieken en zelfs trends herkennen in accounts die zijn gemarkeerd in verdachte of beperkte toestanden, waardoor er een probleem kan zijn met de beveiliging en het welzijn van uw tenant.</span><span class="sxs-lookup"><span data-stu-id="4388f-135">With frequent use, the Compromised User report can spot spikes, and even trends, in accounts marked in suspicious or restricted states, giving evidence there could be an issue with security and the wellness of your tenant.</span></span>

![Het rapport van gecompromitteerde gebruikers zoals het wordt weergegeven in Office 365.](../../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

## <a name="encryption-report"></a><span data-ttu-id="4388f-137">Versleutelingsrapport</span><span class="sxs-lookup"><span data-stu-id="4388f-137">Encryption report</span></span>

<span data-ttu-id="4388f-138">In **het versleutelingsrapport** worden informatie weergegeven over e-mailberichten die zijn versleuteld, via het beleid van uw organisatie of via besturingselementen voor eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="4388f-138">The **Encryption report** shows information about email messages that were encrypted, either through your organization's policies, or through end-user controls.</span></span> <span data-ttu-id="4388f-139">Het beveiligingsteam van uw organisatie kan informatie in dit rapport gebruiken om patronen te identificeren en proactief beleid voor gevoelige e-mailberichten toe te passen of aan te passen.</span><span class="sxs-lookup"><span data-stu-id="4388f-139">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span>

<span data-ttu-id="4388f-140">Als u dit rapport wilt bekijken, gaat u in het & Compliance Center beveiliging naar **Dashboard** \> **het rapport Dashboardversleuteling** **rapporten** \> .</span><span class="sxs-lookup"><span data-stu-id="4388f-140">To view this report, in the Security & Compliance Center, go to **Reports** \> **Dashboard** \> **Encryption report**.</span></span>

![Versleutelingsrapport](../../media/encryptionreport-defaultview.png)

<span data-ttu-id="4388f-142">Wanneer het rapport voor het eerst wordt geopend, ziet u gegevens over versleutelingsmethoden die de afgelopen zeven (7) dagen in e-mailberichten zijn gebruikt.</span><span class="sxs-lookup"><span data-stu-id="4388f-142">When the report first opens, you'll see data about encryption methods used on email messages for the past seven (7) days.</span></span> <span data-ttu-id="4388f-143">U het datumbereik en de details die in het rapport worden weergegeven wijzigen door te klikken op **Filters** in de rechterbovenhoek van het scherm.</span><span class="sxs-lookup"><span data-stu-id="4388f-143">You can change the date range and the details that are displayed in the report by clicking **Filters** in the upper right corner of the screen.</span></span>

![Versleutelingsrapportfilters](../../media/encryptionreport-filters.png)

<span data-ttu-id="4388f-145">U het menu **Opsplitsen per** menu ook gebruiken om gegevens te bekijken op versleutelingssjabloon (of methode).</span><span class="sxs-lookup"><span data-stu-id="4388f-145">You can also use the **Break down by** menu to view data by encryption template (or method).</span></span>

![Versleutelingsmethode of sjabloon](../../media/encryptionreport-breakdownby.png)

<span data-ttu-id="4388f-147">En u het menu Gegevens per menu **weergeven** gebruiken om de weergave te wijzigen om het aantal versleutelde berichten te bekijken in de vijf belangrijkste adressendomeinen.</span><span class="sxs-lookup"><span data-stu-id="4388f-147">And, you can use the **View data by** menu to change the view to see counts of encrypted messages to the top five recipient domains.</span></span>

![Gegevens per menu voor versleutelingsrapportweerweergave](../../media/encryptionreport-viewdataby.png)

<span data-ttu-id="4388f-149">Met de flexibiliteit van het nieuwe versleutelingsrapport u trends bekijken en passende acties ondernemen.</span><span class="sxs-lookup"><span data-stu-id="4388f-149">With the flexibility of the new Encryption report, you can view trends and take appropriate actions.</span></span> <span data-ttu-id="4388f-150">Als u bijvoorbeeld een groot aantal e-mailberichten ziet die door gebruikers zijn versleuteld, u een versleutelingsbeleid toevoegen om versleuteling voor bepaalde use cases te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="4388f-150">For example, if you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="4388f-151">(Zie Regels voor [e-mailstroom definiëren om e-mailberichten in Office 365 te versleutelen](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) Als een ander voorbeeld, als u een aantal encryptiesjablonen beschikbaar hebt, maar niemand ze gebruikt, u onderzoeken of gebruikers training nodig hebben voor die functie.</span><span class="sxs-lookup"><span data-stu-id="4388f-151">(To get help with that, see [Define mail flow rules to encrypt email messages in Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) As another example, if you have a number of encryption templates available but no one is using them, you might explore whether users need training for that feature.</span></span>

<span data-ttu-id="4388f-152">Met dit rapport kan het beveiligings- en complianceteam van uw organisatie controleren hoe berichtversleuteling wordt gebruikt en of er verdere acties nodig zijn.</span><span class="sxs-lookup"><span data-stu-id="4388f-152">Use this report enables your organization's security and compliance team to monitor how message encryption is being used, and whether further actions are needed.</span></span> <span data-ttu-id="4388f-153">Zie [E-mailversleuteling in Office 365](../../compliance/email-encryption.md)voor meer informatie over versleuteling.</span><span class="sxs-lookup"><span data-stu-id="4388f-153">To learn more about encryption, see [Email encryption in Office 365](../../compliance/email-encryption.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="4388f-154">Statusrapport risicobeveiliging</span><span class="sxs-lookup"><span data-stu-id="4388f-154">Threat Protection Status report</span></span>

<span data-ttu-id="4388f-155">Het rapport **Status van bedreigingsbeveiliging** is een slim rapport met schadelijke e-mail die is gedetecteerd en geblokkeerd door Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="4388f-155">The **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection.</span></span> <span data-ttu-id="4388f-156">Dit rapport is handig voor het bekijken van e-mail die is geïdentificeerd als malware of een phishing-poging in de loop van de tijd (tot 90 dagen) en stelt beveiligingsbeheerders in staat trends te identificeren of te bepalen of het beleid moet worden aangepast.</span><span class="sxs-lookup"><span data-stu-id="4388f-156">This report is useful for viewing email identified as malware or a phishing attempt over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

> [!NOTE]
> <span data-ttu-id="4388f-157">Een rapport over de status van bedreigingsbescherming is beschikbaar voor klanten die [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) of [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP) hebben; De informatie die wordt weergegeven in het rapport Status bedreigingsstatus voor ATP-klanten zal echter waarschijnlijk andere gegevens bevatten dan wat EOP-klanten kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="4388f-157">A Threat Protection Status report is available to customers who have either [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) or [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="4388f-158">EOP-klanten kunnen bijvoorbeeld informatie over malware die in e-mail is gedetecteerd, bekijken, maar geen informatie over [schadelijke bestanden die zijn gedetecteerd in SharePoint Online, OneDrive of Microsoft Teams,](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)een ATP-specifieke mogelijkheid.</span><span class="sxs-lookup"><span data-stu-id="4388f-158">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams), an ATP-specific capability.</span></span> <span data-ttu-id="4388f-159">([Meer informatie over ATP-rapporten](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)</span><span class="sxs-lookup"><span data-stu-id="4388f-159">([Learn more about ATP reports](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)</span></span>

<span data-ttu-id="4388f-160">Als u dit rapport wilt bekijken, gaat u in het [Security & Compliance Center](https://protection.office.com)naar de status **bedreigingsbeveiliging** **van het** \> **dashboard** \> rapporten .</span><span class="sxs-lookup"><span data-stu-id="4388f-160">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>

![Statusrapport risicobeveiliging](../../media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)

<span data-ttu-id="4388f-162">Wanneer u het rapport Status bedreigingsbeveiliging voor het eerst opent, worden in het rapport standaard gegevens van de afgelopen zeven dagen weergegeven. U echter op **Filters** klikken en het datumbereik wijzigen voor maximaal 90 dagen details.</span><span class="sxs-lookup"><span data-stu-id="4388f-162">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail.</span></span> <span data-ttu-id="4388f-163">(Als u een proefabonnement gebruikt, bent u mogelijk beperkt tot 30 dagen aan gegevens.)</span><span class="sxs-lookup"><span data-stu-id="4388f-163">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

<span data-ttu-id="4388f-164">Dit rapport is handig voor het bekijken van de effectiviteit en impact van de [Exchange Online Protection-functies](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)van uw organisatie en voor trending op langere termijn.</span><span class="sxs-lookup"><span data-stu-id="4388f-164">This report is useful for viewing the effectiveness and impact of your organization's [Exchange Online Protection features](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features), and for longer-term trending.</span></span>

![Rapportfilters voor statusvan bedreigingsbeveiliging](../../media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)

<span data-ttu-id="4388f-166">U ook kiezen of u gegevens wilt bekijken voor e-mail die als kwaadaardig is geïdentificeerd, e-mail wordt geïdentificeerd als een phishing-poging of een e-mail die is geïdentificeerd als malware.</span><span class="sxs-lookup"><span data-stu-id="4388f-166">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>

![Opties voor de statusweergave van bedreigingsbeveiliging](../../media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)

## <a name="malware-detections-report"></a><span data-ttu-id="4388f-168">Malware detecties rapport</span><span class="sxs-lookup"><span data-stu-id="4388f-168">Malware Detections report</span></span>

<span data-ttu-id="4388f-169">Het rapport **Malware Detecties** laat zien hoeveel inkomende en uitgaande berichten zijn gedetecteerd als malware bevatten voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="4388f-169">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span>

<span data-ttu-id="4388f-170">Ga naar \> **Meldingen** \> **dashboardmalwaredetecties**om dit rapport te bekijken in het [Security & Compliance Center.](https://protection.office.com) **Dashboard**</span><span class="sxs-lookup"><span data-stu-id="4388f-170">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>

![Voorbeeld van rapport Malware Detecties](../../media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)

<span data-ttu-id="4388f-172">Net als bij andere rapporten, zoals het [rapport Status bedreigingsbeveiliging,](#threat-protection-status-report)worden in het rapport standaard gegevens van de afgelopen zeven dagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4388f-172">Similar to other reports, like the [Threat Protection Status report](#threat-protection-status-report), the report displays data for the past seven days by default.</span></span> <span data-ttu-id="4388f-173">U echter **filters** kiezen om het datumbereik te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="4388f-173">However, you can choose **Filters** to change the date range.</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="4388f-174">Rapport Top malware</span><span class="sxs-lookup"><span data-stu-id="4388f-174">Top Malware report</span></span>

<span data-ttu-id="4388f-175">De **Top Malware** rapport toont de verschillende soorten malware die werd gedetecteerd door Exchange [Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features).</span><span class="sxs-lookup"><span data-stu-id="4388f-175">The **Top Malware** report shows the various kinds of malware that was detected by [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features).</span></span>

<span data-ttu-id="4388f-176">Ga naar **Dashboard** \> **Top** \> **Malware**voor het bekijken van dit rapport in het Security & [Compliance Center.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="4388f-176">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>

![SCC - EOP Top Malware](../../media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)

<span data-ttu-id="4388f-178">Wanneer u boven een wig in het cirkeldiagram zweeft, u de naam van een soort malware zien en hoeveel berichten zijn gedetecteerd als het hebben van die malware.</span><span class="sxs-lookup"><span data-stu-id="4388f-178">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="4388f-179">Klik (of tik) op het rapport om het te openen in een nieuw browservenster, waar u een meer gedetailleerde weergave van het rapport krijgen.</span><span class="sxs-lookup"><span data-stu-id="4388f-179">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>

![Dit rapport toont de belangrijkste malware gedetecteerd voor uw organisatie](../../media/3fded224-fb31-4713-86f2-8afce5ce2991.png)

<span data-ttu-id="4388f-181">Onder de grafiek ziet u een lijst met gedetecteerde malware en hoeveel berichten zijn gedetecteerd als het hebben van die malware.</span><span class="sxs-lookup"><span data-stu-id="4388f-181">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="4388f-182">Rapport Topafzenders en geadresseerden</span><span class="sxs-lookup"><span data-stu-id="4388f-182">Top Senders and Recipients report</span></span>

<span data-ttu-id="4388f-183">Het rapport **Top afzenders en geadresseerden** is een cirkeldiagram met uw belangrijkste e-mailafzenders.</span><span class="sxs-lookup"><span data-stu-id="4388f-183">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span>

<span data-ttu-id="4388f-184">Als u dit rapport wilt bekijken, gaat u in het [Security & Compliance Center](https://protection.office.com)naar **Rapporten** \> **Dashboard** \> **Top Afzenders en Geadresseerden**.</span><span class="sxs-lookup"><span data-stu-id="4388f-184">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>

![Als u dit rapport wilt bekijken, gaat \> u \> in het Beveiligings- & Compliance Center naar Rapporten Dashboard Top Afzenders en Geadresseerden](../../media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)

<span data-ttu-id="4388f-186">Wanneer u de boventoon over een wig in het cirkeldiagram zweeft, ziet u een aantal verzonden of ontvangen berichten.</span><span class="sxs-lookup"><span data-stu-id="4388f-186">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="4388f-187">Klik (of tik) op het rapport om het te openen in een nieuw browservenster, waar u een meer gedetailleerde weergave van het rapport krijgen.</span><span class="sxs-lookup"><span data-stu-id="4388f-187">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>

<span data-ttu-id="4388f-188">Gebruik de lijst **Gegevens weergeven voor** om te kiezen of u gegevens wilt weergeven voor ontvangers van topafzenders, ontvangers, spamen en malwareontvangers.</span><span class="sxs-lookup"><span data-stu-id="4388f-188">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients.</span></span> <span data-ttu-id="4388f-189">U ook zien wie malware heeft ontvangen die is gedetecteerd door [Exchange Online Protection.](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop)</span><span class="sxs-lookup"><span data-stu-id="4388f-189">You can also see who received malware that was detected by [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop).</span></span>

![De lijst Gegevens weergeven voor om specifieke informatie weer te geven](../../media/bd91449f-7d42-4749-8666-7b44044049b8.png)

<span data-ttu-id="4388f-191">Onder de grafiek ziet u wie de belangrijkste afzenders of ontvangers van e-mail waren, samen met een aantal berichten die voor de opgegeven periode zijn verzonden of ontvangen.</span><span class="sxs-lookup"><span data-stu-id="4388f-191">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="4388f-192">Rapport spoofdetecties</span><span class="sxs-lookup"><span data-stu-id="4388f-192">Spoof Detections report</span></span>

<span data-ttu-id="4388f-193">Het **rapport Spoofdetecties** laat zien hoeveel spoof-e-mailberichten zijn gedetecteerd en welke, welke als "goed" werden beschouwd (spoofmail die om legitieme zakelijke redenen is gedaan).</span><span class="sxs-lookup"><span data-stu-id="4388f-193">The **Spoof Detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span>

<span data-ttu-id="4388f-194">Als u dit rapport wilt bekijken, gaat u in het [Beveiligings& Compliance Center](https://protection.office.com)naar Dashboard **Dashboard** \> **Spoofmail** **rapporten** \> .</span><span class="sxs-lookup"><span data-stu-id="4388f-194">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>

![Ga in het Beveiligingscentrum & \> \> naar Dashboard Spoofmail rapporten](../../media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)

<span data-ttu-id="4388f-196">Wanneer u meer dan een dag in de grafiek zweeft, u zien hoeveel spoof-e-mailberichten zijn binnengekomen.</span><span class="sxs-lookup"><span data-stu-id="4388f-196">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="4388f-197">Klik (of tik) op het rapport om het te openen in een nieuw browservenster, waar u een meer gedetailleerde weergave van het rapport krijgen.</span><span class="sxs-lookup"><span data-stu-id="4388f-197">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span> <span data-ttu-id="4388f-198">Zie [Anti-spoofing beveiliging in Office 365](anti-spoofing-protection.md)voor meer informatie over antispoofbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="4388f-198">To learn more about anti-spoof protection, see [Anti-spoofing protection in Office 365](anti-spoofing-protection.md).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="4388f-199">Spam detecties rapport</span><span class="sxs-lookup"><span data-stu-id="4388f-199">Spam Detections report</span></span>

<span data-ttu-id="4388f-200">Het rapport **Spamdetecties** toont alle spam-inhoud die door Exchange Online is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="4388f-200">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> <span data-ttu-id="4388f-201">Berichten worden geteld per bericht en niet per ontvanger.</span><span class="sxs-lookup"><span data-stu-id="4388f-201">Messages are counted per message, and not per recipient.</span></span> <span data-ttu-id="4388f-202">Als er bijvoorbeeld een e-mailbericht is verzonden naar 100 ontvangers in uw organisatie, wordt het als één bericht geteld.</span><span class="sxs-lookup"><span data-stu-id="4388f-202">For example, if an email message was sent to 100 recipients in your organization, it is counted as one message.</span></span>

<span data-ttu-id="4388f-203">Ga naar **Meldingen** \> \> **dashboardspamdetecties**om dit rapport in het [Security & Compliance Center](https://protection.office.com)te bekijken. **Dashboard**</span><span class="sxs-lookup"><span data-stu-id="4388f-203">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>

![Ga naar Het Dashboard \> \> EOP Spamdetecties in het &-beveiligingscentrum voor rapporten om dit rapport te bekijken.](../../media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)

<span data-ttu-id="4388f-205">Wanneer u meer dan een dag in de grafiek zweeft, u zien hoeveel items die dag zijn geblokkeerd en hoe deze items zijn gecategoriseerd.</span><span class="sxs-lookup"><span data-stu-id="4388f-205">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span> <span data-ttu-id="4388f-206">U bijvoorbeeld zien hoeveel spamberichten zijn gefilterd en hoeveel items afkomstig zijn van een IP-adres (Blocked Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="4388f-206">For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>

<span data-ttu-id="4388f-207">Klik (of tik) op het rapport om het te openen in een nieuw browservenster, waar u een meer gedetailleerde weergave van het rapport krijgen.</span><span class="sxs-lookup"><span data-stu-id="4388f-207">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>

![Het rapport Spamdetecties vertelt u hoeveel spamberichten zijn geblokkeerd of uitgefilterd](../../media/370ec67d-eb30-4863-bfcf-68a41be02295.png)

<span data-ttu-id="4388f-209">Onder de grafiek ziet u een lijst met spamitems die zijn gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="4388f-209">Below the chart, you'll see a list of spam items that were detected.</span></span> <span data-ttu-id="4388f-210">Selecteer een item om aanvullende informatie weer te geven, zoals of het spam-item binnen- of uitgaand was, de bericht-id en de ontvanger.</span><span class="sxs-lookup"><span data-stu-id="4388f-210">Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span> <span data-ttu-id="4388f-211">Zie Antispambeveiliging van Office [365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)voor meer informatie over antispambeveiliging.</span><span class="sxs-lookup"><span data-stu-id="4388f-211">To learn more about anti-spam protection, see [Office 365 email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="4388f-212">Verzonden en ontvangen e-mailrapport</span><span class="sxs-lookup"><span data-stu-id="4388f-212">Sent and received email report</span></span>

<span data-ttu-id="4388f-213">Het **verzonden en ontvangen e-mailrapport** is een slim rapport met informatie over binnenkomende en uitgaande e-mail, inclusief spamdetecties, malware en e-mail die als 'goed' is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="4388f-213">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span>

<span data-ttu-id="4388f-214">Als u dit rapport wilt bekijken, gaat u in het [Beveiligingscentrum & Compliance](https://protection.office.com)naar **Rapporten** \> **Dashboard** \> **verzonden en ontvangen e-mail**.</span><span class="sxs-lookup"><span data-stu-id="4388f-214">To view this report, in the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>

![Als u dit rapport wilt bekijken, gaat \> u \> in het & Compliance Center naar Rapporten dashboard verzonden en ontvangen e-mail](../../media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)

<span data-ttu-id="4388f-216">Wanneer u meer dan een dag in de grafiek zweeft, u zien hoeveel berichten zijn binnengekomen en hoe deze berichten zijn gecategoriseerd.</span><span class="sxs-lookup"><span data-stu-id="4388f-216">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized.</span></span> <span data-ttu-id="4388f-217">U bijvoorbeeld zien hoeveel berichten zijn gedetecteerd als malware en hoeveel er als spam zijn geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="4388f-217">For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>

<span data-ttu-id="4388f-218">Klik (of tik) op het rapport om het te openen in een nieuw browservenster, waar u een meer gedetailleerde weergave van het rapport krijgen.</span><span class="sxs-lookup"><span data-stu-id="4388f-218">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>

<span data-ttu-id="4388f-219">U de lijst **Opsplitsen per** lijst gebruiken om informatie per type of op richting te bekijken (inkomende en uitgaande).</span><span class="sxs-lookup"><span data-stu-id="4388f-219">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span>

![De lijst Opsplitsen gebruiken om informatie per type of richting weer te geven](../../media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)

<span data-ttu-id="4388f-221">Onder de grafiek ziet u een lijst met e-mailcategorieën, zoals **GoodMail**, **SpamContentFiltered,** enzovoort.</span><span class="sxs-lookup"><span data-stu-id="4388f-221">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on.</span></span> <span data-ttu-id="4388f-222">Selecteer een categorie om aanvullende informatie weer te geven, zoals acties die zijn uitgevoerd voor malware en of e-mail binnenkomend of uitgaand was.</span><span class="sxs-lookup"><span data-stu-id="4388f-222">Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>

![Dit rapport vertelt u over anti-malware, anti-spam en andere berichtdetecties](../../media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)

<span data-ttu-id="4388f-224">Zie Mail flow intelligence [in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365)voor meer informatie over e-mailinformatie.</span><span class="sxs-lookup"><span data-stu-id="4388f-224">To learn more about email intelligence, see [Mail flow intelligence in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="4388f-225">Rapport met door de gebruiker gerapporteerde berichten</span><span class="sxs-lookup"><span data-stu-id="4388f-225">User-reported messages report</span></span>

<span data-ttu-id="4388f-226">Het rapport **Met gebruikers gerapporteerde berichten** bevat informatie over e-mailberichten die gebruikers hebben gerapporteerd als ongewenste e-mail, phishingpogingen of goede e-mail met behulp van de [invoegtoepassing Bericht melden](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span><span class="sxs-lookup"><span data-stu-id="4388f-226">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="4388f-227">Details zijn beschikbaar voor elk bericht, inclusief de leveringsreden, zoals een uitzondering op het spambeleid of de regel voor e-mailstroom die is geconfigureerd voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="4388f-227">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="4388f-228">Als u details wilt weergeven, selecteert u een item in de lijst met gebruikersrapporten en bekijkt u de informatie op de tabbladen **Overzicht** en **Details.**</span><span class="sxs-lookup"><span data-stu-id="4388f-228">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![In het rapport Met gebruikers gerapporteerde berichten worden berichten weergegeven die gebruikers hebben aangeduid als ongewenste, geen ongewenste of phishingpogingen.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="4388f-230">Ga als volgt te werk om dit rapport in het [Security & Compliance Center](https://protection.office.com)te bekijken:</span><span class="sxs-lookup"><span data-stu-id="4388f-230">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="4388f-231">Ga naar Meldingen van gebruikers **van het** \> **Dashboard voor** \> **bedreigingen**.</span><span class="sxs-lookup"><span data-stu-id="4388f-231">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="4388f-232">Ga naar Meldingen van gebruikers **controleren** \> naar **Bedreigingsbeheer** \> . **User-reported messages**</span><span class="sxs-lookup"><span data-stu-id="4388f-232">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![Kies in het Security & \> Compliance \> Center de optie Gerapporteerde berichten van gebruikerscontrole van het risicobeheer](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="4388f-234">Als het rapport Met meldingen van door de gebruiker gerapporteerde berichten correct kan werken, **moet controlelogboekregistratie zijn ingeschakeld** voor uw Office 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="4388f-234">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="4388f-235">Dit wordt meestal gedaan door iemand die de rol Controlelogboeken heeft toegewezen in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4388f-235">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="4388f-236">Voor meer informatie, zie [Auditlogboeken zoeken in Office 365 in- of uitschakelen](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="4388f-236">For more information, see [Turn Office 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="4388f-237">Welke machtigingen zijn nodig om deze rapporten te bekijken?</span><span class="sxs-lookup"><span data-stu-id="4388f-237">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="4388f-238">Als u de in dit artikel beschreven rapporten wilt bekijken en gebruiken, **moet u een geschikte rol hebben toegewezen voor zowel het Security & Compliance Center als het Exchange-beheercentrum.**</span><span class="sxs-lookup"><span data-stu-id="4388f-238">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security & Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="4388f-239">Voor het Beveiligingscentrum & Compliance Center moet u een van de volgende rollen toegewezen hebben:</span><span class="sxs-lookup"><span data-stu-id="4388f-239">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  <span data-ttu-id="4388f-240">-Organisatiebeheer - Beveiligingsbeheerder (dit kan worden toegewezen in[https://aad.portal.azure.com](https://aad.portal.azure.com)het Azure Active Directory-beheercentrum ( ) -Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="4388f-240">-Organization Management -Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)) -Security Reader</span></span>

- <span data-ttu-id="4388f-241">Voor Exchange Online moet u een van de volgende rollen[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)hebben toegewezen in het Exchange-beheercentrum ( ) of met PowerShell-cmdlets (Zie [Exchange Online PowerShell):](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="4388f-241">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>

  <span data-ttu-id="4388f-242">-Organisatiebeheer -Alleen organisatiebeheer -Functie-weergave-alleen ontvangers -ComplianceManagement</span><span class="sxs-lookup"><span data-stu-id="4388f-242">-Organization Management -View-only Organization Management -View-Only Recipients role -Compliance Management</span></span>

<span data-ttu-id="4388f-243">Zie de volgende bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="4388f-243">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="4388f-244">Machtigingen in het Office 365 Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="4388f-244">Permissions in the Office 365 Security & Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

- [<span data-ttu-id="4388f-245">Functiemachtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4388f-245">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="4388f-246">Wat gebeurt er als de rapporten geen gegevens weergeven?</span><span class="sxs-lookup"><span data-stu-id="4388f-246">What if the reports aren't showing data?</span></span>

<span data-ttu-id="4388f-247">Als u geen gegevens in uw rapporten ziet, controleert u of uw beleid correct is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="4388f-247">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="4388f-248">Zie [Beschermen tegen bedreigingen in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4388f-248">To learn more, see [Protect against threats in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4388f-249">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4388f-249">Related topics</span></span>

[<span data-ttu-id="4388f-250">Beveiliging tegen spam in Office 365</span><span class="sxs-lookup"><span data-stu-id="4388f-250">Office 365 Email Anti-Spam Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

[<span data-ttu-id="4388f-251">Rapporten en inzichten in het Office 365 Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="4388f-251">Reports and insights in the Office 365 Security & Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)

[<span data-ttu-id="4388f-252">Een planning maken voor een rapport in het Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="4388f-252">Create a schedule for a report in the Security & Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-a-schedule-for-a-report)

[<span data-ttu-id="4388f-253">Een aangepast rapport instellen en downloaden in het Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="4388f-253">Set up and download a custom report in the Security & Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-and-download-a-custom-report)
