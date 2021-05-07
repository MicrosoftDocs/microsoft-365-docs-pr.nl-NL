---
title: Uw organisatiemerk toevoegen aan uw versleutelde berichten
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Lees hoe Office 365 globale beheerders de huisstijl van uw organisatie kunnen toepassen op versleutelde e-mailberichten & inhoud van de versleutelingsportal.
ms.openlocfilehash: 2898e12ad00d11cd9eb2f3be5d817ef113607e79
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162485"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>Het merk van uw organisatie toevoegen aan uw Microsoft 365 berichtenversleuteling voor bedrijven

U kunt de huisstijl van uw bedrijf toepassen om het uiterlijk van de e-mailberichten van uw organisatie en de versleutelingsportal aan te passen. U moet globale beheerdersmachtigingen toepassen op uw werk- of schoolaccount voordat u aan de slag kunt. Wanneer u deze machtigingen hebt, gebruikt u de Get-OMEConfiguration en Set-OMEConfiguration Windows PowerShell cmdlets om deze onderdelen van versleutelde e-mailberichten aan te passen:
  
- Inleidende tekst

- Vrijwaringstekst

- URL voor de privacyverklaring van uw organisatie

- Tekst in de OME-portal

- Logo dat wordt weergegeven in het e-mailbericht en de OME-portal, of dat u helemaal geen logo wilt gebruiken

- Achtergrondkleur in het e-mailbericht en de OME-portal

U kunt ook op elk moment terugkeren naar het standaard-uiterlijk.

Als u meer controle wilt, gebruikt u Office 365 Advanced Message Encryption om meerdere sjablonen te maken voor versleutelde e-mailberichten die afkomstig zijn van uw organisatie. Gebruik deze sjablonen om delen van de eindgebruikerservaring te beheren. Geef bijvoorbeeld op of geadresseerden Google, Yahoo en Microsoft-accounts kunnen gebruiken om zich aan te melden bij de versleutelingsportal. Gebruik sjablonen om aan verschillende gebruiksgevallen te voldoen, zoals:

- Afzonderlijke afdelingen, zoals Financiën, Verkoop, en dergelijke.

- Verschillende producten

- Verschillende geografische regio's of landen

- Of u wilt toestaan dat e-mailberichten worden ingetrokken

- Of u wilt dat e-mailberichten die naar externe geadresseerden worden verzonden, na een bepaald aantal dagen verlopen.

Nadat u de sjablonen hebt gemaakt, kunt u deze toepassen op versleutelde e-mailberichten met behulp van Exchange regels voor e-mailstroom. Als u een Office 365 Advanced Message Encryption, kunt u alle e-mailberichten die u hebt gebrandmerkt, intrekken met behulp van deze sjablonen.

## <a name="work-with-ome-branding-templates"></a>Werken met OME-huisstijlsjablonen

U kunt verschillende functies in een huisstijlsjabloon wijzigen. U kunt de standaardsjabloon wijzigen, maar niet verwijderen. Als u geavanceerde berichtversleuteling hebt, kunt u ook aangepaste sjablonen maken, wijzigen en verwijderen. Gebruik Windows PowerShell om met één huisstijlsjabloon tegelijk te werken.

- [Set-OMEConfiguration-](/powershell/module/exchange/set-omeconfiguration) Wijzig de standaardbrandingsjabloon of een aangepaste huisstijlsjabloon die u hebt gemaakt.
- [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Maak een nieuwe huisstijlsjabloon, alleen Geavanceerde berichtversleuteling.
- [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Verwijder een aangepaste huisstijlsjabloon, alleen Geavanceerde berichtversleuteling. U kunt de standaardsjabloon voor huisstijl niet verwijderen.
  
## <a name="modify-an-ome-branding-template"></a>Een OME-huisstijlsjabloon wijzigen

Gebruik Windows PowerShell om één huisstijlsjabloon tegelijk te wijzigen. Als u geavanceerde berichtversleuteling hebt, kunt u ook aangepaste sjablonen maken, wijzigen en verwijderen.

1. Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online. Zie Verbinding maken [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)voor instructies.

2. Gebruik de Set-OMEConfiguration cmdlet zoals beschreven in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) of gebruik de volgende afbeelding en tabel voor richtlijnen.

![Aanpasbare e-mailonderdelen](../media/ome-template-breakout.png)

|**Deze functie van de versleutelingservaring aanpassen**|**Deze opdrachten gebruiken**|
|:-----|:-----|
|Achtergrondkleur|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **Voorbeeld:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> Zie de sectie Achtergrondkleuren [](#background-color-reference) verder in dit artikel voor meer informatie over achtergrondkleuren.|
|Logo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **Voorbeeld:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Ondersteunde bestandsindelingen: .png, .jpg, .bmp of .tiff  <br/> Optimale grootte van het logobestand: minder dan 40 KB  <br/> Optimale grootte van de afbeelding van het logo: 170x70 pixels. Als de afbeelding deze dimensies overschrijdt, wordt het logo voor weergave in de portal door de service van het 1000-jaar-10-2017-2019-2019-2019-2010-2019- De service wijzigt het afbeeldingsbestand zelf niet. Gebruik de optimale grootte voor het beste resultaat.|
|Tekst naast de naam en het e-mailadres van de afzender|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **Voorbeeld:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Tekst die wordt weergegeven op de knop Bericht lezen|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **Voorbeeld:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Tekst die wordt weergegeven onder de knop Bericht lezen|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **Voorbeeld:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|URL voor de koppeling Privacyverklaring|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **Voorbeeld:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|Vrijwaringsverklaring in het e-mailbericht met het versleutelde bericht|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Voorbeeld:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Tekst die boven aan de portal voor het weergeven van versleutelde e-mail wordt weergegeven|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Voorbeeld:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Verificatie in- of uitschakelen met een een time pass-code voor deze aangepaste sjabloon|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **Voorbeelden:** <br/>Een een time passcodes inschakelen voor deze aangepaste sjabloon <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Een een time passcodes uitschakelen voor deze aangepaste sjabloon <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Verificatie met Microsoft-, Google- of Yahoo-identiteiten in- of uitschakelen voor deze aangepaste sjabloon|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **Voorbeelden:** <br/>Sociale ID's inschakelen voor deze aangepaste sjabloon <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Sociale ID's uitschakelen voor deze aangepaste sjabloon <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Een OME-huisstijlsjabloon maken (Geavanceerde berichtversleuteling)

Als u een Office 365 Advanced Message Encryption, kunt u aangepaste huisstijlsjablonen voor uw organisatie maken met de cmdlet [New-OMEConfiguration.](/powershell/module/exchange/new-omeconfiguration) Nadat u de sjabloon hebt gemaakt, wijzigt u de sjabloon met de Set-OMEConfiguration cmdlet zoals beschreven in [Een OME-merksjabloon wijzigen.](#modify-an-ome-branding-template) U kunt meerdere sjablonen maken.

Een nieuwe sjabloon voor aangepaste huisstijl maken:

1. Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online. Zie Verbinding maken [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)voor instructies.

2. Gebruik de [cmdlet Nieuw-OMEConfiguratie](/powershell/module/exchange/new-omeconfiguration) om een nieuwe sjabloon te maken.

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   Bijvoorbeeld:

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>De standaardsjabloon voor huisstijl retourneren naar de oorspronkelijke waarden

Als u alle wijzigingen uit de standaardsjabloon wilt verwijderen, inclusief merkaanpassingen, en dergelijke, gaat u als volgende stappen te werk:
  
1. Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online. Zie Verbinding maken [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)voor instructies.

2. Gebruik de **cmdlet Set-OMEConfiguration** zoals beschreven in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration). Als u de merkaanpassingen van uw organisatie wilt verwijderen uit de waarden DisclaimerTekst, E-mailtekst en PortalTekst, stelt u de waarde in op een lege `""` tekenreeks, . Voor alle afbeeldingswaarden, zoals Logo, stelt u de waarde in op  `"$null"` .

   In de volgende tabel wordt de standaardinstelling voor versleutelingsaanpassing beschreven.

   |Deze functie van de versleutelingservaring terugdraaien naar de standaardtekst en afbeelding|Deze opdrachten gebruiken|
   |:-----|:-----|
   |Standaardtekst die wordt geleverd met versleutelde e-mailberichten.  De standaardtekst wordt weergegeven boven de instructies voor het weergeven van versleutelde berichten|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **Voorbeeld:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |Vrijwaringsverklaring in het e-mailbericht met het versleutelde bericht|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **Voorbeeld:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |Tekst die boven aan de portal voor het weergeven van versleutelde e-mail wordt weergegeven|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **Voorbeeld om terug te keren naar standaard:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Logo|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **Voorbeeld om terug te keren naar standaard:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Achtergrondkleur|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **Voorbeeld om terug te keren naar standaard:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Een aangepaste huisstijlsjabloon verwijderen (Geavanceerde berichtversleuteling)

U kunt alleen merksjablonen verwijderen of verwijderen die u hebt gemaakt. U kunt de standaardsjabloon voor huisstijl niet verwijderen.

Een aangepaste huisstijlsjabloon verwijderen:
  
1. Als u een werk- of schoolaccount gebruikt met globale beheerdersmachtigingen in uw organisatie, start u een Windows PowerShell en maakt u verbinding met Exchange Online. Zie Verbinding maken [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)voor instructies.

2. Gebruik de **cmdlet Remove-OMEConfiguration** als volgt:

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   Bijvoorbeeld:

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Zie [Remove-OMEConfiguration (Verwijderen-OMEConfiguration) voor meer informatie.](/powershell/module/exchange/remove-omeconfiguration)

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Maak een Exchange e-mailstroomregel die uw aangepaste huisstijl op versleutelde e-mailberichten van toepassing is

Nadat u de standaardsjabloon hebt gewijzigd of nieuwe huisstijlsjablonen hebt gemaakt, kunt u Exchange regels voor e-mailstroom maken om uw aangepaste huisstijl toe te passen op basis van bepaalde voorwaarden. Een dergelijke regel is in de volgende scenario's van toepassing op aangepaste huisstijl:

- Als de e-mail handmatig is versleuteld door de eindgebruiker met Outlook of Outlook op het web, voorheen Outlook Web App

- Als de e-mail automatisch is versleuteld door een Exchange regel voor e-mailstroom of beleid voor preventie van gegevensverlies

Zie Regels voor e-mailstroom definiëren om e-mailberichten te versleutelen in Office 365 voor informatie over het maken van een Exchange [e-mailstroomregel](define-mail-flow-rules-to-encrypt-email.md)die versleuteling van toepassing is.

1. Meld u in een webbrowser met behulp van een werk- of schoolaccount dat globale beheerdersmachtigingen is verleend, [aan bij Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. Kies de **tegel** Beheerder.

3. Kies in Microsoft 365 beheercentrum de optie **Beheercentra** \> **Exchange.**

4. Ga in het EAC naar **E-mailstroomregels** \>  en selecteer **Nieuw** nieuw pictogram Een nieuwe ![ regel ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **maken.** Zie voor meer informatie over het gebruik van het EAC [Exchange beheercentrum in Exchange Online.](/exchange/exchange-admin-center)

5. Typ **in Naam** een naam voor de regel, zoals Huisstijl voor verkoopafdeling.

6. Selecteer **in Deze regel toepassen als** de voorwaarde De afzender bevindt zich **binnen** de organisatie en andere voorwaarden die u wilt in de lijst met beschikbare voorwaarden. U kunt bijvoorbeeld een bepaalde huisstijlsjabloon toepassen op:

   - Alle versleutelde e-mailberichten die zijn verzonden van leden van de financiële afdeling
   - Versleutelde e-mailberichten die zijn verzonden met een bepaald trefwoord, zoals 'Extern' of 'Partner'.
   - Versleutelde e-mailberichten die naar een bepaald domein zijn verzonden

7. Selecteer **in Ga als volgt** te werk en selecteer De **berichtbeveiliging** Aanpassen Aangepaste \> **huisstijl toepassen op OME-berichten.** Selecteer vervolgens in de vervolgkeuzekeuzepagina een huisstijlsjabloon.

8. (Optioneel) U kunt de regel voor de e-mailstroom zo configureren dat versleuteling en aangepaste huisstijl worden toegepast. Selecteer **in Ga als volgt** te werk, selecteer De **berichtbeveiliging wijzigen** en kies vervolgens Office 365-berichtversleuteling en **rechtenbescherming toepassen.** Selecteer een RMS-sjabloon in de lijst, kies **Opslaan** en kies **ok.**
  
   De lijst met sjablonen bevat standaardsjablonen en opties en eventuele aangepaste sjablonen die u maakt. Als de lijst leeg is, moet u ervoor zorgen dat u Office 365-berichtversleuteling met de nieuwe mogelijkheden. Zie Nieuwe functies voor Office 365-berichtversleuteling instellen voor [instructies.](set-up-new-message-encryption-capabilities.md) Zie Sjablonen configureren en beheren voor [Azure Information Protection](/information-protection/deploy-use/configure-policy-templates)voor meer informatie over de standaardsjablonen. Zie Optie  Niet doorsturen voor e-mailberichten voor informatie over de optie Niet doorsturen. [](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) Zie Alleen **versleutelen** voor e-mailberichten voor informatie over de enige optie [voor versleutelen.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

   Kies **Actie toevoegen** als u een andere actie wilt opgeven.

## <a name="background-color-reference"></a>Achtergrondkleurverwijzing

De kleurnamen die u voor de achtergrondkleur kunt gebruiken, zijn beperkt. In plaats van een kleurnaam kunt u een hexcodewaarde (#RRGGBB). U kunt een hexcodewaarde gebruiken die overeenkomt met een kleurnaam of u kunt een aangepaste hex-codewaarde gebruiken. Zorg ervoor dat u de hexcodewaarde tussen aanhalingstekens (bijvoorbeeld) `"#f0f8ff"` omsluit.

De beschikbare achtergrondkleurnamen en de bijbehorende hexcodewaarden worden in de volgende tabel beschreven.

|**Naam van kleur**|**Kleurcode**|
|---|---|
|`aliceblue`|#f0f8ff|
|`antiquewhite`|#faebd7|
|`aqua`|#00ffff|
|`aquamarine`|#7fffd4|
|`azure`|#f0ffff|
|`beige`|#f5f5dc|
|`bisque`|#ffe4c4|
|`black`|#000000|
|`blanchedalmond`|#ffebcd|
|`blue`|#0000ff|
|`blueviolet`|#8a2be2|
|`brown`|#a52a2a|
|`burlywood`|#deb887|
|`cadetblue`|#5f9ea0|
|`chartreuse`|#7fff00|
|`chocolate`|#d2691e|
|`coral`|#ff7f50|
|`cornflowerblue`|#6495ed|
|`cornsilk`|#fff8dc|
|`crimson`|#dc143c|
|`cyan`|#00ffff|
|`darkblue`|#00008b|
|`darkcyan`|#008b8b|
|`darkgoldenrod`|#b8860b|
|`darkgray`|#a9a9a9|
|`darkgreen`|#006400|
|`darkkhaki`|#bdb76b|
|`darkmagenta`|#8b008b|
|`darkolivegreen`|#556b2f|
|`darkorange`|#ff8c00|
|`darkorchid`|#9932cc|
|`darkred`|#8b0000|
|`darksalmon`|#e9967a|
|`darkseagreen`|#8fbc8f|
|`darkslateblue`|#483d8b|
|`darkslategray`|#2f4f4f|
|`darkturquoise`|#00ced1|
|`darkviolet`|#9400d3|
|`deeppink`|#ff1493|
|`deepskyblue`|#00bfff|
|`dimgray`|#696969|
|`dodgerblue`|#1e90ff|
|`firebrick`|#b22222|
|`floralwhite`|#fffaf0|
|`forestgreen`|#228b22|
|`fuchsia`|#ff00ff|
|`gainsboro`|#dcdcdc|
|`ghostwhite`|#f8f8ff|
|`gold`|#ffd700|
|`goldenrod`|#daa520|
|`gray`|#808080|
|`green`|#008000|
|`greenyellow`|#adff2f|
|`honeydew`|#f0fff0|
|`hotpink`|#ff69b4|
|`indianred`|#cd5c5c|
|`indigo`|#4b0082|
|`ivory`|#fffff0|
|`khaki`|#f0e68c|
|`lavender`|#e6e6fa|
|`lavenderblush`|#fff0f5|
|`lawngreen`|#7cfc00|
|`lemonchiffon`|#fffacd|
|`lightblue`|#add8e6|
|`lightcoral`|#f08080|
|`lightcyan`|#e0ffff|
|`lightgoldenrodyellow`|#fafad2|
|`lightgray`|#d3d3d3|
|`lightgrey`|#d3d3d3|
|`lightgreen`|#90ee90|
|`lightpink`|#ffb6c1|
|`lightsalmon`|#ffa07a|
|`lightseagreen`|#20b2aa|
|`lightskyblue`|#87cefa|
|`lightslategray`|#778899|
|`lightsteelblue`|#b0c4de|
|`lightyellow`|#ffffe0|
|`lime`|#00ff00|
|`limegreen`|#32cd32|
|`linen`|#faf0e6|
|`magenta`|#ff00ff|
|`maroon`|#800000|
|`mediumaquamarine`|#66cdaa|
|`mediumblue`|#0000cd|
|`mediumorchid`|#ba55d3|
|`mediumpurple`|#9370db|
|`mediumseagreen`|#3cb371|
|`mediumslateblue`|#7b68ee|
|`mediumspringgreen`|#00fa9a|
|`mediumturquoise`|#48d1cc|
|`mediumvioletred`|#c71585|
|`midnightblue`|#191970|
|`mintcream`|#f5fffa|
|`mistyrose`|#ffe4e1|
|`moccasin`|#ffe4b5|
|`navajowhite`|#ffdead|
|`navy`|#000080|
|`oldlace`|#fdf5e6|
|`olive`|#808000|
|`olivedrab`|#6b8e23|
|`orange`|#ffa500|
|`orangered`|#ff4500|
|`orchid`|#da70d6|
|`palegoldenrod`|#eee8aa|
|`palegreen`|#98fb98|
|`paleturquoise`|#afeeee|
|`palevioletred`|#db7093|
|`papayawhip`|#ffefd5|
|`peachpuff`|#ffdab9|
|`peru`|#cd853f|
|`pink`|#ffc0cb|
|`plum`|#dda0dd|
|`powderblue`|#b0e0e6|
|`purple`|#800080|
|`red`|#ff0000|
|`rosybrown`|#bc8f8f|
|`royalblue`|#4169e1|
|`saddlebrown`|#8b4513|
|`salmon`|#fa8072|
|`sandybrown`|#f4a460|
|`seagreen`|#00ff00|
|`seashell`|#fff5ee|
|`sienna`|#a0522d|
|`silver`|#c0c0c0|
|`skyblue`|#87ceeb|
|`slateblue`|#6a5acd|
|`slategray`|#708090|
|`snow`|#fffafa|
|`springgreen`|#00ff7f|
|`steelblue`|#4682b4|
|`tan`|#d2b48c|
|`teal`|#008080|
|`thistle`|#d8bfd8|
|`tomato`|#ff6347|
|`turquoise`|#40e0d0|
|`violet`|#ee82ee|
|`wheat`|#f5deb3|
|`white`|#ffffff|
|`whitesmoke`|#f5f5f5|
|`yellow`|#ffff00|
|`yellowgreen`|#9acd32|