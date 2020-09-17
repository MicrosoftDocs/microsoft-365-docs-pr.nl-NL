---
title: Microsoft Teams
description: Hoe teams op apparaten wordt geïnstalleerd en daarna later worden bijgewerkt
keywords: Microsoft Managed Desktop, Microsoft 365, service, Documentatie, apps, line-of-Business-Apps, LOB-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950915"
---
# <a name="microsoft-teams"></a><span data-ttu-id="a4440-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a4440-104">Microsoft Teams</span></span>

<span data-ttu-id="a4440-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is een [Berichten-app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) voor uw organisatie die ook een werkruimte biedt voor samenwerking in realtime en communicatie, vergaderingen en het delen van bestanden en apps.</span><span class="sxs-lookup"><span data-stu-id="a4440-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="a4440-106">Eerste implementatie</span><span class="sxs-lookup"><span data-stu-id="a4440-106">Initial deployment</span></span>

<span data-ttu-id="a4440-107">Voor de meeste hardwareleveranciers zijn er nog geen teams opgenomen als onderdeel van hun afbeeldingen, zodat Microsoft Managed Desktop teams implementeert op uw apparaten via Microsoft intune.</span><span class="sxs-lookup"><span data-stu-id="a4440-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="a4440-108">Voor alle beheerde apparaten is het [pakket teams. msi](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) geïnstalleerd, zodat alle gebruikers die zich aanmelden bij een apparaat, al Microsoft teams kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a4440-108">All managed devices have the [Teams .msi package](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="a4440-109">Wanneer het pakket eerst is geïnstalleerd, wordt in teams automatisch een snelkoppeling naar het bureaublad toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="a4440-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="a4440-110">Microsoft intune-wijzigingen</span><span class="sxs-lookup"><span data-stu-id="a4440-110">Microsoft Intune changes</span></span>

<span data-ttu-id="a4440-111">Microsoft Managed Desktop voegt twee toepassingen toe aan uw Azure AD-organisatie voor Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="a4440-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="a4440-112">Ze worden gedistribueerd naar 64-bits-of 32-bits-clients, wat van toepassing is op het apparaat:</span><span class="sxs-lookup"><span data-stu-id="a4440-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="a4440-113">Modern Workplace-teams machine Wide Installer x64</span><span class="sxs-lookup"><span data-stu-id="a4440-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="a4440-114">Modern Workplace: teams-hele Installer x32</span><span class="sxs-lookup"><span data-stu-id="a4440-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="a4440-115">Updates</span><span class="sxs-lookup"><span data-stu-id="a4440-115">Updates</span></span>

<span data-ttu-id="a4440-116">Teams volgt een apart update traject in Microsoft 365-apps voor Enterprise en de bureaublad client werkt automatisch.</span><span class="sxs-lookup"><span data-stu-id="a4440-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="a4440-117">Teams controleert om de paar uur een update voor updates, downloadt ze en vervalt de computer totdat de computer inactief is voordat de update is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="a4440-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="a4440-118">Met de productgroep teams kunnen beheerders geen updates beheren, zodat Microsoft Managed Desktop gebruikmaakt van het [standaardkanaal voor automatische updates](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span><span class="sxs-lookup"><span data-stu-id="a4440-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="a4440-119">Teams handmatig bijwerken</span><span class="sxs-lookup"><span data-stu-id="a4440-119">Manually updating Teams</span></span>

<span data-ttu-id="a4440-120">Individuele gebruikers kunnen ook updates downloaden door **controleren op updates**te selecteren   in de vervolgkeuzelijst **profiel**rechtsboven in   de app.</span><span class="sxs-lookup"><span data-stu-id="a4440-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="a4440-121">Als er een update beschikbaar is, wordt deze gedownload en op de achtergrond geïnstalleerd wanneer de computer inactief is.</span><span class="sxs-lookup"><span data-stu-id="a4440-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="a4440-122">Delivery Optimization-updates</span><span class="sxs-lookup"><span data-stu-id="a4440-122">Delivery optimization of updates</span></span>

<span data-ttu-id="a4440-123">Delivery Optimizing voor team updates is standaard ingeschakeld en is geen actie van beheerders of gebruikers vereist.</span><span class="sxs-lookup"><span data-stu-id="a4440-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span> 