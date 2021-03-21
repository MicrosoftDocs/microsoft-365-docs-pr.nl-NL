---
title: Microsoft 365 Multi-Geo tenantconfiguratie
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
description: In dit artikel leert u hoe u satellietlocaties toevoegt en uw tenant configureert voor Microsoft 365 Multi-Geo.
ms.openlocfilehash: 9176c66e8d0aa7e893ef137131147f8e0c85d3ac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923646"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a>Microsoft 365 Multi-Geo tenantconfiguratie

Voordat u uw tenant configureert voor Microsoft 365 [Multi-Geo, moet u Plan voor Microsoft 365 Multi-Geo hebben gelezen.](plan-for-multi-geo.md) Als u de stappen in dit artikel wilt volgen, hebt u een lijst nodig met de geografische locaties die u wilt inschakelen als satellietlocaties en de testgebruikers die u wilt inrichten voor die locaties.

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a>De multi-geo-mogelijkheden in uw Microsoft 365-abonnement toevoegen aan uw tenant

Als u Microsoft 365 Multi-Geo wilt gebruiken, hebt u de _Multi-Geo-mogelijkheden in microsoft 365-abonnement_ nodig. Werk samen met uw accountteam om dit plan toe te voegen aan uw tenant. Uw accountteam verbindt u met de juiste licentiespecialist en laat uw tenant configureren.

Houd er rekening _mee dat de Multi-Geo Capabilities in Microsoft 365-abonnement_ een serviceplan op gebruikersniveau zijn. U hebt een licentie nodig voor elke gebruiker die u wilt hosten op een satellietlocatie. U kunt in de tijd meer licenties toevoegen als u gebruikers toevoegt op satellietlocaties.

Zodra uw tenant is ingericht met de  _multi-geo-mogelijkheden in microsoft 365-abonnement,_ wordt het tabblad Geolocaties beschikbaar in de OneDrive- en SharePoint-beheercentra.

## <a name="add-satellite-locations-to-your-tenant"></a>Satellietlocaties toevoegen aan uw tenant

U moet een satellietlocatie toevoegen voor elke geografische locatie waar u gegevens wilt opslaan. Beschikbare geografische locaties worden weergegeven in de volgende tabel:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![Schermafbeelding van de pagina geolocaties in het SharePoint-beheercentrum](../media/sharepoint-multi-geo-admin-center.png)

Een satellietlocatie toevoegen

1. Open het SharePoint-beheercentrum.

2. Ga naar het **tabblad Geolocaties.**

3. Klik **op Locatie toevoegen.**

4. Selecteer de locatie die u wilt toevoegen en klik vervolgens op **Volgende.**

5. Typ het domein dat u wilt gebruiken met de geografische locatie en klik vervolgens op **Toevoegen.**

6. Klik op **Sluiten**.

Inrichting kan enkele uren tot 72 uur duren, afhankelijk van de grootte van uw tenant. Wanneer de inrichting van een satellietlocatie is voltooid, ontvangt u een bevestiging per e-mail. Wanneer de nieuwe geografische locatie blauw wordt  weergegeven op de kaart op het tabblad Geolocaties in het OneDrive-beheercentrum, kunt u doorgaan met het instellen van de gewenste gegevenslocatie van gebruikers op die geografische locatie. 

> [!IMPORTANT]
> Uw nieuwe satellietlocatie wordt ingesteld met standaardinstellingen. Op deze manier kunt u die satellietlocatie zo configureren dat deze geschikt is voor uw lokale nalevingsbehoeften.

## <a name="setting-users-preferred-data-location"></a>De gewenste gegevenslocatie van gebruikers instellen
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

Nadat u de benodigde satellietlocaties hebt ingeschakeld, kunt u uw gebruikersaccounts bijwerken om de gewenste gegevenslocatie te gebruiken. We raden u aan een voorkeurslocatie voor gegevens in te stellen voor elke gebruiker, zelfs als deze gebruiker zich op de centrale locatie bevindt.

> [!IMPORTANT]
> Als de gewenste gegevenslocatie van een gebruiker is ingesteld op een locatie die niet is geconfigureerd als een satellietlocatie of de centrale locatie, wordt het systeem standaard op de centrale locatie ingesteld bij het inrichten van OneDrive- en SharePoint-sites en Groepspostvakken.

> [!TIP]
> U wordt aangeraden validaties te starten met een testgebruiker of een kleine groep gebruikers voordat u multi-geo uitrolt naar uw bredere organisatie.

In Azure Active Directory (Azure AD) zijn er twee typen gebruikersobjecten: alleen cloudgebruikers en gesynchroniseerde gebruikers. Volg de juiste instructies voor uw type gebruiker.

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a>De voorkeurslocatie voor gegevens van de gebruiker synchroniseren met Azure AD Connect 

Als de gebruikers van uw bedrijf worden gesynchroniseerd van een on-premises Active Directory-systeem naar Azure AD, moet hun PreferredDataLocation worden ingevuld in AD en worden gesynchroniseerd met Azure AD.

Volg het proces in Azure Active Directory Connect-synchronisatie: Configureer voorkeursgegevenslocatie voor [Microsoft 365-resources](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) om synchronisatie van voorkeursgegevenslocatie te configureren van uw on-premises Active Directory Domain Services (AD DS) naar Azure AD.

U wordt aangeraden de voorkeurslocatie voor gegevens van de gebruiker in te stellen als onderdeel van uw standaardwerkstroom voor het maken van gebruikers.

> [!IMPORTANT]
> Voor nieuwe gebruikers zonder OneDrive-inrichting moet u ten minste 24 uur wachten nadat de PDL van een gebruiker is gesynchroniseerd met Azure AD voordat de gebruiker zich aanmeldt bij OneDrive voor Bedrijven. (Als u de gewenste gegevenslocatie instelt voordat de gebruiker zich aanmeldt om zijn of haar OneDrive voor Bedrijven in te delen, zorgt u ervoor dat de nieuwe OneDrive van de gebruiker op de juiste locatie wordt ingericht.)

### <a name="setting-preferred-data-location-for-cloud-only-users"></a>Voorkeursgegevenslocatie instellen voor alleen gebruikers in de cloud 

Als de gebruikers van uw bedrijf niet worden gesynchroniseerd van een on-premises Active Directory-systeem naar Azure AD, wat betekent dat ze worden gemaakt in Microsoft 365 of Azure AD, moet de PDL worden ingesteld met de Microsoft Azure Active Directory-module voor Windows PowerShell.

Voor de procedures in deze sectie is de [Microsoft Azure Active Directory-module voor Windows PowerShell-module vereist.](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0) Als u deze module al hebt geïnstalleerd, controleert u of u de nieuwste versie hebt bijgewerkt.

1.  [Maak verbinding en meld u aan](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) met een set globale beheerdersreferenties voor uw tenant.

2.  Gebruik de [cmdlet Set-MsolUser](/powershell/msonline/v1/set-msoluser) om de gewenste gegevenslocatie in te stellen voor elk van uw gebruikers. Bijvoorbeeld:

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    U kunt controleren of de gewenste gegevenslocatie correct is bijgewerkt met de Get-MsolUser cmdlet. Bijvoorbeeld:

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![Schermafbeelding van PowerShell-venster met set-msoluser](../media/multi-geo-tenant-configuration-image3.png)

U wordt aangeraden de voorkeurslocatie voor gegevens van de gebruiker in te stellen als onderdeel van uw standaardwerkstroom voor het maken van gebruikers.

> [!IMPORTANT]
> Voor nieuwe gebruikers zonder OneDrive-inrichting moet u ten minste 24 uur wachten nadat de PDL van een gebruiker is ingesteld om de wijzigingen door te voeren voordat de gebruiker zich aanmeldt bij OneDrive. (Als u de gewenste gegevenslocatie instelt voordat de gebruiker zich aanmeldt om zijn of haar OneDrive voor Bedrijven in te delen, zorgt u ervoor dat de nieuwe OneDrive van de gebruiker op de juiste locatie wordt ingericht.)

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a>OneDrive-inrichting en het effect van PDL

Als de gebruiker al een OneDrive-site heeft gemaakt in de tenant, wordt de bestaande OneDrive niet automatisch verplaatst door de PDL in te stellen. Zie OneDrive voor Bedrijven Geo Move als u oneDrive van een gebruiker [wilt verplaatsen.](move-onedrive-between-geo-locations.md)

> [!NOTE]
> Exchange Online verplaatst automatisch het postvak van de gebruiker als de PLD wordt gewijzigd en de Postvakregio niet meer overeenkomt met de geolocatiecode van de postvakdatabase. Zie Exchange Online-postvakken beheren in een [multi-geoomgeving](./administering-exchange-online-multi-geo.md)voor meer informatie.

Als de gebruiker geen OneDrive-site binnen de tenant heeft, wordt OneDrive voor de gebruiker ingericht op basis van de PDL-waarde, ervan uitgaande dat de PDL voor de gebruiker overeenkomt met een van de satellietlocaties van het bedrijf.

## <a name="configuring-multi-geo-search"></a>Zoeken met meerdere geografische gegevens configureren

Uw multi-geoten tenant heeft statistische zoekmogelijkheden waarmee een zoekquery resultaten kan retourneren vanaf elke locatie in de tenant.

Zoekopdrachten op deze invoerpunten leveren standaard statistische resultaten op, ook al bevindt elke zoekindex zich op de relevante geografische locatie:

- OneDrive voor Bedrijven

- Delve

- SharePoint Home

- Zoekcentrum

Bovendien kunnen zoekmogelijkheden met meerdere geografische functies worden geconfigureerd voor uw aangepaste zoektoepassingen die gebruikmaken van de SharePoint-zoek-API.

Raadpleeg [Zoeken naar OneDrive voor Bedrijven Multi-Geo](configure-search-for-multi-geo.md) configureren voor instructies, inclusief eventuele beperkingen en verschillen.

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a>De Configuratie van Microsoft 365 Multi-Geo valideren

Hieronder vindt u enkele basisgebruiksgevallen die u mogelijk wilt opnemen in uw validatieplan voordat u Microsoft 365 Multi-Geo breed uitrolt naar uw bedrijf. Nadat u deze tests en eventuele aanvullende gebruiksgevallen hebt voltooid die relevant zijn voor uw bedrijf, kunt u ervoor kiezen om door te gaan met het toevoegen van de gebruikers in uw eerste testgroep.

**OneDrive voor Bedrijven**

Selecteer OneDrive in het start programma voor apps van Microsoft 365 en bevestig dat u automatisch wordt doorgestuurd naar de juiste geografische locatie voor de gebruiker, op basis van de PDL van de gebruiker. OneDrive voor Bedrijven moet nu beginnen met de inrichting op die locatie. Wanneer u deze hebt ingericht, kunt u proberen om bepaalde documenten te uploaden en te downloaden.

**OneDrive Mobile App**

Meld u aan bij uw mobiele OneDrive-app met uw testaccountreferenties. Bevestig dat u uw OneDrive voor Bedrijven-bestanden kunt zien en dat u er vanaf uw mobiele apparaat mee kunt werken.

**OneDrive-synchronisatieclient**

Controleer of de OneDrive-synchronisatieclient automatisch uw oneDrive voor Bedrijven-geografische locatie detecteert wanneer u zich aanmeldt. Als u de synchronisatieclient wilt downloaden, klikt u op **Synchroniseren** in de OneDrive-bibliotheek.

**Office-toepassingen**

Bevestig dat u toegang hebt tot OneDrive voor Bedrijven door u aan te melden vanuit een Office-toepassing, zoals Word. Open de Office-toepassing en selecteer 'OneDrive – <TenantName> '. Office detecteert uw OneDrive-locatie en toont u de bestanden die u kunt openen.

**Delen**

Probeer OneDrive-bestanden te delen. Controleer of de personen picker u al uw SharePoint Online-gebruikers laat zien, ongeacht hun geografische locatie.