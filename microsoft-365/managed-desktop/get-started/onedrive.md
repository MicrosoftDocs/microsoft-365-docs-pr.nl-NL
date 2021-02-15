---
title: Microsoft OneDrive
description: Hoe Microsoft Beheerd bureaublad OneDrive voor geregistreerde apparaten in stelt
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, apps, lob-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 6cd2c993e0ca9d4c456a2914b866b65b59799afa
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233904"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft Managed Desktop gebruikt [OneDrive voor](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) Bedrijven als cloudopslagservice voor alle door Microsoft beheerde desktopapparaten om ervoor te zorgen dat de apparaten zo stateless mogelijk zijn. Gebruikers kunnen hun bestanden vinden, ongeacht op welk apparaat ze zich aanmelden. Als u bijvoorbeeld een door Microsoft Beheerd bureaublad-apparaat vervangt door een nieuw apparaat, worden bestanden automatisch gesynchroniseerd met het nieuwe apparaat.

Deze instellingen worden standaard automatisch geconfigureerd op door Microsoft beheerde apparaten:

- OneDrive wordt op de silently geconfigureerd met het gebruikersaccount en automatisch aangemeld (zonder tussenkomst van de gebruiker) bij het gebruikersaccount waarmee u zich hebt aangemeld bij Windows. Zie Gebruikersaccounts op de volgende [tabbladen configureren - OneDrive](https://docs.microsoft.com/onedrive/use-silent-account-configuration)

- De functie Files-On-Demand is ingeschakeld, zodat gebruikers toegang hebben tot bestanden vanuit hun cloudopslag in OneDrive zonder onnodig schijfruimte te gebruiken. Zie Schijfruimte besparen [met OneDrive Files On-Demand voor Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)voor meer informatie.

- De functie Bekende map verplaatsen is op de silently ingeschakeld om back-up te maken van gegevens van gebruikers in de cloud, waardoor ze vanaf elk apparaat toegang hebben tot hun bestanden. Zie Een back-up maken van uw documenten, afbeeldingen en [bureaubladmappen met OneDrive voor meer informatie.](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)

- Gebruikers kunnen de functie Bekende map verplaatsen niet uitschakelen en de locatie van bekende mappen niet wijzigen om een consistente ervaring te garanderen op beheerde desktopapparaten van Microsoft.

## <a name="user-experience"></a>Gebruikerservaring

Wanneer microsoft Managed Desktop-gebruikers een nieuw apparaat ontvangen, doorloop ze een first-runervaring door hun Azure-referenties in te voeren tijdens het instellen van het apparaat. Nadat dit proces is voltooid, hebben ze toegang tot hun bureaublad en hebben ze de OneDrive-ervaring.

1. Het systeem meldt aan gebruikers dat OneDrive is geconfigureerd en dat ze automatisch zijn aangemeld bij OneDrive.

:::image type="content" source="media/onedrive-sync.png" alt-text="Melding dat u OneDrive nu synchroniseert en bestanden kunt bewerken in OneDrive. klik hier om uw bestanden te bekijken":::

2. Het systeem vertelt gebruikers dat bekende map verplaatsen in OneDrive voor hen is geconfigureerd.

:::image type="content" source="media/onedrive-folders.png" alt-text="Melding voor het lezen Van uw IT-afdeling is een back-up van uw belangrijke mappen maakt. Van de mappen wordt nu een back-up gemaakt in OneDrive en deze zijn beschikbaar op andere apparaten":::

3. Als u dubbele pictogrammen op het bureaublad wilt voorkomen wanneer apparaten opnieuw worden ingesteld of een nieuwe animatie worden ingesteld, worden de pictogrammen van Microsoft Edge en Microsoft Teams automatisch verwijderd uit de OneDrive-synchronisatie, zoals wordt weergegeven in deze weergave in Verkenner.

:::image type="content" source="media/onedrive-teams.png" alt-text="Verkenner met Teams- en Edge-vermeldingen met gewinkte selectievakjes en tekst met aanwijzer die Wordt uitgesloten van synchronisatie weergegeven.":::


## <a name="onedrive-sync-restrictions"></a>Synchronisatiebeperkingen voor OneDrive

Als u de synchronisatie van OneDrive wilt beperken, raden we u aan de toegang te beperken met een beleid voor voorwaardelijke toegang van Azure Active Directory. Zie Ondersteuning voor voorwaardelijke [toegang inschakelen in de OneDrive-synchronisatie-app voor meer informatie.](https://docs.microsoft.com/onedrive/enable-conditional-access)

Als u geen beleid voor voorwaardelijke toegang van Azure AD kunt gebruiken in uw organisatie, moet uw IT-beheerder deze stappen volgen:

1. Als u dit nog niet weet, zoek dan uw tenant-id op, zoals wordt beschreven in [Uw tenant-id van Microsoft 365 zoeken.](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)
2. Meld u aan bij het OneDrive-beheercentrum en **selecteer** Synchroniseren in het linkerdeelvenster. Schakel het **selectievakje Synchronisatie alleen** toestaan op pc's die lid zijn van bepaalde domeinen in en voeg vervolgens de tenant-id toe aan de lijst met domeinen. Zie Synchronisatie alleen toestaan op computers die lid zijn [van bepaalde domeinen voor meer informatie.](https://docs.microsoft.com/onedrive/allow-syncing-only-on-specific-domains)

> [!NOTE]
> Deze richtlijnen gelden alleen voor tenants in Het beheerde bureaublad van Microsoft. Er zijn andere instellingen die niet worden besproken in dit artikel.
