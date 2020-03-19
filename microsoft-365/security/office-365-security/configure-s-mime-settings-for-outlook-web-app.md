---
title: S/MIME-instellingen configureren in Exchange Online voor de webversie van Outlook
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
description: Een korte beschrijving van wat Exchange Online-beheerders moeten doen om de S/MIME-instellingen in de webversie van Outlook in Exchange Online te bekijken en configureren.
ms.openlocfilehash: 354b247c2b0e0e610e6cb0626f4a404b582db717
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2020
ms.locfileid: "42809527"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>S/MIME-instellingen configureren in Exchange Online voor de webversie van Outlook

Als beheerder van Exchange Online u Outlook op internet (voorheen Outlook Web App) instellen om het verzenden en ontvangen van door S/MIME beveiligde berichten mogelijk te maken. Gebruik de **cmdlets Get-SmimeConfig** en **Set-SmimeConfig** om deze functie te bekijken en te beheren in Exchange Online PowerShell. Zie Verbinding maken met [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)als u verbinding wilt maken met Exchange Online PowerShell.

Zie [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) en [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Overwegingen voor nieuwe Microsoft Edge (Chromium-gebaseerd)

Als u S/MIME wilt gebruiken in de webversie van Outlook in de nieuwe [Microsoft Edge-webbrowser,](https://www.microsoft.com/windows/microsoft-edge) moet u (of een andere beheerder) het Microsoft Edge-browserbeleid met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie in de nieuwe Microsoft Edge te installeren. De beleidswaarde `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`is . En houd er rekening mee dat voor het toepassen van dit beleid computers die bij het domein zijn aangesloten, vereist dat voor het gebruik van S/MIME in de nieuwe Microsoft Edge-browser, effectief computers die bij het domein zijn aangesloten, worden gebruikt.

Zie [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)voor meer informatie over het **extensieinstallForcelist-beleid.**

Deze stap is een voorwaarde voor het gebruik van nieuwe Microsoft Edge; het vervangt niet het S/MIME-besturingselement dat door gebruikers is geïnstalleerd. Gebruikers worden gevraagd om het S/MIME-besturingselement in het web van Outlook te downloaden en te installeren tijdens hun eerste gebruik van S/MIME. Of gebruikers kunnen proactief naar **S/MIME** gaan in hun Outlook op de webinstellingen om de downloadkoppeling voor het besturingselement te krijgen.

## <a name="considerations-for-chrome"></a>Overwegingen voor Chrome

Als u S/MIME wilt gebruiken in de webversie van Outlook in de Webbrowser Google Chrome, moet u (of een andere beheerder) het Chromium-beleid met de naam **ExtensionInstallForcelist** instellen en configureren om de Microsoft S/MIME-extensie in Chrome te installeren. De beleidswaarde `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`is . En houd er rekening mee dat het toepassen van dit beleid vereist domein-verbonden computers, dus het gebruik van S / MIME in Chrome effectief vereist domein-aangesloten computers.

Zie [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)voor meer informatie over het **extensieinstallForcelist-beleid.**

Deze stap is een voorwaarde voor het gebruik van Chrome; het vervangt niet het S/MIME-besturingselement dat door gebruikers is geïnstalleerd. Gebruikers worden gevraagd om het S/MIME-besturingselement in het web van Outlook te downloaden en te installeren tijdens hun eerste gebruik van S/MIME. Of gebruikers kunnen proactief naar **S/MIME** gaan in hun Outlook op de webinstellingen om de downloadkoppeling voor het besturingselement te krijgen.

## <a name="for-more-information"></a>Voor meer informatie

[S/MIME voor het ondertekenen en versleutelen van berichten](s-mime-for-message-signing-and-encryption.md)
