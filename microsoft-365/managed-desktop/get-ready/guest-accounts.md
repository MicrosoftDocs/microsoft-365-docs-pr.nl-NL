---
title: Vereisten voor gastaccounts
description: Configuratie richtlijnen voor gastaccounts en hoe u deze kunt aanpassen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073200"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="71640-104">Vereisten voor gastaccounts</span><span class="sxs-lookup"><span data-stu-id="71640-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="71640-105">Voor het Microsoft-beheer bureaublad zijn de volgende instellingen nodig in de Azure AD-organisatie voor toegang tot een gastaccount.</span><span class="sxs-lookup"><span data-stu-id="71640-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="71640-106">U kunt deze instellingen wijzigen bij [Azure Portal](https://portal.azure.com) onder **externe identiteiten/extern samenwerken** :</span><span class="sxs-lookup"><span data-stu-id="71640-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration** :</span></span>

-   <span data-ttu-id="71640-107">**Beheerders en gebruikers in de rol van gast invite kunnen de set uitnodigen** op **Ja**</span><span class="sxs-lookup"><span data-stu-id="71640-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="71640-108">Kies voor **samenwerkings beperkingen** een van deze opties:</span><span class="sxs-lookup"><span data-stu-id="71640-108">For **Collaboration restrictions** , choose any of these options:</span></span>
    -   <span data-ttu-id="71640-109">Als u **uitnodigingen toestaan selecteert voor het verzenden van een domein (meestal)** , hoeft u geen andere configuratie uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="71640-109">If you select **Allow invitations to be sent to any domain (most inclusive)** , no other configuration required.</span></span>
    -   <span data-ttu-id="71640-110">Als u **uitnodigingen voor de opgegeven domeinen weigeren** selecteert, controleert u of Microsoft.com niet wordt vermeld in de doeldomeinen.</span><span class="sxs-lookup"><span data-stu-id="71640-110">If you select **Deny invitations to the specified domains** , make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="71640-111">Als u **alleen uitnodigingen toestaan selecteert voor de opgegeven domeinen (de meeste beperkingen)** , controleert u of Microsoft.com in de doeldomeinen *wordt* weergegeven.</span><span class="sxs-lookup"><span data-stu-id="71640-111">If you select **Allow invitations only to the specified domains (most restrictive)** , make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="71640-112">Als u beperkingen instelt voor de instellingen van deze instellingen, moet u ervoor zorgen dat de service accounts van Azure Active Directory voor de **moderne werkplek** worden uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="71640-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="71640-113">Als u bijvoorbeeld een beleid voor voorwaardelijke toegang hebt om te voorkomen dat gastaccounts toegang krijgen tot de intune-Portal, moet u de groep **service accounts van modern werk** stroom uitsluiten van dit beleid.</span><span class="sxs-lookup"><span data-stu-id="71640-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

