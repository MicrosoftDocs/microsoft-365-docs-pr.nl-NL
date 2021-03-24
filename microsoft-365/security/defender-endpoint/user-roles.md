---
title: Rollen maken en beheren voor toegangsbeheer op basis van rollen
description: Rollen maken en de machtigingen definiëren die aan de rol zijn toegewezen als onderdeel van de implementatie van toegangsbeheer op basis van rollen in het Microsoft Defender-beveiligingscentrum
keywords: gebruikersrollen, rollen, toegangs-rbac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059237"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a><span data-ttu-id="93e92-104">Rollen maken en beheren voor toegangsbeheer op basis van rollen</span><span class="sxs-lookup"><span data-stu-id="93e92-104">Create and manage roles for role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="93e92-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="93e92-105">**Applies to:**</span></span>
- [<span data-ttu-id="93e92-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="93e92-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="93e92-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93e92-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="93e92-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="93e92-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="93e92-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="93e92-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a><span data-ttu-id="93e92-110">Rollen maken en de rol toewijzen aan een Azure Active Directory-groep</span><span class="sxs-lookup"><span data-stu-id="93e92-110">Create roles and assign the role to an Azure Active Directory group</span></span>

<span data-ttu-id="93e92-111">In de volgende stappen vindt u informatie over het maken van rollen in het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="93e92-111">The following steps guide you on how to create roles in Microsoft Defender Security Center.</span></span> <span data-ttu-id="93e92-112">Er wordt ervan uitgenomen dat u al Azure Active Directory-gebruikersgroepen hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="93e92-112">It assumes that you have already created Azure Active Directory user groups.</span></span>

1. <span data-ttu-id="93e92-113">Meld u aan [bij het Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com/) met behulp van een account met een beveiligingsbeheerder of globale beheerdersrol toegewezen.</span><span class="sxs-lookup"><span data-stu-id="93e92-113">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with a Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="93e92-114">Selecteer in het navigatiedeelvenster **Instellingen > Rollen.**</span><span class="sxs-lookup"><span data-stu-id="93e92-114">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="93e92-115">Selecteer **Item toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="93e92-115">Select **Add item**.</span></span>

4. <span data-ttu-id="93e92-116">Voer de rolnaam, beschrijving en machtigingen in die u wilt toewijzen aan de rol.</span><span class="sxs-lookup"><span data-stu-id="93e92-116">Enter the role name, description, and permissions you'd like to assign to the role.</span></span>

5. <span data-ttu-id="93e92-117">Selecteer **Volgende** om de rol toe te wijzen aan een Azure AD-beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="93e92-117">Select **Next** to assign the role to an Azure AD Security group.</span></span>

6. <span data-ttu-id="93e92-118">Gebruik het filter om de Azure AD-groep te selecteren die u wilt toevoegen aan deze rol.</span><span class="sxs-lookup"><span data-stu-id="93e92-118">Use the filter to select the Azure AD group that you'd like to add to this role to.</span></span>

7. <span data-ttu-id="93e92-119">**Opslaan en sluiten.**</span><span class="sxs-lookup"><span data-stu-id="93e92-119">**Save and close**.</span></span>

8. <span data-ttu-id="93e92-120">Pas de configuratie-instellingen toe.</span><span class="sxs-lookup"><span data-stu-id="93e92-120">Apply the configuration settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93e92-121">Nadat u rollen hebt gemaakt, moet u een apparaatgroep maken en toegang geven tot de apparaatgroep door deze toe te wijzen aan een rol die u zojuist hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="93e92-121">After creating roles, you'll need to create a device group and provide access to the device group by assigning it to a role that you just created.</span></span>

### <a name="permission-options"></a><span data-ttu-id="93e92-122">Machtigingsopties</span><span class="sxs-lookup"><span data-stu-id="93e92-122">Permission options</span></span>

- <span data-ttu-id="93e92-123">**Gegevens weergeven**</span><span class="sxs-lookup"><span data-stu-id="93e92-123">**View data**</span></span>
    - <span data-ttu-id="93e92-124">**Beveiligingsbewerkingen:** alle gegevens over beveiligingsbewerkingen weergeven in de portal</span><span class="sxs-lookup"><span data-stu-id="93e92-124">**Security operations** - View all security operations data in the portal</span></span>
    - <span data-ttu-id="93e92-125">**Bedreigings- en kwetsbaarheidsbeheer** : gegevens over bedreigings- en kwetsbaarheidsbeheer weergeven in de portal</span><span class="sxs-lookup"><span data-stu-id="93e92-125">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

- <span data-ttu-id="93e92-126">**Actieve herstelacties**</span><span class="sxs-lookup"><span data-stu-id="93e92-126">**Active remediation actions**</span></span>
    - <span data-ttu-id="93e92-127">**Beveiligingsbewerkingen:** actie ondernemen, in behandeling zijnde herstelacties goedkeuren of afwijzen, toegestane/geblokkeerde lijsten voor automatisering en indicatoren beheren</span><span class="sxs-lookup"><span data-stu-id="93e92-127">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
    - <span data-ttu-id="93e92-128">**Bedreigings- en kwetsbaarheidsbeheer - Afhandeling van uitzonderingen** - Nieuwe uitzonderingen maken en actieve uitzonderingen beheren</span><span class="sxs-lookup"><span data-stu-id="93e92-128">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
    - <span data-ttu-id="93e92-129">**Bedreigings- en kwetsbaarheidsbeheer - Herstelafhandeling** - Nieuwe herstelaanvragen indienen, tickets maken en bestaande herstelactiviteiten beheren</span><span class="sxs-lookup"><span data-stu-id="93e92-129">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

- <span data-ttu-id="93e92-130">**Onderzoek naar waarschuwingen:** waarschuwingen beheren, geautomatiseerde onderzoeken starten, scans uitvoeren, onderzoekspakketten verzamelen, apparaatlabels beheren en alleen draagbare uitvoerbare (PE)-bestanden downloaden</span><span class="sxs-lookup"><span data-stu-id="93e92-130">**Alerts investigation** - Manage alerts, initiate automated investigations, run scans, collect investigation packages, manage device tags, and download only portable executable (PE) files</span></span> 

- <span data-ttu-id="93e92-131">**Portalsysteeminstellingen** beheren : Opslaginstellingen, SIEM- en bedreigingsinstellingen voor Intel API configureren (is globaal van toepassing), geavanceerde instellingen, geautomatiseerde bestands uploads, rollen en apparaatgroepen</span><span class="sxs-lookup"><span data-stu-id="93e92-131">**Manage portal system settings** - Configure storage settings, SIEM and threat intel API settings (applies globally), advanced settings, automated file uploads, roles and device groups</span></span>

    > [!NOTE]
    > <span data-ttu-id="93e92-132">Deze instelling is alleen beschikbaar in de microsoft defender voor eindpuntbeheerder (standaardrol).</span><span class="sxs-lookup"><span data-stu-id="93e92-132">This setting is only available in the Microsoft Defender for Endpoint administrator (default) role.</span></span>

- <span data-ttu-id="93e92-133">**Beveiligingsinstellingen beheren in** het Beveiligingscentrum: instellingen voor het onderdrukken van waarschuwingen configureren, mapuitsluitingen voor automatisering, onboard en offboard-apparaten beheren en e-mailmeldingen beheren, evaluatielab beheren</span><span class="sxs-lookup"><span data-stu-id="93e92-133">**Manage security settings in Security Center** - Configure alert suppression settings, manage folder exclusions for automation, onboard and offboard devices, and manage email notifications, manage evaluation lab</span></span>

- <span data-ttu-id="93e92-134">**Mogelijkheden voor live-antwoorden**</span><span class="sxs-lookup"><span data-stu-id="93e92-134">**Live response capabilities**</span></span>
    - <span data-ttu-id="93e92-135">**Basisopdrachten:**</span><span class="sxs-lookup"><span data-stu-id="93e92-135">**Basic** commands:</span></span>
        - <span data-ttu-id="93e92-136">Een livereactiesessie starten</span><span class="sxs-lookup"><span data-stu-id="93e92-136">Start a live response session</span></span>
        - <span data-ttu-id="93e92-137">Alleen-lezen live-antwoordopdrachten uitvoeren op een extern apparaat (met uitzondering van bestandsexemplaar en uitvoering</span><span class="sxs-lookup"><span data-stu-id="93e92-137">Perform read only live response commands on remote device (excluding file copy and execution</span></span>
    - <span data-ttu-id="93e92-138">**Geavanceerde** opdrachten:</span><span class="sxs-lookup"><span data-stu-id="93e92-138">**Advanced** commands:</span></span>
        - <span data-ttu-id="93e92-139">Een bestand downloaden van het externe apparaat via livereactie</span><span class="sxs-lookup"><span data-stu-id="93e92-139">Download a file from the remote device via live response</span></span>
        - <span data-ttu-id="93e92-140">PE- en niet-PE-bestanden downloaden van de bestandspagina</span><span class="sxs-lookup"><span data-stu-id="93e92-140">Download PE and non-PE files from the file page</span></span>
        - <span data-ttu-id="93e92-141">Een bestand uploaden naar het externe apparaat</span><span class="sxs-lookup"><span data-stu-id="93e92-141">Upload a file to the remote device</span></span>
        - <span data-ttu-id="93e92-142">Een script weergeven vanuit de bestandenbibliotheek</span><span class="sxs-lookup"><span data-stu-id="93e92-142">View a script from the files library</span></span>
        - <span data-ttu-id="93e92-143">Een script uitvoeren op het externe apparaat vanuit de bestandenbibliotheek</span><span class="sxs-lookup"><span data-stu-id="93e92-143">Execute a script on the remote device from the files library</span></span>

<span data-ttu-id="93e92-144">Zie Apparaten onderzoeken met livereactie voor meer informatie over de beschikbare [opdrachten.](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="93e92-144">For more information on the available commands, see [Investigate devices using Live response](live-response.md).</span></span>
  
## <a name="edit-roles"></a><span data-ttu-id="93e92-145">Rollen bewerken</span><span class="sxs-lookup"><span data-stu-id="93e92-145">Edit roles</span></span>

1. <span data-ttu-id="93e92-146">Meld u aan [bij het Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com/) met een account aan beveiligingsbeheerder of globale beheerdersrol toegewezen.</span><span class="sxs-lookup"><span data-stu-id="93e92-146">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="93e92-147">Selecteer in het navigatiedeelvenster **Instellingen > Rollen.**</span><span class="sxs-lookup"><span data-stu-id="93e92-147">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="93e92-148">Selecteer de rol die u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="93e92-148">Select the role you'd like to edit.</span></span>

4. <span data-ttu-id="93e92-149">Klik op **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="93e92-149">Click **Edit**.</span></span>

5. <span data-ttu-id="93e92-150">Wijzig de details of de groepen die aan de rol zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="93e92-150">Modify the details or the groups that are assigned to the role.</span></span> 

6. <span data-ttu-id="93e92-151">Klik **op Opslaan en sluiten.**</span><span class="sxs-lookup"><span data-stu-id="93e92-151">Click **Save and close**.</span></span>

## <a name="delete-roles"></a><span data-ttu-id="93e92-152">Rollen verwijderen</span><span class="sxs-lookup"><span data-stu-id="93e92-152">Delete roles</span></span>

1. <span data-ttu-id="93e92-153">Meld u aan [bij het Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com/) met een account aan beveiligingsbeheerder of globale beheerdersrol toegewezen.</span><span class="sxs-lookup"><span data-stu-id="93e92-153">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="93e92-154">Selecteer in het navigatiedeelvenster **Instellingen > Rollen.**</span><span class="sxs-lookup"><span data-stu-id="93e92-154">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="93e92-155">Selecteer de rol die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="93e92-155">Select the role you'd like to delete.</span></span>

4. <span data-ttu-id="93e92-156">Klik op de vervolgkeuzeknop en selecteer **Rol verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="93e92-156">Click the drop-down button and select **Delete role**.</span></span>

## <a name="related-topic"></a><span data-ttu-id="93e92-157">Gerelateerd onderwerp</span><span class="sxs-lookup"><span data-stu-id="93e92-157">Related topic</span></span>

- [<span data-ttu-id="93e92-158">Basismachtigingen voor gebruikers voor toegang tot de portal</span><span class="sxs-lookup"><span data-stu-id="93e92-158">User basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="93e92-159">Apparaatgroepen maken en beheren</span><span class="sxs-lookup"><span data-stu-id="93e92-159">Create and manage device groups</span></span>](machine-groups.md)
