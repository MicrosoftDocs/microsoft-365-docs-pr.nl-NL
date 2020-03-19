---
title: Office 365 ATP-antiphishingbeleid instellen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 08/29/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
description: Bescherming tegen phishing, met uitgebreide bescherming als onderdeel van Office 365 Advanced Threat Protection en basisbescherming in Office 365 Exchange Online Protection, kan uw organisatie beschermen tegen phishingaanvallen op basis van schadelijke imitaties en andere phishing-aanvallen.
ms.openlocfilehash: cc9c8ec0aa819696f3c53cff690be40ae82009fb
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2020
ms.locfileid: "42809856"
---
# <a name="set-up-office-365-atp-anti-phishing-and-anti-phishing-policies"></a>Office 365 ATP antiphishing- en antiphishingbeleid instellen

[ATP-bescherming tegen phishing](atp-anti-phishing.md), onderdeel van [Office 365 Advanced Threat Protection](office-365-atp.md), kan uw organisatie beschermen tegen schadelijke phishing-aanvallen en andere phishing-aanvallen. Als u een globale office 365 Enterprise- of beveiligingsbeheerder bent, u ATP-beleid voor antiphishing instellen.

Phishing-aanvallen komen in een verscheidenheid van vormen van commodity-gebaseerde aanvallen om gerichte spear phishing of walvisvangst. Met de groeiende complexiteit, is het moeilijk voor zelfs een getraind oog om een aantal van deze geavanceerde aanvallen te identificeren. Gelukkig kan Office 365 Advanced Threat Protection helpen. U een ATP-antiphishingbeleid instellen om ervoor te zorgen dat uw organisatie tegen dergelijke aanvallen wordt beschermd.

> [!NOTE]
> ATP anti-phishing is alleen beschikbaar in Advanced Threat Protection (ATP). ATP is opgenomen in abonnementen, zoals [Microsoft 365 Enterprise,](https://www.microsoft.com/microsoft-365/enterprise/home) [Microsoft 365 Business,](https://www.microsoft.com/microsoft-365/business)Office 365 Enterprise E5, Office 365 Education A5, enz. Als uw organisatie een Office 365-abonnement heeft dat geen Office 365 ATP bevat, u mogelijk ATP als invoegtoepassing aanschaffen. Zie [office 365 Advanced Threat Protection-abonnementen en -prijzen en](https://products.office.com/exchange/advance-threat-protection) de [office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)voor meer informatie. Zorg ervoor dat uw organisatie de nieuwste versie van Office 365 ProPlus op Windows gebruikt om optimaal te profiteren van de bescherming tegen phishing van ATP.

Een anti-phishingbeleid is ook beschikbaar voor Office 365 Exchange Online Protection, met een beperkte set anti-spoofing bescherming die bedoeld is om te beschermen tegen op verificatie gebaseerde en op misleiding gebaseerde aanvallen.

Wat te doen:

1. Bekijk de voorwaarden.

2. Meer informatie over uw anti-phishing- en ATP-beleid tegen phishing.Learn about your anti-phishing and ATP anti-phishing policy options.

3. Stel een antiphishingbeleid of een ATP-antiphishingbeleid in.

> [!IMPORTANT]
> Zie [Welk beleid van toepassing is op meerdere beveiligingsmethoden en detectiescans op uw e-mail](how-policies-and-protections-are-combined.md)voor meer technologieën.

## <a name="review-the-prerequisites"></a>Bekijk de voorwaarden

- Als u ATP-beleid wilt definiëren (of bewerken), moet u een geschikte rol toegewezen krijgen. Enkele voorbeelden worden beschreven in de volgende tabel:

  |Rol|Waar/hoe toegewezen|
  |---------|---------|
  |Globale beheerder van Office 365|De persoon die zich aanmeldt om Office 365 te kopen, is standaard een globale beheerder. (Zie [Over Office 365-beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.)|
  |Beveiligingsbeheerder|Azure Active Directory-beheercentrum ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
  |Exchange Online Organisatiebeheer|Exchange-beheercentrum[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)( ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell)](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|

  Zie Machtigingen in het Office [365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.

- U zult waarschijnlijk meerdere anti-phishingbeleidsregels instellen voor uw organisatie. Office 365 handhaaft dit beleid in de volgorde waarin ze worden vermeld op de **antiphishingpagina's** en **ATP-antiphishingpagina's** in het Security &amp; Compliance Center. Zodra u uw [beleidsopties](#learn-about-atp-anti-phishing-policy-options)hebt beoordeeld, neemt u enige tijd om te bepalen hoeveel beleidsregels u nodig hebt en de prioriteit voor elk beleid.

- Plan om ongeveer 5-15 minuten door te brengen om uw eerste anti-phishingbeleid in te stellen.

- Geef u tot 30 minuten de tijd om uw nieuwe of bijgewerkte beleid te verspreiden naar alle Office 365-datacenters.

## <a name="set-up-an-anti-phishing-or-atp-anti-phishing-policy"></a>Een anti-phishing- of ATP-antiphishingbeleid instellen

Elke organisatie in Office 365 heeft een standaard antiphishingbeleid dat van toepassing is op alle gebruikers. U meerdere aangepaste antiphishingbeleidsregels maken die u aanpassen aan specifieke gebruikers, groepen of domeinen binnen uw organisatie. Het aangepaste beleid dat u maakt, heeft voorrang op het standaardbeleid. U voegt antiphishingbeleid toe, bewerkt en verwijdert deze &amp; in het Office 365 Security Compliance Center.

1. Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan met je werk- of schoolaccount.

2. Kies In het Office &amp; 365 Security Compliance Center, in het linkernavigatiedeelvenster, onder **Bedreigingsbeheer**, **Beleid**.

3. Kies **op** de pagina Beleid de optie **Anti-phishing** of **ATP anti-phishing.**

4. Ga op de **antiphishing-** of **ATP-antiphishingpagina** een van de volgende handelingen uit:

   - Als u een nieuw beleid wilt toevoegen, selecteert **u + Maken**.

   - Als u een bestaand beleid wilt bewerken, selecteert u de beleidsnaam in de lijst die wordt weergegeven op de **pagina Anti-phishing.** (U of kiest afwisselend **standaardbeleid** boven de lijst.) Kies op de pagina die wordt weergegeven het **beleid bewerken**.

5. Geef de naam, beschrijving en instellingen voor uw beleid op. Zie [Meer informatie over de beleidsopties voor antiphishing](#learn-about-atp-anti-phishing-policy-options) op ATP voor meer informatie.

6. Nadat u uw instellingen hebt gecontroleerd, kiest **u Dit beleid maken** (of **Opslaan).**

## <a name="learn-about-atp-anti-phishing-policy-options"></a>Meer informatie over atp-beleidsopties voor phishing

Terwijl u uw ATP-antiphishingbeleid instelt of bewerkt, u kiezen uit verschillende opties die de meest geavanceerde en uitgebreide bescherming bieden, zoals beschreven in de volgende tabel:

|**Deze instelling**|**Is dit**|**Gebruik wanneer u dat wilt:**|
|:-----|:-----|:-----|
|**Gebruikers toevoegen om te beschermen**|Hiermee bepaalt u welke e-mailadressen door het beleid worden beschermd. U maximaal 60 interne en externe adressen toevoegen die u wilt beschermen tegen imitatie.|Wanneer u ervoor wilt zorgen dat e-mail van buiten uw organisatie geen imitatie is van een van de gebruikers in de lijst met gebruikers die u beschermt. Voorbeelden van gebruikers die u wilt beschermen zijn leidinggevenden op hoog niveau, bedrijfseigenaren, externe bestuursleden, enzovoort.  <br/> Deze lijst met beschermde gebruikers verschilt van de lijst met personen waarop het beleid van toepassing is, of beter gezegd, waarvoor het beleid wordt afgedwongen. U definieert de lijst van toepassing op in de sectie **Toegepast op** de beleidsopties.  <br/> Als u bijvoorbeeld `Mary Smith <marys@contoso.com>` als gebruiker toevoegt om te beschermen, past u het beleid toe op de groep 'Alle gebruikers'. Dit zou ervoor zorgen dat een e-mail die leek te imiteren "Mary Smith" verzonden naar een gebruiker in de "Alle gebruikers" groep zou worden gehandeld door het beleid.|
|**Domeinen toevoegen om te beschermen**|Hiermee u kiezen welke domeinen u wilt beschermen tegen imitatie. U opgeven dat het beleid al uw aangepaste domeinen, een door komma's gescheiden lijst met domeinen of een combinatie van beide bevat. Als u **automatisch domeinen opneemt waarvan ik eigenaar ben**en u later een domein toevoegt aan uw Office 365-organisatie, is dit antiphishingbeleid van kracht voor het nieuwe domein.|Wanneer u ervoor wilt zorgen dat e-mail van buiten uw organisatie geen imitatie is van een van de domeinen die zijn gedefinieerd in uw lijst met geverifieerde domeinen of die van een partnerdomein.|
|**Acties kiezen**|Kies de actie die u moet uitvoeren wanneer Office 365 een imitatiepoging detecteert tegen de gebruikers en domeinen die u aan het beleid hebt toegevoegd. U verschillende acties kiezen voor gebruikers en domeinen in hetzelfde anti-phishingbeleid. Deze acties zijn van toepassing op binnenkomende e-mail die door Office 365 is geïdentificeerd als een gebruikersaccount of -domein dat onder de bescherming van dit antiphishingbeleid valt.  <br/> **Quarantainebericht** E-mail wordt verzonden naar Office 365 quarantaine. Wanneer u deze optie kiest, wordt de e-mail niet naar de oorspronkelijke ontvanger verzonden.  <br/> **Bericht doorverwijzen naar een ander e-mailadres** E-mail wordt verzonden naar het opgegeven e-mailadres. U meerdere e-mailadressen opgeven. Wanneer u deze optie kiest, wordt de e-mail niet naar de oorspronkelijke ontvanger verzonden.  <br/> **Bericht verplaatsen naar de map Ongewenste e-mail van de geadresseerden** E-mail wordt verzonden naar de map Ongewenste e-mail van de geadresseerden. Wanneer u deze optie kiest, wordt de e-mail nog steeds naar de oorspronkelijke ontvanger verzonden, maar wordt deze niet in het postvak IN van de ontvanger geplaatst.  <br/> **Het bericht afgeven en andere adressen toevoegen aan de BCC-regel** E-mail wordt aan de oorspronkelijke ontvanger bezorgd. Bovendien worden de gebruikers die u identificeert toegevoegd aan de bcc-regel van het bericht voordat het wordt bezorgd. Wanneer u deze optie kiest, wordt de e-mail nog steeds naar het postvak IN van de oorspronkelijke ontvanger verzonden.  <br/> **Geen actie toepassen** E-mail wordt bezorgd in de inbox van de oorspronkelijke ontvanger. Er wordt geen andere actie ondernomen op het e-mailbericht.  <br/> **Phishing-beveiligingstips inschakelen** Hiermee kunnen anti-phishing veiligheidstips in e-mail worden gebruikt.|Wanneer u een actie wilt uitvoeren voor berichten waarvan Office 365 heeft bepaald dat het een imitatie is van een gebruiker of domein zoals gedefinieerd in het beleid.|
|**Postvakintelligentie inschakelen**|Hiermee schakelt u postvakintelligentie voor dit beleid in of uit. U postvakinformatie alleen inschakelen voor cloudaccounts, dat wil zeggen accounts waarvan het postvak volledig wordt gehost in Office 365.| Deze functie maakt gebruik van machine learning om de e-mailpatronen van een gebruiker te bepalen met hun contactpersonen. Met deze informatie kan de AI beter onderscheid maken tussen echte en phishing e-mails.|
|**Bescherming op basis van postbusinformatie inschakelen**|Hiermee schakelt u postvakintelligentie in of uit voor imitatiebescherming voor dit beleid. Het belangrijkste aspect hier is de controle van de imitatie voor een bepaalde mailbox.|Wanneer u de imitatieresultaten voor gebruikers wilt verbeteren op basis van de individuele afzenderkaart van elke gebruiker. Met deze intelligentie kan Office 365 de detectie van gebruikersimitatieaanpassen en fout-positieven beter verwerken. Wanneer de imitatie van gebruikers wordt gedetecteerd op basis van postvakinformatie, u bepalen welke actie u moet ondernemen op het bericht.|
|**Vertrouwde afzenders en domeinen toevoegen**|Definieert e-mailadressen en domeinen die door dit beleid niet als imitatie worden beschouwd. Berichten van de e-mailadressen en domeinen van de afzender die u toevoegt als vertrouwde afzenders en domeinen, worden nooit geclassificeerd als een aanval op basis van imitatie. Als gevolg hiervan worden de acties en instellingen in dit beleid niet toegepast op berichten van deze afzenders en domeinen.  <br/><br/>De maximumlimiet voor deze lijsten is ongeveer 1000 vermeldingen.|Wanneer gebruikers communiceren met domeinen of gebruikers die imitatie activeren, maar als veilig worden beschouwd. Als een partner bijvoorbeeld dezelfde/vergelijkbare weergavenaam of domeinnaam heeft als een gebruiker die in de lijst is gedefinieerd.|
|**Toegepast op**|Hiermee definieert u de geadresseerden waarvan de binnenkomende e-mailberichten onderworpen zijn aan de regels van het beleid. U voorwaarden en uitzonderingen maken voor de ontvangers die aan het beleid zijn gekoppeld.  <br/> U bijvoorbeeld een algemeen beleid voor uw organisatie maken door de regel toe te passen op alle ontvangers in uw domein.  <br/> U ook uitzonderingsregels maken, zoals een regel die geen e-mailberichten scant voor een specifieke groep ontvangers.|Elk beleid moet worden gekoppeld aan een set gebruikers, bijvoorbeeld gebruikers in een bepaalde groep of domein.|
|**Geavanceerde phishingdrempels**|Hiermee definieert u het niveau van de instellingen voor de manier waarop phishingberichten worden verwerkt.  <br/> **Standaard**: E-mail waarvan wordt vermoed dat deze phish is, wordt standaard behandeld.  <br/> **Agressief**: Het systeem behandelt e-mails waarvan wordt vermoed dat ze phish met een hoge mate van vertrouwen, op dezelfde manier als die verdacht met een zeer hoge mate van vertrouwen.  <br/> **Agressiever**: Het systeem behandelt e-mails waarvan wordt vermoed dat ze phish zijn met een gemiddelde of hoge mate van vertrouwen, op dezelfde manier als die verdacht met een zeer hoge mate van vertrouwen.  <br/> **Meest agressief**: Het systeem behandelt e-mails waarvan wordt vermoed dat ze phish zijn met een lage, gemiddelde of hoge mate van vertrouwen, op dezelfde manier als die verdacht met een zeer hoge mate van vertrouwen.|Wanneer u agressiever wilt zijn in de behandeling van mogelijk phishingberichten binnen Office 365. Bijvoorbeeld, berichten met een zeer hoge kans op phish zal de meest agressieve acties op hen, terwijl berichten met een lage waarschijnlijkheid hebben minder agressieve acties op hen. Deze instelling heeft ook gevolgen voor andere delen van het filtersysteem die signalen combineren. Dit betekent niet noodzakelijkerwijs dat verschillende acties worden uitgevoerd.  In wezen stelt u de kans op e-mail wordt phish, om de (dezelfde) aangewezen actie te bepalen. De kans op het verplaatsen van goede berichten neemt toe naarmate het niveau van de instellingen toeneemt.|

## <a name="learn-about-anti-phishing-policy-options"></a>Meer informatie over beleidsopties tegen phishing

Terwijl u uw antiphishing instelt of bewerkt, u kiezen uit verschillende opties, zoals beschreven in de volgende tabel:

|**Deze instelling**|**Is dit**|**Gebruik wanneer u dat wilt:**|
|:-----|:-----|:-----|
|**Toegepast op**|Hiermee definieert u de geadresseerden waarvan de binnenkomende e-mailberichten onderworpen zijn aan de regels van het beleid. U voorwaarden en uitzonderingen maken voor de ontvangers die aan het beleid zijn gekoppeld.  <br/> U bijvoorbeeld een algemeen beleid voor uw organisatie maken door de regel toe te passen op alle ontvangers in uw domein.  <br/> U ook uitzonderingsregels maken, zoals een regel die geen e-mailberichten scant voor een specifieke groep ontvangers.|Elk beleid moet worden gekoppeld aan een set gebruikers, bijvoorbeeld gebruikers in een bepaalde groep of domein.|
|**Acties kiezen**|Kies de actie die u moet uitvoeren wanneer Office 365 een poging voor spoofing via een intra-org of externe organisatie tegen uw gebruikers detecteert. Deze acties zijn van toepassing op binnenkomende e-mail die door Office 365 is geïdentificeerd als een spoofing-poging voor gebruikers die onder de bescherming van dit antiphishingbeleid vallen.  <br/> **Quarantainebericht** E-mail wordt verzonden naar Office 365 quarantaine. Wanneer u deze optie kiest, wordt de e-mail niet naar de oorspronkelijke ontvanger verzonden.  <br/> **Bericht verplaatsen naar de map Ongewenste e-mail van de geadresseerden** E-mail wordt verzonden naar de map Ongewenste e-mail van de geadresseerden. Wanneer u deze optie kiest, wordt de e-mail nog steeds naar de oorspronkelijke ontvanger verzonden, maar wordt deze niet in het postvak IN van de ontvanger geplaatst.  <br/> **Geen actie toepassen** E-mail wordt bezorgd in de inbox van de oorspronkelijke ontvanger. Er wordt geen andere actie ondernomen op het e-mailbericht.|Wanneer u een actie wilt uitvoeren voor berichten waarvan Office 365 heeft bepaald dat het een spoofing-poging is van interne of externe domeinen zoals gedefinieerd in het beleid.|

Nadat uw organisatie antiphishingbeleid of ATP-antiphishingbeleid heeft ingesteld, u zien hoe de service werkt door [rapporten voor Geavanceerde bedreigingsbeveiliging te bekijken.](view-reports-for-atp.md)

## <a name="example-anti-phishing-policy-to-protect-a-user-and-a-domain"></a>Voorbeeld: Anti-phishingbeleid om een gebruiker en een domein te beschermen

In dit voorbeeld wordt een beleid ingesteld dat "Domein en CEO" wordt genoemd en dat zowel gebruikers- `contoso.com`als domeinbescherming biedt tegen imitatie en vervolgens het beleid toepast op alle e-mail die door gebruikers binnen het domein wordt ontvangen. De beveiligingsbeheerder heeft vastgesteld dat het beleid aan deze bedrijfsvereisten moet voldoen:

- Het beleid moet bescherming bieden voor het e-mailaccount van de CEO en het hele domein.

- Berichten waarvan is vastgesteld dat ze imitatiepogingen zijn tegen het gebruikersaccount van de CEO, moeten worden doorgestuurd naar het e-mailadres van de beveiligingsbeheerder.

- Berichten waarvan is vastgesteld dat ze imitatiepogingen tegen het domein zijn, zijn minder urgent en moeten in quarantaine worden geplaatst voor latere beoordeling.

De beveiligingsbeheerder van Contoso kan waarden als de volgende gebruiken om een antiphishingbeleid te maken dat aan deze behoeften voldoet.

|||
|:-----|:-----|
|**Instellen of optie**|**Voorbeeld**|
|Name|Domein en CEO|
|Beschrijving|Zorg ervoor dat de CEO en ons domein niet worden nagebootst.|
|Gebruikers toevoegen om te beschermen|Het e-mailadres van de CEO minimaal.|
|Domeinen toevoegen om te beschermen|Het organisatiedomein dat het kantoor van de CEO omvat.|
|Acties kiezen|Als e-mail wordt verzonden door een nagebootste gebruiker: kies **Bericht omleiden naar een ander e-mailadres** en typ vervolgens het e-mailadres van de beveiligingsbeheerder, bijvoorbeeld . `securityadmin@contoso.com`  <br/> Als e-mail wordt verzonden door een nagebootst domein: Kies **Quarantainebericht**.|
|Postvakintelligentie|Postvakinformatie wordt standaard geselecteerd wanneer u een nieuw antiphishingbeleid maakt. Laat deze instelling **Aan** voor de beste resultaten.|
|Vertrouwde afzenders en domeinen toevoegen|Definieer in dit voorbeeld geen overschrijvingen.|
|Toegepast op|Selecteer **Het domein van de geadresseerde is**. Selecteer **onder Een van deze**opties **Kiezen**. Selecteer **+ Toevoegen**. Schakel bijvoorbeeld `contoso.com`het selectievakje naast de naam van het domein in de lijst in en selecteer **Toevoegen**. Selecteer **Gereed**.|

## <a name="delete-an-anti-phishing-or-atp-anti-phishing-policy"></a>Een anti-phishing- of ATP-antiphishingbeleid verwijderen

U aangepaste beleidsregels verwijderen die &amp; u hebt gemaakt met behulp van het Security Compliance Center. U het standaardbeleid voor uw organisatie niet verwijderen. We raden u &amp; aan het Security Compliance Center te gebruiken om een van uw ATP-beleid te bekijken of te bewerken.

1. Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan met je werk- of schoolaccount.

2. Kies In de linkernavigatie, onder **Bedreigingsbeheer**, **Beleid**.

3. Kies **op** de pagina Beleid de optie **Anti-phishing** of **ATP anti-phishing.**

4. Selecteer op de **antiphishing-** of **ATP-antiphishingpagina** de beleidsnaam in de lijst.

5. Kies op de pagina die wordt weergegeven **het beleid verwijderen**. Geef u tot 30 minuten de tijd om uw wijzigingen te verspreiden naar alle Office 365-datacenters.

## <a name="next-steps"></a>Volgende stappen

Zodra uw antiphishingbeleid van kracht is, u zien hoe uw functies voor bedreigingsbescherming voor uw organisatie werken door rapporten te bekijken. Zie de volgende bronnen voor meer informatie:

- [Rapporten voor Office 365 ATP bekijken](view-reports-for-atp.md) of [e-mailbeveiligingsrapporten weergeven](view-email-security-reports.md)

- [Threat Explorer (of realtime detecties) gebruiken](threat-explorer.md)

Blijf op de hoogte van nieuwe functies die naar ATP komen. bezoek de [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) en leer meer over [nieuwe functies die worden toegevoegd aan ATP.](office-365-atp.md#new-features-in-office-365-atp)
