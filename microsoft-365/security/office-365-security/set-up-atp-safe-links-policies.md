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
ms.openlocfilehash: 54b896616cf09c84525b812fed6fb3f35b07bf10
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617216"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Office 365 ATP-beleid voor veilige koppelingen instellen

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Zie [Geavanceerde Outlook.com beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)als u een thuisgebruiker bent die op zoek is naar informatie over veilige koppelingen.

[ATP Safe Links](atp-safe-links.md), een functie van [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), kan uw organisatie beschermen tegen schadelijke links die worden gebruikt bij phishing en andere aanvallen. Als u over de benodigde [machtigingen beschikt voor het Security &amp; Compliance Center,](permissions-in-the-security-and-compliance-center.md)u atp-beleid voor veilige koppelingen instellen om ervoor te zorgen dat wanneer mensen op webadressen (URL's klikken), uw organisatie wordt beschermd. Uw ATP-beleid voor veilige koppelingen kan worden geconfigureerd om URL's in e-mail en URL's in Office-documenten te scannen.

Als een gebruiker op een koppeling in een e-mail klikt en de URL is geblokkeerd door de aangepaste geblokkeerde URL-lijst van uw organisatie of als de URL als kwaadaardig is, wordt een waarschuwingspagina geopend.
  
[Nieuwe functies worden voortdurend toegevoegd aan ATP.](office-365-atp.md#new-features-in-office-365-atp) Als er nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande ATP Safe Links-beleid aanpassen.

## <a name="what-to-do"></a>Wat te doen 
  
1. Bekijk de vereisten.
    
2. Controleer en bewerk het standaard ATP Safe Links-beleid dat voor iedereen van toepassing is. U bijvoorbeeld [de aangepaste lijst met geblokkeerde URL's instellen voor ATP-veilige koppelingen.](set-up-a-custom-blocked-urls-list-atp.md)
    
3. Beleidsregels toevoegen of bewerken voor specifieke e-mailontvangers, waaronder [het instellen van de aangepaste URL's voor ATP Safe Links.](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
    
4. Meer informatie over beleidsopties voor veilige koppelingen atp (in dit artikel), inclusief instellingen voor recente wijzigingen.
    
## <a name="step-1-review-the-prerequisites"></a>Stap 1: Bekijk de vereisten

- Zorg ervoor dat uw organisatie [geavanceerde bedreigingsbeveiliging van Office 365](office-365-atp.md)heeft.
    
- Zorg ervoor dat u over de benodigde machtigingen beschikt. Als u ATP-beleid wilt definiëren (of bewerken), moet u een geschikte rol toegewezen krijgen. Enkele voorbeelden worden beschreven in de volgende tabel: <br>

    |Rol  |Waar/hoe toegewezen  |
    |---------|---------|
    |globale beheerder |De persoon die zich aanmeldt om Microsoft 365 te kopen, is standaard een globale beheerder. (Zie [Over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)         |
    |Beveiligingsbeheerder |Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
    |Exchange Online Organisatiebeheer |Exchange-beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)) |

    Zie [Machtigingen in het Security &amp; Compliance Center voor](permissions-in-the-security-and-compliance-center.md)meer informatie over rollen en machtigingen.

- Zorg ervoor dat Office-clients zijn geconfigureerd voor het gebruik [van moderne verificatie](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (dit is voor de beveiliging van ATP-veilige koppelingen in Office-documenten).
    
- [Meer informatie over beleidsopties voor veilige koppelingen bij ATP](#step-4-learn-about-atp-safe-links-policy-options) (in dit artikel). 

- Sta maximaal 30 minuten toe voor uw nieuwe of bijgewerkte beleid om zich te verspreiden naar alle Microsoft 365-datacenters.
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>Stap 2: Het ATP-beleid voor veilige koppelingen definiëren (of controleren) dat voor iedereen van toepassing is

Wanneer u [Office 365 Advanced Threat Protection hebt,](office-365-atp.md)hebt u een standaard ATP-beleid voor veilige koppelingen dat van toepassing is op iedereen in uw organisatie. Zorg ervoor dat u uw standaardbeleid controleert en indien nodig bewerkt.
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan met je werk- of schoolaccount. 
    
2. Kies in de linkernavigatie onder **Bedreigingsbeheer**De optie Veilige **koppelingen voor** **beleid \> ** .
    
3. Selecteer **Policies that apply to the entire organization** **standaard**en kies **Vervolgens Bewerken** (de knop Bewerken lijkt op een potlood).<br/>![Klik op Bewerken om uw standaardbeleid voor beveiliging van veilige koppelingen te bewerken](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. Geef in de sectie **Url's blokkeren** een of meer URL's op die u wilt voorkomen dat mensen in uw organisatie een bezoek bezoeken. (Zie [Een aangepaste lijst met geblokkeerde URL's instellen met ATP-veilige koppelingen](set-up-a-custom-blocked-urls-list-atp.md).)
    
5. Selecteer (of schakel) in de **sectie Instellingen die van toepassing zijn op inhoud, behalve op e-mail,** de opties die u wilt gebruiken in de sectie Instellingen die van toepassing zijn op inhoud, behalve op e-mail, in (of wissen). (We raden u aan alle opties te selecteren.) 
    
6. Selecteer **Save**.
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>Stap 3: ATP-beleid voor veilige koppelingen toevoegen (of bewerken) dat van toepassing is op specifieke e-mailontvangers

Nadat u het standaard ATP-beleid voor veilige koppelingen hebt gecontroleerd (of bewerkt) dat op iedereen van toepassing is, is uw volgende stap het definiëren van aanvullende beleidsregels die van toepassing zijn op specifieke ontvangers. U bijvoorbeeld uitzonderingen op uw standaardbeleid opgeven door een aanvullend beleid te definiëren. 
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan met je werk- of schoolaccount. 
    
2. Kies **beleid**in de linkernavigatie onder **Bedreigingsbeheer**.
    
3. Kies **Veilige links**.
    
4. Kies Nieuw in de sectie **Beleid dat van toepassing is op specifieke ontvangers** **(de** knop Nieuw lijkt op een plusteken ( **+** )).<br/>![Kies Nieuw om een beleid voor veilige koppelingen toe te voegen voor specifieke e-mailontvangers](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. Geef de naam, beschrijving en instellingen voor uw beleid op.<br/>**Voorbeeld:** Als u een beleid wilt instellen dat 'geen directe doorklik' wordt genoemd, waarmee mensen in een bepaalde groep in uw organisatie niet kunnen doorklikken naar een specifieke website zonder bescherming tegen veilige koppelingen van ATP, u de volgende aanbevolen instellingen opgeven: 
    
    - Typ **in** het vak Naam geen directe klik.

    - Typ in het vak **Beschrijving** een beschrijving zoals: Voorkomt dat mensen in bepaalde groepen doorklikken naar een website zonder verificatie van ATP Safe Links.

    - Kies in **de sectie Selecteer de actie** de optie **Aan**.

    - Selecteer **Real-time URL-scannen toepassen op verdachte koppelingen en koppelingen die verwijzen naar bestanden** als u URL-detonatie wilt inschakelen voor verdachte en bestandswijzende URL's (aanbevolen). En selecteer **Wachten tot URL-scannen is voltooid voordat u het bericht afgeeft** als u alleen wilt dat gebruikers berichten ontvangen nadat de URL's volledig zijn gescand.

    - Selecteer **Veilige koppelingen toepassen op berichten die binnen de organisatie worden verzonden** als u veilige koppelingen wilt inschakelen voor berichten die worden verzonden tussen gebruikers binnen uw organisatie (aanbevolen).

    - Selecteer **De gebruiker niet toestaan door te klikken naar de oorspronkelijke URL** als u niet wilt dat de afzonderlijke gebruikers een lopende *scan* of *URL-geblokkeerde* meldingspagina's overschrijven.

    - (Dit is optioneel) Geef in de sectie **De volgende URL's niet opnieuw te schrijven** een of meer URL's op die als veilig voor uw organisatie worden beschouwd. (Zie [Een aangepaste URL's'niet herschrijven instellen met ATP Safe Links)](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)

    - Kies in de sectie **Toegepast op** de ontvanger **lid van**de groep(en) die u in uw polis wilt opnemen. Kies **Toevoegen**en kies **vervolgens OK**.
    
6. Selecteer **Save**.

> [!NOTE]
> ATP Safe Links beleid met een hogere prioriteit zal voorrang hebben. Als een gebruiker is onderworpen aan twee of meer politie, alleen de hogere prioriteit beleid van kracht.
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>Stap 4: Meer informatie over beleidsopties voor VEILIGE KOPPELINGEN BIJ ATP

Als u uw ATP Safe Links-beleid instelt of bewerkt, worden er verschillende opties beschikbaar. In het geval u zich afvraagt wat deze opties zijn, beschrijft de volgende tabel elk en het effect ervan. Vergeet niet dat er twee belangrijke soorten ATP Safe Links-beleid zijn om te definiëren of te bewerken:
- een [standaardbeleid](#default-policy-options) dat voor iedereen van toepassing is; En  
- aanvullend [beleid voor specifieke ontvangers](#policies-that-apply-to-specific-email-recipients) 

### <a name="default-policy-options"></a>Standaardbeleidsopties

Standaardbeleidsopties zijn van toepassing op iedereen in uw organisatie.

|Deze optie  |Doet dit  |
|---------|---------|
| **De volgende URL's blokkeren** <br/>    | Hiermee kan uw organisatie een aangepaste lijst met URL's hebben die automatisch worden geblokkeerd. Wanneer gebruikers op een URL in deze lijst klikken, worden ze naar een [waarschuwingspagina](atp-safe-links-warning-pages.md) geleid waarin wordt uitgelegd waarom de URL is geblokkeerd. Zie [Een aangepaste lijst met geblokkeerde URL's instellen met veilige koppelingen voor Office 365 ATP](set-up-a-custom-blocked-urls-list-atp.md)voor meer informatie. |
| **Microsoft 365-apps voor bedrijven, Office voor iOS en Android** <br/>    | Wanneer deze optie is geselecteerd, wordt de bescherming van ATP Safe Links toegepast op URL's in Word-, Excel- en PowerPoint-bestanden in Windows of Mac OS, e-mailberichten in Outlook, Office-documenten op iOS- of Android-apparaten, Visio 2016-bestanden in Windows en bestanden die worden geopend in de webversies van Office-apps (Word, PowerPoint, Excel, Outlook en OneNote), op voorwaarde dat de gebruiker zich heeft aangemeld bij Office 365. |
| **Niet bijhouden wanneer gebruikers op veilige koppelingen atp klikken** <br/>  | Wanneer deze optie is geselecteerd, wordt de klik op gegevens voor URL's in Word, Excel, PowerPoint, Visio-documenten en Outlook-e-mailberichten niet opgeslagen.  <br/> |
|**Laat gebruikers niet door atp-veilige koppelingen klikken naar de oorspronkelijke URL** <br/> |Wanneer deze optie is geselecteerd, kunnen gebruikers niet voorbij een [waarschuwingspagina](atp-safe-links-warning-pages.md) naar een URL gaan waarvan wordt vastgesteld dat deze schadelijk is.  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>Beleidsregels die van toepassing zijn op specifieke e-mailontvangers

|Deze optie  |Doet dit  |
|---------|---------|
|**Uit** <br/> |Scant geen URL's in e-mailberichten.  <br/> Hiermee u een uitzonderingsregel definiëren, zoals een regel die geen URL's in e-mailberichten scant voor een specifieke groep geadresseerden.  <br/> |
|**Aan** <br/> |Herschrijft URL's om gebruikers te routeren via atp-beveiliging voor veilige koppelingen wanneer de gebruikers op URL's in e-mailberichten klikken en ATP Safe Links in Outlook (C2R) op Windows inschakelen.  <br/> Hiermee wordt een URL gecontroleerd wanneer wordt geklikt op een lijst met geblokkeerde of schadelijke URL's en wordt asynchroon een ontploffing van de URL op de achtergrond geactiveerd als de URL geen geldige reputatie heeft.  <br/> |
|**Real-time URL-scannen toepassen op verdachte koppelingen en koppelingen die verwijzen naar bestanden** <br/> |Wanneer deze optie is geselecteerd, worden verdachte URL's en koppelingen die verwijzen naar downloadbare inhoud gescand.  <br/> |
|**Wacht tot het scannen van url's is voltooid voordat u het bericht aflevert** <br/> |Wanneer deze optie is geselecteerd, worden berichten met URL's die moeten worden gescand, bewaard totdat de URL's klaar zijn met scannen en worden bevestigd dat ze veilig zijn voordat de berichten worden bezorgd.  <br/> |
|**Veilige koppelingen toepassen op berichten die binnen de organisatie worden verzonden** <br/> | Wanneer deze optie beschikbaar en geselecteerd is, wordt de bescherming van ATP Safe Links toegepast op e-mailberichten die worden verzonden tussen mensen in uw organisatie, op voorwaarde dat de e-mailaccounts worden gehost in Office 365.  <br/> |
|**Klikken van gebruikers niet bijhouden** <br/> |Wanneer deze optie is geselecteerd, worden klikgegevens voor URL's in e-mail van externe afzenders niet opgeslagen. URL-kliktracking voor koppelingen in e-mailberichten die binnen de organisatie worden verzonden, wordt momenteel niet ondersteund.  <br/> |
|**Gebruikers niet toestaan door te klikken naar de oorspronkelijke URL** <br/> |Wanneer deze optie is geselecteerd, kunnen gebruikers niet voorbij een [waarschuwingspagina](atp-safe-links-warning-pages.md) naar een URL gaan waarvan wordt vastgesteld dat deze schadelijk is.  <br/> |
|**De volgende URL's niet herschrijven** <br/> |Laat URL's zoals ze zijn. Hiermee houdt u een aangepaste lijst bij met veilige URL's die niet hoeven te worden gescand op een specifieke groep e-mailontvangers in uw organisatie.  Zie Een [aangepaste URL's-lijst 'Niet herschrijven' instellen met ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) instellen voor meer informatie, inclusief recente wijzigingen in de ondersteuning van wildcard-sterretjes ( \* ).  <br/> |
   
## <a name="next-steps"></a>Volgende stappen

Zodra uw ATP Safe Links-beleid is ingevoerd, u zien hoe ATP werkt voor uw organisatie door rapporten te bekijken. Zie de volgende bronnen voor meer informatie:

- [Rapporten voor geavanceerde bedreigingsbeveiliging van Office 365 weergeven](view-reports-for-atp.md)

- [Explorer gebruiken in het Security &amp; Compliance Center](threat-explorer.md)

Blijf op de hoogte van nieuwe functies die naar ATP komen. bezoek de [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).
