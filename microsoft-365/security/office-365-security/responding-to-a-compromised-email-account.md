---
title: Reageren op een gehackt e-mailaccount
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Lees hoe u een gehackt e-mailaccount kunt herkennen en hierop kunt reageren met behulp van de hulpmiddelen die beschikbaar zijn in Microsoft 365.
ms.openlocfilehash: 8a7bb98432529bfca70764314d251810d3cdb2a4
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819483"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="fc7a8-103">Reageren op een gehackt e-mailaccount</span><span class="sxs-lookup"><span data-stu-id="fc7a8-103">Responding to a Compromised Email Account</span></span>

<span data-ttu-id="fc7a8-104">**Overzicht** Lees hoe u een gehackt e-mailaccount in Microsoft 365 kunt herkennen en hierop kunt reageren</span><span class="sxs-lookup"><span data-stu-id="fc7a8-104">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="fc7a8-105">Wat is een gehackt e-mailaccount in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="fc7a8-105">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="fc7a8-106">Toegang tot Microsoft 365-postvakken, -gegevens en andere services wordt geregeld door het gebruik van referenties, zoals een gebruikersnaam en wachtwoord of pincode.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-106">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="fc7a8-107">Als iemand anders dan de bedoelde gebruiker die referenties steelt, worden de gestolen referenties geacht te zijn gehackt.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-107">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="fc7a8-108">Hiermee kan de hacker zich aanmelden als de oorspronkelijke gebruiker en illegale acties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-108">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="fc7a8-109">Met de gestolen referenties kan de hacker toegang krijgen tot het Microsoft 365-postvak, SharePoint-mappen of bestanden in de OneDrive van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-109">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="fc7a8-110">Een actie die vaak wordt gezien, is dat de hacker e-mails verzendt als de oorspronkelijke gebruiker naar geadresseerden binnen en buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-110">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="fc7a8-111">Wanneer de hacker gegevens naar externe geadresseerden stuurt, wordt dit gegevensexfiltratie genoemd.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-111">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="fc7a8-112">Symptomen van een gehackt Microsoft-e-mailaccount</span><span class="sxs-lookup"><span data-stu-id="fc7a8-112">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="fc7a8-113">Gebruikers kunnen ongebruikelijke activiteiten in hun Microsoft 365-postvakken opmerken en melden.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-113">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="fc7a8-114">Hier volgen enkele veelvoorkomende symptomen:</span><span class="sxs-lookup"><span data-stu-id="fc7a8-114">Here are some common symptoms:</span></span>

- <span data-ttu-id="fc7a8-115">Verdachte activiteiten, zoals ontbrekende of verwijderde e-mails.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-115">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="fc7a8-116">Het is mogelijk dat andere gebruikers e-mails ontvangen van het gehackte account, zonder dat de desbetreffende e-mail aanwezig is in de map met **Verzonden items** van de afzender.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="fc7a8-117">De aanwezigheid van regels voor Postvak IN die niet zijn aangemaakt door de bedoelde gebruiker of door de beheerder.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-117">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="fc7a8-118">Met deze regels kunnen e-mails automatisch worden doorgestuurd naar onbekende adressen of worden deze verplaatst naar de mappen met **Notities**, **Ongewenste e-mail** of **RSS-abonnementen**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-118">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="fc7a8-119">De weergavenaam van de gebruiker kan worden gewijzigd in de algemene adreslijst.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-119">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="fc7a8-120">Het postvak van de gebruiker is geblokkeerd voor het verzenden van e-mails.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-120">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="fc7a8-121">De mappen met Verzonden of Verwijderde items in Microsoft Outlook of de webversie van Outlook (voorheen bekend als Outlook Web App) bevatten berichten die vaak worden gestuurd door gehackte accounts, zoals "Ik zit vast in Londen, stuur geld".</span><span class="sxs-lookup"><span data-stu-id="fc7a8-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="fc7a8-122">Ongebruikelijke profielwijzigingen, zoals de naam, het telefoonnummer of de postcode zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="fc7a8-123">Ongebruikelijke referentiewijzigingen, zoals meerdere wachtwoordwijzigingen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-123">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="fc7a8-124">Het doorsturen van e-mail is onlangs toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-124">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="fc7a8-125">Er is onlangs een ongebruikelijke handtekening toegevoegd, zoals een valse bankhandtekening of een handtekening voor voorgeschreven medicijnen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="fc7a8-126">Als een gebruiker een van de bovenstaande problemen meldt, moet u nader onderzoek doen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="fc7a8-127">Het Microsoft 365-beveiligings- en compliancecentrum en de Azure-portal bieden hulpmiddelen voor het onderzoeken van de activiteiten van een gebruikersaccount waarvan u vermoedt dat het niet meer betrouwbaar is.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="fc7a8-128">**Geïntegreerde auditlogboeken in het Beveiligings- en compliancecentrum**: Bekijk alle activiteiten van het verdachte account door de resultaten te filteren op het datumbereik van vlak voordat de verdachte activiteiten zich voordeden tot nu.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-128">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="fc7a8-129">Filter niet op de activiteiten tijdens het zoeken.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-129">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="fc7a8-130">**Auditlogboeken voor beheerders in het Exchange-beheercentrum (EAC)**: In Exchange Online kunt u het Exchange-beheercentrum gebruiken om vermeldingen te zoeken en weer te geven in het auditlogboek van de beheerder.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-130">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="fc7a8-131">In het auditlogboek van de beheerder worden specifieke acties vastgelegd, gebaseerd op Exchange Online PowerShell-cmdlets, die worden uitgevoerd door beheerders en gebruikers aan wie beheerdersbevoegdheden zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-131">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="fc7a8-132">Vermeldingen in het auditlogboek van de beheerder bieden informatie over welke cmdlet is uitgevoerd, welke parameters zijn gebruikt, wie de cmdlet heeft uitgevoerd en welke objecten zijn beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-132">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="fc7a8-133">**Azure AD-aanmeldingslogboeken en andere risicorapporten in de Azure AD-portal**: Bekijk de waarden in deze kolommen:</span><span class="sxs-lookup"><span data-stu-id="fc7a8-133">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="fc7a8-134">Controleer het IP-adres</span><span class="sxs-lookup"><span data-stu-id="fc7a8-134">Review IP address</span></span>

  - <span data-ttu-id="fc7a8-135">aanmeldingslocaties</span><span class="sxs-lookup"><span data-stu-id="fc7a8-135">sign-in locations</span></span>

  - <span data-ttu-id="fc7a8-136">aanmeldingstijden</span><span class="sxs-lookup"><span data-stu-id="fc7a8-136">sign-in times</span></span>

  - <span data-ttu-id="fc7a8-137">geslaagde of misluke aanmeldingen</span><span class="sxs-lookup"><span data-stu-id="fc7a8-137">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="fc7a8-138">E-mailfunctionaliteit van een vermoedelijk gehackt Microsoft 365-account en -postvak beveiligen en herstellen</span><span class="sxs-lookup"><span data-stu-id="fc7a8-138">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="fc7a8-139">Zelfs nadat u opnieuw toegang heeft gekregen tot uw account, is het mogelijk dat de hacker verborgen toegangsmogelijkheden heeft aangemaakt waardoor de hacker beheer van het account kan hervatten.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-139">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="fc7a8-140">U moet de volgende stappen uitvoeren om weer toegang te krijgen tot uw account. Het is verstandig dit zo snel mogelijk te doen, zodat de hacker niet opnieuw controle over uw account kan krijgen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-140">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="fc7a8-141">Met deze stappen verwijdert u alle verborgen toegangsmogelijkheden die de hacker mogelijk aan uw account heeft toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-141">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="fc7a8-142">Nadat u deze stappen hebt uitgevoerd, raden we u aan een virusscan uit te voeren om er zeker van te zijn dat uw computer niet gehackt is.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-142">After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="fc7a8-143">Stap 1 Stel het gebruikerswachtwoord opnieuw in</span><span class="sxs-lookup"><span data-stu-id="fc7a8-143">Step 1 Reset the user's password</span></span>

> [!WARNING]
> <span data-ttu-id="fc7a8-144">Stuur het nieuwe wachtwoord niet via e-mail naar de bedoelde gebruiker, aangezien de hacker op dit moment nog steeds toegang tot het postvak heeft.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-144">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="fc7a8-145">Volg de procedures voor het opnieuw instellen van een wachtwoord van iemand anders voor Microsoft 365-apps voor ondernemingen in [Wachtwoorden voor Microsoft 365-apps voor ondernemingen opnieuw instellen](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)</span><span class="sxs-lookup"><span data-stu-id="fc7a8-145">Follow the Reset a Microsoft 365 Apps for business password for someone else procedures in [Reset Microsoft 365 Apps for business passwords](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)</span></span>

<span data-ttu-id="fc7a8-146">**Opmerkingen**:</span><span class="sxs-lookup"><span data-stu-id="fc7a8-146">**Notes**:</span></span>

- <span data-ttu-id="fc7a8-147">Zorg ervoor dat het wachtwoord sterk is en dat het hoofdletters en kleine letters, tenminste één cijfer en tenminste één speciaal teken bevat.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-147">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>

- <span data-ttu-id="fc7a8-148">Gebruik uw laatste vijf wachtwoorden niet opnieuw.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-148">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="fc7a8-149">Hoewel u volgens de vereisten voor wachtwoordgeschiedenis een recenter wachtwoord opnieuw kunt gebruiken, is het verstandig om iets te selecteren dat de hacker niet kan raden.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-149">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>

- <span data-ttu-id="fc7a8-150">Als uw identiteit op locatie federatief is met Microsoft 365, moet u uw wachtwoord op locatie wijzigen en uw beheerder op de hoogte stellen van de aanval.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-150">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

> [!TIP]
> <span data-ttu-id="fc7a8-151">We raden u ten zeerste aan om meervoudige verificatie in te schakelen om een inbreuk te voorkomen, met name voor accounts met beheerdersbevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-151">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span>  <span data-ttu-id="fc7a8-152">Voor meer informatie over MFA, gaat u naar [Meervoudige verificatie instellen]((https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="fc7a8-152">To learn more about MFA, go to [Set up multi-factor authentication]((https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="fc7a8-153">Stap 2 E-mailadressen verwijderen die verdachte mails doorsturen</span><span class="sxs-lookup"><span data-stu-id="fc7a8-153">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="fc7a8-154">Open het **Microsoft 365-beheercentrum > Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-154">Open the **Microsoft 365 admin center > Active Users**.</span></span>

2. <span data-ttu-id="fc7a8-155">Zoek het gebruikersaccount in kwestie en vouw **E-mail instellingen** uit.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-155">Find the user account in question and expand **Mail Settings**.</span></span>

3. <span data-ttu-id="fc7a8-156">Kies **Bewerken** bij **E-mail doorsturen**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-156">For **Email forwarding**, click **Edit**.</span></span>

4. <span data-ttu-id="fc7a8-157">Verwijder alle verdachte doorstuuradressen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-157">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="fc7a8-158">Stap 3 Alle verdachte regels voor Postvak IN uitschakelen</span><span class="sxs-lookup"><span data-stu-id="fc7a8-158">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="fc7a8-159">Meld u aan bij het postvak van de gebruiker met de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-159">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="fc7a8-160">Klik op het tandwielpictogram en klik op **Mail**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-160">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="fc7a8-161">Klik op **Regels voor postvak in en opruimen** en controleer de regels.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-161">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="fc7a8-162">Blokkeer of verwijder alle verdachte regels.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-162">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="fc7a8-163">Stap 4 De gebruiker opnieuw toestemming geven om mail te verzenden</span><span class="sxs-lookup"><span data-stu-id="fc7a8-163">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="fc7a8-164">Als het vermoedelijk gehackte postvak op illegale wijze is gebruikt voor het verzenden van ongewenste e-mail, is de kans groot dat het verzenden van mails vanuit dit postvak is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-164">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="fc7a8-165">Om ervoor te zorgen dat er weer mails kunnen worden verzonden vanuit dit postvak, volgt u de procedures in [Een gebruiker verwijderen uit de portal voor gebruikers met beperkte rechten na het verzenden van ongewenste e-mail](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="fc7a8-165">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="fc7a8-166">Stap 5 Optioneel: Aanmelden bij het gebruikersaccount blokkeren</span><span class="sxs-lookup"><span data-stu-id="fc7a8-166">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc7a8-167">U kunt ervoor zorgen dat er niet meer ingelogd kan worden bij het vermoedelijk gehackte account tot u ervan overtuigd bent dat het veilig is om de blokkering op te heffen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-167">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="fc7a8-168">Ga naar het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-168">Go to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="fc7a8-169">Selecteer **Gebruikers** in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-169">In the Microsoft 365 admin center, select **Users**.</span></span>

3. <span data-ttu-id="fc7a8-170">Selecteer de werknemer die u wilt blokkeren en kies **Bewerken** naast **Aanmeldstatus** in het gebruikersdeelvenster.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-170">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane.</span></span>

4. <span data-ttu-id="fc7a8-171">Kies in het deelvenster **Aanmeldstatus** de optie **Aanmelding geblokkeerd** en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-171">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span>

5. <span data-ttu-id="fc7a8-172">Vouw in het Beheercentrum, in het navigatievenster linksonder, **Beheercentra** uit en selecteer **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-172">In the Admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>

6. <span data-ttu-id="fc7a8-173">Ga in het Exchange-beheercentrum naar **Ontvangers > Postvakken**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-173">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>

7. <span data-ttu-id="fc7a8-174">Selecteer de gebruiker en klik op de pagina met gebruikerseigenschappen onder **Mobiele apparaten** op **Exchange ActiveSync uitschakelen** en **OWA voor apparaten uitschakelen** en klik bij beide items op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-174">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>

8. <span data-ttu-id="fc7a8-175">Klik onder **E-mailconnectiviteit** op **Uitschakelen** en klik op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-175">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="fc7a8-176">Stap 6 Optioneel: Verwijder het vermoedelijk gehackte account uit alle beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-176">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="fc7a8-177">Het lidmaatschap van de administratieve rolgroep kan worden hersteld nadat het account is beveiligd.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-177">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="fc7a8-178">Meld u met een algemeen beheerdersaccount aan bij het Microsoft 365-beheercentrum en open **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-178">Sign in to the Microsoft 365 admin center with a global administrator account and open **Active Users**.</span></span>

2. <span data-ttu-id="fc7a8-179">Zoek het vermoedelijk gehackte account en controleer handmatig of er beheerdersrollen aan het account zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-179">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>

3. <span data-ttu-id="fc7a8-180">Open het **Beveiligings- en compliancecentrum**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-180">Open the **Security & Compliance Center**.</span></span>

4. <span data-ttu-id="fc7a8-181">Klik op **Machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-181">Click **Permissions**.</span></span>

5. <span data-ttu-id="fc7a8-182">Bekijk de rolgroepen handmatig om te zien of het vermoedelijk gehackte account lid is van een van deze groepen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-182">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span>  <span data-ttu-id="fc7a8-183">Zo ja:</span><span class="sxs-lookup"><span data-stu-id="fc7a8-183">If it is:</span></span>

   <span data-ttu-id="fc7a8-184">a.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-184">a.</span></span> <span data-ttu-id="fc7a8-185">Klik op de rolgroep en klik op **Rolgroep bewerken**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-185">Click the role group and click **Edit Role Group**.</span></span>

   <span data-ttu-id="fc7a8-186">b.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-186">b.</span></span> <span data-ttu-id="fc7a8-187">Klik op **Leden kiezen** en **Bewerken** om de gebruiker uit de rolgroep te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-187">Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>

6. <span data-ttu-id="fc7a8-188">Open het **Exchange-beheercentrum**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-188">Open the **Exchange admin center**.</span></span>

7. <span data-ttu-id="fc7a8-189">Klik op **Machtigingen**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-189">Click **Permissions**.</span></span>

8. <span data-ttu-id="fc7a8-190">Bekijk de rolgroepen handmatig om te zien of het vermoedelijk gehackte account lid is van een van deze groepen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-190">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span> <span data-ttu-id="fc7a8-191">Zo ja:</span><span class="sxs-lookup"><span data-stu-id="fc7a8-191">If it is:</span></span>

   <span data-ttu-id="fc7a8-192">a.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-192">a.</span></span> <span data-ttu-id="fc7a8-193">Klik op de rolgroep en klik op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-193">Click the role group and click **Edit**.</span></span>

   <span data-ttu-id="fc7a8-194">b.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-194">b.</span></span> <span data-ttu-id="fc7a8-195">Gebruik de **leden**-sectie om de gebruiker uit de rolgroep te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-195">Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="fc7a8-196">Stap 7 Optioneel: Extra voorzorgsmaatregelen</span><span class="sxs-lookup"><span data-stu-id="fc7a8-196">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="fc7a8-197">Zorg ervoor dat u uw verzonden items controleert.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-197">Make sure that you verify your sent items.</span></span> <span data-ttu-id="fc7a8-198">Het is verstandig om de personen in uw contactenlijst op de hoogte te stellen van het feit dat uw account is gehackt.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-198">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="fc7a8-199">De hacker heeft hen mogelijk om geld gevraagd, spoofing, bijvoorbeeld dat u zich in een ander land bevindt en geld nodig heeft, of het kan zijn dat de hacker een virus heeft verstuurd om ook hun computers te overnemen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-199">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="fc7a8-200">Een andere service die gebruik heeft gemaakt van dit Exchange-account als alternatief e-mailaccount kan ook gehackt zijn.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-200">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="fc7a8-201">Voer deze stappen eerst uit voor uw Microsoft 365-abonnement en voer ze vervolgens uit voor uw andere accounts.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-201">First, perform these steps for your Microsoft 365 subscription, and then perform these steps for your other accounts.</span></span>

3. <span data-ttu-id="fc7a8-202">Zorg ervoor dat uw contactgegevens, zoals telefoonnummers en adressen, correct zijn.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-202">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="fc7a8-203">Microsoft 365 beveiligen als een cybersecurity pro</span><span class="sxs-lookup"><span data-stu-id="fc7a8-203">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="fc7a8-204">Uw Microsoft 365-abonnement heeft een krachtige reeks aan beveiligingsmogelijkheden die u kunt gebruiken om uw gegevens en gebruikers te beschermen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-204">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="fc7a8-205">Gebruik de [Microsoft 365-roadmap voor beveiliging - Topprioriteiten voor de eerste 30 dagen, 90 dagen en verder](security-roadmap.md) om door Microsoft aanbevolen procedures voor het beveiligen van uw Microsoft 365-tenant te implementeren.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-205">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="fc7a8-206">Taken die in de eerste 30 dagen moeten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-206">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="fc7a8-207">Deze hebben direct effect en weinig invloed op uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-207">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="fc7a8-208">Taken die binnen 90 dagen moeten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-208">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="fc7a8-209">Deze nemen qua planning en implementatie iets meer tijd in beslag, maar zorgen voor aanzienlijke verbeteringen in uw beveiligingspostuur.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-209">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="fc7a8-210">Na 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-210">Beyond 90 days.</span></span> <span data-ttu-id="fc7a8-211">Deze verbeteringen zijn gebaseerd op de eerste 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="fc7a8-211">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc7a8-212">Zie ook</span><span class="sxs-lookup"><span data-stu-id="fc7a8-212">See also</span></span>

- [<span data-ttu-id="fc7a8-213">Injectieaanvallen op Outlook-regels en aangepaste formulieren detecteren en verhelpen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc7a8-213">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="fc7a8-214">Internet Crime Complaint Center</span><span class="sxs-lookup"><span data-stu-id="fc7a8-214">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="fc7a8-215">Securities and Exchange Commission - "Phishing" fraude</span><span class="sxs-lookup"><span data-stu-id="fc7a8-215">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="fc7a8-216">Om ongewenste e-mailberichten rechtstreeks bij Microsoft en uw beheerder te melden, kunt u [De invoegtoepassing rapporteer bericht gebruiken](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="fc7a8-216">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
