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
ms.openlocfilehash: a1a78afe7480ed9f68f8cd893c00876872317785
ms.sourcegitcommit: c876d58b34454f211b50ae5d06f193c1a1e5c4ff
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/11/2020
ms.locfileid: "43230978"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Office 365 ATP-beleid voor veilige koppelingen instellen

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Zie [Geavanceerde Outlook.com beveiliging](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)als u een thuisgebruiker bent die op zoek is naar informatie over veilige koppelingen in Outlook.

[ATP Safe Links](atp-safe-links.md), een functie van [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), kan uw organisatie beschermen tegen schadelijke links die worden gebruikt bij phishing en andere aanvallen. Als u over de benodigde [machtigingen beschikt &amp; voor het Office 365 Security Compliance Center,](permissions-in-the-security-and-compliance-center.md)u het beleid voor veilige koppelingen van ATP instellen om ervoor te zorgen dat wanneer mensen op webadressen (URL's) klikken, uw organisatie wordt beschermd. Uw BELEID voor veilige koppelingen van ATP kan worden geconfigureerd om URL's in e-mail en URL's in Office-documenten te scannen.

Als ATP Safe Links is ingeschakeld, wordt er een waarschuwingspagina geopend als een gebruiker op een koppeling in een e-mail klikt en de URL is geblokkeerd door de aangepaste geblokkeerde URL-lijst van uw organisatie of als de URL kwaadaardig is verklaard, wordt een waarschuwingspagina geopend.
  
[Nieuwe functies worden voortdurend toegevoegd aan ATP](office-365-atp.md#new-features-in-office-365-atp). Als er nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande ATP Safe Links-beleid aanpassen.

## <a name="what-to-do"></a>Wat te doen 
  
1. Bekijk de voorwaarden.
    
2. Bekijk en bewerk het standaard BELEID voor veilige links van ATP dat op iedereen van toepassing is. U bijvoorbeeld [uw aangepaste geblokkeerde URL's-lijst instellen voor ATP Safe Links.](set-up-a-custom-blocked-urls-list-wtih-atp.md)
    
3. Beleid toevoegen of bewerken voor specifieke e-mailontvangers, inclusief [het instellen van de aangepaste URL's-lijst 'Niet herschrijven' voor ATP Safe Links.](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
    
4. Meer informatie over de beleidsopties voor veilige links van ATP (in dit artikel), inclusief instellingen voor recente wijzigingen.
    
## <a name="step-1-review-the-prerequisites"></a>Stap 1: Bekijk de vereisten

- Controleer of uw organisatie [office 365 Advanced Threat Protection](office-365-atp.md)heeft.
    
- Zorg ervoor dat u over de benodigde machtigingen beschikt. Als u ATP-beleid wilt definiëren (of bewerken), moet u een geschikte rol toegewezen krijgen. Enkele voorbeelden worden beschreven in de volgende tabel: <br>

    |Rol  |Waar/hoe toegewezen  |
    |---------|---------|
    |Globale beheerder van Office 365 |De persoon die zich aanmeldt om Office 365 te kopen, is standaard een globale beheerder. (Zie [Over Office 365-beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.)         |
    |Beveiligingsbeheerder |Azure Active Directory-beheercentrum ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
    |Exchange Online Organisatiebeheer |Exchange-beheercentrum[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)( ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell)](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell) |

    Zie Machtigingen in het Office [365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.

- Zorg ervoor dat Office-clients zijn geconfigureerd om [moderne verificatie](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) te gebruiken (dit is voor de bescherming van ATP Safe Links in Office-documenten).
    
- [Meer informatie over de beleidsopties voor veilige links van ATP](#step-4-learn-about-atp-safe-links-policy-options) (in dit artikel). 

- Geef u tot 30 minuten de tijd om uw nieuwe of bijgewerkte beleid te verspreiden naar alle Office 365-datacenters.
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>Stap 2: Het BELEID voor veilige links van ATP definiëren (of beoordelen) dat voor iedereen van toepassing is

Wanneer u [Office 365 Advanced Threat Protection hebt,](office-365-atp.md)hebt u een standaard BELEID voor veilige koppelingen van ATP dat van toepassing is op iedereen in uw organisatie. Zorg ervoor dat u uw standaardbeleid controleert en indien nodig bewerkt.
  
1. Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan met je werk- of schoolaccount. 
    
2. Kies in de linkernavigatie onder **Bedreigingsbeheer**de optie **Veilige koppelingen** ** \> beleid** .
    
3. Selecteer **Standaard**en kies Bewerken in **de sectie Beleid dat van toepassing is op de hele organisatiesectie** en kies **Bewerken** (de knop Bewerken lijkt op een potlood).<br/>![Klik op Bewerken om uw standaardbeleid voor beveiliging van veilige koppelingen te bewerken](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. Geef in de sectie **De volgende URL's blokkeren** een of meer URL's op die u wilt voorkomen dat mensen in uw organisatie bezoeken. (Zie [Een aangepaste geblokkeerde URL-lijst instellen met ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).)
    
5. Selecteer **in de sectie Instellingen die van toepassing zijn op inhoud, behalve de sectie e-mail,** de opties die u wilt gebruiken.In the Settings that apply to content except email section, select (or clear) the options you want to use. (We raden u aan alle opties te selecteren.) 
    
6. Selecteer **Save**.
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>Stap 3: Beleid voor ATP-veilige koppelingen toevoegen (of bewerken) dat van toepassing is op specifieke e-mailontvangers

Nadat u het standaard BELEID voor veilige koppelingen van ATP hebt beoordeeld (of bewerkt) dat op iedereen van toepassing is, is uw volgende stap het definiëren van aanvullende beleidsregels die van toepassing zijn op specifieke ontvangers. U bijvoorbeeld uitzonderingen op uw standaardbeleid opgeven door een aanvullend beleid te definiëren. 
  
1. Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan met je werk- of schoolaccount. 
    
2. Kies In de linkernavigatie, onder **Bedreigingsbeheer**, **Beleid**.
    
3. Kies **Veilige koppelingen**.
    
4. **Kies** Nieuw in de sectie Beleid dat van toepassing is op **+** **specifieke ontvangers** (de knop Nieuw lijkt op een plusteken ( )).<br/>![Nieuw kiezen om een beleid voor veilige koppelingen toe te voegen voor specifieke e-mailontvangers](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. Geef de naam, beschrijving en instellingen voor uw beleid op.<br/>**Voorbeeld:** Als u een beleid wilt instellen dat 'geen directe klik door' wordt genoemd, zodat mensen in een bepaalde groep in uw organisatie niet naar een specifieke website kunnen klikken zonder bescherming tegen ATP Safe Links, u de volgende aanbevolen instellingen opgeven: 
    
    - Typ geen directe klik door in het vak **Naam.**

    - Typ **in het** vak Beschrijving een beschrijving zoals: Voorkomt dat mensen in bepaalde groepen doorklikken naar een website zonder verificatie van ATP Safe Links.

    - Kies **Onder De actie selecteren voor onbekende mogelijk schadelijke URL's in berichten**, kies **Aan**.

    - Als u **De actie selecteren voor onbekende of mogelijk schadelijke URL's binnen Microsoft Teams**ziet selecteren, kiest u **Op**. <br/>

    - Selecteer **Real-time URL-scannen toepassen op verdachte koppelingen en koppelingen die naar bestanden verwijzen** als u URL-ontploffing wilt inschakelen voor verdachte en bestandsaanwijzende URL's (aanbevolen). En selecteer **Wachten tot het scannen van url's is voltooid voordat** u het bericht aflevert als u wilt dat gebruikers alleen berichten ontvangen nadat de URL's volledig zijn gescand.

    - Selecteer **Veilige koppelingen toepassen op berichten die binnen de organisatie worden verzonden** als u Veilige koppelingen wilt inschakelen voor berichten die worden verzonden tussen gebruikers binnen uw organisatie (aanbevolen).

    - Selecteer **Niet toestaan dat de gebruiker doorklikt naar de oorspronkelijke URL** als u niet wilt dat de afzonderlijke gebruikers een lopende *scan* of *geblokkeerde meldingspagina's* overschrijven.

    - (Dit is optioneel) Geef in de sectie **Niet opnieuw schrijven van de volgende URL's** een of meer URL's op die als veilig voor uw organisatie worden beschouwd. (Zie [Een aangepaste URL's-lijst 'Niet herschrijven' instellen met BEHULP van ATP Safe Links)](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)

    - Kies **in** de sectie Toegepast op **De ontvanger is lid van**, en kies vervolgens de groep(en) die u in uw beleid wilt opnemen. Kies **Toevoegen**en kies **OK**.
    
6. Selecteer **Save**.

> [!NOTE]
> Het BELEID voor veilige links van ATP met een hogere prioriteit heeft voorrang. Als een gebruiker onderworpen is aan twee of meer beleidsregels, wordt alleen het beleid met een hogere prioriteit van kracht.
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>Stap 4: Meer informatie over de beleidsopties voor veilige links van ATP

Terwijl u uw ATP Safe Links-beleid instelt of bewerkt, worden verschillende opties weergegeven. In het geval u zich afvraagt wat deze opties zijn, beschrijft de volgende tabel elk en het effect ervan. Vergeet niet dat er twee belangrijke soorten ATP Safe Links-beleidsregels zijn om te definiëren of te bewerken:
- een [standaardbeleid](#default-policy-options) dat op iedereen van toepassing is; En  
- aanvullende [beleidsregels voor specifieke ontvangers](#policies-that-apply-to-specific-email-recipients) 

### <a name="default-policy-options"></a>Standaardbeleidsopties

Standaardbeleidsopties zijn van toepassing op iedereen in uw organisatie.

|Deze optie  |Is dit  |
|---------|---------|
| **De volgende URL's blokkeren** <br/>    | Hiermee kan uw organisatie een aangepaste lijst met URL's hebben die automatisch worden geblokkeerd. Wanneer gebruikers op een URL in deze lijst klikken, worden ze naar een [waarschuwingspagina](atp-safe-links-warning-pages.md) geleid waarin wordt uitgelegd waarom de URL is geblokkeerd. Zie Een [aangepaste geblokkeerde URL-lijst instellen met office 365 ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md)voor meer informatie. |
| **Office 365 ProPlus, Office voor iOS en Android** <br/>    | Wanneer deze optie is geselecteerd, wordt de bescherming van ATP Safe Links toegepast op URL's in Word-, Excel- en PowerPoint-bestanden in Windows of Mac OS, e-mailberichten in Outlook, Office-documenten op iOS- of Android-apparaten, Visio 2016-bestanden in Windows en bestanden die zijn geopend in de webversies van Office-apps (Word, PowerPoint, Excel, Outlook en OneNote), mits de gebruiker zich heeft aangemeld bij Office 365. |
| **Niet bijhouden wanneer gebruikers op ATP Safe Links klikken** <br/>  | Wanneer deze optie is geselecteerd, klikt u op gegevens voor URL's in Word, Excel, PowerPoint, Visio-documenten en Outlook-e-mailberichten.  <br/> |
|**Laat gebruikers niet door ATP Safe Links naar originele URL klikken** <br/> |Wanneer deze optie is geselecteerd, kunnen gebruikers niet verder gaan dan een [waarschuwingspagina](atp-safe-links-warning-pages.md) naar een URL waarvan is vastgesteld dat deze kwaadaardig is.  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>Beleid dat van toepassing is op specifieke e-mailontvangers

|Deze optie  |Is dit  |
|---------|---------|
|**Uit** <br/> |Scant geen URL's in e-mailberichten.  <br/> Hiermee u een uitzonderingsregel definiëren, zoals een regel die geen URL's scant in e-mailberichten voor een specifieke groep ontvangers.  <br/> |
|**Aan** <br/> |Herschrijft URL's om gebruikers te routeren via de bescherming van ATP Safe Links wanneer de gebruikers op URL's in e-mailberichten klikken en ATP Safe Links in Outlook (C2R) op Windows inschakelen.  <br/> Hiermee controleert u een URL wanneer deze wordt aangeklikt tegen een lijst met geblokkeerde of schadelijke URL's en wordt de URL op de achtergrond asynchroon gedetoerd als de URL geen geldige reputatie heeft.  <br/> |
|**Onbekende of mogelijk schadelijke URL's binnen Microsoft Teams** |Wanneer deze optie beschikbaar en geselecteerd is, worden ATP Safe Links in Microsoft Teams-chats en -kanalen ingeschakeld. Wanneer een gebruiker op een URL in een Microsoft Teams-chat of -kanaal klikt, wordt de koppeling gecontroleerd. De URL wordt gecontroleerd aan de hand van een lijst met geblokkeerde of kwaadaardige URL's en activeert een ontploffing van de URL op de achtergrond asynchroon als de URL geen geldige reputatie heeft. |
|**Real-time URL scannen toepassen op verdachte links en koppelingen die naar bestanden verwijzen** <br/> |Wanneer deze optie is geselecteerd, worden verdachte URL's en koppelingen die verwijzen naar downloadbare inhoud gescand.  <br/> |
|**Wachten tot het scannen van url's is voltooid voordat het bericht wordt geleverd** <br/> |Wanneer deze optie is geselecteerd, worden berichten met URL's die moeten worden gescand, bewaard totdat de URL's zijn gescand en worden bevestigd dat ze veilig zijn voordat de berichten worden bezorgd.  <br/> |
|**Veilige koppelingen toepassen op berichten die binnen de organisatie worden verzonden** <br/> | Wanneer deze optie is geselecteerd, wordt de bescherming van ATP Safe Links toegepast op e-mailberichten die worden verzonden tussen mensen in uw organisatie, op voorwaarde dat de e-mailaccounts worden gehost in Office 365.  <br/> |
|**Houd klikken van gebruikers niet bij** <br/> |Wanneer deze optie is geselecteerd, klikt u op gegevens voor URL's in e-mail van externe afzenders. URL-kliktracking voor koppelingen in e-mailberichten die binnen de organisatie worden verzonden, wordt momenteel niet ondersteund.  <br/> |
|**Gebruikers niet toestaan door te klikken naar de oorspronkelijke URL** <br/> |Wanneer deze optie is geselecteerd, kunnen gebruikers niet verder gaan dan een [waarschuwingspagina](atp-safe-links-warning-pages.md) naar een URL waarvan is vastgesteld dat deze kwaadaardig is.  <br/> |
|**De volgende URL's niet herschrijven** <br/> |Laat URL's zoals ze zijn. Houdt een aangepaste lijst bij met veilige URL's die niet hoeven te worden gescand voor een specifieke groep e-mailontvangers in uw organisatie.  Zie [Een aangepaste URL's-lijst 'Niet herschrijven' instellen met ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) voor meer\*informatie, inclusief recente wijzigingen in de ondersteuning van sterretjes voor jokertekens ( ).  <br/> |
   
## <a name="next-steps"></a>Volgende stappen

Zodra uw ATP Safe Links-beleid van kracht is, u zien hoe ATP voor uw organisatie werkt door rapporten te bekijken. Zie de volgende bronnen voor meer informatie:

- [Rapporten weergeven voor geavanceerde bedreigingsbeveiliging van Office 365](view-reports-for-atp.md)

- [Explorer gebruiken in &amp; het Security Compliance Center](threat-explorer.md)

Blijf op de hoogte van nieuwe functies die naar ATP komen. bezoek de [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).
