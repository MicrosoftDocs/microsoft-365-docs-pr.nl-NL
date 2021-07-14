---
title: Regels voor e-mailstroom definiëren om e-mailberichten te versleutelen
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren om regels voor e-mailstroom (transportregels) te maken om berichten te versleutelen en te ontsleutelen met Office 365-berichtversleuteling.
ms.openlocfilehash: 5274c2368de9825bd0568b7abd4e060e22fe9c70
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430454"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>Regels voor e-mailstroom definiëren om e-mailberichten te versleutelen

Als beheerder die Exchange Online beheert, kunt u regels voor e-mailstroom (ook wel transportregels genoemd) maken om e-mailberichten die u verzendt en ontvangt te beveiligen. U kunt regels instellen om uitgaande e-mailberichten te versleutelen en versleuteling te verwijderen uit versleutelde berichten die afkomstig zijn van uw organisatie of van antwoorden naar versleutelde berichten die vanuit uw organisatie worden verzonden. U kunt het Exchange (EAC) of Exchange Online PowerShell gebruiken om deze regels te maken. Naast algemene versleutelingsregels kunt u er ook voor kiezen om afzonderlijke opties voor berichtversleuteling voor eindgebruikers in of uit te schakelen.

U kunt binnenkomende e-mail van afzenders buiten uw organisatie niet versleutelen.

Als u onlangs bent gemigreerd van Active Directory RMS naar Azure Information Protection, moet u de bestaande regels voor de e-mailstroom controleren om ervoor te zorgen dat ze blijven werken in uw nieuwe omgeving. Als u wilt profiteren van de nieuwe Office 365-berichtversleuteling (OME)-mogelijkheden die beschikbaar zijn via Azure Information Protection, moet u uw bestaande regels voor e-mailstroom bijwerken. Anders blijven uw gebruikers versleutelde e-mail ontvangen die de vorige HTML-bijlageindeling gebruikt in plaats van de nieuwe, naadloze OME-ervaring. Als u OME nog niet hebt ingesteld, gaat u naar Nieuwe functies Office 365-berichtversleuteling [voor](set-up-new-message-encryption-capabilities.md) informatie.

Zie Regels voor e-mailstroom [(transportregels) in](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)Exchange Online. Zie Het configureren van Exchange Online regels voor e-mailstroom voor [Azure Information Protection-labels voor](/azure/information-protection/deploy-use/configure-exo-rules)meer informatie over hoe e-mailstroomregels werken met Azure Information Protection.

> [!IMPORTANT]
> Voor hybride Exchange kunnen on-premises gebruikers alleen versleutelde e-mail verzenden en ontvangen met OME als e-mail wordt doorgestuurd via Exchange Online. Als u OME wilt configureren in een hybride [](/Exchange/exchange-hybrid) Exchange-omgeving, moet u eerst hybride configureren met de wizard Hybride configuratie en vervolgens e-mail configureren om van [Office 365 naar](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) uw e-mailserver te stromen en e-mail zo configureren dat de e-mail van uw e-mailserver naar de [Office 365.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365) Nadat u e-mail hebt geconfigureerd om door de Office 365, kunt u e-mailstroomregels voor OME configureren met behulp van deze richtlijnen.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Regels voor e-mailstroom maken om e-mailberichten te versleutelen met de nieuwe OME-mogelijkheden

U kunt e-mailstroomregels definiëren voor het activeren van berichtversleuteling met de nieuwe OME-mogelijkheden met behulp van de EAC.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>Gebruik het EAC om een regel te maken voor het versleutelen van e-mailberichten met de nieuwe OME-mogelijkheden

1. Meld u in een webbrowser met behulp van een werk- of schoolaccount dat globale beheerdersmachtigingen is verleend, [aan bij Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. Kies de **tegel** Beheerder.

3. Kies beheercentra Microsoft 365-beheercentrum de  \> Exchange.

4. Ga in het EAC naar **E-mailstroomregels** \>  en selecteer **Nieuw** nieuw pictogram Een nieuwe ![ regel ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **maken.** Zie voor meer informatie over het gebruik van het EAC [Exchange beheercentrum in Exchange Online.](/exchange/exchange-admin-center)

5. Typ **in Naam** een naam voor de regel, zoals E-mail versleutelen voor DrToniRamos@hotmail.com.

6. Selecteer **in Deze regel toepassen als**, selecteer een voorwaarde en voer zo nodig een waarde in. Als u bijvoorbeeld berichten wilt versleutelen die naar DrToniRamos@hotmail.com:

   1. Selecteer **in Deze regel toepassen als**, selecteer de **geadresseerde is**.

   2. Selecteer een bestaande naam in de lijst met contactpersonen of typ een nieuw e-mailadres in **het selectievakje Namen.**

      - Als u een bestaande naam wilt selecteren, selecteert u deze in de lijst en klikt u vervolgens op **OK.**

      - Als u een nieuwe naam wilt invoeren, typt u een e-mailadres in het **selectievakje** Namen en selecteert u **namen controleren** \> **OK.**

7. Als u meer voorwaarden wilt toevoegen, kiest u **Meer opties** en kiest u vervolgens **Voorwaarde toevoegen** en selecteert u in de lijst.

   Als u de regel bijvoorbeeld alleen wilt toepassen als de geadresseerde zich buiten uw organisatie, selecteert u **voorwaarde** toevoegen en selecteert u Vervolgens De geadresseerde **is extern/intern** \> **Buiten de organisatie** \> **OK.**

8. Als u versleuteling wilt inschakelen met de nieuwe OME-mogelijkheden, selecteert u in Do the **following**, Modify the message **security** and then choose Apply Office 365-berichtversleuteling and **rights protection**. Selecteer een RMS-sjabloon in de lijst, kies **Opslaan** en kies **ok.**
  
  De lijst met sjablonen bevat alle standaardsjablonen en -opties, evenals alle aangepaste sjablonen die u hebt gemaakt voor gebruik door Office 365. Als de lijst leeg is, moet u ervoor zorgen dat u Office 365-berichtversleuteling hebt ingesteld met de nieuwe mogelijkheden zoals beschreven in Nieuwe functies [Office 365-berichtversleuteling instellen.](set-up-new-message-encryption-capabilities.md) Zie Sjablonen configureren en beheren voor [Azure Information Protection](/information-protection/deploy-use/configure-policy-templates)voor meer informatie over de standaardsjablonen. Zie Optie  Niet doorsturen voor e-mailberichten voor informatie over de optie Niet doorsturen. [](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) Zie **Versleutelen-only-optie** voor e-mailberichten voor informatie over de optie [alleen-versleutelen.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

  U kunt actie **toevoegen kiezen** als u een andere actie wilt opgeven.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>De EAC gebruiken om een bestaande e-mailstroomregel bij te werken om de nieuwe OME-mogelijkheden te gebruiken

1. Meld u in een webbrowser met behulp van een werk- of schoolaccount dat globale beheerdersmachtigingen is verleend, [aan bij Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. Kies de **tegel** Beheerder.

3. Kies beheercentra Microsoft 365-beheercentrum de  \> Exchange.

4. Ga in het EAC naar **E-mailstroomregels.** \> 

5. Selecteer in de lijst met regels voor e-mailstroom de regel die u wilt wijzigen om de nieuwe OME-mogelijkheden te gebruiken en kies vervolgens **Pictogram** ![ Bewerken ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) bewerken.

6. Als u versleuteling wilt inschakelen met de nieuwe OME-mogelijkheden, kiest u in Do the **following**, Modify the message **security** and then choose Apply Office 365-berichtversleuteling and **rights protection**. Selecteer een RMS-sjabloon in de lijst, kies **Opslaan** en kies **OK.**

   De lijst met sjablonen bevat alle standaardsjablonen en -opties, evenals alle aangepaste sjablonen die u hebt gemaakt voor gebruik door Office 365. Als de lijst leeg is, moet u ervoor zorgen dat u Office 365-berichtversleuteling hebt ingesteld met de nieuwe mogelijkheden zoals beschreven in Nieuwe Office 365-berichtversleuteling-mogelijkheden instellen die bovenop Azure Information Protection zijn [gebouwd.](set-up-new-message-encryption-capabilities.md) Zie Sjablonen configureren en beheren voor [Azure Information Protection](/information-protection/deploy-use/configure-policy-templates)voor meer informatie over de standaardsjablonen. Zie Optie Niet doorsturen voor [](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)e-mailberichten voor informatie over de optie Niet doorsturen. Zie Alleen versleutelen voor [e-mailberichten](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)voor informatie over de optie alleen-versleutelen.

   U kunt actie **toevoegen kiezen** als u een andere actie wilt opgeven.

7. Verwijder in **de lijst Ga als volgt** te werk om alle acties te verwijderen die zijn toegewezen aan **De** berichtbeveiliging wijzigen De vorige versie \> **van OME toepassen.**

8. Selecteer **Opslaan**.

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-the-new-ome-capabilities"></a>Regels voor e-mailstroom maken om versleuteling voor e-mailberichten te verwijderen met de nieuwe OME-mogelijkheden

U kunt regels voor e-mailstroom definiëren voor het activeren van berichtversleuteling met de nieuwe OME-mogelijkheden met behulp van de EAC.

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>Gebruik het EAC om een regel te maken om versleuteling te verwijderen uit e-mailberichten met de nieuwe OME-mogelijkheden

U kunt versleuteling verwijderen die wordt toegepast door uw organisatie.

1. Meld u in een webbrowser met behulp van een werk- of schoolaccount dat globale beheerdersmachtigingen is verleend, [aan bij Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. Kies de **tegel** Beheerder.

3. Kies beheercentra Microsoft 365-beheercentrum de  \> Exchange.

4. Ga in het EAC naar **E-mailstroomregels** \>  en selecteer **Nieuw** nieuw pictogram Een nieuwe ![ regel ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **maken.** Zie voor meer informatie over het gebruik van het EAC [Exchange beheercentrum in Exchange Online.](/exchange/exchange-admin-center)

5. Typ **in Naam** een naam voor de regel, zoals Versleuteling verwijderen uit uitgaande e-mail.

6. Selecteer **in Deze regel toepassen als** de voorwaarden voor het verwijderen van versleuteling uit berichten. Toevoegen **De afzender bevindt zich binnen** de organisatie voor het verzenden van e-mail of De geadresseerde bevindt zich binnen de \>    \> **organisatie** voor het ontvangen van e-mail.

7. Selecteer **in Ga als volgt** te werk en selecteer De **berichtbeveiliging** wijzigen \> **Office 365-berichtversleuteling en rechtenbescherming**.

8. Kies **Opslaan**.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>E-mailstroomregels maken voor Office 365-berichtversleuteling zonder de nieuwe mogelijkheden

Als u uw organisatie nog niet hebt verplaatst naar de nieuwe OME-mogelijkheden, raadt Microsoft u aan een plan te maken om over te gaan naar de nieuwe OME-mogelijkheden zodra dit redelijk is voor uw organisatie. Zie Nieuwe functies Office 365-berichtversleuteling Azure Information Protection instellen voor [instructies.](set-up-new-message-encryption-capabilities.md) Zie Anders E-mailstroomregels definiëren voor Office 365-berichtversleuteling die geen gebruik maken van de [nieuwe OME-mogelijkheden.](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities)

## <a name="related-topics"></a>Verwante onderwerpen

[Versleuteling in Office 365](encryption.md)

[De nieuwe mogelijkheden van Office 365-berichtversleuteling instellen](set-up-new-message-encryption-capabilities.md)

[Huisstijl toevoegen aan versleutelde berichten](add-your-organization-brand-to-encrypted-messages.md)

[Regels voor e-mailstroom (transportregels) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
