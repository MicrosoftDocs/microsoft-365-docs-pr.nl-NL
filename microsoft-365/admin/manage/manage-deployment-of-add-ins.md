---
title: Implementatie van invoegtoepassingen in het beheercentrum beheren
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Meer informatie over het implementeren van invoegtoepassingen voor gebruikers en groepen in uw organisatie met behulp van gecentraliseerde implementatie in het beheercentrum.
ms.openlocfilehash: 25a4cd4147f6388cdbd8982eb10624e7b7e8f6cb
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780119"
---
# <a name="manage-deployment-of-add-ins-in-the-microsoft-365-admin-center"></a>De implementatie van invoegtoepassingen in het Microsoft 365-beheercentrum beheren

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Met Office-invoegtoepassingen kunt u uw documenten aan uw persoonlijke voorkeur aanpassen en de manier waarop u toegang krijgt tot informatie op internet stroomlijnen (zie [Uw Office-invoegtoepassing gebruiken](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Als beheerder u Office-invoegtoepassingen implementeren voor de gebruikers in uw organisatie. U dit doen met de functie Gecentraliseerde implementatie in het Microsoft 365-beheercentrum.
  
Gecentraliseerde implementatie is de aanbevolen en meest veelzijdige manier voor de meeste beheerders om invoegtoepassingen te implementeren voor gebruikers en groepen binnen een organisatie. Zie [Bepalen of Gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie voor](centralized-deployment-of-add-ins.md)meer informatie over hoe u bepalen of uw organisatie gecentraliseerde implementatie kan ondersteunen.
  
Gecentraliseerde implementatie biedt de volgende voordelen:
  
- Een globale beheerder kan een invoegtoepassing rechtstreeks aan een gebruiker toewijzen, aan meerdere gebruikers via een groep, of aan iedereen in de tenant.
    
- When the relevant Office application starts, the add-in automatically downloads for the user. If the add-in supports add-in commands, the add-in automatically appears in the Ribbon within the Office application.
    
- Invoegtoepassingen worden niet meer weergegeven voor gebruikers als de beheerder de invoegtoepassing uitschakelt of verwijdert, of als de gebruiker wordt verwijderd uit Azure Active Directory of uit een groep waaraan de invoegtoepassing is toegewezen.
    
> [!NOTE]
>  Voor Word gebruiken Excel en PowerPoint een [SharePoint-app-catalogus](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) om invoegtoepassingen te implementeren voor gebruikers in een on-premises omgeving zonder dat er verbinding is met Microsoft 365 en/of ondersteuning voor SharePoint-invoegtoepassingen. > Voor Outlook gebruik exchange-configuratiescherm om te implementeren in een on-premises omgeving zonder verbinding met Microsoft 365. > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Aanbevolen werkwijze voor de implementatie van Office-invoegtoepassingen

Consider rolling out add-ins in a phased approach to help ensure your add-in deployment goes smoothly. We recommend the following plan:
  
1. Roll-out the add-in to a small set of business stakeholders and members of the IT department. Evaluate if the deployment was successful, and if so, move on to step 2.
    
2. Roll-out to a larger set of individuals within the business who will be using the add-in. Again, evaluate results and, if all went well, go to the next step of a full deployment.
    
3. Rol de invoegtoepassing volledig uit naar de gehele doelgroep.
    
Afhankelijk van de grootte van de doelgroep, kunt u eventueel uitrolstappen toevoegen of verwijderen.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Een Office-invoegtoepassing implementeren met het beheercentrum

Zie [Bepalen of Gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie.](centralized-deployment-of-add-ins.md)

  
1. Ga in het beheercentrum **Settings** naar de pagina \> **Instellingen invoegtoepassingen.**
    
2. Selecteer **Invoegtoepassing** implementeren boven aan de pagina. Selecteer Volgende op de **overzichtspagina.**
    
3. Selecteer een optie en volg de instructies.
  
4. Als u de optie hebt geselecteerd om een invoegtoepassing toe te voegen in de Office Store, u nu uw invoegselectie maken. De beschikbare invoegtoepassingen worden weergegeven in de categorieën **Voorgesteld voor u**, **Beoordeling** en **Naam**. Er kunnen alleen gratis invoegtoepassingen worden toegevoegd vanuit de Office Store. Betaalde invoegtoepassingen worden momenteel niet ondersteund. Zodra je je invoegtoepassing hebt geselecteerd, moet je akkoord gaan met een aantal aanvullende voorwaarden om door te gaan. <br/><br/> OPMERKING: Met de optie Office Store worden updates en verbeteringen aan de invoegtoepassing automatisch beschikbaar gesteld aan gebruikers zonder tussenkomst.

5. Selecteer op de volgende pagina **Iedereen**, **Specifieke gebruikers/groepen** of **Just me** om aan te geven aan wie de invoegtoepassing is geïmplementeerd. Gebruik het vak Zoeken om de gebruikers of groepen te zoeken waarvoor u de invoegtoepassing wilt implementeren. <br/>OPMERKING: Meer informatie over de andere statussen die van toepassing zijn op een invoegtoepassing. Zie [Statussen van invoegtoepassingen](#add-in-states) verderop in dit onderwerp.
  
6. Selecteer **Implementeren**.
  
7. Er verschijnt een groene teek wanneer de invoegtoepassing is geïmplementeerd. U de instructies op de pagina volgen om te testen of de invoegtoepassing is geïmplementeerd.

> [!NOTE]
> Gebruikers moeten Office mogelijk opnieuw starten om het invoegpictogram op het lint van de app te zien verschijnen. Outlook-invoegtoepassingen kunnen tot 24 uur duren voordat ze op linten van gebruikers worden weergegeven.
    
8. Selecteer **Volgende**als u klaar bent. Als u alleen bent geïmplementeerd, u Wijzigen selecteren **die toegang heeft tot invoegtoepassing** om meer gebruikers te implementeren.



Als u de invoegtoepassing voor leden van uw organisatie anders dan uzelf hebt geïmplementeerd, volgt u de instructies die worden weergegeven om de implementatie van de invoegtoepassing effectief aan te kondigen. <br/>U ziet nu uw invoegtoepassing samen met andere apps in Microsoft 365.
  
It's a good idea to inform the users and groups who you deployed the add-in to so that they know that it's available. Consider sending an email to them that describes when and how to use the add-in and explains how the add-in can help them do their job better. Include or link to relevant Help content or FAQs that might help if users have any problems with the add-in.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Overwegingen bij het toewijzen van een invoegtoepassing aan gebruikers en groepen

Admins can assign an add-in to everyone or to specific users and groups. Each option has implications:
  
- **Everyone**: As the name implies, this option assigns the add-in to every user in the tenant. Use this option sparingly and only for add-ins that are truly universal to your organization. 
    
- **Users**: If you assign an add-in to an individual user, then to deploy the add-in to a new user, you will need to first add that user. The same goes for removing users. 
    
- **Groups**: If you assign an add-in to a group, users who are added to the group will automatically be assigned the add-in. And, when a user is removed from a group, the user loses access to the add-in. In either case, no additional action is required from you as the admin. 

- **Just me**: Als u een invoegtoepassing aan uzelf toewijst, wijst dit de invoegtoepassing alleen aan uw account toe. Dit is ideaal als u de add-in eerst wilt testen.
    
The option that is right for your organization depends on your configuration. However, we recommend making assignments via groups. As an admin, you might find it easier to manage add-ins using groups and control the membership of those groups rather than having to change the users assigned each time. On the other hand, in some situations, you may want to restrict access to a very small set of users and therefore make assignments to specific users. As a result, you will need to manage the assigned users manually.
  
### <a name="add-in-states"></a>Statussen van invoegtoepassingen

Een invoegtoepassing kan zich in de status **Aan** of **Uit** besgaan.
  
|**Status**|**Hoe de status optreedt**|**Impact**|
|:-----|:-----|:-----|
|**Actief**  <br/> |De beheerder heeft de invoegtoepassing geüpload en toegewezen aan gebruikers of groepen.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, zien de invoegtoepassing in de desbetreffende clients.  <br/> |
|**Uitgeschakeld**  <br/> |De beheerder heeft de invoegtoepassing uitgeschakeld.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.  <br/> Als de status van de invoegtoepassing wordt gewijzigd in Actief, hebben de gebruikers en groepen opnieuw toegang tot de invoegtoepassing.  <br/> |
|**Verwijderd**  <br/> |De beheerder heeft de invoegtoepassing verwijderd.  <br/> |Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.  <br/> |
   
Consider deleting an add-in if no one is using it any more. Turning off an add-in may make sense if an add-in is used only during specific times of the year.
  
### <a name="security-of-office-add-ins"></a>Beveiliging van Office-invoegtoepassingen

Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:
  
- Gegevens weergeven.
    
- Het document van een gebruiker lezen om op context gebaseerde services te bieden.
    
- Gegevens van het document van een gebruiker lezen of er gegevens naar schrijven.
    
Zie [Office Add-ins platform overview](https://go.microsoft.com/fwlink/p/?linkid=846362) (Overzicht van platforms voor Office-invoegtoepassingen), met name de sectie Anatomy of an Office Add-in (Anatomie van een Office-invoegtoepassing).
  
To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.
  
Updates voor invoegtoepassingen worden als volgt uitgevoerd:
  
- **Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 

    > [!NOTE]
    > De beheerder hoeft geen LOB-invoegtoepassing te verwijderen voor het uitvoeren van een update.   In de sectie Invoegtoepassingen kan admin eenvoudig op de LOB-invoegtoepassing klikken en de **knop Bijwerken** rechtsonder kiezen. Update werkt alleen als de versie van de nieuwe invoegtoepassing groter is dan die van de bestaande invoegtoepassing.   
    
- **Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 

### <a name="edit-add-in-access"></a>Invoegtoepassingstoegang bewerken

Na de implementatie kunnen beheerders ook de gebruikerstoegang tot invoegtoepassingen wijzigen.

1. Ga in het beheercentrum **Settings**naar de  >  **pagina Instellingenservices & invoegtoepassingen.**

2. Selecteer de geïmplementeerde invoegtoepassing.

3. Klik op **Bewerken** onder **Wie heeft Toegang**.
4. Sla de wijzigingen op.
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Downloads van invoegtoepassing voorkomen door de Office Store voor alle clients uit te schakelen (behalve Outlook)

> [!NOTE]
> De installatie van Outlook-invoegtoepassingen wordt beheerd via een [ander proces](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).

As an organization you may wish to prevent the download of new Office add-ins from the Office Store. This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.
  
Aanschaf van invoegtoepassingen uitschakelen:
  
1. Ga in het beheercentrum naar de pagina**Instellingen** \> [Services &amp; invoegtoepassingen](https://go.microsoft.com/fwlink/p/?linkid=2053743).
    
3. Selecteer **apps en services van gebruikers.**
    
4. Schakel de optie uit om gebruikers toegang te geven tot het Office-winkel.

Hierdoor wordt voorkomen dat alle gebruikers de volgende invoegtoepassingen via de store kunnen aanschaffen.
  
- Invoegtoepassingen voor Word, Excel en PowerPoint 2016 van:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Aanschaf die begint vanuit **AppSource**
    
- Invoegtoepassingen binnen Microsoft 365
    
Een gebruiker die toegang probeert te krijgen tot de store, ziet het volgende bericht: **Sorry, Microsoft 365 is geconfigureerd om individuele acquisitie van Office Store-invoegtoepassingen te voorkomen.**
  
Ondersteuning voor het uitschakelen van Office Store is beschikbaar in de volgende versies:
  
- Windows: 16.0.9001 - Momenteel beschikbaar.
    
- Mac: 16.10.18011401: momenteel beschikbaar.
    
- iOS: 2.9.18010804: momenteel beschikbaar.
    
- Het web - Momenteel beschikbaar.
    
Hiermee wordt niet voorkomen dat een beheerder Gecentraliseerde implementatie gebruikt om invoegtoepassingen vanuit Office Store toe te wijzen.
  
To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account. For more information, look [here](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minderjarigen en het verkrijgen van invoegtoepassingen uit de Store

The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018. It gives users rights to and protection of their data. One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved. The specific age defined as a minor depends on the region where the individual is located.
  
Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union. For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired. For countries without statutory regulations, there will be no download restrictions.
  
A user is determined to be a minor based on data specified in Azure Active Directory. The tenant admin is responsible for declaring the legal age group and the parental consent for that user.
  
Als de ouders of voogd toestaan dat een minderjarige een bepaalde invoegtoepassing gebruikt, kan de tenantbeheerder gecentraliseerde implementatie gebruiken om deze invoegtoepassing te implementeren voor alle minderjarigen die toestemming hebben.
  
Als u wilt dat uw school of organisatie voldoet aan de AVG-vereisten voor minderjarigen, moet een van de volgende versies van Office zijn geïmplementeerd in uw school/organisatie.
  
 **Voor Word, Excel, PowerPoint en Project**: 
  
|||
|:-----|:-----|
|**Platform** <br/> |**Buildnummer** <br/> |
|Microsoft 365-apps voor bedrijven (huidig kanaal)  <br/> |9001.2138   <br/> |
|Microsoft 365 Apps voor bedrijven (halfjaarlijks Bedrijfskanaal)  <br/> |8431.2159  <br/> |
|Office 2016 voor Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 voor Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 voor Mac  <br/> |16.11.18020200  <br/> |
|Office voor het web  <br/> |N.v.t.  <br/> |
   
 **Voor Outlook**: 
  
|||
|:-----|:-----|
|**Platform** <br/> |**Buildnummer** <br/> |
|Outlook 2016 voor Windows (MSI)  <br/> |Buildnummer n.t.b.  <br/> |
|Outlook 2016 voor Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 voor Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile voor iOS  <br/> |2.75.0  <br/> |
|Outlook Mobile voor Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |N.v.t.  <br/> |
   
 **Vereisten voor Office 2013**
  
Word, Excel, and PowerPoint 2013 for Windows will support the same minor checks if Active Directory Authentication Library (ADAL) is enabled. There are two options for compliance, as explained next.
  
- **ADAL inschakelen**. In dit artikel wordt uitgelegd hoe u ADAL voor Office 2013 inschakelen: [Microsoft 365 moderne verificatie gebruiken met Office-clients](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).<br/>U hebt ook de registersleutels nodig om ADAL in te schakelen, zoals wordt beschreven in [Moderne verificatie inschakelen voor Office 2013 op Windows-apparaten](../security-and-compliance/enable-modern-authentication.md).<br/>Daarnaast moet u deze updates van april voor Office 2013 installeren:
    
  - [Beschrijving van de beveiligingsupdate voor Outlook 2013: 10 april 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 april 2018, update voor Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Schakel ADAL niet in.** Als u ADAL niet kunt inschakelen in Office 2013, bevelen wij aan om Groepsbeleid te gebruiken om de Store voor de Office-clients uit te schakelen. Informatie over het uitschakelen van de app voor Office-instellingen vindt u [hier](https://technet.microsoft.com/library/cc178992.aspx).
    
## <a name="end-user-experience-with-add-ins"></a>Ervaring van eindgebruikers met invoegtoepassingen

Now that you've deployed the add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). The add-in will appear on all platforms that the add-in supports.
  
If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in. 

![Office-lint met zoekvermeldingen](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Als de geïmplementeerde invoegtoepassing geen ondersteuning biedt voor opdrachten van de invoegtoepassing of als u alle geïmplementeerde invoegtoepassingen wilt weergeven, kunt u ze weergeven via **Mijn invoegtoepassingen**. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>In Word 2016, Excel 2016 of PowerPoint 2016

1. Selecteer ** \> Mijn invoegtoepassingen invoegen**. 
    
2. Selecteer het tabblad **Beheerd door beheerder** in het venster Office-invoegtoepassingen. 
    
3. Dubbelklik op de invoegtoepassing die u eerder hebt geïmplementeerd (in dit voorbeeld **Bronvermeldingen** ). <br/>![Tabblad Beheerde van de pagina Office-invoegtoepassingen](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>In Outlook

1. Selecteer op **het** startlint de optie **Invoegtoepassingen ophalen**.<br/>![Knop Store in Outlook](../../media/getaddinsicon.png)
  
2. Selecteer **Beheerd beheer** in het linkernavigatiesysteem.

## <a name="delete-the-add-in"></a>De invoegtoepassing verwijderen

U ook een invoegtoepassing verwijderen die is geïmplementeerd.

1. Ga in het beheercentrum **Settings**naar de  >  **pagina Instellingenservices & invoegtoepassingen.**

2. Selecteer de geïmplementeerde invoegtoepassing.

3. Klik op **Invoegtoepassing verwijderen**. Verwijder de invoegknop rechtsonder.
4. Valideer uw selecties en kies **Invoegtoepassing verwijderen.**
  
## <a name="learn-more"></a>Meer informatie

Lees meer over het maken en bouwen van [Office-invoegtoepassingen](https://go.microsoft.com/fwlink/p/?linkid=846362).
  
[Gebruik Gecentraliseerde PowerShell-cmdlets voor het beheren van invoegtoepassingen.](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Problemen oplossen: gebruiker ziet geen invoegtoepassingen](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
