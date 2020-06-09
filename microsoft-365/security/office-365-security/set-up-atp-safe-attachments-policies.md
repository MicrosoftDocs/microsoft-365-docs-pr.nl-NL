---
title: Office 365 ATP-beleid voor veilige bijlagen instellen
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
ms.openlocfilehash: 581c45c9c5b606b3b4b0ba91bd96740bc838629d
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617228"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Office 365 ATP-beleid voor veilige bijlagen instellen

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Zie [Geavanceerde Outlook.com beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)als u een thuisgebruiker bent die op zoek is naar informatie over veilige bijlagen.

Mensen verzenden, ontvangen en delen regelmatig bijlagen, zoals documenten, presentaties, spreadsheets en meer. Het is niet altijd gemakkelijk om te zien of een bijlage veilig of kwaadaardig is door alleen maar naar een e-mailbericht te kijken. En het laatste wat je wilt is een kwaadaardige gehechtheid te krijgen door, ravage aanrichten voor uw organisatie. Gelukkig kan [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) helpen. U [atp-beleid](atp-safe-attachments.md) voor veilige bijlagen instellen om ervoor te zorgen dat uw organisatie wordt beschermd tegen aanvallen door onveilige e-mailbijlagen.

## <a name="what-to-do"></a>Wat te doen

1. De vereisten bekijken

2. Een ATP-beleid voor veilige bijlagen instellen

3. Meer informatie over beleidsopties voor ATP-veilige bijlagen

## <a name="step-1-review-the-prerequisites"></a>Stap 1: Bekijk de vereisten

- Zorg ervoor dat uw organisatie [geavanceerde bedreigingsbeveiliging van Office 365](office-365-atp.md)heeft.

- Zorg ervoor dat u over de benodigde machtigingen beschikt. Als u ATP-beleid wilt definiëren (of bewerken), moet u een Exchange Online Organization Management-rol toegewezen krijgen (globale beheerder is standaard aan deze rol toegewezen) of aan zowel exchange online hygiënebeheer- als beveiligingsbeheerdersrollen. Zie de volgende tabel voor meer informatie:

  |Rol|Waar/hoe toegewezen|
  |---------|---------|
  |globale beheerder |De persoon die zich aanmeldt om Microsoft 365 te kopen, is standaard een globale beheerder. (Zie [Over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)|
  |Beveiligingsbeheerder |Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
  |Exchange Online Organization Management, Exchange Online Hygiene Management |Exchange-beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
  |

  Zie [Machtigingen in het Security &amp; Compliance Center voor](permissions-in-the-security-and-compliance-center.md)meer informatie over rollen en machtigingen.

- [Meer informatie over beleidsopties voor ATP Safe Attachments](#step-3-learn-about-atp-safe-attachments-policy-options) (in dit artikel). Sommige opties, zoals de opties Controleren of Vervangen, kunnen leiden tot een kleine vertraging van e-mail terwijl bijlagen worden gescand. Als u berichtvertragingen wilt voorkomen, u [overwegen Dynamische levering en voorbeelden te](dynamic-delivery-and-previewing.md)gebruiken.

- Sta maximaal 30 minuten toe voor uw nieuwe of bijgewerkte beleid om zich te verspreiden naar alle Microsoft 365-datacenters.

## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Stap 2: Een ATP-beleid voor veilige bijlagen instellen (of bewerken)

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan met je werk- of schoolaccount.

2. Kies in het Security &amp; Compliance Center in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**de optie Veilige bijlagen **voor beleid** \> **Safe Attachments**.

3. Als u **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams**ziet, raden we u aan deze optie te selecteren. Hiermee [u Office 365 Advanced Threat Protection voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md) inschakelen voor uw Microsoft 365-omgeving.

4. Kies **Nieuw** (de knop Nieuw lijkt op een plusteken ( **+** )) om te beginnen met het maken van uw beleid.

5. Geef de naam, beschrijving en instellingen voor het beleid op.<br/><br/>**Voorbeeld:** Als u een beleid wilt instellen dat 'geen vertragingen' wordt genoemd en dat de berichten van iedereen onmiddellijk verzendt en vervolgens bijlagen opnieuw wordt bevestigd nadat deze zijn gescand, u de volgende instellingen opgeven:

   - Typ in het vak **Naam** geen vertragingen.

   - Typ in het vak **Beschrijving** een beschrijving zoals: Berichten wordt onmiddellijk verzonden en bijlagen na het scannen opnieuw bevestigen.

   - Kies in de sectie Antwoord de optie **Dynamische levering.** (Meer[informatie over dynamische levering en voorvertoning met ATP Safe Attachments](dynamic-delivery-and-previewing.md).)

   - Selecteer in de sectie **Bijlage omleiden** de optie om omleiding in te schakelen en typ het e-mailadres van uw globale beheerder, beveiligingsbeheerder of beveiligingsanalist die schadelijke bijlagen zal onderzoeken.

   - Kies **in** de sectie Toegepast op **de optie Het domein van de ontvanger is**en selecteer vervolgens uw domein. Kies **Toevoegen**en kies **vervolgens OK**.

6. Selecteer **Save**.

Overweeg het instellen van meerdere ATP Safe Attachments-beleid voor uw organisatie. Dit beleid wordt toegepast in de volgorde waarin ze worden weergegeven op de pagina **Veilige bijlagen bij de ATP.** Nadat een beleid is gedefinieerd of bewerkt, moet u de politie ten minste 30 minuten toestaan om in alle Microsoft-datacenters van kracht te worden.

## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Stap 3: Meer informatie over beleidsopties voor ATP-veilige bijlagen

Terwijl u uw ATP-beleid voor veilige bijlagen instelt, kiest u uit vele opties, waaronder Monitor, Blok, Vervangen, Dynamische levering, enzovoort. Als u zich afvraagt wat deze opties doen, wordt in de volgende tabel elk en het effect ervan samengevat.

||||
|---|---|---|
|**Optie**|**Effect**|**Gebruik wanneer u het:**|
|**Uit**|Scant geen bijlagen op malware  <br/> Vertraagt de bezorging van berichten niet|Scannen uitschakelen voor scanners, faxen of slimme hosts die alleen bekende, goede bijlagen verzenden  <br/> Voorkom onnodige vertragingen bij het routeren van interne e-mail.  <br/> **We raden deze optie niet aan voor de meeste gebruikers. U mag deze optie alleen gebruiken om het scannen van ATP Safe Attachments uit te schakelen voor een kleine groep vertrouwde afzenders.**|
|**Monitor**|Levert berichten met bijlagen en houdt vervolgens bij wat er gebeurt met gedetecteerde malware|Bekijk waar gedetecteerde malware naartoe gaat in uw organisatie|
|**Blok**|Voorkomt dat berichten met gedetecteerde malware-bijlagen worden voortgezet  <br/> Stuurt berichten met gedetecteerde malware naar [quarantaine in Office 365](manage-quarantined-messages-and-files.md) waar een beveiligingsbeheerder of -analist deze berichten kan controleren en vrijgeven (of verwijderen)  <br/> Blokkeert toekomstige berichten en bijlagen automatisch|Bescherm uw organisatie tegen herhaalde aanvallen met dezelfde malware-bijlagen|
|**Vervangen**|Verwijdert gedetecteerde malware-bijlagen  <br/> Ontvangers op de hoogte brengen dat bijlagen zijn verwijderd  <br/> Stuurt berichten met gedetecteerde malware naar [quarantaine in Office 365](manage-quarantined-messages-and-files.md) waar een beveiligingsbeheerder of -analist deze berichten kan controleren en vrijgeven (of verwijderen)|De zichtbaarheid van ontvangers vergroten dat bijlagen zijn verwijderd vanwege gedetecteerde malware|
|**Dynamische levering**|Levert berichten onmiddellijk  <br/> Vervangt bijlagen door een tijdelijke aanduidingsbestand totdat het scannen is voltooid en plaatst de bijlagen opnieuw als er geen malware wordt gedetecteerd  <br/> Bevat mogelijkheden voor het bekijken van bijlagen voor de meeste PDF's en Office-bestanden tijdens het scannen  <br/> Stuurt berichten met gedetecteerde malware naar Quarantaine waar een beveiligingsbeheerder of -analist die berichten kan controleren en vrijgeven (of verwijderen)  <br/> [Meer informatie over dynamische levering en voorvertoning met ATP Safe-bijlagen](dynamic-delivery-and-previewing.md) <br/> |Voorkom berichtvertragingen terwijl ontvangers worden beschermd tegen schadelijke bestanden  <br/> Ontvangers in staat stellen bijlagen in de veilige modus te bekijken terwijl het scannen plaatsvindt|
|**Omleiding inschakelen**|Van toepassing wanneer de optie Monitor, Blokkeren of Vervangen is gekozen  <br/> Hiermee stuurt u bijlagen naar een opgegeven e-mailadres waar beveiligingsbeheerders of -analisten|Beveiligingsbeheerders en analisten in staat stellen verdachte bijlagen te onderzoeken|
|**De bovenstaande selectie toepassen als er een keer een storing optreedt bij het scannen van malware voor bijlagen**|Hiermee past u de actie toe die is geconfigureerd voor onveilige bijlagen op de bijlagen die niet kunnen worden gescand (vanwege een time-out of fout)|
|

## <a name="next-steps"></a>Volgende stappen

Zodra uw ATP Safe Attachments-beleid is ingevoerd, u zien hoe ATP voor uw organisatie werkt door rapporten te bekijken. Zie de volgende bronnen voor meer informatie:

- [Rapporten voor geavanceerde bedreigingsbeveiliging van Office 365 weergeven](view-reports-for-atp.md)

- [Explorer gebruiken in het Security & Compliance Center](threat-explorer.md)

Blijf op de hoogte van nieuwe functies die naar ATP komen. bezoek de [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) en leer meer over [nieuwe functies die worden toegevoegd aan ATP](office-365-atp.md#new-features-in-office-365-atp).
