---
title: Office 365 ATP-beleid voor veilige koppelingen instellen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Stel beleid voor veilige koppelingen in om uw organisatie te beschermen tegen schadelijke koppelingen in Word-, Excel-, PowerPoint- en Visio-bestanden en in e-mailberichten.
ms.openlocfilehash: f06b2b895899973d071df384b53a090b766fd77f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809872"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Office 365 ATP-beleid voor veilige koppelingen instellen

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md)hebben. Zie [Geavanceerde Outlook.com beveiliging](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)als u een thuisgebruiker bent die op zoek is naar informatie over veilige koppelingen in Outlook.

[ATP Safe Links](atp-safe-links.md), een functie van [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), kan uw organisatie helpen beschermen tegen schadelijke koppelingen die worden gebruikt bij phishing en andere aanvallen. Als u over de [benodigde machtigingen beschikt &amp; voor het Office 365 Security Compliance Center,](permissions-in-the-security-and-compliance-center.md)u een ATP-beleid voor veilige koppelingen instellen om ervoor te zorgen dat wanneer mensen op webadressen (URL's) klikken, uw organisatie wordt beschermd. Uw ATP-beleid voor veilige koppelingen kan worden geconfigureerd om URL's in e-mail en URL's in Office-documenten te scannen.
  
[Nieuwe functies worden voortdurend toegevoegd aan ATP](office-365-atp.md#new-features-in-office-365-atp). Als er nieuwe functies worden toegevoegd, moet u mogelijk aanpassingen aanbrengen in uw bestaande ATP Safe Links-beleid.

## <a name="what-to-do"></a>Wat te doen 
  
1. Bekijk de vereisten.
    
2. Bekijk en bewerk het standaard ATP Safe Links-beleid dat voor iedereen geldt. U bijvoorbeeld [uw aangepaste geblokkeerde URL'slijst instellen voor ATP Safe Links.](set-up-a-custom-blocked-urls-list-wtih-atp.md)
    
3. Beleid toevoegen of bewerken voor specifieke e-mailontvangers, waaronder [het instellen van de aangepaste URL'slijst 'Niet herschrijven' voor ATP Safe Links.](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
    
4. Meer informatie over beleidsopties voor veilig links van ATP (in dit artikel), inclusief instellingen voor recente wijzigingen.
    
## <a name="step-1-review-the-prerequisites"></a>Stap 1: Bekijk de vereisten

- Zorg ervoor dat uw organisatie [office 365 Advanced Threat Protection](office-365-atp.md)heeft.
    
- Zorg ervoor dat u over de benodigde machtigingen beschikt. Als u het ATP-beleid wilt definiëren (of bewerken), moet u een geschikte rol toegewezen krijgen. Enkele voorbeelden worden beschreven in de volgende tabel: <br>

    |Rol  |Waar/hoe toegewezen  |
    |---------|---------|
    |Globale beheerder van Office 365 |De persoon die zich aanmeldt om Office 365 te kopen, is standaard een globale beheerder. (Zie [Informatie over office 365-beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.)         |
    |Beveiligingsbeheerder |Azure Active Directory-beheercentrum ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
    |Exchange Online Organisatiebeheer |Exchange-beheercentrum[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)( ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

    Zie Machtigingen in het Office [365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.

- Zorg ervoor dat Office-clients zijn geconfigureerd om [moderne verificatie](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) te gebruiken (dit is voor ATP Safe Links-beveiliging in Office-documenten).
    
- [Meer informatie over de beleidsopties](#step-4-learn-about-atp-safe-links-policy-options) voor veilig links van ATP (in dit artikel). 

- Geef maximaal 30 minuten de tijd om uw nieuwe of bijgewerkte beleid te verspreiden naar alle Office 365-datacenters.
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>Stap 2: Definieer (of bekijk) het ATP Safe Links-beleid dat voor iedereen geldt

Wanneer u [Office 365 Advanced Threat Protection hebt,](office-365-atp.md)hebt u een standaard ATP Safe Links-beleid dat van toepassing is op iedereen in uw organisatie. Zorg ervoor dat u uw standaardbeleid controleert en indien nodig bewerkt.
  
1. Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan met je werk- of schoolaccount. 
    
2. Kies in de linkernavigatie onder **Bedreigingsbeheer**de optie ** \> Veilig beleid** **links**.
    
3. Selecteer **standaard**in de sectie **Beleid dat van toepassing is op de hele organisatiesectie** en kies **Bewerken** (de knop Bewerken lijkt op een potlood).<br/>![Klik op Bewerken om uw standaardbeleid voor beveiliging van veilige koppelingen te bewerken](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. Geef in de sectie **Blokkeren de volgende URL's** een of meer URL's op die u wilt voorkomen dat mensen in uw organisatie een bezoek brengen. (Zie [Een aangepaste geblokkeerde URL'slijst instellen met ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).)
    
5. Selecteer in de sectie **Instellingen die van toepassing zijn op inhoud, behalve e-mail,** de opties die u wilt gebruiken (of wissen). (We raden u aan alle opties te selecteren.) 
    
6. Selecteer **Save**.
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>Stap 3: ATP-beleid voor veilige koppelingen toevoegen (of bewerken) dat van toepassing is op specifieke e-mailontvangers

Nadat u het standaard BELEID voor veilige links hebt beoordeeld (of bewerkt) dat voor iedereen van toepassing is, is uw volgende stap het definiëren van aanvullend beleid dat van toepassing zou zijn op specifieke ontvangers. U bijvoorbeeld uitzonderingen op uw standaardbeleid opgeven door een extra beleid te definiëren. 
  
1. Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan met je werk- of schoolaccount. 
    
2. Kies beleid in de linkernavigatie, onder **Bedreigingsbeheer,** **beleid**.
    
3. Kies **Veilige koppelingen**.
    
4. Kies **nieuw** in de sectie Beleid dat van toepassing is op **+** **specifieke geadresseerden** (de knop Nieuw lijkt op een plusteken ( )).<br/>![Kies Nieuw om een beleid voor veilige koppelingen toe te voegen voor specifieke e-mailontvangers](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. Geef de naam, beschrijving en instellingen voor uw beleid op.<br/>**Voorbeeld:** Als u een beleid wilt instellen met de naam 'geen directe klik door' waarmee mensen in een bepaalde groep in uw organisatie niet naar een specifieke website kunnen klikken zonder ATP Safe Links-beveiliging, u de volgende aanbevolen instellingen opgeven: 
    
  - Typ in het vak **Naam** geen directe klik door.
    
  - Typ in het vak **Beschrijving** een beschrijving zoals voorkomt dat mensen in bepaalde groepen naar een website klikken zonder verificatie van ATP Safe Links.
    
  - Kies in de sectie **De actie selecteren** de optie **Aan**.
    
  - Selecteer **Realtime URL-scannen** toepassen op verdachte koppelingen en koppelingen die naar bestanden verwijzen als u URL-ontploffing wilt inschakelen voor verdachte en file-pointing URL's (aanbevolen). En selecteer **Wachten op URL-scannen voordat** u het bericht aflevert als u gebruikers alleen berichten wilt laten ontvangen nadat de URL's volledig zijn gescand.
    
  - Selecteer Veilige koppelingen toepassen op berichten die binnen de organisatie worden **verzonden** als u Veilige koppelingen wilt inschakelen voor berichten die tussen gebruikers binnen uw organisatie worden verzonden (aanbevolen).
    
  - Selecteer **Niet toestaan dat de gebruiker doorklikt naar de oorspronkelijke URL** als u niet wilt dat de afzonderlijke gebruikers een lopende *scan* of *URL-geblokkeerde* meldingspagina's overschrijven.
    
  - (Dit is optioneel) Geef in de sectie **Niet opnieuw schrijven van de volgende URL's** een of meer URL's op die als veilig worden beschouwd voor uw organisatie. (Zie [Een aangepaste URL's-lijst 'Niet herschrijven' instellen met ATP Safe Links)](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
    
  - Kies in de sectie **Toegepast op** de optie De ontvanger is **lid van**en kies vervolgens de groep(en) die u in uw beleid wilt opnemen. Kies **Toevoegen**en kies **OK**.
    
6. Selecteer **Save**.

> [!NOTE]
> ATP Safe Links-beleid met een hogere prioriteit heeft voorrang. Als een gebruiker onderworpen is aan twee of meer politiekorpsen, wordt alleen het beleid met een hogere prioriteit van kracht.
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>Stap 4: Meer informatie over beleidsopties voor veilig links voor ATP

Tijdens het instellen of bewerken van uw ATP Safe Links-beleid ziet u verschillende opties beschikbaar. In het geval u zich afvraagt wat deze opties zijn, beschrijft de volgende tabel elk en het effect ervan. Vergeet niet dat er twee belangrijke soorten ATP Safe Links-beleid zijn om te definiëren of te bewerken:
- een [standaardbeleid](#default-policy-options) dat voor iedereen geldt; En  
- aanvullende [beleidsregels voor specifieke ontvangers](#policies-that-apply-to-specific-email-recipients) 

### <a name="default-policy-options"></a>Standaardbeleidsopties

Standaardbeleidsopties zijn van toepassing op iedereen in uw organisatie.

|Deze optie  |Heeft dit  |
|---------|---------|
| **De volgende URL's blokkeren** <br/>    | Hiermee kan uw organisatie een aangepaste lijst met URL's hebben die automatisch worden geblokkeerd. Wanneer gebruikers op een URL in deze lijst klikken, worden ze naar een [waarschuwingspagina](atp-safe-links-warning-pages.md) geleid waarin wordt uitgelegd waarom de URL is geblokkeerd. Zie [Een aangepaste lijst met geblokkeerde URL's instellen met Office 365 ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md)voor meer informatie. |
| **Office 365 ProPlus, Office voor iOS en Android** <br/>    | Wanneer deze optie is geselecteerd, wordt ATP Safe Links-beveiliging toegepast op URL's in Word-, Excel- en PowerPoint-bestanden op Windows of Mac OS, e-mailberichten in Outlook, Office-documenten op iOS- of Android-apparaten, Visio 2016-bestanden op Windows en bestanden die worden geopend in de webversies van Office-apps (Word, PowerPoint, Excel, Outlook en OneNote), op voorwaarde dat de gebruiker zich heeft aangemeld bij Office 365. |
| **Niet bijhouden wanneer gebruikers op ATP Safe Links klikken** <br/>  | Wanneer deze optie is geselecteerd, klikt u op gegevens voor URL's in Word, Excel, PowerPoint, Visio-documenten en E-mailberichten van Outlook niet.  <br/> |
|**Laat gebruikers niet klikken via ATP Safe Links naar originele URL** <br/> |Wanneer deze optie is geselecteerd, kunnen gebruikers niet voorbij een [waarschuwingspagina](atp-safe-links-warning-pages.md) gaan naar een URL waarvan wordt vastgesteld dat ze kwaadaardig zijn.  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>Beleid dat van toepassing is op specifieke e-mailontvangers

|Deze optie  |Heeft dit  |
|---------|---------|
|**Uit** <br/> |Scant geen URL's in e-mailberichten.  <br/> Hiermee u een uitzonderingsregel definiëren, zoals een regel die URL's niet scant in e-mailberichten voor een specifieke groep ontvangers.  <br/> |
|**Op** <br/> |Herschrijft URL's om gebruikers te routeren via atp safe links-beveiliging wanneer de gebruikers op URL's in e-mailberichten klikken en ATP Safe Links in Outlook (C2R) op Windows inschakelen.  <br/> Hiermee controleert u een URL wanneer u wordt aangeklikt tegen een lijst met geblokkeerde of schadelijke URL's en wordt de URL op de achtergrond asynchroon gedetonatied als de URL geen geldige reputatie heeft.  <br/> |
|**Realtime URL-scannen toepassen op verdachte koppelingen en koppelingen die naar bestanden verwijzen** <br/> |Wanneer deze optie is geselecteerd, worden verdachte URL's en koppelingen die verwijzen naar downloadbare inhoud gescand.  <br/> |
|**Wacht tot URL-scan is voltooid voordat u het bericht aflevert** <br/> |Wanneer deze optie is geselecteerd, worden berichten met URL's die moeten worden gescand, bewaard totdat de URL's het scannen zijn voltooid en worden bevestigd dat ze veilig zijn voordat de berichten worden bezorgd.  <br/> |
|**Veilige koppelingen toepassen op berichten die binnen de organisatie worden verzonden** <br/> | Wanneer deze optie beschikbaar en geselecteerd is, wordt de atp-beveiliging voor veilige koppelingen toegepast op e-mailberichten die tussen mensen in uw organisatie worden verzonden, op voorwaarde dat de e-mailaccounts worden gehost in Office 365.  <br/> |
|**Klikken van gebruikers niet bijhouden** <br/> |Wanneer deze optie is geselecteerd, klikt u op gegevens voor URL's in e-mail van externe afzenders. URL-kliktracking voor koppelingen in e-mailberichten die binnen de organisatie worden verzonden, wordt momenteel niet ondersteund.  <br/> |
|**Laat gebruikers niet doorklikken naar de oorspronkelijke URL** <br/> |Wanneer deze optie is geselecteerd, kunnen gebruikers niet voorbij een [waarschuwingspagina](atp-safe-links-warning-pages.md) gaan naar een URL waarvan wordt vastgesteld dat ze kwaadaardig zijn.  <br/> |
|**De volgende URL's niet herschrijven** <br/> |Laat URL's zoals ze zijn. Houdt een aangepaste lijst bij met veilige URL's die niet hoeven te worden gescand voor een specifieke groep e-mailontvangers in uw organisatie.  Zie [Een aangepaste URL's instellen met behulp van ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) voor meer informatie, inclusief\*recente wijzigingen in de ondersteuning voor wildcardsterretjes ( ).  <br/> |
   
## <a name="next-steps"></a>Volgende stappen

Zodra uw ATP Safe Links-beleid van kracht is, u zien hoe ATP werkt voor uw orgnization door rapporten te bekijken. Zie de volgende bronnen voor meer informatie:

- [Rapporten weergeven voor geavanceerde bedreigingsbeveiliging van Office 365](view-reports-for-atp.md)

- [Explorer gebruiken in &amp; het Security Compliance Center](threat-explorer.md)

Blijf op de hoogte van nieuwe functies die naar ATP komen. bezoek de [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).
