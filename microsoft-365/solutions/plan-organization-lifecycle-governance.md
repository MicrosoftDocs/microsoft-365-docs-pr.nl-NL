---
title: Organisatie en levenscyclusbeheer plannen voor Microsoft 365-groepen en Microsoft Teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Lean about lifecycle governance options for collaboration tools in Microsoft 365
ms.openlocfilehash: ff3a3a60ce49c423410b51dc6fee2137ebf8952a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907926"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Organisatie en levenscyclusbeheer plannen voor Microsoft 365-groepen en Microsoft Teams

Microsoft 365-groepen beschikt over een uitgebreide set hulpprogramma's voor het implementeren van de beheermogelijkheden die uw organisatie nodig heeft. 

In de volgende sectie worden de mogelijkheden beschreven, aanbevolen procedures en worden richtlijnen gegeven voor het stellen van de juiste vragen om de vereisten voor beheer te bepalen en hoe u aan deze vereisten kunt voldoen.

## <a name="control-who-can-create-microsoft-365-groups"></a>Bepalen wie Microsoft 365-groepen kan maken

Groepen kunnen door eindgebruikers worden gemaakt vanuit meerdere eindpunten, waaronder Outlook, SharePoint, Teams en andere omgevingen.

![afbeeldingssc](../media/04.png)

We raden selfservice ten zeerste aan om groepseigenaren in staat te stellen en gebruikers te helpen hun werk gemakkelijker te doen. Het beperken van het maken van groepen en het maken van teams kan de productiviteit van gebruikers vertragen, omdat voor veel Microsoft 365-services groepen moeten worden gemaakt om de service te laten functioneren.

Overweeg de volgende beheeropties voor het maken van groepen:

- Als u groepsuitbreiding wilt beperken, gebruikt u [verloopbeleid](microsoft-365-groups-expiration-policy.md) voor groepen om groepen die niet worden gebruikt, automatisch te verwijderen.
- Beperk het maken van groepen tot leden van een [beveiligingsgroep met dynamisch](/azure/active-directory/users-groups-roles/groups-create-rule) lidmaatschap, bijvoorbeeld alle voltijdse werknemers.
- Beperk het maken van groepen tot een beveiligingsgroep en vereist dat gebruikers de training in het groepsbeleid van uw organisatie voltooien om lid te worden van de beveiligingsgroep.

Zie Beheren wie [Microsoft 365-groepen](manage-creation-of-groups.md) kan maken voor informatie over het configureren van deze groepen als u wilt beperken wie groepen kan maken.

## <a name="group-delete-restore-and-archiving"></a>Verwijderen, herstellen en archiveren groeperen

Wanneer een Microsoft 365-groep wordt verwijderd, wordt deze standaard 30 dagen bewaard. Tijdens deze periode van 30 dagen kunt u de groep nog steeds herstellen. Na 30 dagen worden de groep en de bijbehorende inhoud definitief verwijderd en kunnen deze niet worden hersteld.

Als u bewaarbeleid hebt om chat, bestanden of e-mail te behouden, blijven deze items behouden nadat de groep is verwijderd. Zie [Meer informatie over bewaarbeleid](../compliance/retention.md) voor meer informatie.

Zie Groepen, teams en [Yammer](end-life-cycle-groups-teams-sites-yammer.md) archiveren voor informatie als u een groep wilt verwijderen, maar de inhoud wilt behouden van een of meer services die met de groep zijn verbonden.

## <a name="group-naming-policy"></a>Groepsbeleid voor naamgeving

Met een naamgevingsbeleid voor groepen kunt u groepen op twee manieren besturen:

- Een naamgevingsbeleid voor voorvoegsels/achtervoegsels kan worden gebruikt om vaste tekenreeksen of Azure AD-kenmerken af te dwingen aan het begin of einde van een groepsnaam en het bijbehorende e-mailadres. Hierdoor kunt u ervoor zorgen dat bijvoorbeeld afdelingsnamen of regio's in groepsnamen worden opgenomen.
- Een beleid voor geblokkeerde woorden kan ervoor zorgen dat bepaalde woorden, zoals de namen van leidinggevenden, niet worden gebruikt in groepsnamen.

Naamgevingsbeleid wordt toegepast wanneer groepen worden gemaakt op een van de met de groep verbonden services.

Zie Naamgevingsbeleid voor [Microsoft 365 Groepen](groups-naming-policy.md)als u besluit naamgevingsbeleid voor groepen te gebruiken.

## <a name="group-expiration-policy"></a>Verloopbeleid groep

U kunt een verloopperiode opgeven en elke groep die het einde van die periode bereikt en niet wordt verlengd, wordt verwijderd. De verloopperiode begint wanneer de groep wordt gemaakt of op de datum waarop de groep voor het laatst is verlengd.

Nadat u groepen hebt ingesteld op verlopen:
- Eigenaren van de groep krijgen een melding om de groep te verlengen zodra de vervaldatum nadert.
- Actieve groepen worden automatisch verlengd.
- Een groep die niet wordt verlengd, wordt verwijderd.
- Elke groep die wordt verwijderd, kan binnen 30 dagen worden hersteld door de groepseigenaars of de beheerder.

Verloopbeleid is een goede manier om groepsuitbreiding te beperken door ervoor te zorgen dat groepen die niet meer worden gebruikt, worden verwijderd. Zie Microsoft [365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md)(Verloopbeleid voor groepen) als u een verloopbeleid voor groepen wilt maken.

## <a name="related-topics"></a>Verwante onderwerpen

[Planning van samenwerkingsbeheer stap voor stap](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Uw samenwerkingsbeheerplan maken](collaboration-governance-first.md)