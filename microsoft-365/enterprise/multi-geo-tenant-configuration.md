---
title: Tenant configuratie voor Microsoft 365 multi-geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: In dit artikel vindt u informatie over het toevoegen van satelliet locaties en het configureren van uw Tenant voor Microsoft 365 multi-geo.
ms.openlocfilehash: 4276d8ff70fed99e74f2cbab29386c81da06d17b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689110"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a>Tenant configuratie voor Microsoft 365 multi-geo

Voordat u uw Tenant voor Microsoft 365 multi-geo configureert, moet u ervoor zorgen dat u het [abonnement voor Microsoft 365 multi-geo](plan-for-multi-geo.md)hebt. Als u de stappen in dit artikel wilt uitvoeren, hebt u een lijst met de geografische locaties nodig die u wilt inschakelen als satelliet locaties en de test gebruikers die u wilt inrichten voor die locaties.

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a>De mogelijkheden voor meervoudige geo in uw Microsoft 365-abonnement aan uw Tenant toevoegen

Als u Microsoft 365 multi-geo wilt gebruiken, hebt u de _mogelijkheden voor meervoudige geo in Microsoft 365_ -abonnement nodig. Werk met uw accountteam om dit abonnement toe te voegen aan uw Tenant. Uw accountteam verbindt u met de juiste licentie specialist en de Tenant is geconfigureerd.

Houd er rekening mee dat de _mogelijkheden voor meervoudige geo in Microsoft 365 van_ een serviceplan op gebruikersniveau zijn. U hebt een licentie nodig voor elke gebruiker die u wilt hosten op een satelliet locatie. U kunt meer licenties toevoegen aan de tijd wanneer u gebruikers toevoegt aan locaties van satellieten.

Wanneer uw Tenant is voorzien van de mogelijkheden voor  _Meervoudige geo in Microsoft 365_ , is het tabblad **geografische locaties** beschikbaar in de OneDrive en SharePoint-beheer centra.

## <a name="add-satellite-locations-to-your-tenant"></a>Satelliet locaties toevoegen aan uw Tenant

U moet een satelliet locatie toevoegen voor elke geografische locatie waar u gegevens wilt opslaan. Beschikbare geografische locaties worden weergegeven in de volgende tabel:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![Schermafbeelding van de pagina geografische locaties in het SharePoint-Beheercentrum](../media/sharepoint-multi-geo-admin-center.png)

Een locatie voor satelliet toevoegen

1. Open het SharePoint-beheercentrum.

2. Ga naar het tabblad **geo locations** .

3. Klik op **locatie toevoegen**.

4. Selecteer de locatie die u wilt toevoegen en klik op **volgende**.

5. Typ het domein dat u wilt gebruiken met de geografische locatie en klik op **toevoegen**.

6. Klik op **Sluiten**.

Het inrichten kan van enkele uren tot 72 uur duren, afhankelijk van de grootte van de Tenant. Nadat het inrichten van een satelliet locatie is voltooid, ontvangt u een e-mail bevestiging. Wanneer de nieuwe geografische locatie blauw wordt weergegeven op de kaart op het tabblad **geografische locaties** in het OneDrive-Beheercentrum, kunt u doorgaan met het instellen van de gewenste gegevenslocatie van gebruikers naar die geografische locatie. 

> [!IMPORTANT]
> De nieuwe locatie van de satelliet wordt ingesteld met de standaardinstellingen. Op die manier kunt u die satelliet locatie zo configureren dat dit van toepassing is op uw lokale nalevings behoeften.

## <a name="setting-users-preferred-data-location"></a>Voorkeur van de gebruikerslocatie van de gebruikers instellen
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

Wanneer u de benodigde satelliet locaties hebt ingeschakeld, kunt u uw gebruikersaccounts bijwerken voor gebruik van de juiste gegevenslocatie van uw voorkeur. We raden u aan om voor elke gebruiker een voorkeurs gegevenslocatie in te stellen, ook als deze gebruiker op de centrale locatie woont.

> [!IMPORTANT]
> Als de voorkeurs gegevenslocatie van een gebruiker is ingesteld op een locatie die niet is geconfigureerd als een satelliet locatie of de centrale locatie, wordt het systeem standaard ingesteld op de centrale locatie bij het inrichten van OneDrive-en SharePoint-sites en de groeps postvakken.

> [!TIP]
> U wordt geadviseerd om op basis van validaties te beginnen met een testgebruiker of een kleine groep gebruikers voordat u meerdere geografische rollen gebruikt voor de bredere organisatie.

In azure Active Directory (Azure AD) zijn twee soorten gebruikersobjecten: alleen Cloud gebruikers en gesynchroniseerde gebruikers. Volg de juiste instructies voor uw type gebruiker.

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a>De voorkeurs gegevenslocatie van de gebruiker synchroniseren met Azure AD Connect 

Als de gebruikers van uw bedrijf worden gesynchroniseerd vanuit een on-premises Active Directory-systeem naar Azure AD, moet hun PreferredDataLocation worden ingevuld in AD en gesynchroniseerd met Azure AD.

Volg het proces in [Azure Active Directory Connect Sync: Configureer de gewenste gegevenslocatie voor Microsoft 365-bronnen](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) om de synchronisatie van de gewenste gegevenslocatie te configureren vanuit uw on-premises Active Directory Domain Services (AD DS) naar Azure AD.

U wordt aangeraden de voorkeurs gegevenslocatie van de gebruiker in te stellen als onderdeel van uw standaard werkstroom voor het maken van gebruikers.

> [!IMPORTANT]
> Als er nieuwe gebruikers zijn met geen OneDrive-ingerichte, wacht u minstens 24 uur nadat de PDL van een gebruiker is gesynchroniseerd met Azure AD zodat de wijzigingen worden doorgevoerd voordat de gebruiker zich aanmeldt bij OneDrive voor bedrijven. (Wanneer de gebruiker zich aanmeldt voor het instellen van de locatie van OneDrive voor bedrijven, kunt u het beste de nieuwe OneDrive van de gebruiker op de juiste locatie inrichten).

### <a name="setting-preferred-data-location-for-cloud-only-users"></a>Voorkeurs gegevenslocatie instellen voor gebruikers met Cloud only 

Als de gebruikers van uw bedrijf niet worden gesynchroniseerd vanuit een on-premises Active Directory-systeem naar Azure AD, betekent dit dat ze zijn gemaakt in Microsoft 365 of Azure AD en moet de PDL-module van de Microsoft Azure Active Directory-module voor Windows PowerShell worden ingesteld.

Voor de procedures in deze sectie is de [Microsoft Azure Active Directory-module voor Windows PowerShell module](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0)vereist. Als u deze module al hebt geïnstalleerd, moet u ervoor zorgen dat u de nieuwste versie bijwerkt.

1.  [Maak verbinding en meld](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) u aan met een set globale beheerdersreferenties voor uw Tenant.

2.  U kunt de [set-MsolUser-](https://docs.microsoft.com/powershell/msonline/v1/set-msoluser) cmdlet gebruiken om de voorkeurs gegevenslocatie voor alle gebruikers in te stellen. Bijvoorbeeld:

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    Met de cmdlet Get-MsolUser kunt u controleren of de locatie van de voorkeurs gegevens juist is bijgewerkt. Bijvoorbeeld:

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![Schermafbeelding van het PowerShell-venster met set-msoluser](../media/multi-geo-tenant-configuration-image3.png)

U wordt aangeraden de voorkeurs gegevenslocatie van de gebruiker in te stellen als onderdeel van uw standaard werkstroom voor het maken van gebruikers.

> [!IMPORTANT]
> Als er nieuwe gebruikers zijn met geen OneDrive, wacht u minstens 24 uur nadat de PDL van een gebruiker is ingesteld op de wijzigingen doorgeven voordat de gebruiker zich aanmeldt bij OneDrive. (Wanneer de gebruiker zich aanmeldt voor het instellen van de locatie van OneDrive voor bedrijven, kunt u het beste de nieuwe OneDrive van de gebruiker op de juiste locatie inrichten).

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a>OneDrive inrichten en het effect van PDL

Als de gebruiker al een OneDrive-site in de Tenant heeft gemaakt, wordt de bestaande OneDrive niet automatisch verplaatst via de team site. Als u OneDrive van een gebruiker wilt verplaatsen, raadpleegt u [overstappen op onedrive voor bedrijven](move-onedrive-between-geo-locations.md) en volgt u de instructies in onedrive verplaatsen tussen geo-locaties. (Houd er rekening mee dat het Exchange-postvak van de gebruiker automatisch wordt verplaatst wanneer u de PDL van de gebruiker instelt.)

Als de gebruiker geen OneDrive-site in de Tenant heeft, wordt deze in overeenstemming met hun PDL-waarde ingericht, op voorwaarde dat de PDL voor de gebruiker overeenkomt met een van de satelliet locaties van het bedrijf.

## <a name="configuring-multi-geo-search"></a>Meerdere geografische zoekopdrachten configureren

Uw Tenant voor meervoudige geo-en zoekmogelijkheden biedt een zoekopdracht waarmee een zoekopdracht de resultaten van een willekeurige plaats binnen de Tenant kan retourneren.

Standaard worden in zoekresultaten samengestelde resultaten geretourneerd, zelfs als elke zoekindex zich in de betreffende geografische locatie bevindt:

- OneDrive voor Bedrijven

- Delve

- SharePoint-Startpagina

- Zoekcentrum

U kunt ook de zoekfuncties voor meervoudige geo configureren voor uw aangepaste zoektoepassingen die gebruikmaken van de SharePoint-zoek-API.

Kijk voor meer informatie [over het configureren van de zoekfunctie voor OneDrive voor bedrijven,](configure-search-for-multi-geo.md) waaronder eventuele beperkingen en verschillen.

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a>De configuratie van Microsoft 365 meerdere geo-geografische configuraties valideren

Hieronder vindt u enkele basis situaties die u mogelijk wilt opnemen in uw validatie plan voordat u Microsoft 365 meerdere geografische rollen uitvoert voor uw bedrijf. Wanneer u deze tests en eventuele extra use cases die relevant zijn voor uw bedrijf hebt voltooid, kunt u ervoor kiezen om de gebruikers toe te voegen aan de aanvankelijke testgroep.

**OneDrive voor Bedrijven**

Selecteer OneDrive in het startprogramma voor apps van Microsoft 365 en bevestig dat u automatisch wordt doorgestuurd naar de juiste geografische locatie voor de gebruiker, op basis van de PDL van de gebruiker. OneDrive voor bedrijven moet nu op die locatie beginnen met inrichten. Probeer een aantal documenten te uploaden en te downloaden als u dit hebt ingericht.

**Mobiele OneDrive-app**

Meld u aan bij uw mobiele OneDrive-app met de referenties van uw testaccount. Ga na of u de bestanden van OneDrive voor bedrijven kunt zien en er met ze op kunt werken vanaf uw mobiele apparaat.

**OneDrive-synchronisatieclient**

Ga na of de OneDrive-synchronisatieclient automatisch de geo-locatie van OneDrive voor bedrijven detecteert wanneer u zich aanmeldt. Als u de synchronisatieclient moet downloaden, kunt u op **synchroniseren** klikken in de OneDrive-bibliotheek.

**Office-toepassingen**

Ga na of u toegang hebt tot OneDrive voor bedrijven door u aan te melden bij een Office-toepassing, zoals Word. Open de Office-toepassing en selecteer OneDrive- <TenantName> . Uw OneDrive-locatie wordt door Office herkend en u ziet de bestanden die u kunt openen.

**Delen**

Probeer OneDrive-bestanden te delen. Ga na of de persoon kiezen al uw SharePoint Online-gebruikers ziet, ongeacht hun geografische locatie.
