---
title: Apparaten verwijderen
description: Apparaten verwijderen uit Microsoft Managed Desktop beheer
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
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893735"
---
# <a name="remove-devices"></a><span data-ttu-id="45e76-103">Apparaten verwijderen</span><span class="sxs-lookup"><span data-stu-id="45e76-103">Remove devices</span></span>

<span data-ttu-id="45e76-104">U kunt apparaten verwijderen uit Microsoft Managed Desktop beheer via de beheerportal.</span><span class="sxs-lookup"><span data-stu-id="45e76-104">You can remove devices from Microsoft Managed Desktop management by using the Admin portal.</span></span> <span data-ttu-id="45e76-105">Deze actie is permanent, maar u kunt deze opnieuw registreren met Microsoft Managed Desktop door de [registratiestappen uit te voeren.](../get-started/register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="45e76-105">This action is permanent, but you can register them with Microsoft Managed Desktop again by following the [registration steps](../get-started/register-devices-self.md).</span></span>

<span data-ttu-id="45e76-106">Wanneer u een apparaat verwijdert, vindt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="45e76-106">When you remove a device, all of the following occur:</span></span>

- <span data-ttu-id="45e76-107">We verwijderen het apparaat van Autopilot.</span><span class="sxs-lookup"><span data-stu-id="45e76-107">We remove the device from Autopilot.</span></span>
- <span data-ttu-id="45e76-108">We verwijderen het apparaat uit alle apparaatgroepen 'Moderne werkplek'.</span><span class="sxs-lookup"><span data-stu-id="45e76-108">We remove the device from  all "Modern Workplace" device groups.</span></span>
- <span data-ttu-id="45e76-109">We verwijderen het apparaat uit het **blad Apparaten** in de beheerportal.</span><span class="sxs-lookup"><span data-stu-id="45e76-109">We remove the device from the **Devices** blade in the Admin portal.</span></span>

<span data-ttu-id="45e76-110">Wanneer u een apparaat verwijdert, kunt u dit ook verwijderen uit Azure Active Directory (Azure AD) en Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="45e76-110">When you remove a device, you have the option to also remove it from Azure Active Directory (Azure AD) and Microsoft Intune.</span></span>
 
> [!CAUTION]
> <span data-ttu-id="45e76-111">Het verwijderen van de objecten die betrekking hebben op een apparaat uit Azure AD en Microsoft Intune is permanent.</span><span class="sxs-lookup"><span data-stu-id="45e76-111">Removing the objects related to a device from Azure AD and Microsoft Intune is permanent.</span></span> <span data-ttu-id="45e76-112">Als u de objecten verwijdert, kunt u de apparaten niet bekijken of beheren vanuit de Intune- en Azure-portals.</span><span class="sxs-lookup"><span data-stu-id="45e76-112">If you remove the objects, you won't be able to view or manage the devices from the Intune and Azure portals.</span></span> <span data-ttu-id="45e76-113">De apparaten hebben geen toegang tot de bedrijfsresources van hun bedrijf.</span><span class="sxs-lookup"><span data-stu-id="45e76-113">The devices won't be able to access their company's corporate resources.</span></span> <span data-ttu-id="45e76-114">Bedrijfsgegevens kunnen van hen worden verwijderd als de apparaten zich proberen aan te melden nadat ze zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="45e76-114">Company data might be deleted from them if the devices try to sign in after they're deleted.</span></span>

1. <span data-ttu-id="45e76-115">Selecteer [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)in **het** linkernavigatiedeelvenster apparaten.</span><span class="sxs-lookup"><span data-stu-id="45e76-115">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span>
2. <span data-ttu-id="45e76-116">Zoek naar de **Microsoft Managed Desktop** van het menu en selecteer **Apparaten.**</span><span class="sxs-lookup"><span data-stu-id="45e76-116">Look for the **Microsoft Managed Desktop** section of the menu and select **Devices**.</span></span>
3. <span data-ttu-id="45e76-117">Selecteer in Microsoft Managed Desktop werkruimte Apparaten de apparaten die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="45e76-117">In the Microsoft Managed Desktop Devices workspace, select the devices you want to delete.</span></span>
4. <span data-ttu-id="45e76-118">Selecteer **Apparaatacties** en selecteer vervolgens **Apparaat verwijderen waarmee** een fly-in wordt geopend om de apparaten te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="45e76-118">Select **Device actions**, and then select **Delete Device** which opens a fly-in to remove the devices.</span></span>
5. <span data-ttu-id="45e76-119">Controleer in de fly-in de geselecteerde apparaten en selecteer **vervolgens Apparaten verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="45e76-119">In the fly-in, review the selected devices and then select **Remove devices**.</span></span> <span data-ttu-id="45e76-120">Als u de Azure AD- en Intune-objecten tegelijk wilt verwijderen, schakelt u het selectievakje in.</span><span class="sxs-lookup"><span data-stu-id="45e76-120">If you want to also remove the Azure AD and Intune objects at the same time, select the check box.</span></span> <span data-ttu-id="45e76-121">Het verwijderen van apparaten kan enkele minuten duren.</span><span class="sxs-lookup"><span data-stu-id="45e76-121">Device removal can take a few minutes to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="45e76-122">U kunt apparaten met een in behandeling zijnde registratietoestand **niet** verwijderen.</span><span class="sxs-lookup"><span data-stu-id="45e76-122">You can't remove devices that are in a **pending** registration state.</span></span>