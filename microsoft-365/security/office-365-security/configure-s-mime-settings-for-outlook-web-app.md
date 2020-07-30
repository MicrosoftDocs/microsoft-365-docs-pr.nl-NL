---
title: S/MIME-instellingen configureren - Exchange Online voor Outlook in de webversie
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Een korte beschrijving van wat Exchange Online-beheerders moeten doen om de S/MIME-instellingen in de webversie van Outlook in Exchange Online weer te geven en te configureren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b9f4e6c33369640ad66956568959dd02b01c4fb9
ms.sourcegitcommit: df59c83174d845b8ddec48b9be2659fbfb58bb7f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46517483"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>S/MIME-instellingen configureren in de webversie van Exchange Online voor Outlook

Als beheerder van Exchange Online u de webversie van Outlook (voorheen Outlook Web App) instellen om het verzenden en ontvangen van door S/MIME beveiligde berichten toe te staan. Gebruik de **cmdlets Get-SmimeConfig** en **Set-SmimeConfig** om deze functie in Exchange Online PowerShell te bekijken en te beheren. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

Zie [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) en [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)voor gedetailleerde syntaxis- en parameterinformatie .

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Overwegingen voor nieuwe Microsoft Edge (op chromium gebaseerd)

Als u S/MIME wilt gebruiken in de webversie van Outlook in de nieuwe [Microsoft Edge-webbrowser,](https://www.microsoft.com/windows/microsoft-edge) moet u (of een andere beheerder) het Microsoft Edge-browserbeleid met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie in de nieuwe Microsoft Edge te installeren. De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . En houd er rekening mee dat voor het toepassen van dit beleid apparaten die lid zijn van domeinen of azure ad-joined, vereist het gebruik van S/MIME in de nieuwe Microsoft Edge-browser effectief apparaten met een domein of met Azure AD.

Zie ExtensionInstallForcelist voor meer informatie over het beleid **voor ExtensieinstallForcelist** . [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)

Deze stap is een voorwaarde voor het gebruik van nieuwe Microsoft Edge; het vervangt niet de S / MIME-besturingselement dat is geïnstalleerd door gebruikers. Gebruikers wordt gevraagd om het S/MIME-besturingselement in Outlook op het web te downloaden en te installeren tijdens hun eerste gebruik van S/MIME. Of gebruikers kunnen proactief naar **S/MIME** gaan in hun Web-instellingen van Outlook op om de downloadkoppeling voor het besturingselement te krijgen.

## <a name="considerations-for-chrome"></a>Overwegingen voor Chrome

Als u S/MIME wilt gebruiken in de webversie van Outlook in de Webbrowser Google Chrome, moet u (of een andere beheerder) het Chromium-beleid met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie in Chrome te installeren. De beleidswaarde is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . En houd er rekening mee dat voor het toepassen van dit beleid computers die zijn samengevoegd, vereist het gebruik van S/MIME in Chrome effectief computers die zijn samengevoegd met een domein.

Zie ExtensionInstallForcelist voor meer informatie over het beleid **voor ExtensieinstallForcelist** . [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)

Deze stap is een voorwaarde voor het gebruik van Chrome; het vervangt niet de S / MIME-besturingselement dat is geïnstalleerd door gebruikers. Gebruikers wordt gevraagd om het S/MIME-besturingselement in Outlook op het web te downloaden en te installeren tijdens hun eerste gebruik van S/MIME. Of gebruikers kunnen proactief naar **S/MIME** gaan in hun Web-instellingen van Outlook op om de downloadkoppeling voor het besturingselement te krijgen.

## <a name="for-more-information"></a>Voor meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)
