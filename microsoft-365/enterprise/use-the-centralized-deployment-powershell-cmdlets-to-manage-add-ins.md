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
description: Gebruik de PowerShell-cmdlets voor gecentraliseerde implementatie om Office-invoegtoepassingen te implementeren en beheren voor uw Microsoft 365-organisatie.
ms.openlocfilehash: 659f12d2533601c4b2165a95ddbf59ea521945b8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689437"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>Use the Centralized Deployment PowerShell cmdlets to manage add-ins

Als globale beheerder van Microsoft 365 kunt u Office-invoegtoepassingen implementeren voor gebruikers via de gecentraliseerde implementatie functie (Zie [Office-invoegtoepassingen implementeren in het Beheercentrum](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)). Naast de distributie van Office-invoegtoepassingen via het Microsoft 365-Beheercentrum, kunt u ook Microsoft PowerShell gebruiken. Installeer de [invoegtoepassing O365 Central Deployment module voor Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment). 

Wanneer u de module hebt gedownload, opent u een normaal Windows PowerShell-venster en voert u de volgende cmdlet uit:

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a>Verbinding maken met behulp van uw beheerdersreferenties

Voordat u de cmdlets voor gecentraliseerde implementatie kunt gebruiken, moet u zich aanmelden.
  
1. Start PowerShell.
    
2. Maak verbinding met PowerShell met behulp van uw beheerdersreferenties voor uw bedrijf. Voer de volgende cmdlet uit.
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. Voer op de pagina **referenties invoeren** uw globale beheerdersreferenties voor microsoft 365 in. U kunt ook uw referenties rechtstreeks invoeren in de cmdlet. 
    
    Voer de volgende cmdlet uit om de beheerdersreferenties voor uw bedrijf op te geven als een PSCredential-object.
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> Zie [verbinding maken met Microsoft 365 met PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585)voor meer informatie over het gebruik van PowerShell. 
  
## <a name="upload-an-add-in-manifest"></a>Een manifest van de invoegtoepassing uploaden

Voer de cmdlet **New-verwijdereneen toevoegen** uit om een invoeg toepassingsmanifest te uploaden vanuit een pad, dat een bestandslocatie of URL kan zijn. In het volgende voorbeeld ziet u een bestandslocatie voor de waarde van de  _ManifestPath_ -parameter. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

U kunt ook de **New-verwijdereneen toevoegen-in-** cmdlet uitvoeren om een invoegtoepassing te uploaden en deze toe te wijzen aan gebruikers of groepen rechtstreeks met behulp van de parameters van de  _leden_ , zoals in het volgende voorbeeld wordt weergegeven. Scheid de e-mailadressen van leden met een komma. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>Een invoegtoepassing uploaden vanuit de Office Store

Voer de **New-Get organizationaddin-** cmdlet uit om een manifest te uploaden vanuit de Office Store.
  
In het volgende voorbeeld wordt met de **New-Get organizationaddin** -cmdlet de omkt voor een invoegtoepassing opgegeven voor de vestiging en de inhoud van de Verenigde Staten.
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

Om de waarde van de parameter  _omkt_ te bepalen, kunt u deze kopiëren van de URL van de Office Store-webpagina voor de invoegtoepassing. AssetIds begint altijd met "WA", gevolgd door een cijfer. In het voorgaande voorbeeld is de bron voor de Omkt waarde van WA104099688 de URL van de Office Store-webpagina voor de invoegtoepassing: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .
  
De waarden voor de parameter  _locale_ en de parameter  _ContentMarket_ zijn identiek en geven het land of de regio waarin u de invoegtoepassing wilt installeren. De indeling is en-US, fr-FR. etc. 
  
> [!NOTE]
> Invoegtoepassingen die u uit de Office Store hebt geüpload, worden automatisch bijgewerkt binnen enkele dagen na de laatste update die beschikbaar is in de Office Store. 
  
## <a name="get-details-of-an-add-in"></a>Details van een invoegtoepassing weergeven

Voer de cmdlet **Get-Get organizationaddin** uit, zoals hieronder wordt weergegeven voor informatie over alle invoegtoepassingen die zijn geüpload naar de Tenant, inclusief product-id van invoegtoepassing.
  
```powershell
Get-OrganizationAddIn
```

Voer de cmdlet **Get-Get organizationaddin** uit met een waarde voor de parameter  _ProductID_ om op te geven welke invoegtoepassing u gegevens wilt ophalen. 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

Als u meer wilt weten over alle invoegtoepassingen plus de toegewezen gebruikers en groepen, pipet u de uitvoer van de cmdlet **Get-Get organizationaddin** naar de cmdlet List List, zoals in het volgende voorbeeld wordt weergegeven.
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>Een invoegtoepassing in-of uitschakelen

Als u een invoegtoepassing wilt uitschakelen, zodat gebruikers en groepen die hieraan zijn toegewezen, niet langer toegang hebben, voert u de cmdlet **set-Get organizationaddin** uit met de parameter  _ProductID_ en de  _ingeschakelde_ parameter ingesteld op  `$false` , zoals u kunt zien in het volgende voorbeeld.
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

Als u een invoegtoepassing weer wilt inschakelen, voert u dezelfde cmdlet uit, waarbij de parameter  _enabled_ is ingesteld op  `$true` .
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>Gebruikers aan een invoegtoepassing toevoegen of eruit verwijderen

Als u gebruikers en groepen wilt toevoegen aan een bepaalde invoegtoepassing, voert u de cmdlet **set-OrganizationAddInAssignments** uit met de parameters  _product_-id,  _toevoegen_en  _leden_ . Scheid de e-mailadressen van leden met een komma. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Als u gebruikers en groepen wilt verwijderen, voert u dezelfde cmdlet uit met de parameter  _Remove_ . 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Als u een invoegtoepassing wilt toewijzen aan alle gebruikers in de Tenant, voert u dezelfde cmdlet uit met de parameter  _para assigntoeveryone_ waarbij de waarde is ingesteld op  `$true` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

Als u een invoegtoepassing niet aan iedereen wilt toewijzen en eerder toegewezen gebruikers en groepen wilt herstellen, voert u dezelfde cmdlet uit en schakelt u de parameter  _para assigntoeveryone_ uit door de waarde in te stellen  `$false` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>Een invoegtoepassing bijwerken

Als u een invoegtoepassing wilt bijwerken vanuit een manifest, voert u de cmdlet **set-Get organizationaddin** uit met de parameters  _ProductID_,  _ManifestPath_en  _locale_ , zoals weergegeven in het volgende voorbeeld. 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> Invoegtoepassingen die u uit de Office Store hebt geüpload, worden automatisch bijgewerkt binnen enkele dagen na de laatste update die beschikbaar is in de Office Store. 
  
## <a name="delete-an-add-in"></a>Een invoegtoepassing verwijderen

Als u een invoegtoepassing wilt verwijderen, voert u de cmdlet **Remove-Get organizationaddin** uit met de parameter  _Productnummer_ , zoals wordt weergegeven in het volgende voorbeeld. 
  
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

## <a name="get-detailed-help-for-each-cmdlet"></a>Uitgebreide hulp voor elke cmdlet

Met de cmdlet Get-Help kunt u gedetailleerde Help-informatie raadplegen voor elke cmdlet. De volgende cmdlet bevat bijvoorbeeld gedetailleerde informatie over de Remove-Get organizationaddin-cmdlet.
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```


