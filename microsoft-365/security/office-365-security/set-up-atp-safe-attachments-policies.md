---
title: Beleid voor veilige bijlagen van Office 365 instellen
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
description: Meer informatie over het definiëren van beleid voor veilige bijlagen om uw organisatie te beschermen tegen schadelijke bestanden in e-mail.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab67b66b8773f45e819abef34e1d77ce5de4cc62
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035318"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Beleid voor veilige bijlagen van Office 365 instellen

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Zie [Geavanceerde Outlook.com beveiliging](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)als u een thuisgebruiker bent die op zoek is naar informatie over veilige bijlagen in Outlook.

Mensen verzenden, ontvangen en delen regelmatig bijlagen, zoals documenten, presentaties, spreadsheets en meer. Het is niet altijd gemakkelijk om te vertellen of een bijlage veilig of kwaadaardig is door alleen maar naar een e-mailbericht te kijken. En het laatste wat je wilt is een kwaadaardige gehechtheid te krijgen door middel van, ravage aanrichten voor uw organisatie. Gelukkig kan [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) helpen. U [beleid](atp-safe-attachments.md) voor veilige bijlagen ATP instellen om ervoor te zorgen dat uw organisatie wordt beschermd tegen aanvallen door onveilige e-mailbijlagen.

## <a name="what-to-do"></a>Wat te doen

1. Bekijk de voorwaarden

2. Een beleid voor veilige bijlagen voor ATP instellen

3. Meer informatie over beleidsopties voor veilige bijlagen voor ATP

## <a name="step-1-review-the-prerequisites"></a>Stap 1: Bekijk de vereisten

- Controleer of uw organisatie [office 365 Advanced Threat Protection](office-365-atp.md)heeft.

- Zorg ervoor dat u over de benodigde machtigingen beschikt. Als u ATP-beleid wilt definiëren (of bewerken) moet u een Exchange Online Organization Management-rol (globale beheerder is standaard toegewezen aan deze rol) of beide rollen exchange online hygiënebeheer en beveiligingsbeheerder toegewezen. Zie de volgende tabel voor meer informatie:

  |Rol|Waar/hoe toegewezen|
  |---------|---------|
  |globale beheerder |De persoon die zich aanmeldt om Microsoft 365 te kopen is standaard een globale beheerder. (Zie [Over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.)|
  |Beveiligingsbeheerder |Azure Active Directory-beheercentrum ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
  |Exchange Online Organization Management, Exchange Online Hygiene Management |Exchange-beheercentrum[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)( ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell)](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
  |

  Zie [Machtigingen in het Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.

- [Meer informatie over beleidsopties voor veilige bijlagen atp](#step-3-learn-about-atp-safe-attachments-policy-options) (in dit artikel). Sommige opties, zoals de opties Monitor of Vervangen, kunnen leiden tot een kleine vertraging van e-mail terwijl bijlagen worden gescand. Als u berichtvertragingen wilt voorkomen, u overwegen dynamische bezorging te gebruiken [en een voorbeeld te bekijken.](dynamic-delivery-and-previewing.md)

- Geef u tot 30 minuten de tijd om uw nieuwe of bijgewerkte beleid te verspreiden naar alle Microsoft 365-datacenters.

## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Stap 2: Een beleid voor veilige bijlagen voor ATP instellen (of bewerken)

1. Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan met je werk- of schoolaccount.

2. Kies in &amp; het Beveiligingscompliancecentrum in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**de optie **Veilige bijlagen** **beleid** \> .

3. Als u **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams**ziet, raden we u aan deze optie te selecteren. Hiermee [u geavanceerde bedreigingsbeveiliging van Office 365 inschakelen voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md) voor uw Microsoft 365-omgeving.

4. Kies **Nieuw** (de knop Nieuw lijkt **+** op een plusteken ( )) om te beginnen met het maken van uw beleid.

5. Geef de naam, beschrijving en instellingen voor het beleid op.<br/><br/>**Voorbeeld:** Als u een beleid wilt instellen dat 'geen vertragingen' wordt genoemd en dat de berichten van iedereen onmiddellijk wordt bezorgd en bijlagen opnieuw wilt worden hecht nadat ze zijn gescand, u de volgende instellingen opgeven:

   - Typ geen vertragingen in het vak **Naam.**

   - Typ **in het** vak Beschrijving een beschrijving zoals, Levert berichten onmiddellijk af en koppelt bijlagen na het scannen opnieuw.

   - Kies in de sectie respons de optie **Dynamische bezorging.** ([Meer informatie over dynamische weergave en previewing met ATP Safe Attachments](dynamic-delivery-and-previewing.md).)

   - Selecteer in de sectie **Bijlage omleiden** de optie om het e-mailadres van uw globale beheerder, beveiligingsbeheerder of beveiligingsanalist in te schakelen en te typen die kwaadaardige bijlagen zal onderzoeken.

   - Kies **In** de sectie Toegepast op de optie **Het geadresseerde domein is**en selecteer vervolgens het domein. Kies **Toevoegen**en kies **OK**.

6. Selecteer **Save**.

U overwegen meerdere ATP-beleid voor veilige bijlagen in te stellen voor uw organisatie. Dit beleid wordt toegepast in de volgorde waarin ze worden weergegeven op de pagina **Veilige bijlagen atp.** Nadat een beleid is gedefinieerd of bewerkt, u ten minste 30 minuten toestaan dat de politie in alle Microsoft-datacenters van kracht wordt.

## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Stap 3: Meer informatie over beleidsopties voor veilige bijlagen atp

Terwijl u uw ATP-beleid voor veilige bijlagen instelt, u kiezen uit verschillende opties, waaronder Monitor, Blokkeren, Vervangen, Dynamische levering, enzovoort. In het geval u zich afvraagt wat deze opties doen, vat de volgende tabel elk effect samen.

||||
|---|---|---|
|**Optie**|**Effect**|**Gebruik wanneer u dat wilt:**|
|**Uit**|Scant geen bijlagen op malware  <br/> Vertraagt de bezorging van berichten niet|Scannen uitschakelen voor scanners, faxen of slimme hosts die alleen bekende, goede bijlagen verzenden  <br/> Voorkom onnodige vertragingen bij het routeren van interne e-mail.  <br/> **We raden deze optie voor de meeste gebruikers niet aan. U mag deze optie alleen gebruiken om het scannen van ATP-veilige bijlagen voor een kleine groep vertrouwde afzenders uit te schakelen.**|
|**Monitor**|Levert berichten met bijlagen en houdt vervolgens bij wat er gebeurt met gedetecteerde malware|Bekijk waar gedetecteerde malware naartoe gaat in uw organisatie|
|**Blok**|Hiermee voorkomt u dat berichten met gedetecteerde malwarebijlagen worden voortgezet  <br/> Hiermee verzendt u berichten met gedetecteerde malware naar [quarantaine in Office 365,](manage-quarantined-messages-and-files.md) waar een beveiligingsbeheerder of analist deze berichten kan controleren en vrijgeven (of verwijderen)  <br/> Blokkeert automatisch toekomstige berichten en bijlagen|Bescherm uw organisatie tegen herhaalde aanvallen met dezelfde malwarebijlagen|
|**Vervangen**|Verwijdert gedetecteerde malwarebijlagen  <br/> Ontvangers op de hoogte stelt dat bijlagen zijn verwijderd  <br/> Hiermee verzendt u berichten met gedetecteerde malware naar [quarantaine in Office 365,](manage-quarantined-messages-and-files.md) waar een beveiligingsbeheerder of analist deze berichten kan controleren en vrijgeven (of verwijderen)|Zichtbaarheid verhogen bij ontvangers dat bijlagen zijn verwijderd vanwege gedetecteerde malware|
|**Dynamische levering**|Levert onmiddellijk berichten  <br/> Vervangt bijlagen door een tijdelijke aanduidingsbestand totdat het scannen is voltooid en koppelt de bijlagen opnieuw als er geen malware wordt gedetecteerd  <br/> Inclusief mogelijkheden voor het bekijken van bijlagen voor de meeste PDF's en Office-bestanden tijdens het scannen  <br/> Hiermee verzendt u berichten met gedetecteerde malware naar quarantaine waar een beveiligingsbeheerder of analist deze berichten kan controleren en vrijgeven (of verwijderen)  <br/> [Meer informatie over dynamische weergave en previewing met veilige ATP-bijlagen](dynamic-delivery-and-previewing.md) <br/> |Voorkom vertragingen in berichten en bescherm ontvangers van schadelijke bestanden  <br/> Ontvangers inschakelen om bijlagen in veilige modus te bekijken terwijl het scannen plaatsvindt|
|**Omleiding inschakelen**|Van toepassing wanneer de optie Monitor, Blok of Vervangen wordt gekozen  <br/> Hiermee verzendt u bijlagen naar een opgegeven e-mailadres waar beveiligingsbeheerders of analisten onderzoek kunnen doen|Beveiligingsbeheerders en analisten in staat stellen verdachte bijlagen te onderzoeken|
|**De bovenstaande selectie toepassen als malware scannen op bijlagen een tijd uit of fout optreedt**|Past de actie toe die is geconfigureerd voor onveilige bijlagen op de bijlagen die niet kunnen worden gescand (vanwege een time-out of fout)|
|

## <a name="next-steps"></a>Volgende stappen

Zodra uw beleid voor veilige bijlagen voor ATP is ingevoerd, u zien hoe ATP voor uw organisatie werkt door rapporten te bekijken. Zie de volgende bronnen voor meer informatie:

- [Rapporten weergeven voor geavanceerde bedreigingsbeveiliging van Office 365](view-reports-for-atp.md)

- [Explorer gebruiken in het Beveiligings- & Compliance Center](threat-explorer.md)

Blijf op de hoogte van nieuwe functies die naar ATP komen. bezoek de [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) en leer meer over [nieuwe functies die worden toegevoegd aan ATP.](office-365-atp.md#new-features-in-office-365-atp)
