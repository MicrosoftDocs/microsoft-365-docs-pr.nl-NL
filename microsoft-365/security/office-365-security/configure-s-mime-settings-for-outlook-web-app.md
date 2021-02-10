---
title: S/MIME-instellingen configureren - Exchange Online voor de webversie van Outlook
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Een korte beschrijving van wat Exchange Online-beheerders moeten doen om de S/MIME-instellingen in de webversie van Outlook in Exchange Online te bekijken en te configureren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a81db5ec933f1d0d6e2944103be53c0169dde62f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165677"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>S/MIME-instellingen configureren in Exchange Online voor de webversie van Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Als beheerder van Exchange Online kunt u de webversie van Outlook (voorheen Outlook Web App genoemd) zo instellen dat het verzenden en ontvangen van met S/MIME beveiligde berichten is toegestaan. Gebruik de **cmdlets Get-SmimeConfig** en **Set-SmimeConfig** om deze functie in Exchange Online PowerShell weer te geven en te beheren. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

Zie [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) en [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Overwegingen voor de nieuwe Microsoft Edge (op basis van Chromium)

Als u S/MIME in de webversie van Outlook wilt gebruiken in de nieuwe webbrowser [Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) moet u (of een andere beheerder) het browserbeleid van Microsoft Edge met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie in de nieuwe Microsoft Edge te installeren. De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Houd er rekening mee dat voor het toepassen van dit beleid apparaten zijn vereist die lid zijn van een domein of apparaten die lid zijn van Azure AD. Voor het gebruik van S/MIME in de nieuwe browser Microsoft Edge zijn apparaten die lid zijn van een domein of apparaten die lid zijn van Azure AD, effectief vereist.

Zie **ExtensionInstallForcelist** voor meer informatie over het beleid [ExtensionInstallForcelist.](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)

Deze stap is een vereiste voor het gebruik van het nieuwe Microsoft Edge. Het vervangt niet de S/MIME-besturing die door gebruikers is geïnstalleerd. Gebruikers wordt gevraagd om de S/MIME-besturing in de webversie van Outlook te downloaden en te installeren tijdens hun eerste gebruik van S/MIME. Gebruikers kunnen ook proactief **naar S/MIME** gaan in hun instellingen voor de webversie van Outlook om de downloadkoppeling voor het besturingselement op te halen.

## <a name="considerations-for-chrome"></a>Aandachtspunten voor Chrome

Als u S/MIME in de webversie van Outlook in de webbrowser Google Chrome wilt gebruiken, moet u (of een andere beheerder) het Chromium-beleid met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie te installeren in Chrome. De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Houd er rekening mee dat voor het toepassen van dit beleid computers zijn vereist die lid zijn van een domein. Voor het gebruik van S/MIME in Chrome hebt u dus computers nodig die aan een domein zijn toegevoegd.

Zie **ExtensionInstallForcelist** voor meer informatie over het beleid [ExtensionInstallForcelist.](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)

Deze stap is een vereiste voor het gebruik van Chrome. Het vervangt niet de S/MIME-besturing die door gebruikers is geïnstalleerd. Gebruikers wordt gevraagd om de S/MIME-besturing in de webversie van Outlook te downloaden en te installeren tijdens hun eerste gebruik van S/MIME. Gebruikers kunnen ook proactief **naar S/MIME** gaan in hun instellingen voor de webversie van Outlook om de downloadkoppeling voor het besturingselement op te halen.

## <a name="for-more-information"></a>Voor meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)
