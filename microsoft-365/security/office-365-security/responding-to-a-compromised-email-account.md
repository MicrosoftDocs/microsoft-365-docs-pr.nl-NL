---
title: Reageren op een gehackt e-mailaccount
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
search.appverid:
- MET150
description: Lees hoe u een gehackt e-mailaccount kunt herkennen en hierop kunt reageren met behulp van de hulpmiddelen die beschikbaar zijn in Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1bbd607386b49b45ebd7444c4a91d05e4cee475b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288607"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="b886f-103">Reageren op een gehackt e-mailaccount</span><span class="sxs-lookup"><span data-stu-id="b886f-103">Responding to a Compromised Email Account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b886f-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="b886f-104">**Applies to**</span></span>
- [<span data-ttu-id="b886f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b886f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b886f-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="b886f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b886f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b886f-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="b886f-108">**Overzicht** Lees hoe u een gehackt e-mailaccount in Microsoft 365 kunt herkennen en hierop kunt reageren</span><span class="sxs-lookup"><span data-stu-id="b886f-108">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="b886f-109">Wat is een gehackt e-mailaccount in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="b886f-109">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="b886f-110">Toegang tot Microsoft 365-postvakken, -gegevens en andere services wordt geregeld door het gebruik van referenties, zoals een gebruikersnaam en wachtwoord of pincode.</span><span class="sxs-lookup"><span data-stu-id="b886f-110">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="b886f-111">Als iemand anders dan de bedoelde gebruiker die referenties steelt, worden de gestolen referenties geacht te zijn gehackt.</span><span class="sxs-lookup"><span data-stu-id="b886f-111">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="b886f-112">Hiermee kan de hacker zich aanmelden als de oorspronkelijke gebruiker en illegale acties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="b886f-112">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="b886f-113">Met de gestolen referenties kan de hacker toegang krijgen tot het Microsoft 365-postvak, SharePoint-mappen of bestanden in de OneDrive van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="b886f-113">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="b886f-114">Een actie die vaak wordt gezien, is dat de hacker e-mails verzendt als de oorspronkelijke gebruiker naar geadresseerden binnen en buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="b886f-114">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="b886f-115">Wanneer de hacker gegevens naar externe geadresseerden stuurt, wordt dit gegevensexfiltratie genoemd.</span><span class="sxs-lookup"><span data-stu-id="b886f-115">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="b886f-116">Symptomen van een gehackt Microsoft-e-mailaccount</span><span class="sxs-lookup"><span data-stu-id="b886f-116">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="b886f-117">Gebruikers kunnen ongebruikelijke activiteiten in hun Microsoft 365-postvakken opmerken en melden.</span><span class="sxs-lookup"><span data-stu-id="b886f-117">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="b886f-118">Hier volgen enkele veelvoorkomende symptomen:</span><span class="sxs-lookup"><span data-stu-id="b886f-118">Here are some common symptoms:</span></span>

- <span data-ttu-id="b886f-119">Verdachte activiteiten, zoals ontbrekende of verwijderde e-mails.</span><span class="sxs-lookup"><span data-stu-id="b886f-119">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="b886f-120">Het is mogelijk dat andere gebruikers e-mails ontvangen van het gehackte account, zonder dat de desbetreffende e-mail aanwezig is in de map met **Verzonden items** van de afzender.</span><span class="sxs-lookup"><span data-stu-id="b886f-120">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="b886f-121">De aanwezigheid van regels voor Postvak IN die niet zijn aangemaakt door de bedoelde gebruiker of door de beheerder.</span><span class="sxs-lookup"><span data-stu-id="b886f-121">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="b886f-122">Met deze regels kunnen e-mails automatisch worden doorgestuurd naar onbekende adressen of worden deze verplaatst naar de mappen met **Notities**, **Ongewenste e-mail** of **RSS-abonnementen**.</span><span class="sxs-lookup"><span data-stu-id="b886f-122">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="b886f-123">De weergavenaam van de gebruiker kan worden gewijzigd in de algemene adreslijst.</span><span class="sxs-lookup"><span data-stu-id="b886f-123">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="b886f-124">Het postvak van de gebruiker is geblokkeerd voor het verzenden van e-mails.</span><span class="sxs-lookup"><span data-stu-id="b886f-124">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="b886f-125">De mappen met Verzonden of Verwijderde items in Microsoft Outlook of de webversie van Outlook (voorheen bekend als Outlook Web App) bevatten berichten die vaak worden gestuurd door gehackte accounts, zoals "Ik zit vast in Londen, stuur geld".</span><span class="sxs-lookup"><span data-stu-id="b886f-125">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="b886f-126">Ongebruikelijke profielwijzigingen, zoals de naam, het telefoonnummer of de postcode zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="b886f-126">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="b886f-127">Ongebruikelijke referentiewijzigingen, zoals meerdere wachtwoordwijzigingen.</span><span class="sxs-lookup"><span data-stu-id="b886f-127">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="b886f-128">Het doorsturen van e-mail is onlangs toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="b886f-128">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="b886f-129">Er is onlangs een ongebruikelijke handtekening toegevoegd, zoals een valse bankhandtekening of een handtekening voor voorgeschreven medicijnen.</span><span class="sxs-lookup"><span data-stu-id="b886f-129">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="b886f-130">Als een gebruiker een van de bovenstaande problemen meldt, moet u nader onderzoek doen.</span><span class="sxs-lookup"><span data-stu-id="b886f-130">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="b886f-131">Het Microsoft 365-beveiligings- en compliancecentrum en de Azure-portal bieden hulpmiddelen voor het onderzoeken van de activiteiten van een gebruikersaccount waarvan u vermoedt dat het niet meer betrouwbaar is.</span><span class="sxs-lookup"><span data-stu-id="b886f-131">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="b886f-132">**Geïntegreerde auditlogboeken in het Beveiligings- en compliancecentrum**: Bekijk alle activiteiten van het verdachte account door de resultaten te filteren op het datumbereik van vlak voordat de verdachte activiteiten zich voordeden tot nu.</span><span class="sxs-lookup"><span data-stu-id="b886f-132">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="b886f-133">Filter niet op de activiteiten tijdens het zoeken.</span><span class="sxs-lookup"><span data-stu-id="b886f-133">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="b886f-134">**Auditlogboeken voor beheerders in het Exchange-beheercentrum (EAC)**: In Exchange Online kunt u het Exchange-beheercentrum gebruiken om vermeldingen te zoeken en weer te geven in het auditlogboek van de beheerder.</span><span class="sxs-lookup"><span data-stu-id="b886f-134">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="b886f-135">In het auditlogboek van de beheerder worden specifieke acties vastgelegd, gebaseerd op Exchange Online PowerShell-cmdlets, die worden uitgevoerd door beheerders en gebruikers aan wie beheerdersbevoegdheden zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="b886f-135">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="b886f-136">Vermeldingen in het auditlogboek van de beheerder bieden informatie over welke cmdlet is uitgevoerd, welke parameters zijn gebruikt, wie de cmdlet heeft uitgevoerd en welke objecten zijn beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="b886f-136">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="b886f-137">**Azure AD-aanmeldingslogboeken en andere risicorapporten in de Azure AD-portal**: Bekijk de waarden in deze kolommen:</span><span class="sxs-lookup"><span data-stu-id="b886f-137">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="b886f-138">Controleer het IP-adres</span><span class="sxs-lookup"><span data-stu-id="b886f-138">Review IP address</span></span>
  - <span data-ttu-id="b886f-139">aanmeldingslocaties</span><span class="sxs-lookup"><span data-stu-id="b886f-139">sign-in locations</span></span>
  - <span data-ttu-id="b886f-140">aanmeldingstijden</span><span class="sxs-lookup"><span data-stu-id="b886f-140">sign-in times</span></span>
  - <span data-ttu-id="b886f-141">geslaagde of misluke aanmeldingen</span><span class="sxs-lookup"><span data-stu-id="b886f-141">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="b886f-142">E-mailfunctionaliteit van een vermoedelijk gehackt Microsoft 365-account en -postvak beveiligen en herstellen</span><span class="sxs-lookup"><span data-stu-id="b886f-142">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="b886f-143">Zelfs nadat u opnieuw toegang heeft gekregen tot uw account, is het mogelijk dat de hacker verborgen toegangsmogelijkheden heeft aangemaakt waardoor de hacker beheer van het account kan hervatten.</span><span class="sxs-lookup"><span data-stu-id="b886f-143">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="b886f-144">U moet de volgende stappen uitvoeren om weer toegang te krijgen tot uw account. Des te eerder hoe beter, zodat de hacker niet opnieuw controle over uw account kan krijgen.</span><span class="sxs-lookup"><span data-stu-id="b886f-144">You must do all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="b886f-145">Met deze stappen verwijdert u alle verborgen toegangsmogelijkheden die de hacker mogelijk aan uw account heeft toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="b886f-145">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="b886f-146">Nadat u deze stappen hebt uitgevoerd, raden we u aan een virusscan uit te voeren om er zeker van te zijn dat uw computer niet gehackt is.</span><span class="sxs-lookup"><span data-stu-id="b886f-146">After you do these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="b886f-147">Stap 1 Stel het gebruikerswachtwoord opnieuw in</span><span class="sxs-lookup"><span data-stu-id="b886f-147">Step 1 Reset the user's password</span></span>

<span data-ttu-id="b886f-148">Volg de procedures in [Een zakelijk wachtwoord opnieuw instellen voor iemand](../../admin/add-users/reset-passwords.md#reset-my-admin-password).</span><span class="sxs-lookup"><span data-stu-id="b886f-148">Follow the procedures in [Reset a business password for someone](../../admin/add-users/reset-passwords.md#reset-my-admin-password).</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="b886f-149">Stuur het nieuwe wachtwoord niet via e-mail naar de bedoelde gebruiker, aangezien de hacker op dit moment nog steeds toegang tot het postvak heeft.</span><span class="sxs-lookup"><span data-stu-id="b886f-149">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>
>
> - <span data-ttu-id="b886f-150">Zorg ervoor dat het wachtwoord sterk is en dat het hoofdletters en kleine letters, tenminste één cijfer en tenminste één speciaal teken bevat.</span><span class="sxs-lookup"><span data-stu-id="b886f-150">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>
>
> - <span data-ttu-id="b886f-151">Gebruik uw laatste vijf wachtwoorden niet opnieuw.</span><span class="sxs-lookup"><span data-stu-id="b886f-151">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="b886f-152">Hoewel u volgens de vereisten voor wachtwoordgeschiedenis een recenter wachtwoord opnieuw kunt gebruiken, is het verstandig om iets te selecteren dat de hacker niet kan raden.</span><span class="sxs-lookup"><span data-stu-id="b886f-152">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
>
> - <span data-ttu-id="b886f-153">Als uw identiteit op locatie federatief is met Microsoft 365, moet u uw wachtwoord op locatie wijzigen en uw beheerder op de hoogte stellen van de aanval.</span><span class="sxs-lookup"><span data-stu-id="b886f-153">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>
>
> - <span data-ttu-id="b886f-154">Vergeet niet om app-wachtwoorden bij te werken.</span><span class="sxs-lookup"><span data-stu-id="b886f-154">Be sure to update app passwords.</span></span> <span data-ttu-id="b886f-155">App-wachtwoorden worden niet automatisch ingetrokken bij het opnieuw instellen van een wachtwoord voor een gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="b886f-155">App passwords aren't automatically revoked when a user account password reset.</span></span> <span data-ttu-id="b886f-156">De gebruiker moet bestaande app-wachtwoorden verwijderen en nieuwe app-wachtwoorden maken.</span><span class="sxs-lookup"><span data-stu-id="b886f-156">The user should delete existing app passwords and create new ones.</span></span> <span data-ttu-id="b886f-157">Voor meer informatie, zie [App-wachtwoorden maken en verwijderen op de pagina Aanvullende beveiligingsverificatie](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span><span class="sxs-lookup"><span data-stu-id="b886f-157">For instructions, see [Create and delete app passwords from the Additional security verification page](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span></span>
>
> - <span data-ttu-id="b886f-158">We raden u ten zeerste aan om meervoudige verificatie in te schakelen om een inbreuk te voorkomen, met name voor accounts met beheerdersbevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="b886f-158">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span> <span data-ttu-id="b886f-159">Voor meer informatie over MFA gaat u naar [Meervoudige verificatie instellen](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="b886f-159">To learn more about MFA, go to [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="b886f-160">Stap 2 E-mailadressen verwijderen die verdachte mails doorsturen</span><span class="sxs-lookup"><span data-stu-id="b886f-160">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="b886f-161">Het Microsoft 365-beheercentrum openen in <https://admin.microsoft.com></span><span class="sxs-lookup"><span data-stu-id="b886f-161">Open the Microsoft 365 admin center at <https://admin.microsoft.com></span></span>

2. <span data-ttu-id="b886f-162">Ga naar **Gebruikers** \> **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="b886f-162">Go to **Users** \> **Active users**.</span></span> <span data-ttu-id="b886f-163">Zoek het desbetreffende gebruikersaccount en selecteer de gebruiker (rij) zonder het selectievakje in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="b886f-163">Find the user account in question, and select the user (row) without selecting the checkbox.</span></span>

3. <span data-ttu-id="b886f-164">Selecteer in de flyout met details, het tabblad **E-mail**.</span><span class="sxs-lookup"><span data-stu-id="b886f-164">In the details flyout that appears, select the **Mail** tab.</span></span>

4. <span data-ttu-id="b886f-165">Als de waarde in de sectie **E-mail doorsturen** is **Toegepast**, klikt u op **E-mail doorsturen beheren**.</span><span class="sxs-lookup"><span data-stu-id="b886f-165">If the value in the **Email forwarding** section is **Applied**, click **Manage email forwarding**.</span></span> <span data-ttu-id="b886f-166">Schakel in de flyout **E-mail doorsturen beheren**, **Alle e-mailberichten naar dit postvak IN doorsturen** uit en klik vervolgens op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b886f-166">In the **Manage email forwarding** flyout that appears, clear **Forward all email sent to this mailbox**, and then click **Save changes**.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="b886f-167">Stap 3 Alle verdachte regels voor Postvak IN uitschakelen</span><span class="sxs-lookup"><span data-stu-id="b886f-167">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="b886f-168">Meld u aan bij het postvak van de gebruiker met de webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="b886f-168">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="b886f-169">Klik op het tandwielpictogram en klik op **Mail**.</span><span class="sxs-lookup"><span data-stu-id="b886f-169">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="b886f-170">Klik op **Regels voor postvak in en opruimen** en controleer de regels.</span><span class="sxs-lookup"><span data-stu-id="b886f-170">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="b886f-171">Blokkeer of verwijder alle verdachte regels.</span><span class="sxs-lookup"><span data-stu-id="b886f-171">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="b886f-172">Stap 4 De gebruiker opnieuw toestemming geven om mail te verzenden</span><span class="sxs-lookup"><span data-stu-id="b886f-172">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="b886f-173">Als het vermoedelijk gehackte postvak op illegale wijze is gebruikt voor het verzenden van ongewenste e-mail, is de kans groot dat het verzenden van mails vanuit dit postvak is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="b886f-173">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="b886f-174">Om ervoor te zorgen dat er weer mails kunnen worden verzonden vanuit dit postvak, volgt u de procedures in [Een gebruiker verwijderen uit de portal voor gebruikers met beperkte rechten na het verzenden van ongewenste e-mail](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="b886f-174">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="b886f-175">Stap 5 Optioneel: Aanmelden bij het gebruikersaccount blokkeren</span><span class="sxs-lookup"><span data-stu-id="b886f-175">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b886f-176">U kunt ervoor zorgen dat er niet meer ingelogd kan worden bij het vermoedelijk gehackte account tot u ervan overtuigd bent dat het veilig is om de blokkering op te heffen.</span><span class="sxs-lookup"><span data-stu-id="b886f-176">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="b886f-177">Ga in het Microsoft 365-beheercentrum naar **Gebruikers** \> **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="b886f-177">Open the Microsoft 365 admin center and go to **Users** \> **Active users**.</span></span>

2. <span data-ttu-id="b886f-178">Zoek en selecteer het gebruikersaccount, klik op ![Meer](../../media/ITPro-EAC-MoreOptionsIcon.png)en selecteer vervolgens **Aanmeldstatus bewerken**.</span><span class="sxs-lookup"><span data-stu-id="b886f-178">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Edit sign-in status**.</span></span>

3. <span data-ttu-id="b886f-179">Selecteer in het deelvenster **Aanmelding blokkeren** de optie **Aanmelden van deze gebruiker blokkeren** en klik vervolgens op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b886f-179">On the **Block sign-in** pane that appears, select **Block this user from signing in**, and then click **Save changes**.</span></span>

4. <span data-ttu-id="b886f-180">Open het Exchange-Beheercentrum (SBV) op <admin.protection.outlook.com/ecp/> en ga naar **Geadresseerden > Postvakken**.</span><span class="sxs-lookup"><span data-stu-id="b886f-180">Open the Exchange admin center (EAC) at <admin.protection.outlook.com/ecp/>, and go to **Recipients > Mailboxes**.</span></span>

5. <span data-ttu-id="b886f-181">Zoek en selecteer de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="b886f-181">Find and select the select the user.</span></span> <span data-ttu-id="b886f-182">In het detailvenster voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="b886f-182">In the details pane, do the following steps:</span></span>

   - <span data-ttu-id="b886f-183">Voer de volgende stappen uit in de sectie **Telefoon- en spraakfuncties** :</span><span class="sxs-lookup"><span data-stu-id="b886f-183">In the **Phone and voice features** section, do the following steps:</span></span>

     - <span data-ttu-id="b886f-184">Selecteer **Exchange ActiveSync uitschakelen** en klik vervolgens op **Ja** in het waarschuwingsbericht.</span><span class="sxs-lookup"><span data-stu-id="b886f-184">Select **Disable Exchange ActiveSync** and then click **Yes** in the warning that appears.</span></span>
     - <span data-ttu-id="b886f-185">Selecteer **OWA voor apparaten uitschakelen** en klik vervolgens op **Ja** in het waarschuwingsbericht.</span><span class="sxs-lookup"><span data-stu-id="b886f-185">Select **Disable OWA for Devices** and then click **Yes** in the warning that appears.</span></span>

   - <span data-ttu-id="b886f-186">Klik in de sectie **E-mailconnectiviteit** voor de webversie van Outlook op **Uitschakelen** en klik vervolgens op **Ja** in het waarschuwingsbericht.</span><span class="sxs-lookup"><span data-stu-id="b886f-186">In the **Email Connectivity** section for Outlook on the web, click **Disable** and then click **Yes** in the warning that appears.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="b886f-187">Stap 6 Optioneel: Verwijder het vermoedelijk gehackte account uit alle beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="b886f-187">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="b886f-188">Het lidmaatschap van de administratieve rolgroep kan worden hersteld nadat het account is beveiligd.</span><span class="sxs-lookup"><span data-stu-id="b886f-188">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="b886f-189">Meld u aan met een globale beheerdersaccount:</span><span class="sxs-lookup"><span data-stu-id="b886f-189">Sign in with a global administrator account:</span></span>

2. <span data-ttu-id="b886f-190">Voer de volgende stappen uit in het Microsoft 365-beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="b886f-190">In the Microsoft 365 admin center, do the following steps:</span></span>

   1. <span data-ttu-id="b886f-191">Ga naar **Gebruikers** \> **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="b886f-191">Go to **Users** \> **Active users**.</span></span>
   2. <span data-ttu-id="b886f-192">Zoek en selecteer het gebruikersaccount, klik op ![Meer](../../media/ITPro-EAC-MoreOptionsIcon.png) en selecteer vervolgens **Rollen beheren**.</span><span class="sxs-lookup"><span data-stu-id="b886f-192">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Manage roles**.</span></span>
   3. <span data-ttu-id="b886f-193">Verwijder alle beheerrollen die aan het account zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="b886f-193">Remove any administrative roles that are assigned to the account.</span></span> <span data-ttu-id="b886f-194">Wanneer u gereed bent, klikt u op **Wijzigingen opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b886f-194">When you're finished, click **Save changes**.</span></span>

3. <span data-ttu-id="b886f-195">Voer de volgende stappen uit in het beveiligings- en compliancecentrum op <https://protection.office.com>:</span><span class="sxs-lookup"><span data-stu-id="b886f-195">In the Security & Compliance Center at <https://protection.office.com>, do the following steps:</span></span>

   <span data-ttu-id="b886f-196">Selecteer **Machtigingen**, selecteer elke rollengroep in de lijst en zoek het gebruikersaccount in de sectie **Leden** in de flyout met details.</span><span class="sxs-lookup"><span data-stu-id="b886f-196">Select **Permissions**, select each role group in the list and look for the user account in the **Members** section of the details flyout that appears.</span></span> <span data-ttu-id="b886f-197">Als de rollengroep het gebruikersaccount bevat, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="b886f-197">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="b886f-198">a.</span><span class="sxs-lookup"><span data-stu-id="b886f-198">a.</span></span> <span data-ttu-id="b886f-199">Klik op **Bewerken** naast **Leden**.</span><span class="sxs-lookup"><span data-stu-id="b886f-199">Click **Edit** next to **Members**.</span></span>
   <span data-ttu-id="b886f-200">b.</span><span class="sxs-lookup"><span data-stu-id="b886f-200">b.</span></span> <span data-ttu-id="b886f-201">Klik in de flyout **Bewerken van leden kiezen** op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="b886f-201">On the **Editing Choose members** flyout that appears, click **Edit**.</span></span>
   <span data-ttu-id="b886f-202">c.</span><span class="sxs-lookup"><span data-stu-id="b886f-202">c.</span></span> <span data-ttu-id="b886f-203">Selecteer in de flyout **Leden kiezen** het gebruikersaccount en klik vervolgens op **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="b886f-203">In the **Choose members** flyout that appears, select the user account, and then click **Remove**.</span></span> <span data-ttu-id="b886f-204">Wanneer u gereed bent, klikt u op **Gereed**, **Opslaan** en vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="b886f-204">When you're finished, click **Done**, **Save**, and then **Close**.</span></span>

4. <span data-ttu-id="b886f-205">Voer de volgende stappen uit in het Exchange-beheercentrum SBV via <admin.protection.outlook.com/ecp/>:</span><span class="sxs-lookup"><span data-stu-id="b886f-205">In the EAC at <admin.protection.outlook.com/ecp/>, do the following steps:</span></span>

   <span data-ttu-id="b886f-206">Selecteer **Machtigingen**, selecteer elke rollengroep handmatig en controleer de gebruikersaccounts in de sectie **Leden** in het detailvenster.</span><span class="sxs-lookup"><span data-stu-id="b886f-206">Select **Permissions**, manually select each role group, and in the details pane, verify the user accounts in the **Members** section.</span></span>  <span data-ttu-id="b886f-207">Als de rollengroep het gebruikersaccount bevat, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="b886f-207">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="b886f-208">a.</span><span class="sxs-lookup"><span data-stu-id="b886f-208">a.</span></span> <span data-ttu-id="b886f-209">Selecteer de rollengroep, klik op **Bewerken** ![Pictogram bewerken](../../media/ITPro-EAC-EditIcon.png).</span><span class="sxs-lookup"><span data-stu-id="b886f-209">Select the role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>
   <span data-ttu-id="b886f-210">b.</span><span class="sxs-lookup"><span data-stu-id="b886f-210">b.</span></span> <span data-ttu-id="b886f-211">Selecteer in de sectie **Lid** het gebruikersaccount en klik vervolgens op **Verwijderen** ![Pictogram verwijderen](../../media/ITPro-EAC-RemoveIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="b886f-211">In the **Member** section, select the user account, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span> <span data-ttu-id="b886f-212">Wanneer u gereed bent, klikt u op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b886f-212">When you're finished, click **Save**.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="b886f-213">Stap 7 Optioneel: Extra voorzorgsmaatregelen</span><span class="sxs-lookup"><span data-stu-id="b886f-213">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="b886f-214">Zorg ervoor dat u uw verzonden items controleert.</span><span class="sxs-lookup"><span data-stu-id="b886f-214">Make sure that you verify your sent items.</span></span> <span data-ttu-id="b886f-215">Het is verstandig om de personen in uw contactenlijst op de hoogte te stellen van het feit dat uw account is gehackt.</span><span class="sxs-lookup"><span data-stu-id="b886f-215">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="b886f-216">De hacker heeft hen mogelijk om geld gevraagd, spoofing, bijvoorbeeld dat u zich in een ander land bevindt en geld nodig heeft, of het kan zijn dat de hacker een virus heeft verstuurd om ook hun computers te overnemen.</span><span class="sxs-lookup"><span data-stu-id="b886f-216">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="b886f-217">Een andere service die gebruik heeft gemaakt van dit Exchange-account als alternatief e-mailaccount kan ook gehackt zijn.</span><span class="sxs-lookup"><span data-stu-id="b886f-217">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="b886f-218">Voer deze stappen eerst uit voor uw Microsoft 365-abonnement en voer ze vervolgens uit voor uw andere accounts.</span><span class="sxs-lookup"><span data-stu-id="b886f-218">First, do these steps for your Microsoft 365 subscription, and then do these steps for your other accounts.</span></span>

3. <span data-ttu-id="b886f-219">Zorg ervoor dat uw contactgegevens, zoals telefoonnummers en adressen, correct zijn.</span><span class="sxs-lookup"><span data-stu-id="b886f-219">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="b886f-220">Microsoft 365 beveiligen als een cybersecurity pro</span><span class="sxs-lookup"><span data-stu-id="b886f-220">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="b886f-221">Uw Microsoft 365-abonnement heeft een krachtige reeks aan beveiligingsmogelijkheden die u kunt gebruiken om uw gegevens en gebruikers te beschermen.</span><span class="sxs-lookup"><span data-stu-id="b886f-221">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="b886f-222">Gebruik de [Microsoft 365-roadmap voor beveiliging - Topprioriteiten voor de eerste 30 dagen, 90 dagen en verder](security-roadmap.md) om door Microsoft aanbevolen procedures voor het beveiligen van uw Microsoft 365-tenant te implementeren.</span><span class="sxs-lookup"><span data-stu-id="b886f-222">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="b886f-223">Taken die in de eerste 30 dagen moeten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b886f-223">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="b886f-224">Deze hebben direct effect en weinig invloed op uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b886f-224">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="b886f-225">Taken die binnen 90 dagen moeten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b886f-225">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="b886f-226">Deze nemen qua planning en implementatie iets meer tijd in beslag, maar zorgen voor aanzienlijke verbeteringen in uw beveiligingspostuur.</span><span class="sxs-lookup"><span data-stu-id="b886f-226">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="b886f-227">Na 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="b886f-227">Beyond 90 days.</span></span> <span data-ttu-id="b886f-228">Deze verbeteringen zijn gebaseerd op de eerste 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="b886f-228">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="b886f-229">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b886f-229">See also</span></span>

- [<span data-ttu-id="b886f-230">Injectieaanvallen op Outlook-regels en aangepaste formulieren detecteren en verhelpen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b886f-230">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="b886f-231">Internet Crime Complaint Center</span><span class="sxs-lookup"><span data-stu-id="b886f-231">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="b886f-232">Securities and Exchange Commission - "Phishing" fraude</span><span class="sxs-lookup"><span data-stu-id="b886f-232">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="b886f-233">Om ongewenste e-mailberichten rechtstreeks bij Microsoft en uw beheerder te melden, kunt u [De invoegtoepassing rapporteer bericht gebruiken](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="b886f-233">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
