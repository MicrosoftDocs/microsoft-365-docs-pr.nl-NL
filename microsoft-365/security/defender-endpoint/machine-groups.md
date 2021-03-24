---
title: Apparaatgroepen maken en beheren in Microsoft Defender ATP
description: Maak apparaatgroepen en stel geautomatiseerde herstelniveaus op deze in door de regels in vertrouwen te nemen die van toepassing zijn op de groep
keywords: apparaatgroepen, groepen, herstel, niveau, regels, aadgroep, rol, toewijzen, rang
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dfc7c04bbde2b7061c92f5a25115b75a2f5b47b5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059413"
---
# <a name="create-and-manage-device-groups"></a>Apparaatgroepen maken en beheren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Azure Active Directory
- Office 365

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


In een ondernemingsscenario krijgen beveiligingsbewerkingsteams meestal een set apparaten toegewezen. Deze apparaten worden gegroepeerd op basis van een set kenmerken, zoals hun domeinen, computernamen of aangewezen tags.

In Microsoft Defender voor Eindpunt kunt u apparaatgroepen maken en deze gebruiken om:
- Toegang tot gerelateerde waarschuwingen en gegevens beperken tot specifieke Azure AD-gebruikersgroepen [met toegewezen RBAC-rollen](rbac.md) 
- Verschillende instellingen voor automatisch herstel configureren voor verschillende sets apparaten
- Specifieke herstelniveaus toewijzen die moeten worden toegepast tijdens geautomatiseerde onderzoeken
- Filter in een onderzoek de lijst **Apparaten** op alleen specifieke apparaatgroepen met behulp van het **filter** Groeperen.

U kunt apparaatgroepen maken in de context van op rollen gebaseerde toegang (RBAC) om te bepalen wie specifieke actie kan ondernemen of informatie kan bekijken door de apparaatgroep(s) toe te wijzen aan een gebruikersgroep. Zie Portaltoegang beheren met behulp van op rollen [gebaseerd toegangsbeheer voor meer informatie.](rbac.md)

>[!TIP]
> Lees voor een uitgebreid overzicht van de toepassing RBAC: [Is uw SOC plat met RBAC.](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)

Als onderdeel van het proces voor het maken van een apparaatgroep, gaat u als volgende te werk:
- Stel het geautomatiseerde herstelniveau voor die groep in. Zie Geautomatiseerde onderzoeken gebruiken om bedreigingen te onderzoeken en te corrigeren voor meer informatie over [herstelniveaus.](automated-investigations.md)
- Geef de overeenkomende regel op waarmee wordt bepaald welke apparaatgroep tot de groep behoort op basis van de apparaatnaam, het domein, de tags en het besturingssysteemplatform. Als een apparaat ook is afgestemd op andere groepen, wordt het alleen toegevoegd aan de groep met de hoogst gerangschikte apparaten.
- Selecteer de Azure AD-gebruikersgroep die toegang moet hebben tot de apparaatgroep.
- Rangschik de apparaatgroep ten opzichte van andere groepen nadat deze is gemaakt.

>[!NOTE]
>Een apparaatgroep is toegankelijk voor alle gebruikers als u er geen Azure AD-groepen aan toewijst.

## <a name="create-a-device-group"></a>Een apparaatgroep maken

1. Selecteer in het navigatiedeelvenster **Instellingen**  >  **Apparaatgroepen.**

2. Klik **op Apparaatgroep toevoegen.**

3. Voer de groepsnaam- en automatiseringsinstellingen in en geef de overeenkomende regel op die bepaalt welke apparaten tot de groep behoren. Zie [Hoe het geautomatiseerde onderzoek wordt gestart.](automated-investigations.md#how-the-automated-investigation-starts)

    >[!TIP]
    >Als u apparaten per organisatie-eenheid wilt groeperen, kunt u de registersleutel configureren voor de groep. Zie Apparaatlabels maken en beheren voor meer informatie over [apparaatlabels.](machine-tags.md)

4. Bekijk een voorbeeld van verschillende apparaten die door deze regel worden gematcht. Als u tevreden bent over de regel, klikt u op **het tabblad Gebruikerstoegang.**

5. Wijs de gebruikersgroepen toe die toegang hebben tot de apparaatgroep die u hebt gemaakt.

    >[!NOTE]
    >U kunt alleen toegang verlenen tot Azure AD-gebruikersgroepen die zijn toegewezen aan RBAC-rollen.

6. Klik op **Sluiten**. De configuratiewijzigingen worden toegepast.

## <a name="manage-device-groups"></a>Apparaatgroepen beheren

U kunt de rang van een apparaatgroep promoten of verlagen, zodat deze hogere of lagere prioriteit krijgt tijdens het koppelen. Wanneer een apparaat is afgestemd op meer dan één groep, wordt het alleen toegevoegd aan de groep met de hoogste rangschikking. U kunt ook groepen bewerken en verwijderen.

>[!WARNING]
>Het verwijderen van een apparaatgroep kan van invloed zijn op regels voor e-mailmeldingen. Als een apparaatgroep is geconfigureerd onder een meldingsregel voor e-mail, wordt deze uit die regel verwijderd. Als de apparaatgroep de enige groep is die is geconfigureerd voor een e-mailmelding, wordt deze regel voor e-mailmeldingen samen met de apparaatgroep verwijderd.

Apparaatgroepen zijn standaard toegankelijk voor alle gebruikers met portaltoegang. U kunt het standaardgedrag wijzigen door Azure AD-gebruikersgroepen toe te wijzen aan de apparaatgroep.

Apparaten die niet zijn afgestemd op groepen, worden toegevoegd aan groep Niet-gegroepeerde apparaten (standaard). U kunt de rang van deze groep niet wijzigen of verwijderen. U kunt echter het herstelniveau van deze groep wijzigen en de Azure AD-gebruikersgroepen definiëren die toegang hebben tot deze groep.

>[!NOTE]
> Het kan enkele minuten duren voordat wijzigingen worden toegepast op de configuratie van de apparaatgroep.

## <a name="related-topics"></a>Verwante onderwerpen

- [Portaltoegang beheren met behulp van op rollen gebaseerd toegangsbeheer](rbac.md)
- [Apparaatlabels maken en beheren](machine-tags.md)
- [Lijst met tenantapparaatgroepen met Behulp van Graph API](https://docs.microsoft.com/graph/api/device-list-memberof)
