---
title: Beveiligingsbeleid voor apparaten maken in eenvoudige mobiliteit en beveiliging
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
description: Gebruik basis mobiliteit en beveiliging voor het maken van beleidsregels voor het beschermen van uw organisatie.
ms.openlocfilehash: 077f1e7e0d763aaecfc38fd4b57d9e8912900a3c
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877066"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Beveiligingsbeleid voor apparaten maken in eenvoudige mobiliteit en beveiliging

Met basis mobiliteit en beveiliging kunt u beleidsregels voor apparaten maken waarmee u uw bedrijfsgegevens op Microsoft 365 kunt beschermen tegen toegang door onbevoegden. U kunt beleidsregels toepassen op elk mobiel apparaat in uw organisatie waarbij de gebruiker van het apparaat een toepasselijke Microsoft 365-licentie heeft geregistreerd en het apparaat heeft geregistreerd onder eenvoudige mobiliteit en beveiliging.

## <a name="before-you-begin"></a>Voordat u begint

> [!IMPORTANT]
> Voordat u een beleid voor mobiel apparaat kunt maken, moet u eerst basis mobiliteit en beveiliging inschakelen en instellen. Zie voor meer informatie een overzicht van eenvoudige mobiliteit en beveiliging.

- Meer informatie over de apparaten, apps voor mobiele apparaten en beveiligingsinstellingen die basisondersteuning voor mobiliteit en beveiliging ondersteunen. De [mogelijkheden van eenvoudige mobiliteit en beveiliging](capabilities.md)weergeven.
- Maak beveiligingsgroepen die Microsoft 365-gebruikers bevatten waarop u beleidsregels wilt implementeren en voor gebruikers voor wie u de toegang tot Microsoft 365 mag uitsluiten. U wordt aangeraden het beleid te testen voordat u een nieuw beleid implementeert voor uw organisatie door het te implementeren voor een klein aantal gebruikers. U kunt een beveiligingsgroep maken en gebruiken die uitsluitend uzelf of een klein nummer heeft voor Microsoft 365-gebruikers die het beleid kunnen testen. Zie [een beveiligingsgroep maken, bewerken of verwijderen](https://go.microsoft.com/fwlink/p/?LinkId=518555)voor meer informatie over beveiligingsgroepen.
- Als u basis-en beveiligingsbeleid wilt maken en implementeren in Microsoft 365, moet u een globale beheerder van Microsoft 365 zijn. Voor meer informatie raadpleegt u [machtigingen in de beveiligings & nalevings centrum](https://support.microsoft.com/office/d10608af-7934-490a-818e-e68f17d0e9c1).
- Voordat u beleidsregels implementeert, kunt u de potentiële gevolgen van het registreren van een apparaat op basis van mobiliteit en beveiliging achterhalen. Afhankelijk van de manier waarop u het beleid instelt, kunnen niet-compatibele apparaten toegang krijgen tot Microsoft 365 en gegevens, waaronder geïnstalleerde toepassingen, Foto's en persoonlijke gegevens op een geregistreerd apparaat en kunnen gegevens worden verwijderd.

>[!NOTE]
>Beleidsregels en toegangsregels die zijn gemaakt in basis mobiliteit en beveiliging voor Microsoft 365 Business Standard negeren postvak beleid voor mobiele apparaten van Exchange ActiveSync en regels voor Apparaattoegang die zijn gemaakt in het Exchange-Beheercentrum. Als een apparaat is ingeschreven voor basis mobiliteit en beveiliging voor Microsoft 365 Business Standard, wordt het postvak beleid mobiele apparaten van Exchange ActiveSync of de regel voor het openen van apparaten die op het apparaat zijn toegepast, genegeerd. Zie [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380)voor meer informatie over Exchange ActiveSync.

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Stap 1: een apparaatbeleid maken en implementeren in een testgroep

Voordat u kunt beginnen, moet u ervoor zorgen dat u de optie voor basis mobiliteit en beveiliging hebt ingeschakeld en ingesteld. Zie [overzicht van eenvoudige mobiliteit en beveiliging](overview.md)voor instructies.

1. Typ in uw browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecteer **een beleid maken**.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Basisinstellingen voor mobiliteit en beveiligingsbeleid":::

3. Geef op de pagina **beleidsinstellingen** de vereisten op die u wilt toepassen op mobiele apparaten in uw organisatie.

4. **Beheer van e-mail profiel vereisen**: als deze functie is ingeschakeld, worden apparaten zonder e-mail profiel dat wordt beheerd door basis mobiliteit en beveiliging als niet-compatibel beschouwd. Een apparaat kan geen beheerd e-mail profiel hebben als dit niet correct is ingesteld, of als de gebruiker het e-mailaccount handmatig instelt op het apparaat. Wanneer u deze optie **niet inschakelt** (standaard), wordt deze instelling niet geëvalueerd voor naleving of niet-naleving. Als u wilt weten hoe gebruikers compatibel kunnen zijn wanneer deze optie is geselecteerd, raadpleegt u [een bestaand e-mailaccount gevonden](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).

5. Kies op de pagina **wilt u dit beleid nu toepassen?** de groepen waarop u dit beleid wilt toepassen.

6. Selecteer **dit beleid maken**.

Het beleid voor de volgende keer dat u zich aanmeldt bij Microsoft 365 met behulp van het mobiele apparaat, is van toepassing op het apparaat van de gebruiker. Als gebruikers geen beleid hadden toegepast op hun mobiele apparaat voordat ze het beleid implementeren, ontvangen ze een melding op hun apparaat met de stappen voor het registreren en activeren van basis mobiliteit en beveiliging. Zie voor meer informatie [uw mobiele apparaat registreren met behulp van eenvoudige mobiliteit en beveiliging](enroll-your-mobile-device.md). Toegang tot e-mail, OneDrive en andere services is niet toegestaan totdat de inschrijving wordt voltooid in de basis mobiliteit en beveiliging die wordt gehost door de intune-service. Na voltooiing van de inschrijving met behulp van de app intune Company portal kunnen ze de Services gebruiken en het beleid op hun apparaat toegepast.

## <a name="step-2-verify-that-your-policy-works"></a>Stap 2: Controleer of uw beleid werkt

Nadat u een apparaatbeleid hebt gemaakt, controleert u of het beleid werkt zoals u verwacht voordat u het op uw organisatie implementeert.

1. Typ in uw browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecteer **de lijst met beheerde apparaten weergeven**.
3. Controleer de status van gebruikers apparaten waarop het beleid is toegepast. U wilt dat de **status** van apparaten wordt **beheerd.**
4. U kunt ook een volledig of selectief wissen op een apparaat uitvoeren door te klikken op **de knop bij** **opnieuw instellen** van **Bedrijfsgegevens** na selecteren van een apparaat. Zie voor instructies [een mobiel apparaat wissen in Microsoft 365.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>Stap 3: een beleid implementeren voor uw organisatie

Nadat u een apparaatbeleid hebt gemaakt en hebt gecontroleerd of dit is verwacht, moet u het apparaat implementeren in uw organisatie.

1. Vanuit uw browsertype: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecteer het beleid dat u wilt implementeren en kies **bewerken** naast **groepen toegepast op.**
3. Zoek de groep die u wilt toevoegen en klik op **selecteren**.
4. Selecteer **sluiten** en **instelling wijzigen.**
5. Selecteer **sluiten** en **beleid bewerken.**

Het beleid wordt pusht naar het mobiele apparaat van elke gebruiker waarop het beleid zich de volgende keer aanmeldt bij Microsoft 365 vanaf hun mobiele apparaat. Als gebruikers geen beleid op hun mobiele apparaat hebben toegepast, ontvangen ze een melding op hun apparaat met stappen voor het registreren en activeren van een basis voor mobiliteit en beveiliging. Nadat de registratie is voltooid, wordt het beleid op hun apparaat toegepast. Zie voor meer informatie [uw mobiele apparaat registreren met behulp van eenvoudige mobiliteit en beveiliging](enroll-your-mobile-device.md).

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Stap 4: e-mail toegang blokkeren voor niet-ondersteunde apparaten

Voor de bescherming van uw gegevens van uw organisatie dient u de toegang tot Microsoft 365-e-mail te blokkeren voor mobiele apparaten die niet worden ondersteund door basis mobiliteit en beveiliging. Zie [ondersteunde apparaten](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0#bkmk_supporteddevices)voor een lijst met ondersteunde apparaten.

**Toegang tot app blokkeren:**

1. Typ in uw browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecteer **instellingen voor Apparaattoegang voor de hele organisatie beheren**.
3. Als u niet-ondersteunde apparaten wilt blokkeren, kiest u **blok** onder **als een apparaat niet wordt ondersteund door basis mobiliteit en beveiliging voor Microsoft 365** en selecteert u vervolgens **Opslaan**.

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="De optie eenvoudige toegang voor mobiliteit en beveiligings blokkering":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Stap 5: Kies beveiligingsgroepen die moeten worden uitgesloten van voorwaardelijke toegang

Als u bepaalde personen wilt uitsluiten van controles voor voorwaardelijke toegang op hun mobiele apparaten en u een of meer beveiligingsgroepen voor deze personen hebt gemaakt, kunt u de beveiligingsgroepen hier toevoegen. De personen in deze groepen hebben geen beleidsregels die worden afgedwongen voor hun ondersteunde mobiele apparaten. Dit is de aanbevolen optie als u niet langer de basis mobiliteit en beveiliging van uw organisatie wilt gebruiken.

1. Typ in uw browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecteer **instellingen voor Apparaattoegang voor de hele organisatie beheren**.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="De optie basis mobiliteit en beveiliging voor een beleid maken":::

3. Selecteer **toevoegen** om de beveiligingsgroep toe te voegen met gebruikers waarvan u de toegang tot microsoft 365 wilt uitsluiten. Wanneer een gebruiker is toegevoegd aan deze lijst, hebben ze toegang tot Microsoft 365-e-mail wanneer ze een niet-ondersteund apparaat gebruiken.

4. Selecteer de beveiligingsgroep die u wilt gebruiken in het deelvenster **groep selecteren** .

5. Selecteer de naam en voeg vervolgens   >  **Opslaan** toe.

6. Kies in het deelvenster **Apparaattoegang-instellingen voor de gehele organisatie** de optie **Opslaan**.

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="De optie basis toegang voor de Mobility en beveiliging toestaan":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Wat is de gevolgen van beveiligingsbeleid voor verschillende apparaattypen?

Wanneer u een beleid toepast op gebruikers apparaten, verschilt de invloed op elk apparaat voor de verschillende typen apparaten. Zie de volgende tabel voor voorbeelden van de invloed van het beleid op verschillende apparaten.

|**Beveiligingsbeleid**|**Android 4 of hoger**|**Samsung KNOX**|**iOS 6 en hoger**|**Opmerkingen**|
|:-----|:-----|:-----|:-----|:-----|
|Gecodeerde back-up vereisen|Nee|Ja|Ja|Er is een gecodeerde back-up van iOS vereist.|
|Back-up van Cloud blokkeren|Ja|Ja|Ja|Google back-up voor Android blokkeren (grijs), Cloud back-up voor iOS.|
|Documentsynchronisatie blokkeren|Nee|Nee|Ja|iOS: documenten blokkeren in de Cloud.|
|Foto synchronisatieblok keren |Nee|Nee|Ja|iOS (systeemeigen): foto stroom blokkeren.|
|Schermopname blokkeren |Nee|Ja|Ja|Geblokkeerd indien geprobeerd.|
|Videovergadering blokkeren |Nee|Nee|Ja|FaceTime is geblokkeerd voor iOS, niet op Skype of andere personen.|
|Verzenden van diagnostische gegevensblok keren |Nee|Ja|Ja|Het verzenden van Google crash rapport op Android blokkeren.|
|Toegang tot App Store blokkeren |Nee|Ja|Ja|Het pictogram van de App Store ontbreekt op de startpagina van Android, uitgeschakeld in Windows, ontbreekt in iOS.|
|Wachtwoord vereist voor App Store |Nee|Nee|Ja|iOS: wachtwoord vereist voor iTunes-aankopen.|
|Verbinding met Verwisselbare opslag blokkeren |Nee|Ja|N.v.t.|Android: de SD-kaart wordt grijs weergegeven in instellingen, Windows waarschuwt gebruikers, apps die zijn geïnstalleerd, zijn niet beschikbaar|
|Bluetooth-verbinding blokkeren |Notities weergeven|Notities weergeven|Ja|BlueTooth kan niet worden uitgeschakeld als instelling voor Android. In plaats daarvan worden alle transacties uitgeschakeld waarvoor BlueTooth is vereist: geavanceerde audio distributie, audio/video, afstandsbediening, Handsfree apparaten, headset, telefoonboek toegang en seriële poort. Er verschijnt een klein pop-upvenster aan de onderkant van de pagina, wanneer deze worden gebruikt.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>Wat gebeurt er wanneer u een beleid verwijdert of een gebruiker uit het beleid verwijdert?

Wanneer u een beleid verwijdert of een gebruiker verwijdert uit een groep waarmee het beleid is geïmplementeerd, worden de beleidsinstellingen, het Microsoft 365-e-mail profiel en de in de cache geposte e-mailberichten van de Gebruikersservice verwijderd. Raadpleeg de volgende tabel om te zien wat er is verwijderd voor de verschillende apparaattypen.

|**Wat wordt verwijderd**|**iOS 6 en hoger**|**Android 4 en hoger (inclusief Samsung KNOX**|
|:-----|:-----|:-----|
|Beheerde e-mail profielen<sup>1</sup>|Ja|Nee|
|Back-up van Cloud blokkeren|Ja|Nee|

<sup>1</sup> als het beleid is geïmplementeerd met het optie **e-mail profiel is** geselecteerd, worden de beheerde e-mail profielen en de in de cache geplaatste e-mailberichten van het gebruikersapparaat verwijderd.

Het beleid is van toepassing op het mobiele apparaat voor elke gebruiker waarop het beleid van toepassing is en de volgende keer dat het apparaat met basis mobiliteit en beveiliging controleert. Als u een nieuw beleid implementeert dat van toepassing is op deze gebruikers apparaten, wordt u gevraagd om u opnieuw aan te melden bij basis mobiliteit en beveiliging.

U kunt een apparaat ook geheel wissen, of de bedrijfsgegevens van het apparaat selectief wissen. Zie [een mobiel apparaat wissen in basis mobiliteit en beveiliging](wipe-mobile-device.md)voor meer informatie.

## <a name="related-topics"></a>Verwante onderwerpen

[Overzicht van de Basic Mobility en Security](overview.md)

[Capaciteiten Basic Mobility en Security](capabilities.md)
