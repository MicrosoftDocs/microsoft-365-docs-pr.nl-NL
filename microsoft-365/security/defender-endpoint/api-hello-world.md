---
title: Hello World voor Microsoft Defender voor Endpoint API
ms.reviewer: ''
description: Maak een practice 'Hello world'-style API-oproep naar de Microsoft Defender for Endpoint API.
keywords: api's, ondersteunde api's, geavanceerd zoeken, query, microsoft defender atp, microsoft defender voor eindpunt
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 843fe093a2cfb8c328c51676e55f15ae732f7869
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286019"
---
# <a name="microsoft-defender-for-endpoint-api---hello-world"></a>Microsoft Defender voor Endpoint API - Hello World

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)


- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="get-alerts-using-a-simple-powershell-script"></a>Waarschuwingen ontvangen met een eenvoudig PowerShell-script

### <a name="how-long-it-takes-to-go-through-this-example"></a>Hoe lang duurt het om dit voorbeeld door te nemen?
Het duurt slechts 5 minuten in twee stappen:
- Toepassingsregistratie
- Voorbeelden gebruiken: alleen kopiëren/plakken van een kort PowerShell-script is vereist

### <a name="do-i-need-a-permission-to-connect"></a>Heb ik toestemming nodig om verbinding te maken?
Voor de registratiefase van toepassing moet u een **globale** beheerdersrol hebben in uw Azure Active Directory (Azure AD) tenant.

### <a name="step-1---create-an-app-in-azure-active-directory"></a>Stap 1 - Een app maken in Azure Active Directory

1. Meld u aan [bij Azure](https://portal.azure.com) met uw **globale beheerdergebruiker.**

2. Navigeer **naar Azure Active Directory**  >  **app-registraties Nieuwe**  >  **registratie**.

   ![Afbeelding van Microsoft Azure en navigatie naar toepassingsregistratie](images/atp-azure-new-app2.png)

3. Kies in het registratieformulier een naam voor uw toepassing en klik vervolgens op **Registreren.**

4. Geef uw toepassing toegang tot Defender voor Eindpunt en wijs deze **machtiging 'Alle waarschuwingen lezen'** toe:

   - Klik op uw **toepassingspagina** op API-machtigingen Machtigingen toevoegen Api's die mijn organisatie gebruikt  >    >   > **WindowsDefenderATP** typen en klik op **WindowsDefenderATP.**

   - **Opmerking:** WindowsDefenderATP wordt niet weergegeven in de oorspronkelijke lijst. U moet beginnen met het schrijven van de naam in het tekstvak om deze weer te geven.

   ![Afbeelding van API-toegang en API-selectie1](images/add-permission.png)

   - Kies **Toepassingsmachtigingen**  >  **Alert.Read.All** > Klik op **Machtigingen toevoegen**

   ![Afbeelding van API-toegang en API-selectie2](images/application-permissions.png)

   **Belangrijke opmerking:** u moet de relevante machtigingen selecteren. 'Alle waarschuwingen lezen' is slechts een voorbeeld!

     Bijvoorbeeld:

     - Als [u geavanceerde query's wilt uitvoeren,](run-advanced-query-api.md)selecteert u 'Geavanceerde query's uitvoeren' machtiging
     - Als [u een computer wilt isoleren,](isolate-machine.md)selecteert u machtiging 'Machine isoleren'.
     - Als u wilt bepalen welke machtiging u nodig hebt, kijkt u naar de **sectie** Machtigingen in de API die u wilt bellen.

5. Klik **op Toestemming verlenen**

   - **Opmerking:** Telkens wanneer u machtigingen toevoegt, moet u op Toestemming **verlenen** klikken om de nieuwe machtiging van kracht te laten worden.

   ![Afbeelding van machtigingen verlenen](images/grant-consent.png)

6. Voeg een geheim toe aan de toepassing.

   - Klik **op Certificaten &,** voeg beschrijving toe aan het geheim en klik op **Toevoegen.**

    **Belangrijk:** Nadat u op Toevoegen hebt **geklikt, kopieert u de gegenereerde geheime waarde.** U kunt het niet meer ophalen nadat u bent weggehaald.

    ![Afbeelding van app-sleutel maken](images/webapp-create-key2.png)

7. Schrijf uw toepassings-id en uw tenant-id op:

   - Ga op de toepassingspagina naar **Overzicht** en kopieer het volgende:

   ![Afbeelding van gemaakte app-id](images/app-and-tenant-ids.png)

Klaar! U hebt een toepassing geregistreerd.

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>Stap 2: haal een token op met de App en gebruik dit token om toegang te krijgen tot de API.

- Kopieer het script hieronder naar PowerShell ISE of naar een teksteditor en sla het op als "**Get-Token.ps1**"
- Als u dit script uit te voeren, wordt een token gegenereerd en wordt dit opgeslagen in de werkmap onder de naam "**Latest-token.txt**".

   ```powershell
   # That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
   # Paste below your Tenant ID, App ID and App Secret (App key).

   $tenantId = '' ### Paste your tenant ID here
   $appId = '' ### Paste your Application ID here
   $appSecret = '' ### Paste your Application secret here

   $resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
   $oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
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

- Sanity Check:
  - Voer het script uit.
  - Ga in uw browser naar: <https://jwt.ms/>
  - Kopieer het token (de inhoud van het Latest-token.txt bestand).
  - Plakken in het bovenste vak.
  - Zoek naar de sectie 'rollen'. Zoek de rol Alert.Read.All.

  ![Afbeelding jwt.ms](images/api-jwt-ms.png)

### <a name="lets-get-the-alerts"></a>Hiermee kunt u de waarschuwingen krijgen.

- Het onderstaande script gebruikt **Get-Token.ps1** toegang tot de API en krijgt de afgelopen 48 uur waarschuwingen.
- Sla dit script op in dezelfde map die u het vorige script hebt **Get-Token.ps1.**
- Het script maakt twee bestanden (json en csv) met de gegevens in dezelfde map als de scripts.

  ```powershell
  # Returns Alerts created in the past 48 hours.

  $token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

  # Get Alert from the last 48 hours. Make sure you have alerts in that time frame.
  $dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

  # The URL contains the type of query and the time filter we create above
  # Read more about other query options and filters at   Https://TBD- add the documentation link
  $url = "https://api.securitycenter.microsoft.com/api/alerts?`$filter=alertCreationTime ge $dateTime"

  # Set the WebRequest headers
  $headers = @{
      'Content-Type' = 'application/json'
      Accept = 'application/json'
      Authorization = "Bearer $token"
  }

  # Send the webrequest and get the results.
  $response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

  # Extract the alerts from the results.
  $alerts =  ($response | ConvertFrom-Json).value | ConvertTo-Json

  # Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
  $dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

  # Save the result as json and as csv
  $outputJsonPath = "./Latest Alerts $dateTimeForFileName.json"
  $outputCsvPath = "./Latest Alerts $dateTimeForFileName.csv"

  Out-File -FilePath $outputJsonPath -InputObject $alerts
  ($alerts | ConvertFrom-Json) | Export-CSV $outputCsvPath -NoTypeInformation
  ```

U bent klaar. U hebt zojuist het volgende gedaan:

- Gemaakt en geregistreerd en toepassing
- Machtiging verleend voor deze toepassing om waarschuwingen te lezen
- De API verbonden
- Een PowerShell-script gebruikt om waarschuwingen te retourneren die in de afgelopen 48 uur zijn gemaakt

## <a name="related-topic"></a>Verwant onderwerp

- [Microsoft Defender voor eindpunt-API's](exposed-apis-list.md)
- [Toegang tot Microsoft Defender voor eindpunt met toepassingscontext](exposed-apis-create-app-webapp.md)
- [Toegang tot Microsoft Defender voor Eindpunt met gebruikerscontext](exposed-apis-create-app-nativeapp.md)
