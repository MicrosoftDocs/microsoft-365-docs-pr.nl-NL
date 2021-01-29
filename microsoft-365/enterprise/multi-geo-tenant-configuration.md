---
title: Configuratie van Microsoft 365 Multi Geo-tenant
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
ms.openlocfilehash: fb907c02a4714c5a2d8e47245321252e7186a8a7
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040566"
---
# <a name="microsoft-365-multi-geo-tenant-configuration"></a>Configuratie van Microsoft 365 Multi Geo-tenant

Voordat u uw tenant voor Microsoft 365 Multi-Geo configureert, moet u [Plan voor Microsoft 365 Multi-Geo hebben gelezen.](plan-for-multi-geo.md) Voor het uitvoeren van de stappen in dit artikel hebt u een lijst nodig met de geografische locaties die u als satellietlocaties wilt inschakelen en de testgebruikers die u voor deze locaties wilt inrichten.

## <a name="add-the-multi-geo-capabilities-in-your-microsoft-365-plan-to-your-tenant"></a>De Multi-Geo Capabilities in uw Microsoft 365-abonnement toevoegen aan uw tenant

Als u Microsoft 365 Multi-Geo wilt gebruiken, hebt u de _Multi-Geo Capabilities in Microsoft 365-abonnement_ nodig. Werk samen met uw accountteam om dit plan toe te voegen aan uw tenant. Uw accountteam verbindt u met de juiste licentiespecialist en laat uw tenant configureren.

Het _Multi-Geo Capabilities in Microsoft 365-abonnement_ is een serviceplan op gebruikersniveau. U hebt een licentie nodig voor elke gebruiker die u op een satellietlocatie wilt hosten. U kunt in de tijd meer licenties toevoegen als u gebruikers op satellietlocaties toevoegt.

Nadat uw tenant is ingericht met het _Multi-Geo Capabilities in Microsoft 365-abonnement,_ wordt het tabblad Geografische locaties beschikbaar in de OneDrive- en SharePoint-beheercentra. 

## <a name="add-satellite-locations-to-your-tenant"></a>Satellietlocaties toevoegen aan uw tenant

U moet een satellietlocatie toevoegen voor elke geografische locatie waar u gegevens wilt opslaan. Beschikbare geografische locaties worden weergegeven in de volgende tabel:

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

![Schermafbeelding van de pagina geografische locaties in het SharePoint-beheercentrum](../media/sharepoint-multi-geo-admin-center.png)

Een satellietlocatie toevoegen

1. Open het SharePoint-beheercentrum.

2. Ga naar het **tabblad Geografische** locaties.

3. Klik **op Locatie toevoegen.**

4. Selecteer de locatie die u wilt toevoegen en klik op **Volgende.**

5. Typ het domein dat u wilt gebruiken met de geografische locatie en klik op **Toevoegen.**

6. Klik op **Sluiten**.

De inrichting kan enkele uren tot 72 uur duren, afhankelijk van de grootte van uw tenant. Zodra de inrichting van een satellietlocatie is voltooid, ontvangt u per e-mail een bevestiging. Wanneer de nieuwe geografische locatie blauw wordt  weergegeven op de kaart op het tabblad Geografische locaties in het OneDrive-beheercentrum, kunt u verdergaan met het instellen van de gewenste gegevenslocatie voor gebruikers op die geografische locatie. 

> [!IMPORTANT]
> De nieuwe satellietlocatie wordt ingesteld met standaardinstellingen. Hierdoor kunt u die satellietlocatie zo configureren dat deze voldoet aan uw lokale nalevingsbehoeften.

## <a name="setting-users-preferred-data-location"></a>De voorkeurslocatie voor gegevens van gebruikers instellen
<span id="_Setting_a_User's" class="anchor"><span id="_Toc508109326" class="anchor"></span></span> 

Zodra u de benodigde satellietlocaties hebt ingeschakeld, kunt u uw gebruikersaccounts bijwerken om de juiste voorkeursgegevenslocatie te gebruiken. Het is raadzaam om voor elke gebruiker een voorkeursgegevenslocatie in te stellen, zelfs als die gebruiker op de centrale locatie blijft.

> [!IMPORTANT]
> Als de voorkeursgegevenslocatie van een gebruiker is ingesteld op een locatie die niet is geconfigureerd als een satellietlocatie of centrale locatie, wordt het systeem standaard ingesteld op de centrale locatie bij het inrichten van OneDrive- en SharePoint-sites en groepspostvakken.

> [!TIP]
> Het is raadzaam validaties te starten met een testgebruiker of een kleine groep gebruikers voordat u multige geo uitrolt naar uw bredere organisatie.

In Azure Active Directory (Azure AD) zijn er twee typen gebruikersobjecten: alleen cloudgebruikers en gesynchroniseerde gebruikers. Volg de juiste instructies voor uw type gebruiker.

### <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a>De voorkeursgegevenslocatie van de gebruiker synchroniseren met Azure AD Connect 

Als de gebruikers van uw bedrijf vanuit een on-premises Active Directory-systeem worden gesynchroniseerd met Azure AD, moet de PreferredDataLocation worden ingevuld in AD en worden gesynchroniseerd met Azure AD.

Volg het proces in Azure Active Directory Connect-synchronisatie: Configureer voorkeursgegevenslocatie voor [Microsoft 365-bronnen](/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) om voorkeursgegevenssynchronisatie te configureren van uw on-premises Active Directory Domain Services (AD DS) naar Azure AD.

We raden u aan de voorkeursgegevenslocatie van de gebruiker in te stellen als onderdeel van uw standaardwerkstroom voor het maken van gebruikers.

> [!IMPORTANT]
> Voor nieuwe gebruikers die geen OneDrive hebben ingericht, wacht u ten minste 24 uur nadat het PDL van een gebruiker is gesynchroniseerd met Azure AD totdat de wijzigingen zijn doorgevoerd voordat de gebruiker zich aanmeldt bij OneDrive voor Bedrijven. (Als u de voorkeursgegevenslocatie instelt voordat de gebruiker zich aanmeldt om oneDrive voor Bedrijven in terichten, zorgt u ervoor dat de nieuwe OneDrive van de gebruiker op de juiste locatie wordt ingericht.)

### <a name="setting-preferred-data-location-for-cloud-only-users"></a>Voorkeursgegevenslocatie instellen voor gebruikers die alleen de cloud gebruiken 

Als de gebruikers van uw bedrijf niet vanuit een on-premises Active Directory-systeem worden gesynchroniseerd met Azure AD, wat betekent dat ze worden gemaakt in Microsoft 365 of Azure AD, moet de PDL worden ingesteld met behulp van de Microsoft Azure Active Directory-module voor Windows PowerShell.

Voor de procedures in deze sectie is de [Microsoft Azure Active Directory-module voor Windows PowerShell-module vereist.](https://www.powershellgallery.com/packages/MSOnline/1.1.166.0) Als u deze module al hebt geïnstalleerd, moet u bijwerken naar de nieuwste versie.

1.  [Maak verbinding en meld u aan](/powershell/connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) met een reeks globale beheerdersreferenties voor uw tenant.

2.  Gebruik de [cmdlet Set-MsolUser](https://docs.microsoft.com/powershell/msonline/v1/set-msoluser) om de gewenste gegevenslocatie in te stellen voor al uw gebruikers. Bijvoorbeeld:

    `Set-MsolUser -userprincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR`

    U kunt met behulp van de cmdlet Get-MsolUser controleren of de Get-MsolUser is bijgewerkt. Bijvoorbeeld:

    `(Get-MsolUser -userprincipalName Robyn.Buckley@Contoso.com).PreferredDatalocation`

![Schermafbeelding van PowerShell-venster met set-msoluser](../media/multi-geo-tenant-configuration-image3.png)

We raden u aan de voorkeursgegevenslocatie van de gebruiker in te stellen als onderdeel van uw standaardwerkstroom voor het maken van gebruikers.

> [!IMPORTANT]
> Voor nieuwe gebruikers die geen OneDrive hebben ingericht, wacht u minimaal 24 uur nadat het PDF-logboek van een gebruiker is ingesteld totdat de wijzigingen worden doorgevoerd voordat de gebruiker zich aanmeldt bij OneDrive. (Als u de voorkeursgegevenslocatie instelt voordat de gebruiker zich aanmeldt om OneDrive voor Bedrijven in terichten, zorgt u ervoor dat de nieuwe OneDrive van de gebruiker op de juiste locatie wordt ingericht.)

## <a name="onedrive-provisioning-and-the-effect-of-pdl"></a>OneDrive Provisioning and the effect of PDL

Als de gebruiker al een OneDrive-site heeft die in de tenant is gemaakt, wordt zijn of haar bestaande OneDrive niet automatisch verplaatst als het PDL-site wordt gemaakt. Als u OneDrive van een gebruiker wilt verplaatsen, gaat u [naar OneDrive voor Bedrijven Geo Move.](move-onedrive-between-geo-locations.md)

> [!NOTE]
> Exchange Online verplaatst het postvak van de gebruiker automatisch als de PLD wordt gewijzigd en de MailboxRegion niet meer overeenkomt met de geografische locatiecode van de postvakdatabase. Zie Postvakken van Exchange Online beheren in een omgeving met meerdere geografische gebieden voor [meer informatie.](https://docs.microsoft.com/microsoft-365/enterprise/administering-exchange-online-multi-geo)

Als de gebruiker geen OneDrive-site binnen de tenant heeft, wordt OneDrive voor de gebruiker ingericht op basis van de PDL-waarde, ervan uitgaande dat het PDL voor de gebruiker overeenkomt met een van de satellietlocaties van het bedrijf.

## <a name="configuring-multi-geo-search"></a>Multi-Geo search configureren

Uw multige geoten tenant heeft statistische zoekmogelijkheden waarmee een zoekquery resultaten kan retourneren vanuit elke locatie in de tenant.

Zoekopdrachten op deze invoerpunten retourneren standaard samengevoegde resultaten, ook al bevindt elke zoekindex zich op de relevante geografische locatie:

- OneDrive voor Bedrijven

- Delve

- SharePoint-start

- Zoekcentrum

Bovendien kunnen er meerdere geografische zoekmogelijkheden worden geconfigureerd voor uw aangepaste zoektoepassingen die gebruikmaken van de SharePoint-zoek-API.

Raadpleeg [Zoeken in OneDrive voor Bedrijven Multi Geo](configure-search-for-multi-geo.md) configureren voor instructies, inclusief eventuele beperkingen en verschillen.

## <a name="validating-the-microsoft-365-multi-geo-configuration"></a>De Configuratie van Microsoft 365 Multi-Geo valideren

Hieronder vindt u enkele eenvoudige use cases die u mogelijk wilt opnemen in uw validatieplan voordat u Microsoft 365 Multi-Geo globaal uitrolt voor uw bedrijf. Nadat u deze tests hebt voltooid en eventuele extra use cases die relevant zijn voor uw bedrijf, kunt u ervoor kiezen om verder te gaan met het toevoegen van de gebruikers aan uw eerste testgroep.

**OneDrive voor Bedrijven**

Selecteer OneDrive in het start programma voor apps van Microsoft 365 en controleer of u automatisch wordt doorgestuurd naar de juiste geografische locatie voor de gebruiker, op basis van het PDL-bestand van de gebruiker. OneDrive voor Bedrijven moet nu beginnen met de inrichting op die locatie. Wanneer de inrichting is ingericht, uploadt en downloadt u enkele documenten.

**Mobiele OneDrive-app**

Meld u aan bij uw mobiele OneDrive-app met de referenties van uw testaccount. Bevestig dat u uw OneDrive voor Bedrijven-bestanden kunt zien en er interactief mee kunt werken vanaf uw mobiele apparaat.

**OneDrive-synchronisatieclient**

Controleer of de OneDrive-synchronisatieclient uw geografische locatie voor OneDrive voor Bedrijven automatisch detecteert wanneer u zich aanmeldt. Als u de synchronisatieclient wilt downloaden, klikt u op **Synchroniseren** in de OneDrive-bibliotheek.

**Office-toepassingen**

Bevestig dat u OneDrive voor Bedrijven kunt openen door u aan te melden vanuit een Office-toepassing, zoals Word. Open de Office-toepassing en selecteer 'OneDrive – <TenantName> '. Office detecteert uw OneDrive-locatie en toont de bestanden die u kunt openen.

**Delen**

Probeer OneDrive-bestanden te delen. Controleer of de personen kiezen al uw SharePoint Online-gebruikers toont, ongeacht hun geografische locatie.
