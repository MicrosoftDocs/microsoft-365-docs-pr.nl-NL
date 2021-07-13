---
title: Basislijnen Microsoft 365 Lighthouse implementeren
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Voor MSP's (Managed Service Providers) met Microsoft 365 Lighthouse, leert u hoe u Microsoft 365 Lighthouse basislijnen implementeert.
ms.openlocfilehash: 0bda7edec2a200e51e734db64e2b703a027e57bb
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395193"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>Basislijnen Microsoft 365 Lighthouse implementeren 

> [!NOTE]
> De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn alleen beschikbaar voor partners die aan de vereisten [voldoen.](m365-lighthouse-requirements.md) Als uw organisatie geen Microsoft 365 Lighthouse, zie [Registreren voor Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse basislijnen kunt u standaard beheerde tenantconfiguraties implementeren om tenantgebruikers, apparaten en gegevens te beveiligen. Er zijn zes standaardlijnconfiguraties die standaard worden geleverd met Microsoft 365 Lighthouse:

- MFA vereisen voor beheerders
- MFA vereisen voor eindgebruikers
- Oudere verificatie blokkeren
- Apparaatinschrijving instellen in Microsoft Endpoint Manager : Azure AD Join
- Defender Anti-virusbeleid configureren voor Windows apparaten
- Compliancebeleid configureren voor Windows apparaten

## <a name="before-you-begin"></a>Voordat u begint

Zorg ervoor dat u en uw klantten tenants voldoen aan de vereisten die worden vermeld in [Vereisten voor Microsoft 365 Lighthouse.](m365-lighthouse-requirements.md)

## <a name="learn-more-about-the-default-baseline"></a>Meer informatie over de standaardlijnlijn

Selecteer **Basislijnen** in het linkernavigatiedeelvenster om de pagina Basislijnen te openen. U ziet dat de standaardlijnlijn al is toegevoegd aan de standaardten tenantgroep (alle tenants). Als u de standaardconfiguraties voor basislijn wilt weergeven, selecteert u **Basislijn weergeven** om de pagina Standaard basislijn te openen. De configuraties worden weergegeven als implementatiestappen. Selecteer een van de implementatiestappen om de implementatiedetails en de invloed van de gebruiker weer te geven.

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Schermafbeelding van de standaardpagina basislijn.>.":::

## <a name="deploy-a-baseline-configuration"></a>Een basislijnconfiguratie implementeren  

1. Selecteer op de linkernavigatiepagina **Tenants om** een lijst met uw onboarded tenants weer te geven.

2. Selecteer de tenant waar u de basislijnconfiguratie wilt implementeren.

3. Selecteer het **tabblad Implementatieplan** om alle implementatiestappen te zien van de basislijn die zijn toegevoegd aan het implementatieplan van de tenant.

4. Selecteer een implementatiestap om de pagina met de implementatiestap te openen.

5. Selecteer **Toepassen** om de geselecteerde implementatiestap toe te passen op de tenant. Als de implementatiestap 'Voor deze actie is een handmatige stap vereist' wordt aangegeven, moet u de handmatige stap voltooien, zodat de implementatiestap correct wordt toegepast.

## <a name="related-content"></a>Verwante inhoud

[Overzicht van het gebruik van basislijnen voor het implementeren van standaardtenderconfiguraties](m365-lighthouse-deploying-standard-tenant-configurations-overview.md) (artikel)\
[Microsoft 365 Lighthouse veelgestelde vragen](m365-lighthouse-faq.yml) (artikel)