---
title: Use the Centralized Deployment PowerShell cmdlets to manage add-ins
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 94f4e86d-b8e5-42dd-b558-e6092f830ec9
ms.custom:
- seo-marvel-apr2020
description: Gebruik de PowerShell-cmdlets voor gecentraliseerde implementatie om u te helpen bij het implementeren en beheren van Office invoegingen voor uw Microsoft 365 organisatie.
ms.openlocfilehash: 7872deedfcfe058f0a4ac63c489bbed139699d18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924670"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>Use the Centralized Deployment PowerShell cmdlets to manage add-ins

Als Microsoft 365 globale beheerder kunt u Office-invoegvoegingen implementeren voor gebruikers via de functie Gecentraliseerde implementatie (zie Office-invoegvoegingen implementeren in het [beheercentrum).](../admin/manage/manage-deployment-of-add-ins.md) Naast het implementeren van Office via het Microsoft 365 beheercentrum, kunt u ook Microsoft PowerShell gebruiken. Installeer de [O365 Centralized Add-In Deployment Module voor Windows PowerShell.](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment) 

Nadat u de module hebt gedownload, opent u een Windows PowerShell venster en voer u de volgende cmdlet uit:

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a>Verbinding maken beheerdersreferenties gebruiken

Voordat u de cmdlets gecentraliseerde implementatie kunt gebruiken, moet u zich aanmelden.
  
1. Start PowerShell.
    
2. Verbinding maken powerShell met behulp van uw bedrijfsbeheerdersreferenties. Voer de volgende cmdlet uit.
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. Voer op **de pagina** Referenties invoeren uw Microsoft 365 globale beheerdersreferenties in. U kunt ook uw referenties rechtstreeks in de cmdlet invoeren. 
    
    Voer de volgende cmdlet uit die uw bedrijfsbeheerdersreferenties opgeeft als een PSCredential-object.
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> Zie voor meer informatie over het gebruik van PowerShell [Verbinding maken om Microsoft 365 powershell te gebruiken.](./connect-to-microsoft-365-powershell.md) 
  
## <a name="upload-an-add-in-manifest"></a>Upload invoegmanifest

Voer de **cmdlet New-OrganizationAdd-In** uit om een invoegingsmanifest te uploaden vanaf een pad, dat een bestandslocatie of URL kan zijn. In het volgende voorbeeld ziet u een bestandslocatie voor de waarde van de _parameter ManifestPath._ 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

U kunt ook de **cmdlet New-OrganizationAdd-In** uitvoeren om een invoegvoeging te uploaden en deze rechtstreeks aan gebruikers of groepen toe te wijzen met behulp van de parameter  _Leden,_ zoals wordt weergegeven in het volgende voorbeeld. Scheid de e-mailadressen van leden met een komma. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>Upload een invoeging uit de Office Store

Voer de **cmdlet New-OrganizationAddIn** uit om een manifest te uploaden vanuit de Office Store.
  
In het volgende voorbeeld geeft de **cmdlet New-OrganizationAddIn** de AssetId op voor een invoegvoeging voor een Amerikaanse locatie en inhoudsmarkt.
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

Als u de waarde voor de _parameter AssetId_ wilt bepalen, kunt u deze kopiëren vanuit de URL van de webpagina Office Store voor de invoeging. AssetIds beginnen altijd met 'WA' gevolgd door een getal. In het vorige voorbeeld is de bron voor de AssetId-waarde van WA104099688 bijvoorbeeld de URL van de webpagina van Office Store voor de invoegpagina: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .
  
De waarden voor de parameter  _Locale_ en de parameter  _ContentMarket_ zijn identiek en geven het land/de regio aan waaruit u de invoegvoeging wilt installeren. De notatie is nl-NL, fr-FR. enzovoort. 
  
> [!NOTE]
> Invoegvoegingen die zijn geüpload vanuit de Office Store worden automatisch bijgewerkt binnen enkele dagen na de nieuwste update die beschikbaar is in de Office Store. 
  
## <a name="get-details-of-an-add-in"></a>Meer informatie over een invoegvoegvoeging

Voer de **Get-OrganizationAddIn-cmdlet** uit zoals hieronder wordt weergegeven voor meer informatie over alle invoegingen die naar de tenant zijn geüpload, inclusief de product-id van een invoegvoeginvoeging.
  
```powershell
Get-OrganizationAddIn
```

Voer de **Get-OrganizationAddIn-cmdlet** uit met een waarde voor de  _parameter ProductId_ om op te geven voor welke invoeginvoeging u details wilt ophalen. 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

Als u alle details van alle invoegvoegingen plus de toegewezen gebruikers en groepen wilt bekijken, geeft u de uitvoer van de **cmdlet Get-OrganizationAddIn** door naar de cmdlet Format-List, zoals wordt weergegeven in het volgende voorbeeld.
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>Een invoeging in- of uitschakelen

Als u een invoegvoeginvoeging wilt uitschakelen, zodat gebruikers en groepen die hieraan zijn toegewezen, geen toegang meer hebben, kunt u de **cmdlet Set-OrganizationAddIn** uitvoeren met de  _parameter ProductId_ en de parameter  _Enabled_ ingesteld op , zoals wordt weergegeven in het  `$false` volgende voorbeeld.
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

Als u een invoegvoeginvoeging weer wilt inschakelen, moet u dezelfde cmdlet uitvoeren met de parameter  _Enabled_ ingesteld op  `$true` .
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>Gebruikers toevoegen aan of verwijderen uit een invoegvoegvoeging

Als u gebruikers en groepen wilt toevoegen aan een specifieke invoegvoeging, kunt u de **cmdlet Set-OrganizationAddInAssignments** uitvoeren met de parameters _ProductId,_ _Toevoegen_ en _Leden._ Scheid de e-mailadressen van leden met een komma. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Als u gebruikers en groepen wilt verwijderen, moet u dezelfde cmdlet uitvoeren met de parameter _Verwijderen._ 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Als u een invoegvoeging wilt toewijzen aan alle gebruikers in de tenant, moet u dezelfde cmdlet uitvoeren met de parameter  _AssignToEveryone_ met de waarde die is ingesteld op  `$true` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

Als u geen invoegvoeging aan iedereen wilt toewijzen en wilt terugkeren naar de eerder toegewezen gebruikers en groepen, kunt u dezelfde cmdlet uitvoeren en de parameter  _AssignToEveryone_ uitschakelen door de waarde in te stellen op  `$false` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>Een invoeging bijwerken

Als u een invoegvoeging wilt bijwerken vanuit een manifest, gebruikt u de **cmdlet Set-OrganizationAddIn** met de  _parameters ProductId,_  _ManifestPath_ en  _Locale,_ zoals wordt weergegeven in het volgende voorbeeld. 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> Invoegvoegingen die zijn geüpload vanuit de Office Store worden automatisch bijgewerkt binnen enkele dagen na de nieuwste update die beschikbaar is in de Office Store. 
  
## <a name="delete-an-add-in"></a>Een invoeging verwijderen

Als u een invoeging wilt verwijderen, moet u de **cmdlet Remove-OrganizationAddIn** uitvoeren met de  _parameter ProductId,_ zoals wordt weergegeven in het volgende voorbeeld. 
  
```powershell
Remove-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<!--
## Customize Microsoft Store add-ins for your organization

You must customize the add-in before you deploy it to your organization. Add-ins older than version 1.1 are not supported by this feature. 

We recommend that you deploy a customized add-in  to yourself first to make sure it works as expected before you deploy it to your entire organization.

Note also the following restrictions:
- All URLs must be absolute (include http or https) and valid.
- *DisplayName* must not exceed 125 characters 
- *DisplayName*, *Resources* and *AppDomains* must not include the following characters: 
 
    - \<
    -  \>
    -  ;
    -  =   

If you want to customize an add-in that has been deployed, you have to uninstall it in the admin center, and see [remove an add-in from local cache](#remove-an-add-in-from-local-cache) for steps to remove it from each computer it has been deployed to.

To customize an add-in, run the **Set –OrganizationAddInOverrides** cmdlet with the *ProductId* as a parameter, followed by the tag you want to overwrite and the new value. To find out how to get the *ProductId* see [get details of an add-in](#get-details-of-an-add-in) in this article. For example:

```powershell
 Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -IconUrl "https://site.com/img.jpg" 
```
To customize multiple tags for an add-in, add those tags to the commandline:

```powershell
Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -Hosts h1, 2 -DisplayName "New DocuSign W" -IconUrl "https://site.com/img.jpg" 
```

> [!IMPORTANT]
> You must apply multiple customized tags to one add-in as one command. If you customize tags one by one, only the last customization will be applied. Additionally, if you customize a tag by mistake, you must remove all customizations and start over.

### Tags you can customize

| Tag                  | Description          |
| :------------------- | :------------------- |
| \<IconURL>   </br>| The URL of the image used as the add-in’s icon (in admin center). </br> |
| \<DisplayName>| The title of the add-in  (in admin center).|
| \<Hosts>| List of apps that will support the add-in.|
| \<SourceLocation> | The source URL that the add-in will connect to.| 
| \<AppDomains> | A list of domains that the add-in can connect with. | 
| \<SupportURL>| The URL users can use to access help and support. | 
| \<Resources>  | This tag contains a number of elements including titles, tooltips, and icons of different sizes.| 
|
### Customize Resources tag

Any element in the <Resources> tag of the manifest can be customized dynamically. You first need to check the manifest to find the element id to which you want to assign a new value. The <Resources> tag looks like this:

```
<Resources>  
    <bt:Images> 
          <bt:Image id=”img16icon” DefaultValue=”https://site.com/img.jpg” 
    </bt:Images> 
</Resources> 
``` 
In this case, the element id for the image is “img16icon” and the value associated with it is “http:<i></i>//site.<i></i>com/img.jpg.”

Once you have identified the elements you want to customize, use the following command in Powershell to assign new values to the elements:

```powershell
Set-OrganizationAddInOverrides -Resources @{“ElementID” = “New Value”; “NextElementID” = “Next New Value”} 
```

You can customize as many elements with the command as you need to.

### Remove customization from an add-in

The only option currently available for deleting customizations is to delete all of them at once:

```powershell
Remove-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### View add-in customizations

To view a list of applied customizations, run the **Get-OrganizationAddInOverrides** cmdlet. If **Get-OrganizationAddInOverrides** is run without a *ProductId* then a list of all add-ins with applied overrides are returned.  

```powershell
Get-OrganizationAddInOverrides 
```
If ProductId is specified, then a list of overrides applied to that add-in is returned. 

```powershell
Get-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### Remove an add-in from local cache

If an add-in has been deployed, it has to be removed from the cache in each computer before it can be customized. To remive an add-in from cache:

1. Navigate to the “Users” folder in C:\ 
1. Go to your user folder
1. Navigate to AppData\Local\Microsoft\Office and select the folder associated with your version of Office
1. In the *Wef* folder delete the *Manifests* folder.

-->

## <a name="get-detailed-help-for-each-cmdlet"></a>Gedetailleerde hulp voor elke cmdlet

U kunt gedetailleerde help voor elke cmdlet bekijken met behulp van de get-help-cmdlet. De volgende cmdlet bevat bijvoorbeeld gedetailleerde informatie over de Remove-OrganizationAddIn cmdlet.
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```