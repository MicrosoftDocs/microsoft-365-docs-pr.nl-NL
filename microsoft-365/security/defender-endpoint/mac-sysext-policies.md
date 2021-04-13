---
title: Nieuwe configuratieprofielen voor macOS Catalina en nieuwere versies van macOS
description: In dit onderwerp worden de wijzigingen beschreven die moeten worden aangebracht om te profiteren van de systeemextensies, die een vervanging zijn voor kernelextensies op macOS Catalina en nieuwere versies van macOS.
keywords: microsoft, defender, atp, mac, kernel, systeem, extensies, catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: db24bea3bddc682eceda8e6ea3fe2749b6b2778f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689123"
---
# <a name="new-configuration-profiles-for-macos-catalina-and-newer-versions-of-macos"></a><span data-ttu-id="bef7c-104">Nieuwe configuratieprofielen voor macOS Catalina en nieuwere versies van macOS</span><span class="sxs-lookup"><span data-stu-id="bef7c-104">New configuration profiles for macOS Catalina and newer versions of macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bef7c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bef7c-105">**Applies to:**</span></span>
- [<span data-ttu-id="bef7c-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="bef7c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bef7c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bef7c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bef7c-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="bef7c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bef7c-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="bef7c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="bef7c-110">In overeenstemming met de ontwikkeling van macOS bereiden we een Microsoft Defender voor Eindpunt voor macOS-update voor waarin systeemextensies worden gebruikt in plaats van kernelextensies.</span><span class="sxs-lookup"><span data-stu-id="bef7c-110">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint on macOS update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="bef7c-111">Deze update is alleen van toepassing op macOS Catalina (10.15.4) en nieuwere versies van macOS.</span><span class="sxs-lookup"><span data-stu-id="bef7c-111">This update will only be applicable to macOS Catalina (10.15.4) and newer versions of macOS.</span></span>

<span data-ttu-id="bef7c-112">Als u Microsoft Defender voor Eindpunt hebt geïmplementeerd op macOS in een beheerde omgeving (via JAMF, Intune of een andere MDM-oplossing), moet u nieuwe configuratieprofielen implementeren.</span><span class="sxs-lookup"><span data-stu-id="bef7c-112">If you have deployed Microsoft Defender for Endpoint on macOS in a managed environment (through JAMF, Intune, or another MDM solution), you must deploy new configuration profiles.</span></span> <span data-ttu-id="bef7c-113">Als u deze stappen niet doet, krijgen gebruikers goedkeuringsprompts om deze nieuwe onderdelen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="bef7c-113">Failure to do these steps will result in users getting approval prompts to run these new components.</span></span>

## <a name="jamf"></a><span data-ttu-id="bef7c-114">JAMF</span><span class="sxs-lookup"><span data-stu-id="bef7c-114">JAMF</span></span>

### <a name="system-extensions-policy"></a><span data-ttu-id="bef7c-115">Systeemextensiesbeleid</span><span class="sxs-lookup"><span data-stu-id="bef7c-115">System Extensions Policy</span></span>

<span data-ttu-id="bef7c-116">Als u de systeemextensies wilt goedkeuren, maakt u de volgende payload:</span><span class="sxs-lookup"><span data-stu-id="bef7c-116">To approve the system extensions, create the following payload:</span></span>

1. <span data-ttu-id="bef7c-117">In **Computers > configuratieprofielen selecteert** **u Opties > Systeemextensies.**</span><span class="sxs-lookup"><span data-stu-id="bef7c-117">In **Computers > Configuration Profiles** select **Options > System Extensions**.</span></span>
2. <span data-ttu-id="bef7c-118">Selecteer **Toegestane systeemextensies** in de vervolgkeuzelijst Systeemextensietypen. </span><span class="sxs-lookup"><span data-stu-id="bef7c-118">Select **Allowed System Extensions** from the **System Extension Types** drop-down list.</span></span>
3. <span data-ttu-id="bef7c-119">Gebruik **UBF8T346G9** voor Team-id.</span><span class="sxs-lookup"><span data-stu-id="bef7c-119">Use **UBF8T346G9** for Team Id.</span></span>
4. <span data-ttu-id="bef7c-120">Voeg de volgende bundelaanduidingen toe aan de **lijst Toegestane systeemextensies:**</span><span class="sxs-lookup"><span data-stu-id="bef7c-120">Add the following bundle identifiers to the **Allowed System Extensions** list:</span></span>

    - <span data-ttu-id="bef7c-121">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="bef7c-121">**com.microsoft.wdav.epsext**</span></span>
    - <span data-ttu-id="bef7c-122">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="bef7c-122">**com.microsoft.wdav.netext**</span></span>

    ![Schermafbeelding van goedgekeurde systeemextensies](images/mac-approved-system-extensions.png)

### <a name="privacy-preferences-policy-control"></a><span data-ttu-id="bef7c-124">Beleidsbesturingselement privacyvoorkeuren</span><span class="sxs-lookup"><span data-stu-id="bef7c-124">Privacy Preferences Policy Control</span></span>

<span data-ttu-id="bef7c-125">Voeg de volgende JAMF-payload toe om Volledige schijftoegang toe te staan aan de Microsoft Defender for Endpoint Endpoint Security Extension.</span><span class="sxs-lookup"><span data-stu-id="bef7c-125">Add the following JAMF payload to grant Full Disk Access to the Microsoft Defender for Endpoint Endpoint Security Extension.</span></span> <span data-ttu-id="bef7c-126">Dit beleid is een vereiste voor het uitvoeren van de extensie op uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="bef7c-126">This policy is a pre-requisite for running the extension on your device.</span></span>

1. <span data-ttu-id="bef7c-127">Selecteer **Opties**  >  **Privacyvoorkeuren Beleidsbesturingselement**.</span><span class="sxs-lookup"><span data-stu-id="bef7c-127">Select **Options** > **Privacy Preferences Policy Control**.</span></span>
2. <span data-ttu-id="bef7c-128">Gebruik `com.microsoft.wdav.epsext` dit als id **en** `Bundle ID` als **bundeltype.**</span><span class="sxs-lookup"><span data-stu-id="bef7c-128">Use `com.microsoft.wdav.epsext` as the **Identifier** and `Bundle ID` as **Bundle type**.</span></span>
3. <span data-ttu-id="bef7c-129">Codevereiste instellen op `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="bef7c-129">Set Code Requirement to `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
4. <span data-ttu-id="bef7c-130">App **of service instellen** op **SystemPolicyAllFiles en** toegang tot **Toestaan.**</span><span class="sxs-lookup"><span data-stu-id="bef7c-130">Set **App or service** to **SystemPolicyAllFiles** and access to **Allow**.</span></span>

    ![Beleidsbesturingselement privacyvoorkeuren](images/mac-system-extension-privacy.png)

### <a name="network-extension-policy"></a><span data-ttu-id="bef7c-132">Netwerkextensiebeleid</span><span class="sxs-lookup"><span data-stu-id="bef7c-132">Network Extension Policy</span></span>

<span data-ttu-id="bef7c-133">Als onderdeel van de mogelijkheden voor endpointdetectie en -antwoorden controleert Microsoft Defender voor Eindpunt op macOS het socketverkeer en rapporteert deze informatie aan de microsoft Defender-beveiligingscentrumportal.</span><span class="sxs-lookup"><span data-stu-id="bef7c-133">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="bef7c-134">Met het volgende beleid kan de netwerkextensie deze functionaliteit uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="bef7c-134">The following policy allows the network extension to perform this functionality.</span></span>

>[!NOTE]
><span data-ttu-id="bef7c-135">JAMF heeft geen ingebouwde ondersteuning voor inhoudsfilterbeleid, wat een vereiste is voor het inschakelen van de netwerkextensies die Microsoft Defender voor Eindpunt op macOS op het apparaat installeert.</span><span class="sxs-lookup"><span data-stu-id="bef7c-135">JAMF doesn’t have built-in support for content filtering policies, which are a pre-requisite for enabling the network extensions that Microsoft Defender for Endpoint on macOS installs on the device.</span></span> <span data-ttu-id="bef7c-136">Bovendien verandert JAMF soms de inhoud van het beleid dat wordt geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="bef7c-136">Furthermore, JAMF sometimes changes the content of the policies being deployed.</span></span>
><span data-ttu-id="bef7c-137">Als zodanig bieden de volgende stappen een tijdelijke oplossing voor het ondertekenen van het configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="bef7c-137">As such, the following steps provide a workaround that involve signing the configuration profile.</span></span>

1. <span data-ttu-id="bef7c-138">Sla de volgende inhoud op uw apparaat op als `com.microsoft.network-extension.mobileconfig` een teksteditor:</span><span class="sxs-lookup"><span data-stu-id="bef7c-138">Save the following content to your device as `com.microsoft.network-extension.mobileconfig` using a text editor:</span></span>

    ```xml
    <?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1">
        <dict>
            <key>PayloadUUID</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadType</key>
            <string>Configuration</string>
            <key>PayloadOrganization</key>
            <string>Microsoft Corporation</string>
            <key>PayloadIdentifier</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft Defender ATP Network Extension</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>PayloadRemovalDisallowed</key>
            <true/>
            <key>PayloadScope</key>
            <string>System</string>
            <key>PayloadContent</key>
            <array>
                <dict>
                    <key>PayloadUUID</key>
                    <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                    <key>PayloadType</key>
                    <string>com.apple.webcontent-filter</string>
                    <key>PayloadOrganization</key>
                    <string>Microsoft Corporation</string>
                    <key>PayloadIdentifier</key>
                    <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                    <key>PayloadDisplayName</key>
                    <string>Approved Network Extension</string>
                    <key>PayloadDescription</key>
                    <string/>
                    <key>PayloadVersion</key>
                    <integer>1</integer>
                    <key>PayloadEnabled</key>
                    <true/>
                    <key>FilterType</key>
                    <string>Plugin</string>
                    <key>UserDefinedName</key>
                    <string>Microsoft Defender ATP Network Extension</string>
                    <key>PluginBundleID</key>
                    <string>com.microsoft.wdav</string>
                    <key>FilterSockets</key>
                    <true/>
                    <key>FilterDataProviderBundleIdentifier</key>
                    <string>com.microsoft.wdav.netext</string>
                    <key>FilterDataProviderDesignatedRequirement</key>
                    <string>identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                </dict>
            </array>
        </dict>
    </plist>
    ```

2. <span data-ttu-id="bef7c-139">Controleer of het bovenstaande bestand correct is gekopieerd door het hulpprogramma in de `plutil` Terminal uit te werken:</span><span class="sxs-lookup"><span data-stu-id="bef7c-139">Verify that the above file was copied correctly by running the `plutil` utility in the Terminal:</span></span>

    ```bash
    $ plutil -lint <PathToFile>/com.microsoft.network-extension.mobileconfig
    ```

    <span data-ttu-id="bef7c-140">Als het bestand bijvoorbeeld is opgeslagen in Documenten:</span><span class="sxs-lookup"><span data-stu-id="bef7c-140">For example, if the file was stored in Documents:</span></span>

    ```bash
    $ plutil -lint ~/Documents/com.microsoft.network-extension.mobileconfig
    ```
    
    <span data-ttu-id="bef7c-141">Controleer of de opdracht wordt `OK` uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="bef7c-141">Verify that the command outputs `OK`.</span></span>
        
    ```bash
    <PathToFile>/com.microsoft.network-extension.mobileconfig: OK
    ```
    
3. <span data-ttu-id="bef7c-142">Volg de instructies op [deze pagina om](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) een handtekeningcertificaat te maken met de ingebouwde certificeringsinstantie van JAMF.</span><span class="sxs-lookup"><span data-stu-id="bef7c-142">Follow the instructions on [this page](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) to create a signing certificate using JAMF’s built-in certificate authority.</span></span>

4. <span data-ttu-id="bef7c-143">Nadat het certificaat is gemaakt en geïnstalleerd op uw apparaat, voer u de volgende opdracht uit vanaf de terminal om het bestand te ondertekenen:</span><span class="sxs-lookup"><span data-stu-id="bef7c-143">After the certificate is created and installed to your device, run the following command from the Terminal to sign the file:</span></span>

    ```bash
    $ security cms -S -N "<CertificateName>" -i <PathToFile>/com.microsoft.network-extension.mobileconfig -o <PathToSignedFile>/com.microsoft.network-extension.signed.mobileconfig
    ```
    
    <span data-ttu-id="bef7c-144">Als de certificaatnaam bijvoorbeeld **SignCertificate** is en het ondertekende bestand wordt opgeslagen in Documenten:</span><span class="sxs-lookup"><span data-stu-id="bef7c-144">For example, if the certificate name is **SigningCertificate** and the signed file is going to be stored in Documents:</span></span>
    
    ```bash
    $ security cms -S -N "SigningCertificate" -i ~/Documents/com.microsoft.network-extension.mobileconfig -o ~/Documents/com.microsoft.network-extension.signed.mobileconfig
    ```
    
5. <span data-ttu-id="bef7c-145">Ga vanuit de JAMF-portal naar **Configuratieprofielen** en klik op de **knop** Uploaden.</span><span class="sxs-lookup"><span data-stu-id="bef7c-145">From the JAMF portal, navigate to **Configuration Profiles** and click the **Upload** button.</span></span> <span data-ttu-id="bef7c-146">Selecteer `com.microsoft.network-extension.signed.mobileconfig` wanneer u om het bestand wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="bef7c-146">Select `com.microsoft.network-extension.signed.mobileconfig` when prompted for the file.</span></span>

## <a name="intune"></a><span data-ttu-id="bef7c-147">Intune</span><span class="sxs-lookup"><span data-stu-id="bef7c-147">Intune</span></span>

### <a name="system-extensions-policy"></a><span data-ttu-id="bef7c-148">Systeemextensiesbeleid</span><span class="sxs-lookup"><span data-stu-id="bef7c-148">System Extensions Policy</span></span>

<span data-ttu-id="bef7c-149">De systeemextensies goedkeuren:</span><span class="sxs-lookup"><span data-stu-id="bef7c-149">To approve the system extensions:</span></span>

1. <span data-ttu-id="bef7c-150">Open in Intune   >  **Apparaatconfiguratie beheren.**</span><span class="sxs-lookup"><span data-stu-id="bef7c-150">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="bef7c-151">Selecteer **Profielen beheren**  >  **Profiel**  >  **maken.**</span><span class="sxs-lookup"><span data-stu-id="bef7c-151">Select **Manage** > **Profiles** > **Create Profile**.</span></span>
2. <span data-ttu-id="bef7c-152">Kies een naam voor het profiel.</span><span class="sxs-lookup"><span data-stu-id="bef7c-152">Choose a name for the profile.</span></span> <span data-ttu-id="bef7c-153">**Platform=macOS wijzigen** in **Profieltype=Extensies**.</span><span class="sxs-lookup"><span data-stu-id="bef7c-153">Change **Platform=macOS** to **Profile type=Extensions**.</span></span> <span data-ttu-id="bef7c-154">Selecteer **Maken**. </span><span class="sxs-lookup"><span data-stu-id="bef7c-154">Select **Create**.</span></span>
3. <span data-ttu-id="bef7c-155">Geef op `Basics` het tabblad een naam aan dit nieuwe profiel.</span><span class="sxs-lookup"><span data-stu-id="bef7c-155">In the `Basics` tab, give a name to this new profile.</span></span>
4. <span data-ttu-id="bef7c-156">Voeg op `Configuration settings` het tabblad de volgende vermeldingen toe in de `Allowed system extensions` sectie:</span><span class="sxs-lookup"><span data-stu-id="bef7c-156">In the `Configuration settings` tab, add the following entries in the `Allowed system extensions` section:</span></span>

    <span data-ttu-id="bef7c-157">Bundelaanduiding</span><span class="sxs-lookup"><span data-stu-id="bef7c-157">Bundle identifier</span></span>         | <span data-ttu-id="bef7c-158">Team-id</span><span class="sxs-lookup"><span data-stu-id="bef7c-158">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="bef7c-159">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="bef7c-159">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="bef7c-160">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="bef7c-160">UBF8T346G9</span></span>
    <span data-ttu-id="bef7c-161">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="bef7c-161">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="bef7c-162">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="bef7c-162">UBF8T346G9</span></span>

    ![Schermafbeelding van systeemconfiguratieprofielen](images/mac-system-extension-intune2.png)

5. <span data-ttu-id="bef7c-164">Wijs dit profiel op het tabblad toe `Assignments` aan alle gebruikers & alle **apparaten.**</span><span class="sxs-lookup"><span data-stu-id="bef7c-164">In the `Assignments` tab, assign this profile to **All Users & All devices**.</span></span>
6. <span data-ttu-id="bef7c-165">Controleer en maak dit configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="bef7c-165">Review and create this configuration profile.</span></span>

### <a name="create-and-deploy-the-custom-configuration-profile"></a><span data-ttu-id="bef7c-166">Het aangepaste configuratieprofiel maken en implementeren</span><span class="sxs-lookup"><span data-stu-id="bef7c-166">Create and deploy the Custom Configuration Profile</span></span>

<span data-ttu-id="bef7c-167">Het volgende configuratieprofiel maakt de netwerkextensie mogelijk en verleent volledige schijftoegang aan de systeemextensie Endpoint Security.</span><span class="sxs-lookup"><span data-stu-id="bef7c-167">The following configuration profile enables the network extension and grants Full Disk Access to the Endpoint Security system extension.</span></span> 

<span data-ttu-id="bef7c-168">Sla de volgende inhoud op in een bestand met **desysext.xml:**</span><span class="sxs-lookup"><span data-stu-id="bef7c-168">Save the following content to a file named **sysext.xml**:</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft Corporation</string>
        <key>PayloadIdentifier</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender ATP System Extensions</string>
        <key>PayloadDescription</key>
        <string/>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                <key>PayloadType</key>
                <string>com.apple.webcontent-filter</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                <key>PayloadDisplayName</key>
                <string>Approved Network Extension</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>FilterType</key>
                <string>Plugin</string>
                <key>UserDefinedName</key>
                <string>Microsoft Defender ATP Network Extension</string>
                <key>PluginBundleID</key>
                <string>com.microsoft.wdav</string>
                <key>FilterSockets</key>
                <true/>
                <key>FilterDataProviderBundleIdentifier</key>
                <string>com.microsoft.wdav.netext</string>
                <key>FilterDataProviderDesignatedRequirement</key>
                <string>identifier &quot;com.microsoft.wdav.netext&quot; and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
            </dict>
            <dict>
                <key>PayloadUUID</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadType</key>
                <string>com.apple.TCC.configuration-profile-policy</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadDisplayName</key>
                <string>Privacy Preferences Policy Control</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>Services</key>
                <dict>
                    <key>SystemPolicyAllFiles</key>
                    <array>
                        <dict>
                            <key>Identifier</key>
                            <string>com.microsoft.wdav.epsext</string>
                            <key>CodeRequirement</key>
                            <string>identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                            <key>IdentifierType</key>
                            <string>bundleID</string>
                            <key>StaticCode</key>
                            <integer>0</integer>
                            <key>Allowed</key>
                            <integer>1</integer>
                        </dict>
                    </array>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="bef7c-169">Controleer of het bovenstaande bestand correct is gekopieerd.</span><span class="sxs-lookup"><span data-stu-id="bef7c-169">Verify that the above file was copied correctly.</span></span> <span data-ttu-id="bef7c-170">Voer vanuit de Terminal de volgende opdracht uit en controleer of deze wordt `OK` uitgevoerd:</span><span class="sxs-lookup"><span data-stu-id="bef7c-170">From the Terminal, run the following command and verify that it outputs `OK`:</span></span>

```bash
$ plutil -lint sysext.xml
sysext.xml: OK
```

<span data-ttu-id="bef7c-171">Dit aangepaste configuratieprofiel implementeren:</span><span class="sxs-lookup"><span data-stu-id="bef7c-171">To deploy this custom configuration profile:</span></span>

1.  <span data-ttu-id="bef7c-172">Open in Intune   >  **Apparaatconfiguratie beheren.**</span><span class="sxs-lookup"><span data-stu-id="bef7c-172">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="bef7c-173">Selecteer **Profielen beheren**  >  **Profiel**  >  **maken.**</span><span class="sxs-lookup"><span data-stu-id="bef7c-173">Select **Manage** > **Profiles** > **Create profile**.</span></span>
2. <span data-ttu-id="bef7c-174">Kies een naam voor het profiel.</span><span class="sxs-lookup"><span data-stu-id="bef7c-174">Choose a name for the profile.</span></span> <span data-ttu-id="bef7c-175">**Platform=macOS en** **Profieltype=Aangepast wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="bef7c-175">Change **Platform=macOS** and **Profile type=Custom**.</span></span> <span data-ttu-id="bef7c-176">Selecteer **Configureren**.</span><span class="sxs-lookup"><span data-stu-id="bef7c-176">Select **Configure**.</span></span>
3.  <span data-ttu-id="bef7c-177">Open het configuratieprofiel en upload **sysext.xml.**</span><span class="sxs-lookup"><span data-stu-id="bef7c-177">Open the configuration profile and upload **sysext.xml**.</span></span> <span data-ttu-id="bef7c-178">Dit bestand is gemaakt in de vorige stap.</span><span class="sxs-lookup"><span data-stu-id="bef7c-178">This file was created in the preceding step.</span></span>
4.  <span data-ttu-id="bef7c-179">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="bef7c-179">Select **OK**.</span></span>

    ![Systeemextensie in schermafbeelding van Intune](images/mac-system-extension-intune.png)

5. <span data-ttu-id="bef7c-181">Wijs dit profiel op het tabblad toe `Assignments` aan alle gebruikers & alle **apparaten.**</span><span class="sxs-lookup"><span data-stu-id="bef7c-181">In the `Assignments` tab, assign this profile to **All Users & All devices**.</span></span>
6. <span data-ttu-id="bef7c-182">Controleer en maak dit configuratieprofiel.</span><span class="sxs-lookup"><span data-stu-id="bef7c-182">Review and create this configuration profile.</span></span>
