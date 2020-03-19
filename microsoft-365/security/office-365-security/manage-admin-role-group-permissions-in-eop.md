---
title: Machtigingen voor beheerdersrollengroep beheren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Beheerders kunnen leren hoe u machtigingen toewijzen of verwijderen in het Exchange-beheercentrum (EAC) in Exchange Online Protection.
ms.openlocfilehash: 01676fab3ed69120a35687d1c6939cb466b8d672
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810951"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="b48c8-103">Machtigingen voor beheerdersrollengroep beheren in EOP</span><span class="sxs-lookup"><span data-stu-id="b48c8-103">Manage admin role group permissions in EOP</span></span>

<span data-ttu-id="b48c8-104">In Microsoft Exchange Online Protection (EOP) u het Exchange-beheercentrum (EAC) gebruiken om een gebruiker lid te maken van een rolgroep of -groep om hem of haar machtigingen toe te wijzen voor het uitvoeren van specifieke administratieve taken.</span><span class="sxs-lookup"><span data-stu-id="b48c8-104">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks.</span></span> <span data-ttu-id="b48c8-105">U een gebruiker ook uit een rolgroep of -groep verwijderen met behulp van de EAC.</span><span class="sxs-lookup"><span data-stu-id="b48c8-105">You can also remove a user from a role group or groups by using the EAC.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b48c8-106">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="b48c8-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b48c8-107">Geschatte tijdsduur: 5 - 10 minuten</span><span class="sxs-lookup"><span data-stu-id="b48c8-107">Estimated time to complete: 5-10 minutes</span></span>

- <span data-ttu-id="b48c8-108">Zie [Exchange-beheercentrum in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md)als u het Exchange-beheercentrum wilt openen.</span><span class="sxs-lookup"><span data-stu-id="b48c8-108">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="b48c8-109">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="b48c8-109">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="b48c8-110">Zie het item 'Gebruikers, contactpersonen en rolgroepen' in het onderwerp [Functiemachtigingen in het onderwerp EOP](feature-permissions-in-eop.md) om te zien welke machtigingen u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="b48c8-110">To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="b48c8-111">Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="b48c8-111">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="b48c8-112">Heb je problemen?</span><span class="sxs-lookup"><span data-stu-id="b48c8-112">Having problems?</span></span> <span data-ttu-id="b48c8-113">Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)</span><span class="sxs-lookup"><span data-stu-id="b48c8-113">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="b48c8-114">De EAC gebruiken om leden toe te wijzen aan beheerdersrolgroepen</span><span class="sxs-lookup"><span data-stu-id="b48c8-114">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="b48c8-115">Klik in de EAC naar rollen \> **Machtigingenbeheerder,** klik op de rolgroep waaraan u de gebruiker of](../../media/ITPro-EAC-EditIcon.gif)gebruikers wilt toevoegen en klik vervolgens op Pictogram Bewerken **bewerken** ![. **Permissions**</span><span class="sxs-lookup"><span data-stu-id="b48c8-115">In the EAC, go to **Permissions** \> **Admin roles**, click the role group that you want to add the user or users to, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="b48c8-116">**Klik** ![onder Leden op](../../media/ITPro-EAC-AddIcon.gif)Pictogram toevoegen .</span><span class="sxs-lookup"><span data-stu-id="b48c8-116">Under Members, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="b48c8-117">Het venster Leden selecteren wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b48c8-117">The Select Members window will appear.</span></span>

3. <span data-ttu-id="b48c8-118">Zoek naar de gebruiker of gebruikers die u wilt toevoegen of selecteer ze in de lijst.</span><span class="sxs-lookup"><span data-stu-id="b48c8-118">Search for the user or users that you wish to add, or select them from the list.</span></span>

4. <span data-ttu-id="b48c8-119">Wanneer u de gebruiker of gebruikers hebt geselecteerd die u wilt toevoegen, klikt u op **Toevoegen**en klikt u vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="b48c8-119">When you have selected the user or users that you want to add, click **Add**, and then click **OK**.</span></span> <span data-ttu-id="b48c8-120">Het venster Leden selecteren wordt gesloten.</span><span class="sxs-lookup"><span data-stu-id="b48c8-120">The Select Members window will close.</span></span>

5. <span data-ttu-id="b48c8-121">U ziet dat de gebruiker is toegevoegd aan het deelvenster **Leden.**</span><span class="sxs-lookup"><span data-stu-id="b48c8-121">You will see that the user has been added to the **Members** pane.</span></span> <span data-ttu-id="b48c8-122">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b48c8-122">Click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b48c8-123">Gebruikers moeten zich mogelijk afmelden en opnieuw aanmelden om de wijziging in hun beheerdersrechten te zien nadat u leden hebt toegevoegd of verwijderd uit de rolgroep.</span><span class="sxs-lookup"><span data-stu-id="b48c8-123">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="b48c8-124">De EAC gebruiken om leden uit beheerdersrolgroepen te verwijderen</span><span class="sxs-lookup"><span data-stu-id="b48c8-124">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="b48c8-125">Klik in de EAC naar **Beheerdersrollen** **voor machtigingen,** \> klik op de rolgroep waaruit u een gebruiker](../../media/ITPro-EAC-EditIcon.gif)of gebruikers wilt verwijderen en klik vervolgens op Pictogram Bewerken **bewerken** ![.</span><span class="sxs-lookup"><span data-stu-id="b48c8-125">In the EAC, go to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="b48c8-126">Selecteer onder Leden de gebruiker of gebruikers die **Remove** ![u](../../media/ITPro-EAC-RemoveIcon.gif)wilt verwijderen en klik op Pictogram Verwijderen .</span><span class="sxs-lookup"><span data-stu-id="b48c8-126">Under Members, select the user or users that you want to remove and click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="b48c8-127">Klik **op Opslaan** om de wijziging in de rolgroep op te slaan en terug te keren naar de pagina **Beheerdersrollen.**</span><span class="sxs-lookup"><span data-stu-id="b48c8-127">Click **Save** to save the change to the role group and return to the **Admin Roles** page.</span></span> <span data-ttu-id="b48c8-128">Als u wilt controleren of u de gebruiker uit de beheerdersrolgroep hebt verwijderd, controleert u of het lid niet meer wordt weergegeven onder Leden in het detailvenster voor de geselecteerde rolgroep.</span><span class="sxs-lookup"><span data-stu-id="b48c8-128">To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b48c8-129">Gebruikers moeten zich mogelijk afmelden en opnieuw aanmelden om de wijziging in hun beheerdersrechten te zien nadat u leden hebt toegevoegd of verwijderd uit de rolgroep.</span><span class="sxs-lookup"><span data-stu-id="b48c8-129">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="b48c8-130">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="b48c8-130">For more information</span></span>

[<span data-ttu-id="b48c8-131">Functiemachtigingen in EOP</span><span class="sxs-lookup"><span data-stu-id="b48c8-131">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
