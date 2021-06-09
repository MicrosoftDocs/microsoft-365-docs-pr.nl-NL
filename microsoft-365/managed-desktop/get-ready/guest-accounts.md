---
title: Vereisten voor gast-accounts
description: Configuratierichtlijnen voor gastaccounts en hoe u deze kunt aanpassen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694243"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="5fc9e-104">Vereisten voor gast-accounts</span><span class="sxs-lookup"><span data-stu-id="5fc9e-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="5fc9e-105">Microsoft Managed Desktop vereist de volgende instellingen in uw Azure AD-organisatie voor toegang tot gastaccounts.</span><span class="sxs-lookup"><span data-stu-id="5fc9e-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="5fc9e-106">U kunt deze instellingen aanpassen in de [Azure-portal](https://portal.azure.com) onder Instellingen voor externe **identiteiten /Externe samenwerking:**</span><span class="sxs-lookup"><span data-stu-id="5fc9e-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration settings**:</span></span>

-   <span data-ttu-id="5fc9e-107">Voor **beperkingen voor gast uitnodigen die** zijn ingesteld op Ledengebruikers en gebruikers die zijn toegewezen aan specifieke beheerdersrollen, kunnen gastgebruikers met inbegrip van gasten met **lidmachtigingen worden uitgenodigd**</span><span class="sxs-lookup"><span data-stu-id="5fc9e-107">For **Guest invite restrictions** set to **Member users and users assigned to specific admin roles can invite guest users including guests with member permissions**</span></span>
-   <span data-ttu-id="5fc9e-108">Kies een van de volgende opties voor **samenwerkingsbeperkingen:**</span><span class="sxs-lookup"><span data-stu-id="5fc9e-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="5fc9e-109">Als u **Uitnodigingen toestaan om te worden verzonden naar** een domein (inclusief) selecteert, is er geen andere configuratie vereist.</span><span class="sxs-lookup"><span data-stu-id="5fc9e-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="5fc9e-110">Als u **Uitnodigingen weigeren voor** de opgegeven domeinen selecteert, moet u ervoor zorgen dat Microsoft.com niet wordt weergegeven in de doeldomeinen.</span><span class="sxs-lookup"><span data-stu-id="5fc9e-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="5fc9e-111">Als u Uitnodigingen alleen toestaan voor de opgegeven domeinen **(meest beperkende)** selecteert, moet u ervoor zorgen dat Microsoft.com wordt weergegeven in de doeldomeinen. </span><span class="sxs-lookup"><span data-stu-id="5fc9e-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="5fc9e-112">Als u beperkingen in stelt die met deze instellingen werken, moet u de Azure Active Directory **Moderne werkplekserviceaccounts uitsluiten.**</span><span class="sxs-lookup"><span data-stu-id="5fc9e-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="5fc9e-113">Als u bijvoorbeeld een beleid voor voorwaardelijke toegang hebt dat verhindert dat gastaccounts toegang krijgen tot de Intune-portal, sluit u de groep Moderne **werkplekserviceaccounts** uit van dit beleid.</span><span class="sxs-lookup"><span data-stu-id="5fc9e-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="5fc9e-114">Stappen om u klaar te maken</span><span class="sxs-lookup"><span data-stu-id="5fc9e-114">Steps to get ready</span></span>

1. <span data-ttu-id="5fc9e-115">Lees [vereisten voor Microsoft Managed Desktop](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="5fc9e-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="5fc9e-116">Gebruik [hulpprogramma's voor gereedheidsevaluatie](readiness-assessment-tool.md).</span><span class="sxs-lookup"><span data-stu-id="5fc9e-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="5fc9e-117">[Vereisten voor gastaccounts](guest-accounts.md) (Dit artikel)</span><span class="sxs-lookup"><span data-stu-id="5fc9e-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="5fc9e-118">Netwerkconfiguratie voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5fc9e-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="5fc9e-119">Certificaten en netwerkprofielen voorbereiden voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5fc9e-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="5fc9e-120">Toegang voorbereiden tot on-premises bronnen voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5fc9e-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="5fc9e-121">Apps in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5fc9e-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="5fc9e-122">Toegewezen stations voorbereiden voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5fc9e-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="5fc9e-123">Afdrukbronnen voorbereiden voor Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="5fc9e-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
