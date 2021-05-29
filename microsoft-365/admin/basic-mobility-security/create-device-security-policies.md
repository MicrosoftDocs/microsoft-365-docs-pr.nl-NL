---
title: Apparaatbeveiligingsbeleid maken in Basismobiliteit en Beveiliging
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Gebruik Basismobiliteit en beveiliging om apparaatbeleid te maken dat uw organisatiegegevens beschermt.
ms.openlocfilehash: 5519351db428faa837a63eedb384b42c8d8ee07c
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706320"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Apparaatbeveiligingsbeleid maken in Basismobiliteit en Beveiliging

U kunt Basismobiliteit en beveiliging gebruiken om apparaatbeleid te maken om uw organisatiegegevens op Microsoft 365 te beschermen tegen onbevoegde toegang. U kunt beleid toepassen op elk mobiel apparaat in uw organisatie waar de gebruiker van het apparaat een toepasselijke Microsoft 365-licentie heeft en het apparaat heeft geregistreerd in Basismobiliteit en Beveiliging.

## <a name="before-you-begin"></a>Voordat u begint

> [!IMPORTANT]
> Voordat u een beleid voor mobiele apparaten kunt maken, moet u Basismobiliteit en beveiliging activeren en instellen. Zie Overzicht van basismobiliteit en beveiliging voor meer informatie.

- Meer informatie over de apparaten, apps voor mobiele apparaten en beveiligingsinstellingen die door Basismobiliteit en Beveiliging worden ondersteund. Zie [Mogelijkheden van basismobiliteit en beveiliging.](capabilities.md)
- Maak beveiligingsgroepen met Microsoft 365 gebruikers die u beleid wilt implementeren voor en voor gebruikers die u mogelijk wilt uitsluiten van geblokkeerde toegang tot Microsoft 365. We raden u aan het beleid te testen voordat u een nieuw beleid implementeert voor uw organisatie door het beleid te implementeren voor een klein aantal gebruikers. U kunt een beveiligingsgroep maken en gebruiken die alleen uzelf of een klein aantal Microsoft 365 gebruikers die het beleid voor u kunnen testen. Zie Een beveiligingsgroep maken, bewerken of verwijderen voor meer informatie over [beveiligingsgroepen.](../email/create-edit-or-delete-a-security-group.md)
- Als u basisbeleid voor mobiliteit en beveiliging wilt maken en implementeren in Microsoft 365, moet u een globale beheerder Microsoft 365 zijn. Zie Machtigingen [in het Beveiligings- & compliancecentrum voor meer informatie.](../../security/office-365-security/permissions-in-the-security-and-compliance-center.md)
- Voordat u beleid implementeert, laat u uw organisatie weten wat de mogelijke gevolgen zijn van het registreren van een apparaat in Basismobiliteit en Beveiliging. Afhankelijk van hoe u het beleid in stelt, kunnen niet-compatibele apparaten worden geblokkeerd voor toegang tot Microsoft 365 en gegevens, waaronder geïnstalleerde toepassingen, foto's en persoonlijke gegevens op een geregistreerd apparaat, en kunnen gegevens worden verwijderd.

>[!NOTE]
>Beleidsregels en toegangsregels die zijn gemaakt in Basismobiliteit en beveiliging voor Microsoft 365 Business Standard overschrijven Exchange ActiveSync beleidsregels voor postvakken op mobiele apparaten en regels voor apparaattoegang die zijn gemaakt in het Exchange beheercentrum. Nadat een apparaat is geregistreerd voor Basismobiliteit en beveiliging voor Microsoft 365 Business Standard, wordt elke Exchange ActiveSync beleid voor postvak voor mobiele apparaten of regel voor apparaattoegang die is toegepast op het apparaat, genegeerd. Zie Exchange ActiveSync in Exchange Online voor [meer Exchange ActiveSync informatie](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)over Exchange Online.

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Stap 1: Een apparaatbeleid maken en implementeren in een testgroep

Voordat u kunt beginnen, moet u basismobiliteit en beveiliging hebben geactiveerd en ingesteld. Zie Overzicht van [basismobiliteit en beveiliging voor instructies.](overview.md)

1. Typ in uw browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecteer **Een beleid maken.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Beleidsinstellingen voor basismobiliteit en beveiliging":::

3. Geef op **de pagina Beleidsinstellingen** de vereisten op die u wilt toepassen op mobiele apparaten in uw organisatie.

4. **E-mailprofiel beheren** vereist: apparaten die geen e-mailprofiel hebben dat wordt beheerd door Basismobiliteit en Beveiliging, worden als niet compatibel beschouwd. Een apparaat kan geen beheerd e-mailprofiel hebben als het niet correct is gericht of als de gebruiker het e-mailaccount handmatig op het apparaat heeft ingesteld. Wanneer u de instelling **Niet ingeschakeld** laat (standaard), wordt deze instelling niet geëvalueerd op naleving of niet-naleving. Zie Een bestaand [e-mailaccount gevonden](/intune-user-help/existing-company-email-account-found)voor instructies over hoe gebruikers compatibel kunnen worden wanneer deze optie is geselecteerd.

5. Kies op de pagina Wilt u dit beleid nu **toepassen?** de groepen op wie u dit beleid wilt toepassen.

6. Selecteer **Dit beleid maken.**

Het beleid wordt naar het apparaat van elke gebruiker door het beleid schuift wanneer ze zich de volgende keer aanmelden bij Microsoft 365 mobiele apparaat. Als gebruikers nog niet eerder een beleid hebben toegepast op hun mobiele apparaat, ontvangen ze na het implementeren van het beleid een melding op hun apparaat met de stappen voor het registreren en activeren van Basismobiliteit en beveiliging. Zie Uw mobiele apparaat registreren met [basismobiliteit en beveiliging voor meer informatie.](enroll-your-mobile-device.md) Totdat ze de inschrijving in Basismobiliteit en Beveiliging voltooien die worden gehost door de Intune-service, is de toegang tot e-mail, OneDrive en andere services beperkt. Nadat ze de inschrijving hebben voltooid met de Intune-bedrijfsportal app, kunnen ze de services gebruiken en wordt het beleid toegepast op hun apparaat.

## <a name="step-2-verify-that-your-policy-works"></a>Stap 2: controleren of uw beleid werkt

Nadat u een apparaatbeleid hebt gemaakt, controleert u of het beleid werkt zoals u verwacht voordat u het implementeert naar uw organisatie.

1. Typ in uw browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecteer **De lijst met beheerde apparaten weergeven.**
3. Controleer de status van gebruikersapparaten die het beleid hebben toegepast. U wilt dat **de status** van apparaten wordt **beheerd.**
4. U kunt ook een volledig of selectief wissen  op een apparaat  doen door te klikken op de knop Fabrieksinstellingen opnieuw instellen of **Bedrijfsgegevens** verwijderen uit de knop Beheren nadat u een apparaat hebt geselecteerd. Zie [Een mobiel apparaat wissen in Microsoft 365.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>Stap 3: Een beleid implementeren in uw organisatie

Nadat u een apparaatbeleid hebt gemaakt en hebt gecontroleerd of het werkt zoals verwacht, implementeert u dit naar uw organisatie.

1. Vanuit uw browsertype: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecteer het beleid dat u wilt implementeren en kies **Bewerken** naast **Groepen die zijn toegepast op.**
3. Zoek naar een groep die u wilt toevoegen en klik op **Selecteren.**
4. Selecteer **De instelling** Sluiten en **wijzigen.**
5. Selecteer **Beleid sluiten** **en bewerken.**

Het beleid wordt naar het mobiele apparaat van elke gebruiker door het beleid geduwd wanneer ze zich de volgende keer aanmelden bij Microsoft 365 vanaf hun mobiele apparaat. Als gebruikers geen beleid hebben toegepast op hun mobiele apparaat, ontvangen ze een melding op hun apparaat met stappen om het in te schrijven en te activeren voor Basismobiliteit en Beveiliging. Nadat ze de inschrijving hebben voltooid, wordt het beleid toegepast op hun apparaat. Zie Uw mobiele apparaat registreren met [basismobiliteit en beveiliging voor meer informatie.](enroll-your-mobile-device.md)

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Stap 4: E-mailtoegang blokkeren voor niet-ondersteunde apparaten

Als u uw organisatiegegevens wilt beveiligen, moet u app-toegang tot e-Microsoft 365 blokkeren voor mobiele apparaten die niet worden ondersteund door Basismobiliteit en Beveiliging. Zie Ondersteunde apparaten voor een lijst met [ondersteunde apparaten.](../../admin/basic-mobility-security/capabilities.md)

**App-toegang blokkeren:**

1. Typ in uw browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecteer **Instellingen voor apparaattoegang voor de hele organisatie beheren.**
3. Als u niet-ondersteunde  apparaten wilt blokkeren, kiest u Blokkeren onder Als een apparaat niet wordt ondersteund door **Basismobiliteit** en beveiliging voor Microsoft 365 en selecteert u **Opslaan**.

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Optie Voor toegang tot basismobiliteits- en beveiligingsblokkering":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Stap 5: Beveiligingsgroepen kiezen die moeten worden uitgesloten van controles voor voorwaardelijke toegang

Als u sommige personen wilt uitsluiten van controles voor voorwaardelijke toegang op hun mobiele apparaten en u een of meer beveiligingsgroepen voor deze personen hebt gemaakt, voegt u de beveiligingsgroepen hier toe. De personen in deze groepen hebben geen beleid afgedwongen voor hun ondersteunde mobiele apparaten. Dit is de aanbevolen optie als u basismobiliteit en beveiliging niet meer wilt gebruiken in uw organisatie.

1. Typ in uw browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecteer **Instellingen voor apparaattoegang voor de hele organisatie beheren.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Basismobiliteit en beveiliging maken een beleidsoptie":::

3. Selecteer **Toevoegen** om de beveiligingsgroep toe te voegen met gebruikers die u wilt uitsluiten van geblokkeerde toegang tot Microsoft 365. Wanneer een gebruiker aan deze lijst is toegevoegd, heeft deze toegang tot Microsoft 365 e-mail wanneer deze een niet-ondersteund apparaat gebruikt.

4. Selecteer de beveiligingsgroep die u wilt gebruiken in het **deelvenster** Groep selecteren.

5. Selecteer de naam en voeg **opslaan**  >  **toe.**

6. Kies opslaan in het deelvenster Instellingen voor **apparaattoegang** voor de hele **organisatie.**

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Basic Mobility and Security allow access option":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Wat is het effect van beveiligingsbeleid op verschillende apparaattypen?

Wanneer u een beleid op gebruikersapparaten toe passen, verschilt de invloed op elk apparaat enigszins per apparaattype. Zie de volgende tabel voor voorbeelden van de impact van beleid op verschillende apparaten.

|**Beveiligingsbeleid**|**Android 4 en hoger**|**Samsung KNOX**|**iOS 6 en hoger**|**Opmerkingen**|
|:-----|:-----|:-----|:-----|:-----|
|Versleutelde back-up vereisen|Nee|Ja|Ja|Versleutelde back-up van iOS vereist.|
|Cloudback-up blokkeren|Ja|Ja|Ja|Google-back-up blokkeren op Android (grijs weergegeven), cloudback-up op iOS.|
|Documentsynchronisatie blokkeren|Nee|Nee|Ja|iOS: Documenten blokkeren in de cloud.|
|Fotosynchronisatie blokkeren |Nee|Nee|Ja|iOS (native): Fotostream blokkeren.|
|Schermopname blokkeren |Nee|Ja|Ja|Geblokkeerd wanneer u een poging hebt gedaan.|
|Videovergadering blokkeren |Nee|Nee|Ja|FaceTime is geblokkeerd in iOS, niet op Skype of anderen.|
|Het verzenden van diagnostische gegevens blokkeren |Nee|Ja|Ja|Blokkeer het verzenden van Google-crashrapport op Android.|
|Toegang tot de App Store blokkeren |Nee|Ja|Ja|App Store-pictogram ontbreekt op de startpagina van Android, uitgeschakeld op Windows, ontbreekt in iOS.|
|Wachtwoord vereisen voor de App Store |Nee|Nee|Ja|iOS: Wachtwoord vereist voor iTunes-aankopen.|
|Verbinding met verwisselbare opslag blokkeren |Nee|Ja|N.v.t.|Android: SD-kaart is grijs weergegeven in instellingen, Windows gebruiker op de Windows, geïnstalleerde apps zijn niet beschikbaar|
|Verbinding Bluetooth blokkeren |Notities bekijken|Notities bekijken|Ja|We kunnen BlueTooth niet uitschakelen als instelling voor Android. In plaats daarvan schakelen we alle transacties uit waarvoor BlueTooth nodig is: Geavanceerde audiodistributie, Audio/Video-afstandsbediening, handsfree apparaten, headset, Telefoon Book Access en Seriële poort. Een klein pop-upbericht wordt onder aan de pagina weergegeven wanneer een van deze berichten wordt gebruikt.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>Wat gebeurt er wanneer u een beleid verwijdert of een gebruiker uit het beleid verwijdert?

Wanneer u een beleid verwijdert of een gebruiker verwijdert uit een groep waaraan het beleid is geïmplementeerd, worden de beleidsinstellingen, Microsoft 365 e-mailprofiel en e-mailberichten in de cache mogelijk verwijderd van het apparaat van de gebruiker. Zie de volgende tabel om te zien wat er is verwijderd voor de verschillende apparaattypen.

|**Wat wordt verwijderd**|**iOS 6 en hoger**|**Android 4 en hoger (inclusief Samsung KNOX**|
|:-----|:-----|:-----|
|Beheerde e-mailprofielen<sup>1</sup>|Ja|Nee|
|Cloudback-up blokkeren|Ja|Nee|

<sup>1</sup> Als het beleid is geïmplementeerd met de optie E-mailprofiel **is** geselecteerd, worden het beheerde e-mailprofiel en de e-mailberichten in de cache in dat profiel verwijderd van het gebruikersapparaat.

Het beleid wordt verwijderd van het mobiele apparaat voor elke gebruiker. Het beleid is van toepassing op de volgende keer dat het apparaat wordt incheckt met Basismobiliteit en Beveiliging. Als u een nieuw beleid implementeert dat van toepassing is op deze gebruikersapparaten, wordt deze gevraagd zich opnieuw in te schrijven voor Basismobiliteit en Beveiliging.

U kunt een apparaat ook volledig wissen of organisatiegegevens selectief wissen vanaf het apparaat. Zie Een mobiel apparaat [wissen in Basismobiliteit en Beveiliging voor meer informatie.](wipe-mobile-device.md)

## <a name="related-content"></a>Verwante inhoud

[Overzicht van basismobiliteit en beveiliging](overview.md) (artikel)\
[Mogelijkheden van basismobiliteit en beveiliging](capabilities.md) (artikel)