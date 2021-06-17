---
title: Apparaten toewijzen aan een implementatiegroep
description: Opgeven in welke implementatiegroep apparaten moeten worden gebruikt
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 19465d2d2f077859490c106b9c01f08beb6e3906
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985573"
---
# <a name="assign-devices-to-a-deployment-group"></a>Apparaten toewijzen aan een implementatiegroep

Microsoft Managed Desktop wijst apparaten toe aan de verschillende implementatiegroepen, maar u kunt de groep opgeven of wijzigen die een apparaat aan een apparaat is toegewezen via de beheerportal. U wijzigt de opdracht nadat een apparaat is geregistreerd of nadat een gebruiker zich heeft geregistreerd.

> [!IMPORTANT]
> Als u de toewijzing wijzigt, worden beleidsregels die specifiek zijn voor die groep, toegepast op het apparaat. Met de wijziging wordt mogelijk de nieuwste versie van Windows 10 geïnstalleerd (inclusief nieuwe functies of kwaliteitsupdates). Het is het beste om eerst slechts een paar apparaten te verplaatsen en vervolgens de resulterende gebruikerservaring te controleren. Let op: met bepaalde updates wordt het apparaat opnieuw gestart. Controleer of u de juiste apparaten hebt geselecteerd om toe te wijzen. Het kan tot 24 uur duren voordat de opdracht van kracht wordt.

Als u apparaten wilt toewijzen aan een implementatiegroep, volgt u deze stappen. Als u afzonderlijke apparaten naar verschillende groepen wilt verplaatsen, herhaalt u deze stappen voor elke groep.

1. Selecteer Microsoft Endpoint Manager in **het linkerdeelvenster** apparaten. Selecteer in **Microsoft Managed Desktop** sectie **Apparaten**.
2. Selecteer de apparaten die u wilt toewijzen. Alle geselecteerde apparaten worden toegewezen aan de groep die u opgeeft.
3. Selecteer **Apparaatacties** in het menu.
4. Selecteer **Apparaat toewijzen aan groep**. Er wordt een fly-in geopend.
5. Gebruik de vervolgkeuzelijst om de groep te selecteren waar u apparaten naar wilt verplaatsen en selecteer **opslaan.** De **groep die is toegewezen door** wordt gewijzigd in In **behandeling.**

Wanneer de opdracht is **voltooid,** wordt de groep toegewezen door gewijzigd in  **Beheerder** (aangegeven dat u de wijziging hebt aangebracht) en wordt de nieuwe groepstoewijzing in de kolom Groep aangegeven.

> [!NOTE]
> U kunt apparaten niet naar andere groepen verplaatsen als ze zich in de registratietoestand 'fout' of 'in behandeling' hebben.
>
>Als een apparaat niet correct is verwijderd, kan de status 'gereed' worden weergeven. Als u een dergelijk apparaat verplaatst, is het mogelijk dat de move niet wordt voltooid. Als u Groep  niet ziet die door wijziging is toegewezen aan **In** behandeling in stap 5, controleert u of het apparaat beschikbaar is door te zoeken in Intune. Zie Apparaatgegevens in [Intune voor meer informatie.](/mem/intune/remote-actions/device-inventory)