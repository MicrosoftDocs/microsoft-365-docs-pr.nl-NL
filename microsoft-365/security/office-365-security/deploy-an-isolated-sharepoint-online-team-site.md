---
title: Een geïsoleerde SharePoint Online-teamsite implementeren
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Gebruik deze stapsgewijze instructies voor het maken en configureren van een geïsoleerde SharePoint Online-team site in Microsoft Office 365.
ms.openlocfilehash: 5b37868759dd91fc49fb8354db893f52b8f534dd
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561737"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>Een geïsoleerde SharePoint Online-teamsite implementeren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 **Overzicht:** Implementeer een nieuwe, geïsoleerde SharePoint Online-team site met deze stapsgewijze instructies.

Dit artikel bevat stapsgewijze instructies voor het maken en configureren van een geïsoleerde SharePoint Online-team site in Microsoft Office 365. Bij deze stappen wordt uitgegaan van de drie standaardgroepen met SharePoint en de bijbehorende machtigingsniveaus, met één Azure Active Directory-toepassing op basis van Azure Active Directory (AD) voor elk toegangsniveau.

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>Fase 1: de toegangsgroepen voor de team site maken en vullen

In deze fase maakt u de drie groepen Azure AD-based Access voor de drie standaardgroepen in SharePoint en vult u ze met de juiste gebruikersaccounts in.

> [!NOTE]
> Bij de volgende stappen wordt ervan uitgegaan dat alle benodigde gebruikersaccounts al bestaan en de juiste licenties zijn toegewezen. Als dat niet zo is, kunt u ze toevoegen en licenties toewijzen voordat u verder gaat met stap 1.

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>Stap 1: de SharePoint Online-beheerders voor de site weergeven

De set gebruikersaccounts bepalen die overeenkomen met de SharePoint Online-beheerders voor de geïsoleerde team site.

Als u gebruikersaccounts en groepen beheert via Microsoft 365 en u Windows PowerShell wilt gebruiken, maakt u een lijst met de gebruikers-principal-namen (Upn's) (belindan@contoso.com).

### <a name="step-2-list-the-members-for-the-site"></a>Stap 2: de leden voor de site weergeven

Het bepalen van de gebruikersaccounts die overeenkomen met de leden van de geïsoleerde team site, degene die samenwerken aan resources die zijn opgeslagen in de site.

Als u gebruikersaccounts en groepen beheert via Microsoft 365 en u PowerShell wilt gebruiken, moet u een lijst maken van de Upn's. Als er veel siteleden zijn, kunt u de lijst met Upn's opslaan in een tekstbestand en ze allemaal met één PowerShell-opdracht toevoegen.

### <a name="step-3-list-the-viewers-for-the-site"></a>Stap 3: de kijkers voor de site weergeven

Bepalen welke gebruikersaccounts overeenkomen met de gebruikers van de geïsoleerde team site, met welke gebruikers de bronnen die op de site zijn opgeslagen, niet kunnen wijzigen of rechtstreeks samenwerken aan hun inhoud.

Als u gebruikersaccounts en groepen beheert via Microsoft 365 en u PowerShell wilt gebruiken, moet u een lijst maken van de Upn's. Als er veel siteleden zijn, kunt u de lijst met Upn's opslaan in een tekstbestand en ze allemaal met één PowerShell-opdracht toevoegen.

Kijkers voor de site kunnen directeuren, juridische adviseur of belanghebbenden van de afdeling zijn.

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>Stap 4: de drie toegangsgroepen maken voor de site in azure AD

U moet de volgende toegangsgroepen maken in azure AD:

- Site beheerders (die de lijst uit stap 1) hebben
- Site leden (die de lijst uit stap 2 bevatten)
- Site bezoekers (die de lijst uit stap 3 bevatten)

1. Ga in uw browser naar de Azure-Portal op <https://portal.azure.com> en meld u aan met de referenties van een account dat is toegewezen aan de beheerder van het Gebruikersbeheer of de beheerder van het bedrijf.

2. Klik in de Microsoft Azure-portal op **Microsoft Azure Active Directory > Groepen**.

3. Klik in de blade **Groepen: Alle groepen** op **+ Nieuwe groep**.

4. Op de **nieuwe groeps** Blade:

   - Selecteer **Beveiliging** bij **Groepstype**.

   - Typ een **naam** voor de groep.

   - Typ een beschrijving van de groep in de **groepsbeschrijving**.

   - Selecteer **Toegewezen** bij **Lidmaatschapstype**.

5. Klik op **Maken** en sluit vervolgens de blade **Groep**.

6. Herhaal stappen 3-5 voor uw extra groepen.

> [!NOTE]
> U moet de Azure-Portal gebruiken om de groepen te maken, zodat de Office-functies beschikbaar zijn. Als een geïsoleerde SharePoint Online-site later is geconfigureerd als een zeer vertrouwelijke site met een Azure Information Protection-label om bestanden te versleutelen en machtigingen toe te wijzen aan specifieke groepen, moeten de toegestane groepen zijn gemaakt met de Office-functies ingeschakeld. U kunt de instelling Office-functies van een Azure AD-groep niet wijzigen nadat deze is gemaakt.

Hier ziet u de resultaten van de configuratie met de drie groepen site toegang.

![De drie toegangsgroepen voor de implementatie van een geïsoleerde SharePoint Online-site.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>Stap 5. De gebruikersaccounts toevoegen aan de Access-groepen

In deze stap doet u het volgende:

1. Voeg de lijst met gebruikers uit stap 1 toe aan de groep sitebeheerders toegang.
2. Voeg de lijst met gebruikers uit stap 2 toe aan de groep toegang tot siteleden.
3. Voeg de lijst met gebruikers uit stap 3 toe aan de groep toegang tot sitebezoekers.

Als u gebruikersaccounts en groepen beheert via Active Directory Domain Services (AD DS), voegt u gebruikers toe aan de juiste toegangsgroepen met behulp van uw normale Active Directory-gebruikers-en groepsbeheer procedures en wacht op synchronisatie met uw Microsoft 365-abonnement.

Als u gebruikersaccounts en groepen beheert via Office 365, kunt u het Microsoft 365-Beheercentrum of PowerShell gebruiken. Als u een groepsnaam hebt voor een van de toegangsgroepen, dient u het Microsoft 365-Beheercentrum te gebruiken.

Voor het Microsoft 365-Beheercentrum, meldt u zich aan met een gebruikersaccount waaraan de rol van beheerder of beheerder van het bedrijf is toegewezen en groepen om de juiste gebruikersaccounts en groepen toe te voegen aan de juiste toegangsgroepen.

Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell voor Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

Gebruik vervolgens de volgende opdracht blokkering om een afzonderlijk gebruikersaccount toe te voegen aan een Access-groep:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Als u de Upn's van gebruikersaccounts voor een van de toegangsgroepen in een tekstbestand hebt opgeslagen, kunt u deze met het volgende PowerShell-opdracht blok allemaal tegelijk toevoegen:

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

Gebruik voor PowerShell de volgende opdracht blokkering om een groep toe te voegen aan een Access-groep:

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

U moet het volgende doen:

- De groep sitebeheerders Azure AD bevat de gebruikersaccounts of groepen van de sitebeheerder
- De groep Siteleden Azure AD bevat de gebruikersaccounts of groepen van de siteleden
- De groep site viewers Azure AD bevat de gebruikersaccounts of groepen waarmee de site-inhoud kan worden weergegeven.

Valideer de lijst met groepsleden voor elke toegangsgroep met het Microsoft 365-Beheercentrum of met het volgende PowerShell-opdracht blok:

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

Hier ziet u de resultaten van de drie groepen toegang krijgen tot de sitegroepen, met gebruikersaccounts of groepen.

![De drie toegangsgroepen die zijn gevuld met gebruikersaccounts.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>Fase 2: de geïsoleerde team site maken en configureren

In deze fase maakt u de geïsoleerde SharePoint Online-site en configureert u de machtigingen voor de standaard-SharePoint Online-machtigingsniveaus voor het gebruik van uw nieuwe Azure AD-toegangsgroepen. Nieuwe team sites bevatten standaard een Microsoft 365-groep en andere verwante bronnen, maar in dit geval maken we een team site zonder een Microsoft 365-groep. Hiermee kunt u machtigingen volledig beheren via SharePoint.

Maak eerst de SharePoint Online-team site met deze stappen.

1. Meld u aan bij het Microsoft 365-Beheercentrum met een account dat ook wordt gebruikt voor het beheren van de SharePoint Online-team site (een beheerder van SharePoint Online). Zie [Waar kan ik me aanmelden in Office 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.

2. Klik in het Microsoft 365-Beheercentrum onder **beheer centra** op **SharePoint**.

3. In het SharePoint-Beheercentrum, vouwt u **sites** uit en klikt u op **actieve sites**.

4. Klik op **maken** en kies **andere opties**.

5. Kies in de lijst **een sjabloon kiezen** de optie **team site**.

6. Typ in **site naam** een naam voor de team site.

7. Typ bij **primaire beheerder** het account waarmee u bent aangemeld.

8. Klik op **Voltooien**.

Vervolgens configureert u op de nieuwe SharePoint Online-team site machtigingen.

1. Klik in de werkbalk op het pictogram Instellingen en vervolgens op **Site-machtigingen**.

2. Klik onder **site delen** op **wijzigen hoe leden kunnen delen**.

3. Kies de **enige site-eigenaren kunnen bestanden, mappen en de site delen**.

4. Stel **toegangsaanvragen toestaan** in op **uit**.

5. Klik op **Opslaan**.

6. Klik in het deelvenster **machtigingen** op **Geavanceerde instellingen voor machtigingen**.

7. Klik op het tabblad **machtigingen** van uw browser op **\<site name> leden** in de lijst.

8. Klik in **personen en groepen** op **Nieuw**.

9. Typ in het dialoogvenster **delen** de naam van de groep toegang tot siteleden, Selecteer deze en klik vervolgens op **delen**.

10. Klik op de terugknop in uw browser.

11. Klik op **\<site name> eigenaren** in de lijst.

12. Klik in **personen en groepen** op **Nieuw**.

13. Typ in het dialoogvenster **delen** de naam van de groep sitebeheerders toegang, Selecteer deze en klik vervolgens op **delen**.

14. Klik op de terugknop in uw browser.

15. Klik op **\<site name> bezoekers** in de lijst.

16. Klik in **personen en groepen** op **Nieuw**.

17. Typ in het dialoogvenster **delen** de naam van de groep toegang tot site kijkers, Selecteer deze en klik vervolgens op **delen**.

18. Sluit het tabblad **machtigingen** van uw browser.

De resultaten van deze machtigingsinstellingen zijn:

- De SharePoint-groep **\<site name> eigenaren** bevat de groep sitebeheerders toegang, waarbij alle leden het machtigingsniveau **volledig beheer** hebben.
- De SharePoint-groep **\<site name> leden** bevat de groep toegang tot siteleden, waarbij alle leden het machtigingsniveau voor **bewerken** hebben.
- De SharePoint-groep **\<site name> bezoekers** bevat de groep gebruikers van de site met de machtiging voor het **lezen** van de site.
- De mogelijkheid om leden te uitnodigen andere leden uit te nodigen of voor niet-leden om toegang aan te vragen is uitgeschakeld.

Hier ziet u de resultaten van de SharePoint-groepen waarmee de site is geconfigureerd voor het gebruik van de drie toegangsgroepen, die zijn gevuld met gebruikersaccounts of Azure AD-groepen.

![De laatste configuratie van de geïsoleerde SharePoint Online-site met toegangsgroepen en gebruikersaccounts.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

U en de leden van de site, via groepslidmaatschap in een van de toegangsgroepen, kunnen nu samenwerken via de bronnen van de site.

## <a name="next-step"></a>Volgende stap

Zie [een geïsoleerde SharePoint Online-team site beheren](manage-an-isolated-sharepoint-online-team-site.md)als u lidmaatschap van een site toegangsgroep wilt wijzigen of een map wilt maken met aangepaste machtigingen.

## <a name="see-also"></a>Zie ook

[Geïsoleerde SharePoint Online-teamsites](isolated-sharepoint-online-team-sites.md)

[Een geïsoleerde SharePoint Online-teamsite ontwerpen](design-an-isolated-sharepoint-online-team-site.md)

[Een geïsoleerde SharePoint Online-teamsite beheren](manage-an-isolated-sharepoint-online-team-site.md)
