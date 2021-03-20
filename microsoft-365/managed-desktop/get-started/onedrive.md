---
title: Microsoft OneDrive
description: Hoe Microsoft Managed Desktop OneDrive voor geregistreerde apparaten in stelt
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, apps, line-of-business-apps, LOB-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a26500c1671afffc7b70d509a4242914631b937c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904838"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft Managed Desktop gebruikt [OneDrive voor Bedrijven](/onedrive/plan-onedrive-enterprise) als cloudopslagservice voor alle beheerde bureaubladapparaten van Microsoft om ervoor te zorgen dat de apparaten zo stateloos mogelijk zijn. Gebruikers kunnen hun bestanden vinden, ongeacht op welk apparaat ze zich aanmelden. Als u bijvoorbeeld een Microsoft Managed Desktop-apparaat vervangt door een nieuw apparaat, worden bestanden automatisch gesynchroniseerd met het nieuwe apparaat.

Deze instellingen worden standaard automatisch geconfigureerd op Beheerde apparaten van Microsoft:

- OneDrive is geruisloos geconfigureerd met het gebruikersaccount en automatisch aangemeld (zonder interactie met de gebruiker) bij het gebruikersaccount dat is gebruikt om u aan te melden bij Windows. Zie Gebruikersaccounts [geruisloos configureren - OneDrive voor meer informatie](/onedrive/use-silent-account-configuration)

- De functie Files-On-Demand is ingeschakeld, zodat gebruikers toegang hebben tot bestanden vanuit hun cloudopslag in OneDrive zonder dat ze onnodig schijfruimte moeten gebruiken. Zie Schijfruimte opslaan met [OneDrive Files On-Demand voor Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)voor meer informatie.

- De functie Bekende map verplaatsen is in stilte ingeschakeld om een back-up te maken van de gegevens van gebruikers in de cloud, waardoor ze vanaf elk apparaat toegang hebben tot hun bestanden. Zie Een back-up maken van uw documenten, afbeeldingen en [bureaubladmappen met OneDrive voor meer informatie.](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)

- Gebruikers kunnen de functie Bekende map verplaatsen niet uitschakelen of de locatie van bekende mappen wijzigen om een consistente ervaring te garanderen op Microsoft Managed Desktop-apparaten.

## <a name="user-experience"></a>Gebruikerservaring

Wanneer Microsoft Managed Desktop-gebruikers een nieuw apparaat ontvangen, kunnen ze eerst hun Azure-referenties invoeren tijdens het instellen van het apparaat. Nadat dit proces is voltooid, hebben ze toegang tot hun bureaublad en hebben ze de OneDrive-ervaring.

1. Het systeem laat gebruikers weten dat OneDrive is geconfigureerd en dat ze automatisch zijn aangemeld bij OneDrive.

:::image type="content" source="media/onedrive-sync.png" alt-text="Wanneer u meldingen leest, synchroniseert u OneDrive en kunt u bestanden bewerken in OneDrive. klik hier om uw bestanden te bekijken":::

2. Het systeem laat gebruikers weten dat Map verplaatsen in OneDrive voor hen is geconfigureerd.

:::image type="content" source="media/onedrive-folders.png" alt-text="Melding lezen Uw IT-afdeling heeft een back-up van uw belangrijke mappen. De mappen maken nu een back-up van OneDrive en zijn beschikbaar vanaf andere apparaten":::

3. Als u dubbele pictogrammen op het bureaublad wilt voorkomen wanneer apparaten opnieuw worden ingesteld of opnieuw worden gemaakt, worden microsoft Edge- en Microsoft Teams-pictogrammen automatisch verwijderd uit de OneDrive-synchronisatie, zoals wordt weergegeven in deze weergave in Verkenner.

:::image type="content" source="media/onedrive-teams.png" alt-text="Verkenner met Teams- en Edge-vermeldingen met geweerd selectievakjes en tekst met muisaanwijzer lezen Uitgesloten van synchronisatie.":::


## <a name="onedrive-sync-restrictions"></a>Synchronisatiebeperkingen voor OneDrive

Als u de synchronisatie van OneDrive wilt beperken, raden we u aan toegang te bepalen met een Beleid voor voorwaardelijke toegang van Azure Active Directory. Zie Ondersteuning voor voorwaardelijke toegang inschakelen [in de OneDrive-synchronisatie-app](/onedrive/enable-conditional-access)voor meer informatie.

Als u geen beleid voor voorwaardelijke toegang van Azure AD in uw organisatie kunt gebruiken, moet uw IT-beheerder de volgende stappen uitvoeren:

1. Als u dit nog niet weet, kunt u uw tenant-id op zoeken, zoals wordt beschreven in [Uw Microsoft 365-tenant-id zoeken.](/onedrive/find-your-office-365-tenant-id)
2. Meld u aan bij het OneDrive-beheercentrum en selecteer vervolgens **Synchroniseren** in het linkerdeelvenster. Schakel het **selectievakje Alleen synchroniseren toestaan op pc's** die zijn verbonden met specifieke domeinen in en voeg vervolgens de tenant-id toe aan de lijst met domeinen. Zie Alleen synchroniseren toestaan op computers die zijn verbonden met [specifieke domeinen voor meer informatie.](/onedrive/allow-syncing-only-on-specific-domains)

> [!NOTE]
> Deze richtlijn is alleen van toepassing op tenants in Microsoft Managed Desktop. Er zijn andere instellingen in gebruik die niet worden besproken in dit artikel.