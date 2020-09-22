---
title: Hallo wereld voor Microsoft Threat Protection REST API
description: Leer hoe u een app maakt en een token gebruikt om toegang te krijgen tot de Microsoft Threat Protection-Api's
keywords: app, token, toegang, Aad, app, toepassing registreren, powershell, script, globale beheerder, machtiging
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: cdf3f6a0c007763d2772233b1a299d59c931b2e5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201325"
---
# <a name="hello-world-for-microsoft-threat-protection-rest-api"></a>Hallo wereld voor Microsoft Threat Protection REST API 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd. Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.


## <a name="get-incidents-using-a-simple-powershell-script"></a>Incidenten aanvragen met behulp van een eenvoudig PowerShell-script

### <a name="how-long-it-takes-to-go-through-this-example"></a>Hoe lang duurt het om het volgende voorbeeld te passeren?
U duurt slechts 5 minuten in twee stappen:
- Sollicitatie registratie
- Voorbeelden gebruiken: alleen kopiëren en plakken van een korte PowerShell-script vereist

### <a name="do-i-need-a-permission-to-connect"></a>Heb ik een machtiging nodig om verbinding te maken?
Voor de registratie fase van de toepassing moet u een **globale** beheerdersrol hebben in uw Azure Active Directory (Azure AD)-Tenant.

### <a name="step-1---create-an-app-in-azure-active-directory"></a>Stap 1: een app maken in azure Active Directory

1. Meld u aan bij [Azure](https://portal.azure.com) met de gebruikers van uw **globale beheerder** .

2. Ga naar de **Azure Active Directory**-  >  **app registraties**  >  **nieuwe registratie**. 

   ![Afbeelding van Microsoft Azure en navigatie naar toepassing registreren](../../media/atp-azure-new-app2.png)

3. Kies in het registratieformulier een naam voor de toepassing en selecteer vervolgens **registreren**.

4. Zorg dat uw toepassing toegang heeft tot Microsoft Defender ATP en wijs de machtiging **alle incidenten lezen** toe:

   - Selecteer op de pagina toepassingen de optie **API-machtigingen**  >  **toevoegen**voor  >  **Mijn organisatie** > type **Microsoft Threat Protection** en selecteer **Microsoft Threat Protection**.

   >[!NOTE]
   >Microsoft Threat Protection wordt niet weergegeven in de oorspronkelijke lijst. U moet de naam ervan beginnen te schrijven in het tekstvak om de naam weer te geven.

   ![Afbeelding van API-toegang en API-selectie](../../media/apis-in-my-org-tab.PNG)

   - Kies **Toepassingsmachtigingen**  >  **incident. Read. alle** > Selecteer **machtigingen toevoegen**

   ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   >U moet de relevante machtigingen selecteren. 

     Voorbeeld:

     - Om te bepalen welke machtigingen u nodig hebt, raadpleegt u de sectie **machtigingen** in de API die u wilt bellen.

5. Selecteer **beheerder toestemming verlenen**

    - >[!NOTE]
      > Telkens wanneer u toestemming toevoegt, moet u op **toestemming verlenen** om de nieuwe machtiging van kracht te laten worden.

    ![Afbeelding van machtiging verlenen](../../media/grant-consent.PNG)

6. Voeg een geheim toe aan de toepassing.

    - Selecteer **certificaten & geheimen**, voeg een beschrijving toe aan het geheim en selecteer **toevoegen**.

    >[!IMPORTANT]
    > Nadat u **toevoegen**hebt geselecteerd, **kopieert u de gegenereerde geheime waarde**. Wanneer u niets kunt terughalen.

    ![Afbeelding van de sleutel app maken](../../media/webapp-create-key2.png)

7. Noteer de toepassings-ID en uw Tenant-ID:

   - Ga op de pagina toepassing naar **overzicht** en kopieer de volgende opties:

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)


Klaar! U hebt een toepassing geregistreerd.

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>Stap 2: een token verkrijgen met behulp van de app en dit token gebruiken om toegang te krijgen tot de API.

-   Kopieer het volgende script naar PowerShell ISE of naar een teksteditor en sla het bestand op als '**Get-Token.ps1**'.
-   Als u dit script uitvoert, wordt een token gegenereerd en wordt dit opgeslagen in de werkmap onder de naam '**Latest-token.txt**'.

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

-   Sanity controleren:<br>
Voer het script uit.<br>
Ga in uw browser naar: https://jwt.ms/ <br>
Kopieer de token (de inhoud van het Latest-token.txt bestand).<br>
Plakken in het bovenste vak.<br>
Zoek naar de sectie rollen. De ```Incidents.Read.All``` rol zoeken.<br>
In het onderstaande voorbeeld bevindt zich een app met de ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` machtiging en machtigingen.

![Afbeelding van jwt.ms](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a>Hiermee kunt u de incidenten vinden.

-   In het onderstaande script wordt **Get-Token.ps1** gebruikt voor toegang tot de API en worden de meest recent bijgewerkte aanvragen weergegeven in de afgelopen 48 uur.
-   Sla dit script op in de map waarin u het vorige script hebt opgeslagen **Get-Token.ps1**. 
-   Het script een JSON-bestand met de gegevens in dezelfde map als de scripts.

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

U bent klaar! U hebt zojuist de volgende handelingen uitgevoerd:
-   Gemaakt en geregistreerd en Application
-   Toestemming voor de toepassing van waarschuwingen heeft gekregen
-   Verbonden met de API
-   Gebruik een PowerShell-script om incidenten te retourneren die in de afgelopen 48 uur zijn gemaakt



## <a name="related-topic"></a>Verwante onderwerpen
- [Toegang tot de Microsoft Threat Protection-Api's](api-access.md)
- [Toegang tot Microsoft Threat Protection met toepassingscontext](api-create-app-web.md)
- [Microsoft Threat Protection met gebruikerscontext openen](api-create-app-user-context.md)
