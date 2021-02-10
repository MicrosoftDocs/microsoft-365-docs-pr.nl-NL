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
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Gebruik deze stapsgewijse implementatiehandleiding voor het maken en configureren van een geïsoleerd SharePoint Online-teamsite in Microsoft Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b1f0342afc92b4540330417ad0fc9cabe1dc8a8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165497"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>Een geïsoleerde SharePoint Online-teamsite implementeren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

 **Overzicht:** Implementeer een nieuwe afzonderlijke SharePoint Online-teamsite met deze stapsgewijs instructies.

Dit artikel is een stapsgewijse implementatiehandleiding voor het maken en configureren van een geïsoleerd SharePoint Online-teamsite in Microsoft Office 365. Bij deze stappen wordt ervan uitgenomen dat de drie standaardGroepen van SharePoint en de bijbehorende machtigingsniveaus worden gebruikt, met één op Azure Active Directory (AD) gebaseerde toegangsgroep voor elk toegangsniveau.

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>Fase 1: Toegangsgroepen voor de teamsite maken en in vullen

In deze fase maakt u de drie op Azure AD gebaseerde toegangsgroepen voor de drie standaard SharePoint-groepen en vult u deze met de juiste gebruikersaccounts.

> [!NOTE]
> In de volgende stappen wordt ervan uitgenomen dat alle benodigde gebruikersaccounts al bestaan en dat ze de juiste licenties toegewezen krijgen. Als dat niet zo is, voegt u deze toe en wijst u licenties toe voordat u verdergaat met stap 1.

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>Stap 1: De SharePoint Online-beheerders voor de site in een lijst plaatsen

Bepaal welke set gebruikersaccounts overeenkomt met de SharePoint Online-beheerders voor de geïsoleerde teamsite.

Als u gebruikersaccounts en -groepen beheert via Microsoft 365 en Windows PowerShell wilt gebruiken, maakt u een lijst met hun UPN's (User Principal Names) (voorbeeld UPN: belindan@contoso.com).

### <a name="step-2-list-the-members-for-the-site"></a>Stap 2: Een lijst maken met de leden voor de site

Bepaal de set gebruikersaccounts die betrekking hebben op de leden van de geïsoleerde teamsite, de gebruikers die zullen samenwerken aan resources die op de site zijn opgeslagen.

Als u gebruikersaccounts en -groepen beheert via Microsoft 365 en PowerShell wilt gebruiken, maakt u een lijst met hun UPN's. Als er veel siteleden zijn, kunt u de lijst met UPN's opslaan in een tekstbestand en ze allemaal toevoegen met één PowerShell-opdracht.

### <a name="step-3-list-the-viewers-for-the-site"></a>Stap 3: De viewers voor de site in een lijst plaatsen

Bepaal welke set gebruikersaccounts overeenkomt met de gebruikers van de geïsoleerde teamsite, personen die de resources kunnen bekijken die op de site zijn opgeslagen, maar niet kunnen wijzigen of rechtstreeks kunnen samenwerken aan hun inhoud.

Als u gebruikersaccounts en -groepen beheert via Microsoft 365 en PowerShell wilt gebruiken, maakt u een lijst met hun UPN's. Als er veel siteleden zijn, kunt u de lijst met UPN's opslaan in een tekstbestand en ze allemaal toevoegen met één PowerShell-opdracht.

Gebruikers van de site kunnen bijvoorbeeld leidinggevenden, juridische vertegenwoordigers of belanghebbenden tussen de afdelingen omvatten.

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>Stap 4: De drie toegangsgroepen voor de site maken in Azure AD

U moet de volgende toegangsgroepen maken in Azure AD:

- Sitebeheerders (die de lijst van stap 1 bevatten)
- Siteleden (die de lijst van stap 2 bevatten)
- Sitekijkers (die de lijst uit stap 3 bevatten)

1. Ga in uw browser naar azure portal en meld u aan met de referenties van een account dat is toegewezen met de rol <https://portal.azure.com> User Management Admin of Company Administrator.

2. Klik in de Microsoft Azure-portal op **Microsoft Azure Active Directory > Groepen**.

3. Klik in de blade **Groepen: Alle groepen** op **+ Nieuwe groep**.

4. Op de **nieuwe groeps blade:**

   - Selecteer **Beveiliging** bij **Groepstype**.

   - Typ de groepsnaam in **Naam.**

   - Typ een beschrijving van de groep in **de groepsbeschrijving.**

   - Selecteer **Toegewezen** bij **Lidmaatschapstype**.

5. Klik op **Maken** en sluit vervolgens de blade **Groep**.

6. Herhaal stap 3 tot en met 5 voor uw extra groepen.

> [!NOTE]
> U moet de Azure Portal gebruiken om de groepen te maken, zodat ze Office-functies hebben ingeschakeld. Als een afzonderlijke SharePoint Online-site later wordt geconfigureerd als zeer vertrouwelijke site met een Azure Information Protection-label voor het versleutelen van bestanden en het toewijzen van machtigingen aan specifieke groepen, moeten de toegestane groepen zijn gemaakt met Office-functies ingeschakeld. U kunt de instelling voor Office-functies van een Azure AD-groep niet meer wijzigen nadat deze is gemaakt.

Hier is uw resulterende configuratie met de drie toegangsgroepen voor de site.

![De drie toegangsgroepen voor uw implementatie van een afzonderlijke SharePoint Online-site.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>Stap 5. Gebruikersaccounts toevoegen aan de toegangsgroepen

Ga in deze stap als volgt te werk:

1. Voeg de lijst met gebruikers uit stap 1 toe aan de toegangsgroep voor sitebeheerders.
2. Voeg de lijst met gebruikers uit stap 2 toe aan de groep met siteleden.
3. Voeg de lijst met gebruikers uit stap 3 toe aan de groep voor sitegebruikers.

Als u gebruikersaccounts en -groepen beheert via Active Directory Domain Services (AD DS), voegt u gebruikers toe aan de juiste toegangsgroepen met behulp van de gebruikelijke AD DS-gebruikers- en groepsbeheerprocedures en wacht u op synchronisatie met uw Microsoft 365-abonnement.

Als u gebruikersaccounts en -groepen beheert via Office 365, kunt u het Microsoft 365-beheercentrum of PowerShell gebruiken. Als u dubbele groepsnamen hebt voor een van de toegangsgroepen, gebruikt u het Microsoft 365-beheercentrum.

Meld u voor het Microsoft 365-beheercentrum aan met een gebruikersaccount aan welke de rol Gebruikersaccountbeheerder of Bedrijfsbeheerder is toegewezen en gebruik Groepen om de juiste gebruikersaccounts en -groepen toe te voegen aan de juiste toegangsgroepen.

Maak voor PowerShell eerst [verbinding met de Azure Active Directory PowerShell for Graph-module.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)

Gebruik vervolgens het volgende opdrachtblok om een afzonderlijk gebruikersaccount toe te voegen aan een toegangsgroep:

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Als u de UPN's van gebruikersaccounts hebt opgeslagen voor een van de toegangsgroepen in een tekstbestand, kunt u deze allemaal tegelijk toevoegen met het volgende PowerShell-opdrachtblok:

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

Gebruik voor PowerShell het volgende opdrachtblok om een afzonderlijke groep toe te voegen aan een toegangsgroep:

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Het resultaat moet als volgt zijn:

- De Azure AD-groep sitebeheerders bevat de gebruikersaccounts of groepen van de sitebeheerder
- De siteleden van de Azure AD-groep bevatten de gebruikersaccounts of groepen van de siteleden
- De Azure AD-groep voor sitegebruikers bevat de gebruikersaccounts of groepen die alleen de inhoud van de site kunnen bekijken

Valideer de lijst met groepsleden voor elke toegangsgroep met het Microsoft 365-beheercentrum of met het volgende PowerShell-opdrachtblok:

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

Hier is uw resulterende configuratie met de drie toegangsgroepen voor de site die worden gevuld met gebruikersaccounts of -groepen.

![De drie toegangsgroepen worden gevuld met gebruikersaccounts.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>Fase 2: De geïsoleerde teamsite maken en configureren

In deze fase maakt u de afzonderlijke SharePoint Online-site en configureert u de machtigingen voor de standaardmachtigingsniveaus van SharePoint Online voor het gebruik van uw nieuwe toegangsgroepen op basis van Azure AD. Nieuwe teamsites bevatten standaard een Microsoft 365-groep en andere verwante informatiebronnen, maar in dit geval maken we een teamsite zonder een Microsoft 365-groep. Hierdoor kunnen machtigingen volledig via SharePoint worden onderhouden.

Maak eerst de SharePoint Online-teamsite met deze stappen.

1. Meld u aan bij het Microsoft 365-beheercentrum met een account dat ook wordt gebruikt voor het beheren van de SharePoint Online-teamsite (een beheerder van SharePoint Online). Zie [Waar kan ik me aanmelden in Office 365?](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) voor hulp.

2. Klik in het Microsoft 365-beheercentrum onder **Beheercentra** op **SharePoint.**

3. Vouw in het SharePoint-beheercentrum **Sites uit en** klik op Actieve **sites.**

4. Klik **op** Maken en kies **Andere opties.**

5. Kies **Teamsite in** de lijst Een sjabloon **kiezen.**

6. Typ **in De** naam van de site een naam voor de teamsite.

7. Typ **bij Primaire** beheerder het account met wie u bent aangemeld.

8. Klik op **Voltooien**.

Configureer vervolgens vanaf de nieuwe SharePoint Online-teamsite machtigingen.

1. Klik in de werkbalk op het pictogram Instellingen en vervolgens op **Site-machtigingen**.

2. Klik **onder Site delen** op Wijzigen hoe leden kunnen **delen.**

3. Kies de **optie Alleen site-eigenaren kunnen bestanden, mappen en de site delen.**

4. Stel **Toegangsaanvragen toestaan in** op **Uit.**

5. Klik op **Opslaan**.

6. Klik in **het deelvenster Machtigingen** op **Geavanceerde machtigingsinstellingen.**

7. Klik op **het tabblad** Machtigingen van uw browser op **\<site name> Leden** in de lijst.

8. Klik **in Personen en groepen** op **Nieuw.**

9. Typ in **het** dialoogvenster Delen de naam van de toegangsgroep voor siteleden, selecteer deze en klik op **Delen.**

10. Klik op de terugknop in uw browser.

11. Klik **\<site name> in de** lijst op Eigenaren.

12. Klik **in Personen en groepen** op **Nieuw.**

13. Typ in **het** dialoogvenster Delen de naam van de toegangsgroep voor sitebeheerders, selecteer deze en klik op **Delen.**

14. Klik op de terugknop in uw browser.

15. Klik **\<site name> op Bezoekers** in de lijst.

16. Klik **in Personen en groepen** op **Nieuw.**

17. Typ in **het** dialoogvenster Delen de naam van de groep voor sitekijkers, selecteer deze en klik op **Delen.**

18. Sluit het **tabblad Machtigingen** van uw browser.

De resultaten van deze machtigingsinstellingen zijn:

- De **\<site name> SharePoint-groep** Eigenaren bevat de toegangsgroep voor sitebeheerders, waarin alle leden het machtigingsniveau Volledig **beheer** hebben.
- De **\<site name>** SharePoint-groep Leden bevat de toegangsgroep voor siteleden, waarin alle leden het **machtigingsniveau Bewerken** hebben.
- De **\<site name> SharePoint-groep** Bezoekers bevat de groep Bezoekers van de site, waarin alle leden het **machtigingsniveau** Lezen hebben.
- De mogelijkheid voor leden om andere leden of niet-leden uit te nodigen om toegang aan te vragen, is uitgeschakeld.

Hier is uw resulterende configuratie met de drie SharePoint-groepen voor de site geconfigureerd voor gebruik van de drie toegangsgroepen, die worden gevuld met gebruikersaccounts of Azure AD-groepen.

![De uiteindelijke configuratie van uw afzonderlijke SharePoint Online-site met toegangsgroepen en gebruikersaccounts.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

U en de leden van de site kunnen nu via groepslidmaatschap in een van de toegangsgroepen samenwerken met behulp van de bronnen van de site.

## <a name="next-step"></a>Volgende stap

Zie Een afzonderlijke [SharePoint Online-teamsite](manage-an-isolated-sharepoint-online-team-site.md)beheren wanneer u het groepslidmaatschap van de site wilt wijzigen of een documentmap met aangepaste machtigingen wilt maken.

## <a name="see-also"></a>Zie ook

[Geïsoleerde SharePoint Online-teamsites](isolated-sharepoint-online-team-sites.md)

[Een geïsoleerde SharePoint Online-teamsite ontwerpen](design-an-isolated-sharepoint-online-team-site.md)

[Een geïsoleerde SharePoint Online-teamsite beheren](manage-an-isolated-sharepoint-online-team-site.md)
