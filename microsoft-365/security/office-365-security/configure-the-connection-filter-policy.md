---
title: Het verbindingsfilterbeleid configureren, lijst toestaan, lijst Blokkeren
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
description: U het verbindingsfilterbeleid gebruiken om een lijst met toegestane gegevens te maken, ook wel een veilige afzenderlijst genoemd, van IP-adressen die u vertrouwt. U ook een lijst met geblokkeerde afzenders maken.
ms.openlocfilehash: db0d7acc6189f29b247c1dc4004311d2843d139b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808443"
---
# <a name="configure-the-connection-filter-policy"></a>Het beleid voor verbindingsfilter configureren

De meesten van ons hebben vrienden en zakenpartners die we vertrouwen. Het kan frustrerend zijn om e-mail van hen te vinden in uw ongewenste e-mailmap, of zelfs volledig geblokkeerd door een spamfilter. Als u ervoor wilt zorgen dat e-mail die wordt verzonden van mensen die u vertrouwt niet wordt geblokkeerd, u het beleid voor verbindingsfilter gebruiken om een lijst met toestaan te maken, ook wel een veilige afzenderlijst genoemd, van IP-adressen die u vertrouwt. U ook een lijst met geblokkeerde afzenders maken, een lijst met IP-adressen, meestal van bekende spammers, waarvan u nooit e-mailberichten wilt ontvangen.

- Houd bij het denken over *[Lijsten toestaan](create-safe-sender-lists-in-office-365.md)* rekening met het beleid voor verbindingsfilter en houdt zich bezig met de vertrouwde accounts die door het filter *zijn toegestaan.* Dit wordt gedaan in het belang van nauwkeuriger filteren van minder vertrouwde of niet-vertrouwde mailers terwijl het houden van wat je nodig hebt. Een lijst met verbindingsfilteropties Gaat over het filteren naar de weinige vertrouwde IP's uit een veel grotere groep accounts en IP's en het verzekeren van een betere toegang voor uw vertrouwde mailers.

- Een verbindingsfilterbeleid dat een bloklijst maakt, kan worden beschouwd als het vangen van minder of onbetrouwbare accounts in het filter.

 Voor meer spam-instellingen die van toepassing zijn op de hele organisatie, kijk op [Hoe te voorkomen dat goede e-mail wordt gemarkeerd als spam in Office 365](prevent-email-from-being-marked-as-spam.md) of Hoe [spam-e-mail in Office 365 te verminderen.](reduce-spam-email.md) Deze zijn handig als u controle op administratorniveau hebt en u valse positieven of valse negatieven wilt voorkomen.

> [!TIP]
> U pauzeren en lezen hoe u [lijsten voor toestaan (of veilige afzenders)](create-safe-sender-lists-in-office-365.md) en lijsten blokkeren [maken.](create-block-sender-lists-in-office-365.md)

In de volgende video worden de configuratiestappen voor het verbindingsfilterbeleid weergegeven:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Geschatte tijdsduur: 15 minuten

- U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie het item 'Antispam' in het onderwerp [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) om te zien welke machtigingen u nodig hebt.

- Als u het IP-adres wilt verkrijgen van de afzender wiens berichten u wilt toestaan of blokkeren, u de internetheader van het bericht controleren. Zoek naar de CIP-header zoals beschreven in [antispamberichtenkoppen.](anti-spam-message-headers.md) Zie [Kopteksten voor internetberichten weergeven in Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)voor informatie over het weergeven van een berichtkop in verschillende e-mailclients.

- E-mailberichten die vanaf een IP-adres in de IP-bloklijst worden verzonden, worden geweigerd, niet gemarkeerd als spam en er vindt geen extra filtering plaats.

- De volgende verbindingsfilterprocedure kan ook worden uitgevoerd via externe PowerShell. Gebruik de cmdlet [Get-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedconnectionfilterpolicy) om uw instellingen te controleren en het Beleid voor het instellen [van verbindingsfilter](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedconnectionfilterpolicy) om de beleidsinstellingen van uw verbindingsfilter te bewerken. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)voor meer informatie over het gebruik van Windows PowerShell om verbinding te maken met Exchange Online Protection. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)voor meer informatie over het gebruik van Windows PowerShell om verbinding te maken met Exchange Online.

## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>De EAC gebruiken om het standaardverbindingsfilterbeleid te bewerken

U maakt een lijst met IP-toestaan of IP-blok door het verbindingsfilterbeleid te bewerken in het Exchange-beheercentrum (EAC). De beleidsinstellingen voor verbindingsfilters worden alleen toegepast op binnenkomende berichten.

1. Navigeer in het Exchange-beheercentrum (EAC) naar het \> **filter** **Beveiligingsverbinding** en dubbelklik op het standaardbeleid.

2. Klik **op het menu-item Verbindingsfiltering** en maak vervolgens de gewenste lijsten: een lijst met IP-toestaan, een IP-bloklijst of beide.

   Als u deze ![lijsten](../../media/ITPro-EAC-AddIcon.gif)wilt maken, klikt u op Pictogram toevoegen . Geef in het volgende dialoogvenster het IP-adres- of adresbereik op en klik op **ok**. Herhaal dit proces om extra adressen toe te voegen. (U ook IP-adressen bewerken of verwijderen nadat ze zijn toegevoegd.)

   IPV4 IP-adressen opgeven in de indeling nnn.nnn.nnnn waar nnn een getal van 0 tot 255 is. U ook CIDR-bereiken (Classless Inter-Domain Routing) opgeven in de indeling nnn.nnn.nnn/rr waar rr een getal van 24 tot 32 is. Als u bereiken buiten het bereik van 24 tot 32 wilt opgeven, raadpleegt u de volgende sectie, [Aanvullende overwegingen bij het configureren van IP-lijst toestaan](#additional-considerations-when-configuring-ip-allow-lists).

   > [!NOTE]
   > Als u een IP-adres aan beide lijsten toevoegt, is e-mail die vanaf dat IP-adres wordt verzonden, toegestaan. <br/><br/> U maximaal 1273 vermeldingen opgeven, waarbij een vermelding één IP-adres of een CIDR-reeks IP-adressen is van /24 tot /32. <br/><br/> Als u TLS-versleutelde berichten verzendt, worden IPv6-adressen en adresbereiken niet ondersteund.

3. Schakel optioneel het selectievakje **Veilige lijst inschakelen** in om ontbrekende e-mail van bepaalde bekende afzenders te voorkomen. Hoe? Microsoft abonneert zich op bronnen van vertrouwde afzenders van derden. Als u deze veilige lijst gebruikt, worden deze vertrouwde afzenders niet ten onrechte gemarkeerd als spam. We raden u aan deze optie te selecteren omdat het aantal false positives (goede e-mail die is geclassificeerd als spam) moet verminderen.

4. Klik **op Opslaan**. In het rechterdeelvenster verschijnt een overzicht van uw standaardbeleidsinstellingen.

## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>Aanvullende overwegingen bij het configureren van IP-lijsttoestaan

De volgende zijn aanvullende overwegingen die u overwegen of waarvan u zich bewust moet zijn bij het configureren van een IP-lijst toestaan.

### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>Een CIDR-bereik opgeven dat buiten het aanbevolen bereik valt

Als u een CIDR-IP-adresbereik van /1 tot /23 wilt opgeven, moet u een e-mailstroomregel maken die werkt op het IP-adresbereik waarmee het spamvertrouwensniveau (SCL) wordt ingesteld op **Het filteren van spam omzeilen** (wat betekent dat alle berichten die binnen dit IP-adresbereik zijn ontvangen, zijn ingesteld op "geen spam") en dat er geen extra filtering wordt uitgevoerd door de service). Als een van deze IP-adressen echter op een van de eigen bloklijsten van Microsoft of op een van onze bloklijsten van derden wordt weergegeven, worden deze berichten nog steeds geblokkeerd. Het wordt daarom ten zeerste aanbevolen om het IP-adresbereik van 24 tot /32 te gebruiken.

Voer de volgende stappen uit om deze regel voor e-mailstroom te maken.

1. Navigeer in de EAC naar **E-mailstroomregels** \> **Rules**.

2. Klik ![op](../../media/ITPro-EAC-AddIcon.gif) Pictogram toevoegen en selecteer **Vervolgens Een nieuwe regel maken**.

3. Geef de regel een naam en klik op **Meer opties**.

4. Selecteer **onder Deze regel toepassen als**u De **afzender** selecteert en vervolgens **IP-adres**kiest in een van deze bereiken of exact overeenkomt met .

5. Geef in het **IP-adres opgeven**op, geef](../../media/ITPro-EAC-AddIcon.gif)het IP-adresbereik op, klik op Pictogram **toevoegen** ![en klik vervolgens op **ok**.

6. Stel **onder Het volgende** vak de actie in door de eigenschappen van het bericht **wijzigen** te kiezen en vervolgens **het spamvertrouwensniveau (SCL) in te stellen.** Selecteer in het vak **SCL opgeven** de optie **Spamfilteren omzeilen**en klik op **ok**.

7. Als u wilt, u selecties maken om de regel te controleren, de regel te testen, de regel te activeren gedurende een bepaalde periode en andere selecties. We raden u aan de regel te testen voor een periode voordat u deze afdwingt. [Procedures voor e-mailstroomregels in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) bevatten meer informatie over deze selecties.

8. Klik **op Opslaan** om de regel op te slaan. De regel wordt weergegeven in uw lijst met regels.

Nadat u de regel hebt gemaakt en gehandhaafd, omzeilt de service spamfilters voor het opgegeven IP-adresbereik.

### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>Een uitzondering voor een IP-lijst toestaan voor een specifiek domein scoping

In het algemeen raden we u aan de IP-adressen (of IP-adresbereiken) toe te voegen voor al uw domeinen die u als veilig beschouwt aan de lijst IP-toegestane. Als u echter niet wilt dat uw IP-lijstvermelding toestaan van toepassing is op al uw domeinen, u een e-mailstroomregel (ook wel een transportregel genoemd) maken die specifieke domeinen met uitzondering van.

Stel dat u drie domeinen hebt: ContosoA.com, ContosoB.com en ContosoC.com en u wilt het IP-adres toevoegen (omwille van de eenvoud, laten we 1.2.3.4 gebruiken) en filtering alleen overslaan voor domeinContosoB.com. U zou een IP-lijst toestaan voor 1.2.3.4, die de spam vertrouwen niveau (SCL) sets op -1 (wat betekent dat het is geclassificeerd als niet-spam) voor alle domeinen. U vervolgens een e-mailstroomregel maken die de SCL voor alle domeinen instelt, behalve ContosoB.com op 0. Dit resulteert in het bericht dat opnieuw wordt gescand voor alle domeinen die zijn gekoppeld aan het IP-adres, behalve voor ContosoB.com dat is het domein dat wordt vermeld als uitzondering in de regel. ContosoB.com heeft nog steeds een SCL van -1, wat betekent dat u filtert, terwijl ContosoA.com en ContosoC.com SL's van 0 hebben, wat betekent dat ze opnieuw worden gescand door het inhoudsfilter.

Voer hiervoor de volgende stappen uit:

1. Navigeer in de EAC naar **E-mailstroomregels** \> **Rules**.

2. Klik ![op](../../media/ITPro-EAC-AddIcon.gif) Pictogram toevoegen en selecteer **Vervolgens Een nieuwe regel maken**.

3. Geef de regel een naam en klik op **Meer opties**.

4. Selecteer **onder Deze regel toepassen als**u De **afzender** selecteert en vervolgens **IP-adres**kiest in een van deze bereiken of exact overeenkomt met .

5. Geef in het vak **IP-adressen opgeven** het IP-adres of ip-adresbereik op](../../media/ITPro-EAC-AddIcon.gif)dat u hebt ingevoerd in de lijst IP-toestaan, klik op Pictogram **toevoegen** ![en klik vervolgens op **OK**.

6. Stel **onder Voer het volgende**in door de actie in te stellen door de eigenschappen van het bericht **wijzigen** te kiezen en vervolgens **het spamvertrouwensniveau (SCL) in te stellen.** Selecteer in het vak **SCL opgeven** de optie **0**en klik op **OK**.

7. Klik **op Uitzondering toevoegen**en selecteer onder Behalve **als**, Selecteer **De afzender** en kies domein **is**.

8. Voer **in** het vak Domein opgeven het domein in waarvoor u spamfilters wilt omzeilen, zoals **contosob.com**. Klik **op** ![](../../media/ITPro-EAC-AddIcon.gif) Pictogram toevoegen om het naar de lijst met woordgroepen te verplaatsen. Herhaal deze stap als u extra domeinen wilt toevoegen als uitzonderingen en klik op **ok** wanneer u klaar bent.

9. Als u wilt, u selecties maken om de regel te controleren, de regel te testen, de regel te activeren gedurende een bepaalde periode en andere selecties. We raden u aan de regel te testen voor een periode voordat u deze afdwingt. [Procedures voor e-mailstroomregels in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) bevatten meer informatie over deze selecties.

10. Klik **op Opslaan** om de regel op te slaan. De regel wordt weergegeven in uw lijst met regels.

Nadat u de regel hebt gemaakt en gehandhaafd, wordt spamfiltering voor het door u opgegeven IP-adres- of IP-adresbereik alleen omzeild voor de domeinuitzondering die u hebt ingevoerd.

### <a name="scenarios-where-allowed-ip-addresses-are-still-filtered"></a>Scenario's waarin toegestane IP-adressen nog steeds worden gefilterd

Berichten van toegestane IP-adressen die u hebt geconfigureerd in het filterbeleid voor verbindingen, zijn nog steeds onderhevig aan spamfiltering in de volgende scenario's:

- Het bron-IP-adres in uw verbindingsfilterbeleid is ook geconfigureerd in een on-premises, IP-gebaseerde inkomende connector in *elke* tenant (laten we dit Tenant A noemen) **en** Tenant A en de Exchange Online Protection-server die het bericht voor het eerst tegenkomt in Office 365, bevinden zich toevallig in hetzelfde Active Directory-forest in de Microsoft-datacenters. In dit scenario wordt **IPV:CAL** toegevoegd aan de [antispamberichtenkoppen](anti-spam-message-headers.md) van het bericht (met vermelding van het bericht dat spamfiltering wordt omzeild), maar is het bericht nog steeds onderhevig aan spamfiltering.

- Uw tenant (waarbij u het verbindingsfilterbeleid hebt geconfigureerd) en de Exchange Online Protection-server die het bericht voor het eerst tegenkomt in Office 365, bevinden zich toevallig in verschillende Active Directory-forests in de Microsoft-datacenters. In dit scenario wordt **IPV:CAL** niet toegevoegd aan de berichtkoppen, dus het bericht is nog steeds onderhevig aan spamfiltering.

Als u een van deze scenario's tegenkomt, u een e-mailstroomregel in de EAC maken met (ten minste) de volgende instellingen om ervoor te zorgen dat berichten vanaf het IP-adres of adressen spamfilters omzeilen:

- Regelvoorwaarde: **Pas deze regel toe als** \> het IP-adres van de **afzender** \> **zich in een van deze bereiken bevindt of precies overeenkomt** \> (uw IP-adres of adressen).

- Regelactie: **Wijzig de eigenschappen** \> van het bericht **Stel het spamvertrouwensniveau (SCL)** \> **Spamfiltering in.**

Dit is in principe dezelfde regelcreatieprocedure van de vorige [Scoping an IP Allow-lijstuitzondering voor een specifieke domeinsectie.](#scoping-an-ip-allow-list-exception-for-a-specific-domain)

## <a name="new-to-office-365"></a>Nieuw in Office 365?

||
|:-----|
|![Het korte pictogram voor](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) LinkedIn Learning **New to Office 365?** Ontdek gratis videocursussen voor **Office 365-beheerders en IT-professionals**, aangeboden via LinkedIn Learning.|

## <a name="for-more-information"></a>Voor meer informatie

[Lijsten met veilige afzenders en geblokkeerde afzenders in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)

[Uw beleid voor spamfilters configureren](configure-your-spam-filter-policies.md)

[Het uitgaande spambeleid configureren](configure-the-outbound-spam-policy.md)

[Voorkomen dat goede e-mail wordt gemarkeerd als spam in Office 365](prevent-email-from-being-marked-as-spam.md)

[Spam-e-mail verminderen in Office 365](reduce-spam-email.md)
