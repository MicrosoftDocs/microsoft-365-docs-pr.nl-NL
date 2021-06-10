---
title: Rollen maken en beheren voor toegangsbeheer op basis van rollen
description: Maak rollen en definieert de machtigingen die aan de rol zijn toegewezen als onderdeel van de implementatie van het toegangsbeheer op basis van rollen in de Microsoft Defender-beveiligingscentrum
keywords: gebruikersrollen, rollen, toegangs-rbac
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
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059237"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a>Rollen maken en beheren voor toegangsbeheer op basis van rollen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a>Rollen maken en de rol toewijzen aan een Azure Active Directory groep

In de volgende stappen vindt u informatie over het maken van rollen in Microsoft Defender-beveiligingscentrum. Er wordt ervan uitgenomen dat u al Azure Active Directory gebruikersgroepen hebt gemaakt.

1. Meld u aan [bij Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com/) account met een beveiligingsbeheerder of globale beheerdersrol toegewezen.

2. Selecteer in het navigatiedeelvenster **Instellingen > Rollen.**

3. Selecteer **Item toevoegen.**

4. Voer de rolnaam, beschrijving en machtigingen in die u wilt toewijzen aan de rol.

5. Selecteer **Volgende** om de rol toe te wijzen aan een Azure AD-beveiligingsgroep.

6. Gebruik het filter om de Azure AD-groep te selecteren die u wilt toevoegen aan deze rol.

7. **Opslaan en sluiten.**

8. Pas de configuratie-instellingen toe.

> [!IMPORTANT]
> Nadat u rollen hebt gemaakt, moet u een apparaatgroep maken en toegang geven tot de apparaatgroep door deze toe te wijzen aan een rol die u zojuist hebt gemaakt.

### <a name="permission-options"></a>Machtigingsopties

- **Gegevens weergeven**
    - **Beveiligingsbewerkingen:** alle gegevens over beveiligingsbewerkingen weergeven in de portal
    - **Bedreiging en vulnerability management** - Bekijk Threat and Vulnerability Management gegevens in de portal

- **Actieve herstelacties**
    - **Beveiligingsbewerkingen:** actie ondernemen, in behandeling zijnde herstelacties goedkeuren of afwijzen, toegestane/geblokkeerde lijsten voor automatisering en indicatoren beheren
    - **Bedreiging en vulnerability management - Afhandeling van uitzonderingen** - Nieuwe uitzonderingen maken en actieve uitzonderingen beheren
    - **Bedreiging en vulnerability management -** Herstelafhandeling - Nieuwe herstelaanvragen indienen, tickets maken en bestaande herstelactiviteiten beheren

- **Onderzoek naar waarschuwingen:** waarschuwingen beheren, geautomatiseerde onderzoeken starten, scans uitvoeren, onderzoekspakketten verzamelen, apparaatlabels beheren en alleen draagbare uitvoerbare (PE)-bestanden downloaden 

- **Portalsysteeminstellingen** beheren : Opslaginstellingen, SIEM- en bedreigingsinstellingen voor Intel API configureren (is globaal van toepassing), geavanceerde instellingen, geautomatiseerde bestands uploads, rollen en apparaatgroepen

    > [!NOTE]
    > Deze instelling is alleen beschikbaar in de microsoft defender voor eindpuntbeheerder (standaardrol).

- **Beveiligingsinstellingen beheren in** het Beveiligingscentrum: instellingen voor het onderdrukken van waarschuwingen configureren, mapuitsluitingen voor automatisering, onboard en offboard-apparaten beheren en e-mailmeldingen beheren, evaluatielab beheren

- **Mogelijkheden voor live-antwoorden**
    - **Basisopdrachten:**
        - Een livereactiesessie starten
        - Alleen-lezen live-antwoordopdrachten uitvoeren op een extern apparaat (met uitzondering van bestandsexemplaar en uitvoering
    - **Geavanceerde** opdrachten:
        - Een bestand downloaden van het externe apparaat via livereactie
        - PE- en niet-PE-bestanden downloaden van de bestandspagina
        - Upload bestand naar het externe apparaat
        - Een script weergeven vanuit de bestandenbibliotheek
        - Een script uitvoeren op het externe apparaat vanuit de bestandenbibliotheek

Zie Apparaten onderzoeken met livereactie voor meer informatie over de beschikbare [opdrachten.](live-response.md)
  
## <a name="edit-roles"></a>Rollen bewerken

1. Meld u aan [bij Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com/) account met beveiligingsbeheerder of globale beheerdersrol toegewezen.

2. Selecteer in het navigatiedeelvenster **Instellingen > Rollen.**

3. Selecteer de rol die u wilt bewerken.

4. Klik op **Bewerken**.

5. Wijzig de details of de groepen die aan de rol zijn toegewezen. 

6. Klik **op Opslaan en sluiten.**

## <a name="delete-roles"></a>Rollen verwijderen

1. Meld u aan [bij Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com/) account met beveiligingsbeheerder of globale beheerdersrol toegewezen.

2. Selecteer in het navigatiedeelvenster **Instellingen > Rollen.**

3. Selecteer de rol die u wilt verwijderen.

4. Klik op de vervolgkeuzeknop en selecteer **Rol verwijderen.**

## <a name="related-topic"></a>Verwant onderwerp

- [Basismachtigingen voor gebruikers voor toegang tot de portal](basic-permissions.md)
- [Apparaatgroepen maken en beheren](machine-groups.md)
