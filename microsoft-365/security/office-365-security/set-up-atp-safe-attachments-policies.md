---
title: Beleidsregels voor veilige bijlagen van Office 365 instellen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Meer informatie over het definiëren van beleidsregels voor veilige bijlagen om uw organisatie tegen kwaadwillende bestanden in een e-mail te beschermen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5f9f1a6cc250fdd336e48c19c6cb5d73e9a05800
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197221"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Beleidsregels voor veilige bijlagen van Office 365 instellen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Als u een thuisgebruiker bent die op zoek bent naar informatie over veilige bijlagen in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Mensen verzenden, ontvangen en delen van bijlagen, zoals documenten, presentaties, spreadsheets en meer. Het is niet altijd eenvoudig om te zien of een bijlage veilig of schadelijk is, net zoals u een e-mailbericht bekijkt. En het laatste wat u wilt, is een kwaadaardige bijlage, wreaking Havoc voor uw organisatie. Gelukkig kunt u met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) helpen. U kunt beleidsregels voor een veilige beveiliging van de [bijlage](atp-safe-attachments.md) instellen om ervoor te zorgen dat uw organisatie is beveiligd tegen aanvallen via onveilige e-mailbijlagen.

## <a name="what-to-do"></a>Wat moet u doen?

1. De vereisten controleren

2. Een beleid instellen voor veilige bijlagen

3. Meer informatie over de beleidsopties voor het beveiligen van ATP

## <a name="step-1-review-the-prerequisites"></a>Stap 1: de vereisten controleren

- Zorg ervoor dat uw organisatie [Office 365 Advanced Threat Protection](office-365-atp.md)heeft.

- Zorg ervoor dat u de benodigde machtigingen hebt. Als u ATP-beleidsregels wilt definiëren (of bewerken), moet u beschikken over de rol van Organisatiebeheer van Exchange Online (de globale beheerder wordt standaard toegewezen aan deze rol) of beide Exchange Online-hygiëne beheer en beveiligingsbeheerders rollen. Zie de volgende tabel voor meer informatie:

  ****

  |Rol|Where/hoe toegewezen|
  |---|---|
  |globale beheerder |De persoon die zich registreert voor het kopen van Microsoft 365 is standaard een globale beheerder. (Zie [informatie over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)|
  |Beveiligingsbeheerder |Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
  |Exchange Online Organisatiebeheer, Exchange Online-hygiëne beheer |Exchange-Beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
  |

  Zie [machtigingen in het beveiligings &amp; centrum](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.

- [Meer informatie over ATP-beleidsopties voor het beveiligen van bijlagen](#step-3-learn-about-atp-safe-attachments-policy-options) (in dit artikel). Sommige opties, zoals de opties monitor of vervangen, kunnen een kleine vertraging van de e-mail veroorzaken wanneer bijlagen worden gescand. U kunt de vertragingen van berichten voorkomen door [dynamische levering te gebruiken en een voorbeeld te bekijken](dynamic-delivery-and-previewing.md).

- Maximaal 30 minuten toegestaan voor uw nieuwe of bijgewerkte beleid voor alle Microsoft 365-datacenters.

## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Stap 2: een in-en uitzoomen op een beleid voor veilige bijlagen instellen (of bewerken)

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw werk-of schoolaccount.

2. Kies in het &amp; gedeelte beveiligings compliance in het linker navigatiedeelvenster onder **Threat Management**de optie **beleids** \> **veilige bijlagen**.

3. Als u **ATP voor SharePoint, OneDrive en Microsoft teams**ziet staan, is het raadzaam deze optie te selecteren. Hiermee wordt [Office 365 Advanced Threat Protection voor SharePoint, OneDrive en Microsoft teams](atp-for-spo-odb-and-teams.md) voor uw microsoft 365-omgeving ingeschakeld.

4. Kies **Nieuw** (de knop Nieuw lijkt op een plusteken ( **+** )) om uw beleid te gaan maken.

5. De naam, de beschrijving en de instellingen voor het beleid opgeven.<br/><br/>**Voorbeeld:** Voor het instellen van een beleid met de naam ' geen vertragingen ' waarmee iedereen berichten direct wordt bezorgd en vervolgens bijlagen opnieuw bijgevoegd na de scan, kunt u de volgende instellingen opgeven:

   - Typ in het vak **naam** geen vertragingen.

   - Typ in het vak **Beschrijving** een beschrijving als een beschrijving, zodat de bijlagen direct na het scannen worden gevoegd.

   - Kies in de sectie antwoord de optie **dynamische bezorgings** optie. ([Zie voor meer informatie over dynamische bezorging en voorbeelden met veilige bijlagen met ATP](dynamic-delivery-and-previewing.md).)

   - Selecteer in de sectie **bijlage omleiden** de optie om omleiding in te schakelen en typ het e-mailadres van uw globale beheerder, beveiligingsbeheerder of beveiligings analist die schadelijke bijlagen gaat onderzoeken.

   - Kies in de sectie **toegepast op** **het domein van de ontvanger**en selecteer uw domein. Kies **toevoegen**en kies vervolgens **OK**.

6. Selecteer **Save**.

Overweeg om meerdere ATP-beleidsregels voor veilige bijlagen in te stellen voor uw organisatie. Deze beleidsregels worden toegepast op de volgorde waarin ze worden weergegeven op de pagina met **veilige vrije** vormen. Nadat een beleid is gedefinieerd of bewerkt, mag de politie gedurende minimaal 30 minuten duren voordat de policies in Microsoft-datacenters worden doorgevoerd.

## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Stap 3: meer informatie over de beleidsopties voor het instellen van ATP voor veilige bijlagen

Wanneer u uw beleid voor veilige bijlagen voor ATP instelt, kiest u een van de vele opties, waaronder monitor, blok, vervangen, dynamische bezorging, enzovoort. Als u zich afvraagt wat deze opties zijn, kunt u in de onderstaande tabel een overzicht maken van de verschillende en bijbehorende gevolgen.

****

|Optie|Actief|Gebruik dit wanneer u het volgende wilt doen:|
|---|---|---|
|**Uit**|De bijlagen voor malware worden niet gescand  <br/> De bezorging van berichten wordt niet vertraagd|Scan uitschakelen voor geselecteerde geadresseerden.  <br/> Onnodige vertragingen voor het routeren van interne e-mail voorkomen.  <br/> **Deze optie wordt niet aanbevolen voor de meeste gebruikers. U dient deze optie alleen te gebruiken om te controleren of de lijst met geblokkeerde gebruikersnamen automatisch e-mailberichten van vertrouwde afzenders ontvangt.**|
|**Monitor**|Levert berichten met bijlagen en spoort wat er gebeurt met ontdekte malware|Zien waar de gedetecteerde malware in uw organisatie terechtkomt|
|**Blokkeren**|Voorkomt dat berichten met schadelijke bijlagen voor schadelijke software worden voortgezet  <br/> Verzendt berichten met gedetecteerde malware [in Office 365](manage-quarantined-messages-and-files.md) , waarbij een beveiligingsbeheerder of een analist die berichten kan controleren en vrijgeven (of verwijderen)  <br/> Toekomstige berichten en bijlagen automatisch blokkeren|Uw organisatie beschermen tegen herhaalde aanvallen met dezelfde schadelijke bijlagen|
|**Vervangen**|Verwijdert gedetecteerde schadelijke bijlagen  <br/> Laat geadresseerden u op de hoogte van de bijlagen verwijderen  <br/> Verzendt berichten met gedetecteerde malware [in Office 365](manage-quarantined-messages-and-files.md) , waarbij een beveiligingsbeheerder of een analist die berichten kan controleren en vrijgeven (of verwijderen)|De zichtbaarheid voor geadresseerden verhogen die bijlagen hebben verwijderd vanwege malware die zijn gedetecteerd|
|**Dynamische bezorging**|Levert direct berichten  <br/> Hiermee worden bijlagen met een tijdelijke aanduiding voor bestanden vervangen totdat de scan is voltooid en de bijlagen opnieuw worden bijgevoegd als er geen malware is gedetecteerd  <br/> Inclusief bijlage Voorbeeldfuncties voor de meeste PDF-bestanden en Office-bestanden tijdens het scannen  <br/> Verzendt berichten met gedetecteerde malware in quarantaine, waar een beveiligingsbeheerder of analist de berichten kan controleren en vrijgeven (of verwijderen)  <br/> [Meer informatie over dynamische bezorgings berichten en voorbeelden van veilige bijlagen met ATP](dynamic-delivery-and-previewing.md) <br/> |Voorkom dat berichten worden vertraagd wanneer u geadresseerden tegen kwaadwillende bestanden beschermt  <br/> Voorbeelden van bijlagen weergeven in de veilige modus terwijl de scanfunctie plaatsvindt|
|**Omleiden inschakelen**|Toepassen wanneer de optie monitor, blok of vervangen is geselecteerd  <br/> Hiermee worden bijlagen verzonden naar een opgegeven e-mailadres waar beveiligingsbeheerders of analisten kunnen onderzoeken|Beveiligingsbeheerders en analisten inschakelen voor onderzoek naar verdachte bijlagen|
|**De bovenstaande selectie toepassen als malware wordt gescand op bijlagen wanneer de fout optreedt**|Hiermee past u de actie die is geconfigureerd voor onveilige bijlagen toe op de bijlagen die niet kunnen worden gescand (vanwege een time-out of fout)|
|

## <a name="next-steps"></a>Volgende stappen

Wanneer u de beleidsregels voor veilige beveiliging van de ATP-beleidsregels hebt ingesteld, kunt u de weergave van de werkruimte voor uw organisatie bekijken door rapporten te bekijken. Raadpleeg de volgende bronnen voor meer informatie:

- [Rapporten weergeven voor Office 365 Advanced Threat Protection](view-reports-for-atp.md)

- [Verkenner gebruiken in de beveiligings & compliance Center](threat-explorer.md)

Blijf op de hoogte van nieuwe functies die beschikbaar zijn in ATP. Ga naar het [Microsoft 365-wegwijzer](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) en leer meer over de [nieuwe functies die worden toegevoegd aan ATP](office-365-atp.md#new-features-in-office-365-atp).
