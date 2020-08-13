---
title: Beleidsregels voor veilige koppelingen in Office 365 instellen
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
description: Stel beleidsregels voor veilige koppelingen in om uw organisatie te beschermen tegen kwaadaardige koppelingen in Word-, Excel-, PowerPoint-en Visio-bestanden, evenals e-mailberichten.
ms.openlocfilehash: 4aa6947af114856d73c3e048b829daf8f47f0f48
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652643"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>Beleidsregels voor veilige koppelingen in Office 365 instellen

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Als u een thuisgebruiker bent die op zoek bent naar informatie over veilige koppelingen in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

[Veilige koppelingen voor ATP](atp-safe-links.md), een functie van [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), kan u helpen uw organisatie te beschermen tegen kwaadaardige koppelingen die worden gebruikt in phishing en andere aanvallen. Als u over de benodigde [machtigingen beschikt voor het nalevings centrum voor de beveiliging &](permissions-in-the-security-and-compliance-center.md), kunt u het beleid voor veilige koppelingen van ATP instellen om ervoor te zorgen dat wanneer mensen op webadressen (url's) klikken, uw organisatie is beveiligd. Uw beleidsregels voor veilige koppelingen voor Office kunnen worden geconfigureerd voor het scannen van Url's in e-mail en Url's in Office-documenten.

Wanneer een gebruiker een e-mailbericht op een koppeling in een e-mailbericht op een koppeling in een e-mailbericht klikt, wordt de pagina met geblokkeerde URL'S van de organisatie geblokkeerd, of als de URL is vastgesteld om schadelijk te zijn, wordt een waarschuwingspagina geopend.

[Nieuwe functies worden continu toegevoegd aan ATP](office-365-atp.md#new-features-in-office-365-atp). Wanneer nieuwe functies worden toegevoegd, moet u mogelijk de bestaande beleidsregels voor veilige koppelingen van de toepassing aanpassen.

## <a name="what-to-do"></a>Wat moet u doen?

1. Controleer de vereisten.

2. Het standaardbeleid voor het instellen van vrije verbindingen voor alle gebruikers bekijken en bewerken. U kunt bijvoorbeeld [de lijst met aangepaste geblokkeerde url's instellen voor veilige koppelingen met ATP](set-up-a-custom-blocked-urls-list-atp.md).

3. Hiermee kunt u beleidsregels voor specifieke e-mail geadresseerden toevoegen of bewerken, waaronder [het instellen van de lijst met url's die niet opnieuw schrijven niet herschrijven voor veilige koppelingen met ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).

4. Meer informatie over de beleidsopties voor het instellen van vrije koppelingen (in dit artikel), waaronder instellingen voor recente wijzigingen.

## <a name="step-1-review-the-prerequisites"></a>Stap 1: de vereisten controleren

- Zorg ervoor dat uw organisatie [Office 365 Advanced Threat Protection](office-365-atp.md)heeft.

- Zorg ervoor dat u de benodigde machtigingen hebt. Als u ATP-beleidsregels wilt definiëren (of bewerken), moet aan u de juiste rol zijn toegewezen. In de volgende tabel worden enkele voorbeelden beschreven:

    |Rol|Where/hoe toegewezen|
    |---|---|
    |globale beheerder|De persoon die zich registreert voor het kopen van Microsoft 365 is standaard een globale beheerder. (Zie [informatie over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)|
    |Beveiligingsbeheerder|Azure Active Directory-beheercentrum ( <https://aad.portal.azure.com> )|
    |Beheer van organisatie van Exchange Online|Exchange-Beheercentrum ( <https://outlook.office365.com/ecp> ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|

    Als u meer wilt weten over rollen en machtigingen, raadpleegt u [machtigingen in de sectie beveiliging & nalevings centrum](permissions-in-the-security-and-compliance-center.md).

- Zorg dat Office-clients zijn geconfigureerd voor het gebruik van [moderne verificatie](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (deze optie is bedoeld voor beveiliging van vrije documenten in Office-documenten).

- [Meer informatie over de beleidsopties voor het instellen van vrije koppelingen](#step-4-learn-about-atp-safe-links-policy-options) in dit artikel.

- Maximaal 30 minuten toegestaan voor uw nieuwe of bijgewerkte beleid voor alle Microsoft 365-datacenters.

## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>Stap 2: het beleid voor veilige verbindingen voor ATP definiëren (of controleren) dat van toepassing is op iedereen

Wanneer u [Office 365 Advanced Threat Protection](office-365-atp.md)hebt, beschikt u over het standaardbeleid voor veilige koppelingen voor vrije verbindingen dat van toepassing is op iedereen in uw organisatie. Zorg ervoor dat u het standaardbeleid controleert en zonodig bewerkt.

1. Ga naar <https://protection.office.com> en meld u aan met uw werk-of schoolaccount.

2. Kies in het linker navigatiegedeelte onder **Threat Management**de **optie \> beleids** **veilige koppelingen**.

3. Selecteer in de sectie **beleidsregels die van toepassing zijn op het hele organigram** de optie **standaard**en kies vervolgens **bewerken** (de knop bewerken lijkt op een potlood).

   ![Klik op bewerken om uw standaardbeleid te bewerken voor beveiliging van beveiligde koppelingen](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)

4. Geef in de sectie **de volgende Url's blokkeren** een of meer url's op die u wilt voorkomen dat de personen in uw organisatie bezoeken. (Zie [een aangepaste lijst met geblokkeerde Url's instellen met behulp van behulp van ATP voor veilige koppelingen](set-up-a-custom-blocked-urls-list-atp.md).)

5. Selecteer in de sectie **instellingen die van toepassing zijn op inhoud behalve e-mail** de optie die u wilt gebruiken (of wissen). (U kunt het beste alle opties selecteren.)

6. Selecteer **Save**.

## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>Stap 3: het beleid voor veilige koppelingen voor ATP toevoegen (of bewerken) en toepassen op specifieke e-mail geadresseerden

Nadat u het standaardbeleid voor veilige verbindingen voor ATP hebt gecontroleerd (of bewerkt) dat van toepassing is op iedereen, moet u extra beleidsregels definiëren die van toepassing zijn op bepaalde geadresseerden. U kunt bijvoorbeeld uitzonderingen opgeven voor uw standaardbeleid door een extra beleid te definiëren.

1. Ga naar <https://protection.office.com> en meld u aan met uw werk-of schoolaccount.

2. Kies in het linker navigatiegedeelte onder **Threat Management**de optie **beleid**.

3. Kies **veilige koppelingen**.

4. Kies in de sectie **beleidsregels die gelden voor specifieke geadresseerden** de optie **Nieuw** (de knop Nieuw lijkt op een plusteken ( **+** )).

   ![Kies Nieuw om een beleid voor veilige koppelingen toe te voegen voor specifieke e-mail geadresseerden](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

5. Geef de naam, de beschrijving en de instellingen op voor uw beleid.

   **Voorbeeld:** Als u een beleid met de naam ' niet rechtstreeks klikken ' wilt instellen, kunt u niet dat personen in een bepaalde groep in uw organisatie op de hoogte worden geklikt op een specifieke website zonder dat de beschermings beveiliging vrij is, u kunt de volgende aanbevolen instellingen opgeven:

   - Typ in het vak **naam** niet direct klikken.

   - Typ in het vak **Beschrijving** een beschrijving als beschrijving, zodat personen in bepaalde groepen niet kunnen klikken op een website zonder dat de verificatie voor veilige koppelingen wordt gecontroleerd.

   - Kies in de sectie **Selecteer de actie** **aan**.

   - Selecteer **realtime doorzoeken van Url's toepassen op verdachte koppelingen en koppelingen die verwijzen naar bestanden** als u de detonatie van url's wilt inschakelen voor verdachte bestanden en url's voor bestanden waarnaar wordt verwezen (aanbevolen). En selecteer **wachten tot het scannen van de URL moet voltooien voordat u het bericht** ontvangt als u wilt dat gebruikers alleen berichten kunnen ontvangen nadat de url's volledig zijn gecontroleerd.

   - Selecteer **veilige koppelingen toepassen op berichten die binnen de organisatie worden verzonden** als u veilige koppelingen wilt inschakelen voor berichten die tussen gebruikers binnen uw organisatie worden verzonden (aanbevolen).

   - Selecteer **gebruikers niet toestaan om door te gaan naar de oorspronkelijke URL** als u niet wilt dat de afzonderlijke gebruikers een *Scan* worden overschreven of meldingen met *URL-geblokkeerde* pagina's.

   - (Dit is optioneel) Geef in de sectie **niet herschrijven de volgende url's** een of meer url's op die als veilig worden beschouwd voor uw organisatie. (Zie [een aangepaste lijst van url's die niet opnieuw schrijven is met behulp van behulp van openbare koppelingen instellen](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)

   - Kies in de sectie **toegepast op** **de geadresseerde lid van**en kies vervolgens de groep (en) die u wilt opnemen in uw beleid. Kies **toevoegen**en kies vervolgens **OK**.

6. Selecteer **Save**.

> [!NOTE]
> Beleidsregels voor veilige koppelingen met een hogere prioriteit hebben voorrang. Als een gebruiker twee of meer politiet, wordt alleen het beleid voor de hoogste prioriteit van kracht.

## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>Stap 4: meer informatie over de beleidsopties voor het instellen van ATP voor veilige koppelingen

Wanneer u uw beleid voor veilige koppelingen voor vrije documenten instelt of bewerkt, ziet u diverse beschikbare opties. Als u zich afvraagt wat deze opties zijn, worden deze in de onderstaande tabel beschreven. Houd er rekening mee dat u het volgende moet doen:

- een [standaardbeleid](#default-policy-options) dat van toepassing is op iedereen; en
- extra [beleidsregels voor specifieke geadresseerden](#policies-that-apply-to-specific-email-recipients)

### <a name="default-policy-options"></a>Standaard beleidsopties

Standaard beleidsopties gelden voor iedereen in uw organisatie.

****

|Optie|Doet dit|
|---|---|
|**De volgende Url's blokkeren**|Hiermee kan uw organisatie een aangepaste lijst met Url's maken die automatisch worden geblokkeerd. Wanneer gebruikers op een URL in deze lijst klikken, wordt een [waarschuwingspagina](atp-safe-links-warning-pages.md) weergegeven waarin u uitlegt waarom de URL is geblokkeerd. Zie voor meer informatie [een aangepaste lijst met geblokkeerde Url's instellen met behulp van Office 365](set-up-a-custom-blocked-urls-list-atp.md).|
|**Microsoft 365-apps voor Enterprise, Office voor iOS en Android**| Wanneer deze optie is geselecteerd, beveiliging van ATP voor veilige koppelingen wordt toegepast op Url's in Word-, Excel-en PowerPoint-bestanden in Windows of Mac OS, e-mailberichten in Outlook, Office-documenten op een iOS-of Android-apparaat, Visio 2016-bestanden in Windows en bestanden die zijn geopend in de webversie van Office-apps (Word, PowerPoint, Excel, Outlook en OneNote), mits de 365|
|**Niet bijhouden wanneer gebruikers klikken op veilige koppelingen voor ATP**|Wanneer deze optie is geselecteerd, klikt u op gegevens voor Url's in Word, Excel, PowerPoint, Visio-documenten en e-mailberichten in Outlook worden niet opgeslagen.|
|**Gebruikers niet laten klikken via ATP veilige koppelingen naar de oorspronkelijke URL**|Wanneer deze optie is geselecteerd, kunnen gebruikers niet verdergaan met een [waarschuwingspagina](atp-safe-links-warning-pages.md) op een URL die is ingesteld als schadelijk.|
|

### <a name="policies-that-apply-to-specific-email-recipients"></a>Beleidsregels die gelden voor bepaalde geadresseerden voor e-mail

****

|Optie|Doet dit|
|---|---|
|**Uit**|Scant geen Url's in e-mailberichten.  <br/> Hiermee kunt u een uitzonderingsregel definiëren, zoals een regel die Url's in e-mailberichten voor een bepaalde groep geadresseerden niet scant.|
|**Aan**|Url's opnieuw schrijven voor het doorsturen van gebruikers via een veilige beveiliging van de gebruikerslijst als de gebruikers op Url's in e-mailberichten klikken en veilige verbindingen van ATP in Outlook (C2R) inschakelen.  <br/> Controleert een URL wanneer erop wordt geklikt in een lijst met geblokkeerde of schadelijke Url's en Hiermee wordt de detonatie van de URL op de achtergrond asynchroon geactiveerd als de URL geen geldige reputatie heeft.|
|**Het scannen van realtime-URL'S toepassen op verdachte koppelingen en koppelingen die verwijzen naar bestanden**|Wanneer deze optie is geselecteerd, worden verdachte Url's en koppelingen die verwijzen naar downloadbare inhoud gescand.|
|**Wachten tot URL-Scan is voltooid voordat het bericht wordt bezorgd**|Wanneer deze optie is geselecteerd, worden berichten met Url's die moeten worden gescand bewaard totdat de Url's zijn gecontroleerd en bevestigd zijn dat u veilig bent voordat u berichten ontvangt.|
|**Veilige koppelingen toepassen op berichten die binnen de organisatie zijn verzonden** <br/> | Wanneer u deze optie inschakelt en selecteert, wordt de bescherming van beschikbare verbindingen van ATP toegepast op e-mailberichten die worden verzonden tussen de personen in uw organisatie, mits de e-mailaccounts worden gehost in Office 365.|
|**Geclickte gebruikers niet bijhouden**|Wanneer deze optie is geselecteerd, klikt u op gegevens voor Url's in e-mail van externe afzenders worden niet opgeslagen. URL klik op controleren voor koppelingen in e-mailberichten die binnen de organisatie worden verstuurd, worden momenteel niet ondersteund.|
|**Gebruikers kunnen niet naar de oorspronkelijke URL klikken**|Wanneer deze optie is geselecteerd, kunnen gebruikers niet verdergaan met een [waarschuwingspagina](atp-safe-links-warning-pages.md) op een URL die is ingesteld als schadelijk.|
|**De volgende Url's niet opnieuw schrijven**|Laat Url's doorlopen. Hiermee wordt een aangepaste lijst bijgehouden met veilige Url's die u niet nodig hebt om een specifieke groep e-mail geadresseerden in uw organisatie te doorzoeken. Zie [een aangepaste lijst voor het toevoegen van url's met behulp van ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) voor meer informatie, waaronder recente wijzigingen in de ondersteuning voor jokertekens ( \* ).|
|

## <a name="next-steps"></a>Volgende stappen

Wanneer u het beleid voor veilige koppelingen voor de vrije ruimte gebruikt, kunt u zien hoe de ATP voor uw organisatie werkt door rapporten te bekijken. Raadpleeg de volgende bronnen voor meer informatie:

- [Rapporten weergeven voor Office 365 Advanced Threat Protection](view-reports-for-atp.md)

- [Verkenner gebruiken in de beveiligings & compliance Center](threat-explorer.md)

Blijf op de hoogte van nieuwe functies die beschikbaar zijn in ATP. Ga naar het [Microsoft 365-wegwijzer](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).
