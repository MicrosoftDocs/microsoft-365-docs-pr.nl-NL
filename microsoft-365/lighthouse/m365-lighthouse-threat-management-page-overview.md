---
title: Microsoft 365 Lighthouse Overzicht van de pagina Bedreigingsbeheer
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
description: Voor MSP's (Managed Service Providers) met Microsoft 365 Lighthouse informatie over de pagina Bedreigingsbeheer.
ms.openlocfilehash: 10f39737bb69f4a5080b343cfbe6c6cfe5908d72
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395047"
---
# <a name="microsoft-365-lighthouse-threat-management-page-overview"></a>Microsoft 365 Lighthouse Overzicht van de pagina Bedreigingsbeheer 

> [!NOTE]
> De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn alleen beschikbaar voor partners die aan de vereisten [voldoen.](m365-lighthouse-requirements.md) Als uw organisatie geen Microsoft 365 Lighthouse, zie [Registreren voor Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)

**Van toepassing op:**

- Windows 10

Microsoft Defender Antivirus beschermt tenants, gebruikers en apparaten tegen softwaredreigingen, waaronder virussen, malware en spyware. Het is een krachtige, permanente beveiliging die is ingebouwd in Windows 10 en is opgenomen in Microsoft 365 Business Premium.  
  
Als u de pagina Bedreigingsbeheer in Microsoft 365 Lighthouse wilt openen, selecteert u **Bedreigingsbeheer** in het linkernavigatiedeelvenster om de beveiliging van uw tenants tegen bedreigingen te bekijken. U ziet tenants, gebruikers en apparaten die uw aandacht en aanbevelingen vereisen om de risico's te beperken.  
  
## <a name="overview-tab"></a>Tabblad Overzicht  
  
Op het tabblad Overzicht van de pagina Bedreigingsbeheer kunt u de antivirustoestand in al uw tenants controleren om de gebieden te identificeren die aandacht nodig hebben.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-overview-tab.png" alt-text="Schermafbeelding van het tabblad Overzicht.>.":::

## <a name="threats-tab"></a>Tabblad Bedreigingen

Op het tabblad Bedreigingen van de pagina Bedreigingsbeheer ziet u de bedreigingen Actief, Beperkt, Opgelost en Toegestaan in al uw tenants. U kunt ook meerdere bedreigingen tegelijk in al uw tenants verhelpen door elke bedreiging te filteren en in te boren om te leren welke apparaten, gebruikers of tenants worden beïnvloed.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-threats-tab.png" alt-text="Schermafbeelding van de standaardpagina basislijn.>.":::
  
U kunt bedreigingen filteren op:

- Bedreigingsstatus
- Ernst van bedreiging
- Type bedreiging
- Datumbereik

In de volgende tabel worden de verschillende bedreigingsstatussen en de definitie ervan vermeld:<br><br>

| Bedreigingsstatus | Definitie |
|--|--|
| Actief | Bedreiging is actief op het apparaat. |
| Geen status | Bedreigingsstatus is niet beschikbaar. Voer een volledige scan uit op het apparaat om de bedreiging Microsoft Defender Antivirus te kunnen detecteren. |
| Actie mislukt | Het apparaat loopt geen risico. Een actie is mislukt, maar een mogelijke bedreiging is gestopt en is niet actief op het apparaat. Voer een volledige scan uit op het apparaat. |
| Handmatige stappen vereist | De bedreiging is gestopt, maar hiervoor moet een handmatige stap worden voltooid, zoals een volledige scan of een herstart van het apparaat. |
| Volledige scan vereist | Een volledige scan van het apparaat is vereist. |
| Opnieuw opstarten vereist | Een herstart van het apparaat is vereist. |
| Herstel met niet-kritieke fouten | De bedreiging is gesaneerd en er zijn geen verdere acties nodig. |
| In quarantaine geplaatst | De bedreiging is in quarantaine geplaatst. Er zijn geen verdere acties nodig. |
| Verwijderd | De bedreiging is van het apparaat verwijderd. Er zijn geen verdere acties nodig. |
| Opgeschoond | Microsoft Defender Antivirus bestanden heeft hersteld en gedesinfecteerd. Er zijn geen verdere acties nodig. |
| Toegestaan | De bedreiging is toegestaan door een beheerder om op het apparaat te blijven. | 

## <a name="antivirus-protection-tab"></a>Tabblad Antivirusbeveiliging

Op het tabblad Antivirusbeveiliging op de pagina Bedreigingenbeheer ziet u de apparaten in al uw tenants en de Microsoft Defender Antivirus beveiligingstoestand. U kunt de status beoordelen en actie ondernemen voor een of meer apparaten die mogelijk kwetsbaar zijn. U kunt ook een apparaat selecteren om meer informatie weer te geven, zoals Apparaatoverzicht, Huidige bedreigingen en apparaatactiestatussen.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-antivirus-tab.png" alt-text="Schermafbeelding van het tabblad Antivirus.":::

## <a name="related-content"></a>Verwante inhoud

[Basislijnen Microsoft 365 Lighthouse implementeren](m365-lighthouse-deploy-baselines.md) (artikel)\
[Microsoft 365 Lighthouse veelgestelde vragen](m365-lighthouse-faq.yml) (artikel)
