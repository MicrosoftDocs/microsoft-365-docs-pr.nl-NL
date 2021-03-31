---
title: Stappen voor partners om apparaten te registreren
description: Hoe Partners apparaten kunnen registreren zodat ze kunnen worden beheerd door Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: baf15ca4b83052af84d2b22b3d2604c6022ac900
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445588"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="13164-104">Stappen voor partners om apparaten te registreren</span><span class="sxs-lookup"><span data-stu-id="13164-104">Steps for Partners to register devices</span></span>


<span data-ttu-id="13164-105">In dit onderwerp worden de stappen beschreven die partners moeten volgen om apparaten te registreren.</span><span class="sxs-lookup"><span data-stu-id="13164-105">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="13164-106">Het proces voor het zelf registreren van apparaten wordt gedocumenteerd in [Apparaten registreren in Microsoft Managed Desktop zelf.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="13164-106">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="13164-107">Registratie voorbereiden</span><span class="sxs-lookup"><span data-stu-id="13164-107">Prepare for registration</span></span> 
<span data-ttu-id="13164-108">Voordat u de registratie voor een klant voltooit, moet u eerst een relatie met de klant tot standbrengen in het [Partnercentrum.](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="13164-108">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="13164-109">Zie de [toestemmingsdocumentatie](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) voor meer informatie over dat proces.</span><span class="sxs-lookup"><span data-stu-id="13164-109">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="13164-110">Elke CSP-partner kan apparaten toevoegen namens een klant, zolang de klant toestemming geeft.</span><span class="sxs-lookup"><span data-stu-id="13164-110">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="13164-111">U kunt ook meer informatie krijgen over partnerrelaties en Autopilot-machtigingen bij [Help voor partnercentrum.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="13164-111">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="13164-112">Deze documentatie is alleen voor Partners en OEM's.</span><span class="sxs-lookup"><span data-stu-id="13164-112">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="13164-113">Het proces voor zelfregistratie wordt gedocumenteerd in [Register-apparaten in Microsoft Managed Desktop zelf.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="13164-113">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="13164-114">Apparaten registreren met partnercentrum</span><span class="sxs-lookup"><span data-stu-id="13164-114">Register devices by using Partner Center</span></span>

<span data-ttu-id="13164-115">Nadat u de relatie met uw klanten hebt vastgesteld, kunt u partnercentrum gebruiken om apparaten toe te voegen aan Autopilot voor alle klanten met wie u een relatie hebt door de volgende stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="13164-115">Once you have established the relationship with your customers, you can leverage Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="13164-116">Navigeren naar [Partnercentrum](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="13164-116">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="13164-117">Selecteer **Klanten** in het menu Partnercentrum en selecteer vervolgens de klant van wie u de apparaten wilt beheren.</span><span class="sxs-lookup"><span data-stu-id="13164-117">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="13164-118">Selecteer Apparaten op de detailpagina van **de klant.**</span><span class="sxs-lookup"><span data-stu-id="13164-118">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="13164-119">Selecteer **onder Profielen toepassen** op apparaten de optie Apparaten **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="13164-119">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="13164-120">Voer **Microsoft365Managed_Autopilot** voor de groepsnaam in en selecteer **Bladeren** om de lijst van de klant (in CSV-bestandsindeling) te uploaden naar partnercentrum.</span><span class="sxs-lookup"><span data-stu-id="13164-120">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="13164-121">De groepsnaam moet exact **overeenkomen Microsoft365Managed_Autopilot,** inclusief hoofdletters en speciale tekens.</span><span class="sxs-lookup"><span data-stu-id="13164-121">The Group Name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="13164-122">Hierdoor kunnen de nieuw geregistreerde apparaten worden toegewezen aan het Microsoft Managed Desktop Autopilot-profiel.</span><span class="sxs-lookup"><span data-stu-id="13164-122">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="13164-123">U had dit CSV-bestand moeten ontvangen bij de aankoop van uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="13164-123">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="13164-124">Als u geen CSV-bestand hebt ontvangen, kunt u er zelf een maken door de stappen in Apparaten toevoegen [aan Windows Autopilot te volgen.](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="13164-124">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="13164-125">Het Windows PowerShell-script verschilt van het script dat wordt gebruikt voor de [Microsoft Managed Desktop Admin portal.](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash)</span><span class="sxs-lookup"><span data-stu-id="13164-125">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash).</span></span> <span data-ttu-id="13164-126">Partners moeten [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om apparaten te registreren voor Microsoft Managed Desktop-apparaten in partnercentrum.</span><span class="sxs-lookup"><span data-stu-id="13164-126">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="13164-127">Als u een foutbericht krijgt terwijl u het CSV-bestand probeert te uploaden, controleert u de opmaak van het bestand.</span><span class="sxs-lookup"><span data-stu-id="13164-127">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="13164-128">Zorg ervoor dat de kolomorder overeenkomt met wat wordt beschreven in Windows Autopilot-profielen gebruiken op nieuwe apparaten om de [out-of-box-ervaring](/partner-center/autopilot#add-devices-to-a-customers-account)van een klant aan te passen.</span><span class="sxs-lookup"><span data-stu-id="13164-128">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="13164-129">U kunt ook het csv-voorbeeldbestand van de koppeling naast **Apparaten toevoegen** gebruiken om een lijst met apparaten te maken.</span><span class="sxs-lookup"><span data-stu-id="13164-129">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="13164-130">Zie Apparaten toevoegen aan het account van een klant voor meer informatie over Autopilot in [partnerscenario's.](/partner-center/autopilot#add-devices-to-a-customers-account)</span><span class="sxs-lookup"><span data-stu-id="13164-130">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="13164-131">Apparaten registreren met de OEM-API</span><span class="sxs-lookup"><span data-stu-id="13164-131">Register devices by using the OEM API</span></span>

<span data-ttu-id="13164-132">Voordat u de registratie voor een klant voltooit, moet u eerst een relatie met de klant tot standbrengen.</span><span class="sxs-lookup"><span data-stu-id="13164-132">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="13164-133">U moet een unieke koppeling hebben om aan uw respectieve klanten te leveren.</span><span class="sxs-lookup"><span data-stu-id="13164-133">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="13164-134">Zie [Oem-relatie tot stand komen.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)</span><span class="sxs-lookup"><span data-stu-id="13164-134">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="13164-135">Nadat u de relatie hebt vastgesteld, kunt u apparaten voor klanten registreren met behulp van de **Microsoft365Managed_Autopilot.**</span><span class="sxs-lookup"><span data-stu-id="13164-135">Once you've established the relationship, you can start registering devices for customers using the Group Tag **Microsoft365Managed_Autopilot**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13164-136">De groepsnaam moet exact **overeenkomen Microsoft365Managed_Autopilot,** inclusief hoofdletters en speciale tekens.</span><span class="sxs-lookup"><span data-stu-id="13164-136">The group name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="13164-137">Hierdoor kunnen de nieuw geregistreerde apparaten worden toegewezen aan het Microsoft Managed Desktop Autopilot-profiel.</span><span class="sxs-lookup"><span data-stu-id="13164-137">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>