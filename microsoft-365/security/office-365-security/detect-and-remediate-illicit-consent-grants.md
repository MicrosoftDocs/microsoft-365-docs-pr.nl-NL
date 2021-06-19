---
title: Illegale toestemmingsgelden detecteren en herstellen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Meer informatie over het herkennen en herstellen van de illegale toestemmingsinfarcten in Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4c3c3c06974feb2dab3985a60938fe7d543543c3
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028917"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a><span data-ttu-id="ace8c-103">Illegale toestemmingsgelden detecteren en herstellen</span><span class="sxs-lookup"><span data-stu-id="ace8c-103">Detect and Remediate Illicit Consent Grants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ace8c-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ace8c-104">**Applies to**</span></span>
- [<span data-ttu-id="ace8c-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ace8c-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ace8c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ace8c-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ace8c-107">**Overzicht**  Meer informatie over het herkennen en herstellen van de illegale toestemmingsinfarcten in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ace8c-107">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="ace8c-108">Wat is de illegale toestemmingsinfarct in Office 365?</span><span class="sxs-lookup"><span data-stu-id="ace8c-108">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="ace8c-109">Bij een illegale toestemmingsaanvraag maakt de aanvaller een azure-geregistreerde toepassing waarin toegang wordt gevraagd tot gegevens, zoals contactgegevens, e-mail of documenten.</span><span class="sxs-lookup"><span data-stu-id="ace8c-109">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="ace8c-110">De aanvaller trucs vervolgens een eindgebruiker om die toepassing toestemming te geven om toegang te krijgen tot hun gegevens via een phishing-aanval of door illegale code in te voeren op een vertrouwde website.</span><span class="sxs-lookup"><span data-stu-id="ace8c-110">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="ace8c-111">Nadat toestemming is verleend voor de illegale toepassing, heeft deze toegang op accountniveau tot gegevens zonder dat er een organisatieaccount nodig is.</span><span class="sxs-lookup"><span data-stu-id="ace8c-111">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="ace8c-112">Normale herstelstappen, zoals het opnieuw instellen van wachtwoorden voor inbreukmakende accounts of het vereisen van MFA (Multi-Factor Authentication) op accounts, zijn niet effectief tegen dit type aanval, omdat dit toepassingen van derden zijn en buiten de organisatie vallen.</span><span class="sxs-lookup"><span data-stu-id="ace8c-112">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span>

<span data-ttu-id="ace8c-113">Deze aanvallen maken gebruik van een interactiemodel dat ervan uit gaat dat de entiteit die de informatie aanroept, automatisering is en geen mens.</span><span class="sxs-lookup"><span data-stu-id="ace8c-113">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ace8c-114">Vermoedt u dat u op dit moment problemen ondervindt met illegale toestemmingsgelden vanuit een app?</span><span class="sxs-lookup"><span data-stu-id="ace8c-114">Do you suspect you're experiencing problems with illicit consent-grants from an app, right now?</span></span> <span data-ttu-id="ace8c-115">Microsoft Cloud App Security (MCAS) beschikt over hulpprogramma's voor het detecteren, onderzoeken en corrigeren van uw OAuth-apps.</span><span class="sxs-lookup"><span data-stu-id="ace8c-115">Microsoft Cloud App Security (MCAS) has tools to detect, investigate, and remediate your OAuth apps.</span></span> <span data-ttu-id="ace8c-116">Dit MCAS-artikel bevat een zelfstudie over het onderzoeken van riskante [OAuth-apps.](/cloud-app-security/investigate-risky-oauth)</span><span class="sxs-lookup"><span data-stu-id="ace8c-116">This MCAS article has a tutorial that outlines how to go about [investigating risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span> <span data-ttu-id="ace8c-117">U kunt ook [OAuth-appbeleid](/cloud-app-security/app-permission-policy) instellen om te onderzoeken welke machtigingen voor apps zijn aangevraagd, welke gebruikers deze apps mogen gebruiken en deze machtigingsaanvragen op grote schaal goed te keuren of te verbieden.</span><span class="sxs-lookup"><span data-stu-id="ace8c-117">You can also set [OAuth app policies](/cloud-app-security/app-permission-policy) to investigate app-requested permissions, which users are authorizing these apps, and widely approve or ban these permissions requests.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="ace8c-118">Hoe ziet een illegale toestemmingsinfarct eruit in Office 365?</span><span class="sxs-lookup"><span data-stu-id="ace8c-118">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="ace8c-119">U moet in het **auditlogboek** zoeken naar tekens, ook wel Indicatoren van compromis (IOC) van deze aanval genoemd.</span><span class="sxs-lookup"><span data-stu-id="ace8c-119">You need to search the **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="ace8c-120">Voor organisaties met veel azure-geregistreerde toepassingen en een grote gebruikersbasis is het de beste manier om uw toestemmingsaanvragen voor organisaties wekelijks te bekijken.</span><span class="sxs-lookup"><span data-stu-id="ace8c-120">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="ace8c-121">Stappen voor het vinden van tekenen van deze aanval</span><span class="sxs-lookup"><span data-stu-id="ace8c-121">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="ace8c-122">Open de **Microsoft 365 Defender** portal op <https://security.microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="ace8c-122">Open the **Microsoft 365 Defender** portal at <https://security.microsoft.com>.</span></span>

2. <span data-ttu-id="ace8c-123">**Navigeer naar Zoeken** en selecteer **Auditlogboek zoeken.**</span><span class="sxs-lookup"><span data-stu-id="ace8c-123">Navigate to **Search** and select **Audit log search**.</span></span>

3. <span data-ttu-id="ace8c-124">Zoek (alle activiteiten en alle gebruikers) en voer indien nodig de begin- en einddatum in en klik op **Zoeken.**</span><span class="sxs-lookup"><span data-stu-id="ace8c-124">Search (all activities and all users) and enter the start date and end date if required and then click **Search**.</span></span>

4. <span data-ttu-id="ace8c-125">Klik **op Resultaten filteren** en voer Toestemming voor toepassing in het veld **Activiteit** in.</span><span class="sxs-lookup"><span data-stu-id="ace8c-125">Click **Filter results** and enter Consent to application in the **Activity** field.</span></span>

5. <span data-ttu-id="ace8c-126">Klik op het resultaat om de details van de activiteit te bekijken.</span><span class="sxs-lookup"><span data-stu-id="ace8c-126">Click on the result to see the details of the activity.</span></span> <span data-ttu-id="ace8c-127">Klik **op Meer informatie** voor meer informatie over de activiteit.</span><span class="sxs-lookup"><span data-stu-id="ace8c-127">Click **More Information** to get details of the activity.</span></span> <span data-ttu-id="ace8c-128">Controleer of IsAdminContent is ingesteld op Waar.</span><span class="sxs-lookup"><span data-stu-id="ace8c-128">Check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
>
> <span data-ttu-id="ace8c-129">Het kan 30 minuten tot 24 uur duren voordat de bijbehorende controlelogboekinvoer wordt weergegeven in de zoekresultaten nadat er een gebeurtenis plaatsvindt.</span><span class="sxs-lookup"><span data-stu-id="ace8c-129">It can take from 30 minutes up to 24 hours for the corresponding audit log entry to be displayed in the search results after an event occurs.</span></span>
>
> <span data-ttu-id="ace8c-130">De duur van een auditrecord die in het auditlogboek wordt bewaard en doorzoekbaar is, is afhankelijk van uw Microsoft 365-abonnement, en met name van het type licentie dat aan een specifieke gebruiker is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="ace8c-130">The length of time that an audit record is retained and searchable in the audit log depends on your Microsoft 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="ace8c-131">Zie [Auditlogboek](../../compliance/search-the-audit-log-in-security-and-compliance.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ace8c-131">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
>
> <span data-ttu-id="ace8c-132">Als deze waarde waar is, geeft deze aan dat iemand met globale beheerderstoegang mogelijk uitgebreide toegang tot gegevens heeft verleend.</span><span class="sxs-lookup"><span data-stu-id="ace8c-132">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="ace8c-133">Als dit onverwacht is, moet u stappen ondernemen om [een aanval te bevestigen.](#how-to-confirm-an-attack)</span><span class="sxs-lookup"><span data-stu-id="ace8c-133">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="ace8c-134">Een aanval bevestigen</span><span class="sxs-lookup"><span data-stu-id="ace8c-134">How to confirm an attack</span></span>

<span data-ttu-id="ace8c-135">Als u een of meer exemplaren van de IOC's hierboven hebt vermeld, moet u verder onderzoek doen om positief te bevestigen dat de aanval heeft plaatsgevonden.</span><span class="sxs-lookup"><span data-stu-id="ace8c-135">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="ace8c-136">U kunt een van deze drie methoden gebruiken om de aanval te bevestigen:</span><span class="sxs-lookup"><span data-stu-id="ace8c-136">You can use any of these three methods to confirm the attack:</span></span>

- <span data-ttu-id="ace8c-137">Voorraadtoepassingen en hun machtigingen met de Azure Active Directory portal.</span><span class="sxs-lookup"><span data-stu-id="ace8c-137">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="ace8c-138">Deze methode is grondig, maar u kunt slechts één gebruiker tegelijk controleren, wat erg tijdrovend kan zijn als u veel gebruikers hebt om te controleren.</span><span class="sxs-lookup"><span data-stu-id="ace8c-138">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="ace8c-139">Inventaristoepassingen en hun machtigingen met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ace8c-139">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="ace8c-140">Dit is de snelste en meest grondige methode, met de minste hoeveelheid overhead.</span><span class="sxs-lookup"><span data-stu-id="ace8c-140">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="ace8c-141">Laat uw gebruikers afzonderlijk hun apps en machtigingen controleren en de resultaten rapporteren aan de beheerders voor herstel.</span><span class="sxs-lookup"><span data-stu-id="ace8c-141">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="ace8c-142">Inventaris-apps met toegang in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="ace8c-142">Inventory apps with access in your organization</span></span>

<span data-ttu-id="ace8c-143">U kunt dit doen voor uw gebruikers met de Azure Active Directory Portal of PowerShell of uw gebruikers afzonderlijk hun toepassingstoegang laten opsnoemen.</span><span class="sxs-lookup"><span data-stu-id="ace8c-143">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="ace8c-144">Stappen voor het gebruik van Azure Active Directory portal</span><span class="sxs-lookup"><span data-stu-id="ace8c-144">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="ace8c-145">U kunt de toepassingen zoeken waaraan elke afzonderlijke gebruiker machtigingen heeft verleend met behulp van [de Azure Active Directory Portal.](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="ace8c-145">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="ace8c-146">Meld u aan bij de Azure-portal met beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="ace8c-146">Sign in to the Azure portal with administrative rights.</span></span>

2. <span data-ttu-id="ace8c-147">Selecteer het Azure Active Directory blad.</span><span class="sxs-lookup"><span data-stu-id="ace8c-147">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="ace8c-148">Selecteer **Gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="ace8c-148">Select **Users**.</span></span>

4. <span data-ttu-id="ace8c-149">Selecteer de gebruiker die u wilt controleren.</span><span class="sxs-lookup"><span data-stu-id="ace8c-149">Select the user that you want to review.</span></span>

5. <span data-ttu-id="ace8c-150">Selecteer **Toepassingen**.</span><span class="sxs-lookup"><span data-stu-id="ace8c-150">Select **Applications**.</span></span>

<span data-ttu-id="ace8c-151">Hier ziet u de apps die aan de gebruiker zijn toegewezen en welke machtigingen de toepassingen hebben.</span><span class="sxs-lookup"><span data-stu-id="ace8c-151">This will show you the apps that are assigned to the user and what permissions the applications have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="ace8c-152">Stappen voor het opsnoemen van de toepassingstoegang van uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="ace8c-152">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="ace8c-153">Laten uw gebruikers hun https://myapps.microsoft.com eigen toepassingstoegang daar bekijken.</span><span class="sxs-lookup"><span data-stu-id="ace8c-153">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="ace8c-154">Ze moeten alle apps met toegang kunnen zien, details ervan kunnen bekijken (inclusief het bereik van toegang) en bevoegdheden kunnen intrekken voor verdachte of illegale apps.</span><span class="sxs-lookup"><span data-stu-id="ace8c-154">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="ace8c-155">Stappen om dit te doen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="ace8c-155">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="ace8c-156">De eenvoudigste manier om de aanval van de illegale toestemmingsbeurs te [ verifiëren, ](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)is doorGet-AzureADPSPermissions.ps1uit te voeren, waardoor alle OAuth-toestemmingslening en OAuth-apps voor alle gebruikers in uw huurperiode in één .csv bestand worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="ace8c-156">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="ace8c-157">Vereisten</span><span class="sxs-lookup"><span data-stu-id="ace8c-157">Pre-requisites</span></span>

- <span data-ttu-id="ace8c-158">De Azure AD PowerShell-bibliotheek is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="ace8c-158">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="ace8c-159">Globale beheerdersrechten voor de tenant waar het script tegen wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ace8c-159">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="ace8c-160">Lokale beheerder op de computer waaruit de scripts worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ace8c-160">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ace8c-161">We ***raden u ten*** zeerste aan dat u meervoudige verificatie voor uw beheeraccount nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="ace8c-161">We ***highly recommend*** that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="ace8c-162">Dit script ondersteunt MFA-verificatie.</span><span class="sxs-lookup"><span data-stu-id="ace8c-162">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="ace8c-163">Meld u aan bij de computer waaruit u het script wilt uitvoeren met lokale beheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="ace8c-163">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="ace8c-164">Download of kopieer het [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script van GitHub naar een map waaruit u het script gaat uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ace8c-164">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the script.</span></span> <span data-ttu-id="ace8c-165">Dit is dezelfde map waarop het uitvoerbestand 'permissions.csv' wordt geschreven.</span><span class="sxs-lookup"><span data-stu-id="ace8c-165">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="ace8c-166">Open een PowerShell-exemplaar als beheerder en open de map waarin u het script hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="ace8c-166">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="ace8c-167">Verbinding maken naar uw adreslijst met de [Verbinding maken-AzureAD-cmdlet.](/powershell/module/azuread/connect-azuread)</span><span class="sxs-lookup"><span data-stu-id="ace8c-167">Connect to your directory using the [Connect-AzureAD](/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="ace8c-168">Voer deze PowerShell-opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="ace8c-168">Run this PowerShell command:</span></span>

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="ace8c-169">Het script produceert één bestand met de naam Permissions.csv.</span><span class="sxs-lookup"><span data-stu-id="ace8c-169">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="ace8c-170">Volg deze stappen om te zoeken naar onrechtmatige machtigingen voor toepassingen:</span><span class="sxs-lookup"><span data-stu-id="ace8c-170">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="ace8c-171">Zoek in de kolom ConsentType (kolom G) naar de waarde 'AllPrinciples'.</span><span class="sxs-lookup"><span data-stu-id="ace8c-171">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="ace8c-172">Met de machtiging AllPrincipals heeft de clienttoepassing toegang tot de inhoud van iedereen in de huurperiode.</span><span class="sxs-lookup"><span data-stu-id="ace8c-172">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="ace8c-173">Voor Microsoft 365 toepassingen is deze machtiging nodig om correct te kunnen werken.</span><span class="sxs-lookup"><span data-stu-id="ace8c-173">Native Microsoft 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="ace8c-174">Elke niet-Microsoft-toepassing met deze machtiging moet zorgvuldig worden gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="ace8c-174">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="ace8c-175">Controleer in de kolom Machtiging (kolom F) de machtigingen die elke gedelegeerde toepassing heeft voor inhoud.</span><span class="sxs-lookup"><span data-stu-id="ace8c-175">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="ace8c-176">Zoek naar de machtiging 'Lezen' en 'Schrijven' of '\*. Alle" machtigingen en controleer deze zorgvuldig omdat ze mogelijk niet geschikt zijn.</span><span class="sxs-lookup"><span data-stu-id="ace8c-176">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="ace8c-177">Controleer de specifieke gebruikers die toestemming hebben verleend.</span><span class="sxs-lookup"><span data-stu-id="ace8c-177">Review the specific users that have consents granted.</span></span> <span data-ttu-id="ace8c-178">Als gebruikers met een hoog profiel of hoge impact ongepaste toestemmingen hebben verleend, moet u dit nader onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="ace8c-178">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="ace8c-179">Zoek in de kolom ClientDisplayName (kolom C) naar apps die verdacht lijken.</span><span class="sxs-lookup"><span data-stu-id="ace8c-179">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="ace8c-180">Apps met verkeerd gespelde namen, super saaie namen of hacker-klinkende namen moeten zorgvuldig worden gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="ace8c-180">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="ace8c-181">Het bereik van de aanval bepalen</span><span class="sxs-lookup"><span data-stu-id="ace8c-181">Determine the scope of the attack</span></span>

<span data-ttu-id="ace8c-182">Nadat u klaar bent met het inventariseren van toepassingstoegang, bekijkt u het **auditlogboek** om het volledige bereik van de inbreuk te bepalen.</span><span class="sxs-lookup"><span data-stu-id="ace8c-182">After you have finished inventorying application access, review the **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="ace8c-183">Zoek op de getroffen gebruikers, de tijdframes die de illegale toepassing toegang had tot uw organisatie en de machtigingen die de app had.</span><span class="sxs-lookup"><span data-stu-id="ace8c-183">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="ace8c-184">U kunt het **auditlogboek doorzoeken** in de [Microsoft 365 Defender.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="ace8c-184">You can search the **audit log** in the [Microsoft 365 Defender](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ace8c-185">[Postvakcontrole en](../../compliance/enable-mailbox-auditing.md) [Activiteitenaudit voor beheerders](../../compliance/turn-audit-log-search-on-or-off.md) en gebruikers moeten zijn ingeschakeld vóór de aanval, zodat u deze informatie kunt krijgen.</span><span class="sxs-lookup"><span data-stu-id="ace8c-185">[Mailbox auditing](../../compliance/enable-mailbox-auditing.md) and [Activity auditing for admins and users](../../compliance/turn-audit-log-search-on-or-off.md) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="ace8c-186">Een illegale toestemmingsverklaring stoppen en herstellen</span><span class="sxs-lookup"><span data-stu-id="ace8c-186">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="ace8c-187">Nadat u een toepassing met illegale machtigingen hebt geïdentificeerd, kunt u deze toegang op verschillende manieren verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ace8c-187">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="ace8c-188">U kunt de machtiging van de toepassing intrekken in de Azure Active Directory portal door:</span><span class="sxs-lookup"><span data-stu-id="ace8c-188">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="ace8c-189">Ga naar de betreffende gebruiker in het **Azure Active Directory Gebruikersblad.**</span><span class="sxs-lookup"><span data-stu-id="ace8c-189">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="ace8c-190">Selecteer **Toepassingen**.</span><span class="sxs-lookup"><span data-stu-id="ace8c-190">Select **Applications**.</span></span>

  - <span data-ttu-id="ace8c-191">Selecteer de illegale toepassing.</span><span class="sxs-lookup"><span data-stu-id="ace8c-191">Select the illicit application.</span></span>

  - <span data-ttu-id="ace8c-192">Klik **op Verwijderen** in de inzoomen.</span><span class="sxs-lookup"><span data-stu-id="ace8c-192">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="ace8c-193">U kunt de toestemmingslening voor OAuth met PowerShell intrekken door de stappen in [Remove-AzureADOAuth2PermissionGrant te volgen.](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)</span><span class="sxs-lookup"><span data-stu-id="ace8c-193">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="ace8c-194">U kunt de functietoewijzing voor service-apps intrekken met PowerShell door de stappen in [Remove-AzureADServiceAppRoleAssignment te volgen.](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)</span><span class="sxs-lookup"><span data-stu-id="ace8c-194">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="ace8c-195">U kunt de aanmelding voor het betreffende account ook helemaal uitschakelen, waardoor de toegang van apps tot gegevens in dat account wordt uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ace8c-195">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="ace8c-196">Dit is natuurlijk niet ideaal voor de productiviteit van de eindgebruiker, maar als u de impact snel wilt beperken, kan dit een goede oplossing zijn voor de korte termijn.</span><span class="sxs-lookup"><span data-stu-id="ace8c-196">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="ace8c-197">U kunt geïntegreerde toepassingen uitschakelen voor uw huurperiode.</span><span class="sxs-lookup"><span data-stu-id="ace8c-197">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="ace8c-198">Dit is een drastische stap die eindgebruikers de mogelijkheid uitwijst om toestemming te verlenen op tenantbasis.</span><span class="sxs-lookup"><span data-stu-id="ace8c-198">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="ace8c-199">Hiermee voorkomt u dat uw gebruikers per ongeluk toegang verlenen tot een schadelijke toepassing.</span><span class="sxs-lookup"><span data-stu-id="ace8c-199">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="ace8c-200">Dit wordt niet sterk aanbevolen, omdat het de mogelijkheid van uw gebruikers om productief te zijn met toepassingen van derden ernstig schaadt.</span><span class="sxs-lookup"><span data-stu-id="ace8c-200">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="ace8c-201">U kunt dit doen door de stappen te volgen in [Geïntegreerde apps in- of uitschakelen.](../../admin/misc/user-consent.md)</span><span class="sxs-lookup"><span data-stu-id="ace8c-201">You can do this by following the steps in [Turning Integrated Apps on or off](../../admin/misc/user-consent.md).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="ace8c-202">Microsoft 365 beveiligen als een cybersecurity pro</span><span class="sxs-lookup"><span data-stu-id="ace8c-202">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="ace8c-203">Uw Microsoft 365-abonnement heeft een krachtige reeks aan beveiligingsmogelijkheden die u kunt gebruiken om uw gegevens en gebruikers te beschermen.</span><span class="sxs-lookup"><span data-stu-id="ace8c-203">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="ace8c-204">Gebruik de [Microsoft 365-roadmap voor beveiliging - Topprioriteiten voor de eerste 30 dagen, 90 dagen en verder](security-roadmap.md) om door Microsoft aanbevolen procedures voor het beveiligen van uw Microsoft 365-tenant te implementeren.</span><span class="sxs-lookup"><span data-stu-id="ace8c-204">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="ace8c-205">Taken die in de eerste 30 dagen moeten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ace8c-205">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="ace8c-206">Deze hebben direct effect en weinig invloed op uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ace8c-206">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="ace8c-207">Taken die binnen 90 dagen moeten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ace8c-207">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="ace8c-208">Deze nemen qua planning en implementatie iets meer tijd in beslag, maar zorgen voor aanzienlijke verbeteringen in uw beveiligingspostuur.</span><span class="sxs-lookup"><span data-stu-id="ace8c-208">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="ace8c-209">Na 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="ace8c-209">Beyond 90 days.</span></span> <span data-ttu-id="ace8c-210">Deze verbeteringen zijn gebaseerd op de eerste 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="ace8c-210">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="ace8c-211">Zie ook:</span><span class="sxs-lookup"><span data-stu-id="ace8c-211">See also:</span></span>

- <span data-ttu-id="ace8c-212">[Onverwachte toepassing in mijn lijst met toepassingen](/azure/active-directory/application-access-unexpected-application) laat beheerders verschillende acties zien die ze mogelijk willen uitvoeren nadat ze zich realiseren dat er onverwachte toepassingen zijn met toegang tot gegevens.</span><span class="sxs-lookup"><span data-stu-id="ace8c-212">[Unexpected application in my applications list](/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="ace8c-213">[Het integreren van toepassingen Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) is een overzicht op hoog niveau van toestemming en machtigingen.</span><span class="sxs-lookup"><span data-stu-id="ace8c-213">[Integrating applications with Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="ace8c-214">[Problemen met het ontwikkelen van mijn toepassing](/azure/active-directory/active-directory-application-dev-development-content-map) bevat koppelingen naar verschillende artikelen met betrekking tot toestemming.</span><span class="sxs-lookup"><span data-stu-id="ace8c-214">[Problems developing my application](/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="ace8c-215">[Toepassings- en serviceprincipaalobjecten in Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) bieden een overzicht van de hoofdobjecten Toepassing en Service die de kern van het toepassingsmodel zijn.</span><span class="sxs-lookup"><span data-stu-id="ace8c-215">[Application and service principal objects in Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="ace8c-216">[Toegang tot apps beheren](/azure/active-directory/active-directory-managing-access-to-apps) is een overzicht van de mogelijkheden die beheerders hebben om gebruikerstoegang tot apps te beheren.</span><span class="sxs-lookup"><span data-stu-id="ace8c-216">[Manage access to apps](/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
