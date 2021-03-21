---
title: Microsoft Teams
description: Hoe Teams is geïnstalleerd op apparaten en daarna wordt bijgewerkt
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, apps, line-of-business-apps, LOB-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920654"
---
# <a name="microsoft-teams"></a><span data-ttu-id="d43e5-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d43e5-104">Microsoft Teams</span></span>

<span data-ttu-id="d43e5-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is een [berichten-app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) voor uw organisatie die ook een werkruimte biedt voor realtime samenwerking en communicatie, vergaderingen en het delen van bestanden en apps.</span><span class="sxs-lookup"><span data-stu-id="d43e5-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="d43e5-106">Eerste implementatie</span><span class="sxs-lookup"><span data-stu-id="d43e5-106">Initial deployment</span></span>

<span data-ttu-id="d43e5-107">De meeste hardwareleveranciers bevatten Teams nog niet als onderdeel van hun afbeeldingen, dus Microsoft Managed Desktop implementeert Teams op uw apparaten met Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="d43e5-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="d43e5-108">Op alle beheerde apparaten is [het Teams .msi-pakket](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) geïnstalleerd, zodat alle gebruikers die zich aanmelden bij een apparaat, Microsoft Teams klaar hebben voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="d43e5-108">All managed devices have the [Teams .msi package](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="d43e5-109">Wanneer het pakket voor het eerst is geïnstalleerd, wordt Teams automatisch gestart en wordt er een snelkoppeling toegevoegd aan het bureaublad.</span><span class="sxs-lookup"><span data-stu-id="d43e5-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="d43e5-110">Wijzigingen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d43e5-110">Microsoft Intune changes</span></span>

<span data-ttu-id="d43e5-111">Microsoft Managed Desktop voegt twee toepassingen toe aan uw Azure AD-organisatie voor Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d43e5-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="d43e5-112">Ze worden geïmplementeerd voor 64-bits of 32-bits clients, zoals geschikt voor het apparaat:</span><span class="sxs-lookup"><span data-stu-id="d43e5-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="d43e5-113">Moderne werkplek : Teams Machine Wide Installer x64</span><span class="sxs-lookup"><span data-stu-id="d43e5-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="d43e5-114">Moderne werkplek : Teams Machine Wide Installer x32</span><span class="sxs-lookup"><span data-stu-id="d43e5-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="d43e5-115">Updates</span><span class="sxs-lookup"><span data-stu-id="d43e5-115">Updates</span></span>

<span data-ttu-id="d43e5-116">Teams volgt een afzonderlijk updatepad van Microsoft 365 Apps voor bedrijven en de desktopclient wordt automatisch bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="d43e5-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="d43e5-117">Teams controleert om de paar uur op updates, downloadt ze en wacht totdat de computer inactief is voordat u de update in stilte installeert.</span><span class="sxs-lookup"><span data-stu-id="d43e5-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="d43e5-118">De Teams-productgroep staat beheerders niet toe updates te beheren, dus Microsoft Managed Desktop gebruikt het [standaardkanaal voor automatische update.](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)</span><span class="sxs-lookup"><span data-stu-id="d43e5-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="d43e5-119">Teams handmatig bijwerken</span><span class="sxs-lookup"><span data-stu-id="d43e5-119">Manually updating Teams</span></span>

<span data-ttu-id="d43e5-120">Afzonderlijke gebruikers kunnen ook updates downloaden door **Controleren op updates** te selecteren in de    \*\*\*\*   vervolgkeuzelijst Profiel rechtsboven in de app.</span><span class="sxs-lookup"><span data-stu-id="d43e5-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="d43e5-121">Als er een update beschikbaar is, wordt deze gedownload en geruisloos geïnstalleerd wanneer de computer inactief is.</span><span class="sxs-lookup"><span data-stu-id="d43e5-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="d43e5-122">Leveringsoptimalisatie van updates</span><span class="sxs-lookup"><span data-stu-id="d43e5-122">Delivery optimization of updates</span></span>

<span data-ttu-id="d43e5-123">Leveringsoptimalisatie voor Teams-updates is standaard ingeschakeld en vereist geen actie van beheerders of gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d43e5-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span>