---
title: De Exchange Online-beheerdersrol
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 097ae285-c4af-4319-9770-e2559d66e4c8
description: 'Beheerders van Exchange Online beheren e-mail en postvakken van uw organisatie. Ze herstellen bijvoorbeeld Verwijderde items in het postvak van een gebruiker. '
ms.openlocfilehash: 8e332e886ca25221fefbbc5d1bb790bd4f513f00
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527511"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="0f896-104">De Exchange Online-beheerdersrol</span><span class="sxs-lookup"><span data-stu-id="0f896-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="0f896-105">Om u te helpen bij het beheren van Microsoft 365 kunt u gebruikersmachtigingen [toewijzen](assign-admin-roles.md) voor het beheren van de e-mail en postvakken van uw organisatie vanuit het [Exchange-Beheercentrum](https://go.microsoft.com/fwlink/p/?LinkID=271807).</span><span class="sxs-lookup"><span data-stu-id="0f896-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkID=271807).</span></span> <span data-ttu-id="0f896-106">U doet dit door ze toe te wijzen aan de rol van de Exchange-beheerder.</span><span class="sxs-lookup"><span data-stu-id="0f896-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="0f896-107">**Tip**: Wanneer u aan iemand de rol van Exchange-beheerder toewijst, moet die persoon ook de rol van Servicebeheerder toewijzen.</span><span class="sxs-lookup"><span data-stu-id="0f896-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="0f896-108">Op deze manier kunnen ze belangrijke informatie zien in het Microsoft 365-Beheercentrum, zoals de status van de Exchange Online-service en meldingen wijzigen en vrijgeven.</span><span class="sxs-lookup"><span data-stu-id="0f896-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="0f896-109">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="0f896-109">Before you begin</span></span>

<span data-ttu-id="0f896-110">Hier volgen enkele van de belangrijkste taken die gebruikers kunnen uitvoeren wanneer zij de rol van Exchange-beheerder toegewezen hebben gekregen:</span><span class="sxs-lookup"><span data-stu-id="0f896-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="0f896-111">Recover deleted items in a user mailbox - Admin Help</span><span class="sxs-lookup"><span data-stu-id="0f896-111">Recover deleted items in a user mailbox - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/recover-deleted-items-in-a-mailbox)

- <span data-ttu-id="0f896-112">[Een archief-en verwijderingsbeleid instellen voor postvakken in uw organisatie](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="0f896-112">[Set up an archive and deletion policy for mailboxes in your organization](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes).</span></span>

- <span data-ttu-id="0f896-113">Postvakfuncties instellen zoals het beleid voor het delen van een postvak: hoe gebruikers een agenda en contactpersonen met anderen kunnen delen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0f896-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="0f896-114">Stel de gemachtigden voor '[verzenden als](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)' en '[Verzenden namens ' in](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)voor het postvak van iemand.</span><span class="sxs-lookup"><span data-stu-id="0f896-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on behalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="0f896-115">Een manager wil bijvoorbeeld dat zijn of assistent over de mogelijkheid beschikt om namens hem of haar e-mail te verzenden.</span><span class="sxs-lookup"><span data-stu-id="0f896-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="0f896-116">[Maak een gedeeld postvak](../email/create-a-shared-mailbox.md) zodat een groep personen e-mail kan controleren en verzenden vanaf een gemeenschappelijk e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="0f896-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="0f896-117">[E-mail tegen spam bescherming](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) en de filters voor schadelijke software voor de organisatie.</span><span class="sxs-lookup"><span data-stu-id="0f896-117">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) and malware filters for the organization.</span></span>

- <span data-ttu-id="0f896-118">Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="0f896-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="0f896-119">Exchange Online-rollengroepen</span><span class="sxs-lookup"><span data-stu-id="0f896-119">Exchange Online role groups</span></span>

<span data-ttu-id="0f896-p105">In een grote organisatie kan de Exchange-beheerder gebruikers toewijzen aan Exchange-rollengroepen. Wanneer een beheerder een gebruiker toevoegt aan een rollengroep, krijgt de gebruiker machtigingen voor het uitvoeren van bepaalde bedrijfsfuncties waarover alleen leden van die groep beschikken.</span><span class="sxs-lookup"><span data-stu-id="0f896-p105">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups. When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="0f896-p106">De Exchange-beheerder kan bijvoorbeeld iemand toewijzen aan de rollengroep Discovery-beheer zodat die persoon in postvakken kan zoeken naar gegevens die aan bepaalde criteria voldoen. Zie [Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) en [Rollengroepen beheren](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0f896-p106">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria. To learn more, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-roles"></a><span data-ttu-id="0f896-124">Meer informatie over andere beheerdersrollen</span><span class="sxs-lookup"><span data-stu-id="0f896-124">Learn about other admin roles</span></span>

- [<span data-ttu-id="0f896-125">Over Microsoft 365-beheersrollen</span><span class="sxs-lookup"><span data-stu-id="0f896-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="0f896-126">Info over de SharePoint Online-beheerdersrol</span><span class="sxs-lookup"><span data-stu-id="0f896-126">About the SharePoint Online admin role</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)

- <span data-ttu-id="0f896-127">[About the Skype for Business admin role](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online) (De Skype voor Bedrijven-beheerdersrol)</span><span class="sxs-lookup"><span data-stu-id="0f896-127">[About the Skype for Business admin role](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online)</span></span>

- [<span data-ttu-id="0f896-128">De rol van Microsoft teams-beheerder gebruiken</span><span class="sxs-lookup"><span data-stu-id="0f896-128">Use Microsoft Teams admin role</span></span>](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles) 
