---
title: Niet-Microsoft 365 in een revisieset laden
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Meer informatie over het importeren van niet-Microsoft 365 gegevens in een revisieset voor analyse in Advanced eDiscovery geval.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161757"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>Niet-Microsoft 365 in een revisieset laden

Niet alle documenten die u moet analyseren in Advanced eDiscovery bevinden zich in Microsoft 365. Met de functie Microsoft 365 gegevens importeren in Advanced eDiscovery, kunt u documenten die zich niet in Microsoft 365 bevinden, uploaden naar een revisieset. In dit artikel wordt beschreven hoe u uw niet-Microsoft 365 documenten kunt Advanced eDiscovery voor analyse.

## <a name="requirements-to-upload-non-office-365-content"></a>Vereisten voor het uploaden van niet-Office 365 inhoud

Voor het gebruik van de functie Microsoft 365 uploaden die in dit artikel wordt beschreven, moet u het volgende hebben:

- Aan alle bewaarders die u niet-Microsoft 365 wilt koppelen, moet de juiste licentie worden toegewezen. Zie Aan de slag [met Advanced eDiscovery.](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)

- Een bestaand Advanced eDiscovery geval.

- Bewaarders moeten aan de zaak worden toegevoegd voordat u de niet-Microsoft 365 gegevens kunt uploaden en eraan kunt koppelen.

- Niet-Microsoft 365 gegevens moeten een bestandstype zijn dat wordt ondersteund door Advanced eDiscovery. Zie Ondersteunde [bestandstypen in Advanced eDiscovery.](supported-filetypes-ediscovery20.md)

- Alle bestanden die naar een revisieset worden geüpload, moeten zich bevinden in mappen, waar elke map is gekoppeld aan een specifieke bewaarder. De namen voor deze mappen moeten de volgende naamgevingsindeling gebruiken: *alias@domainname.* De alias@domainname moet de alias en het domein van Microsoft 365 gebruiker zijn. U kunt alle mappen alias@domainname in een hoofdmap verzamelen. De hoofdmap kan alleen de alias@domainname bevatten. Losse bestanden in de hoofdmap worden niet ondersteund.

   De mapstructuur voor de niet-Microsoft 365 gegevens die u wilt uploaden, lijkt op het volgende voorbeeld:

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   Waar abraham.mcmahon@contoso.com, jewell.gordon@contoso.com en staci.gonzalez@contoso.com de SMTP-adressen van bewaarders in de zaak zijn.

   ![Mapstructuur voor niet-Microsoft 365 gegevens uploaden](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- Een account dat is toegewezen aan de rollengroep eDiscovery Manager (en is toegevoegd als eDiscovery-beheerder).

- Het hulpprogramma AzCopy v8.1 is geïnstalleerd op een computer die toegang heeft tot de niet-Microsoft 365 inhoudsmapstructuur. Zie Gegevens overbrengen met de [AzCopy v8.1](/previous-versions/azure/storage/storage-use-azcopy)op Windows . Installeer AzCopy op de standaardlocatie, **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.** U moet AzCopy v8.1 gebruiken. Andere versies van AzCopy werken mogelijk niet bij het laden van niet-Microsoft 365 gegevens in Advanced eDiscovery.


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>Upload niet-Microsoft 365 inhoud in Advanced eDiscovery

1. Als eDiscovery Manager of eDiscovery-beheerder opent u Advanced eDiscovery en gaat u naar het geval dat de niet-Microsoft 365 gegevens worden geüpload naar.  

2. Klik **op Revisiesets** en selecteer vervolgens de revisieset om de niet-Microsoft 365 te uploaden.  Als u geen revisieset hebt, kunt u er een maken. 
 
3. Klik in de revisieset op **Controleset beheren** en klik vervolgens op **Uploads weergeven** op de **tegel Niet-Microsoft 365 gegevens.**

4. Klik **Upload om** de wizard Gegevens importeren te starten.

   ![Upload bestanden](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   De eerste stap in de wizard bereidt een beveiligde door Microsoft verstrekte Azure Storage voor om de bestanden te uploaden naar.  Wanneer de voorbereiding is voltooid, wordt de **knop Volgende: Upload bestanden** actief.

   ![Niet-Microsoft 365 importeren: Voorbereiden](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. Klik **op Volgende: Upload bestanden.**

6. Ga op **Upload pagina bestanden** als volgt te werk:

   ![Niet-Microsoft 365 importeren: Upload bestanden](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. Controleer  of typ in het vak Pad naar locatie van bestanden de locatie van de hoofdmap waar u de niet-Microsoft 365 gegevens hebt opgeslagen die u wilt uploaden. Voor de locatie van de voorbeeldbestanden die worden weergegeven in de sectie Voordat u **begint,** typt u **bijvoorbeeld %USERPROFILE\Downloads\nonO365.** Als u de juiste locatie geeft, zorgt u ervoor dat de opdracht AzCopy die in het vak onder het pad wordt weergegeven, correct wordt bijgewerkt.

   b. Klik **op Kopiëren naar klembord** om de opdracht te kopiëren die in het vak wordt weergegeven.

7. Start een Windows opdrachtprompt, plak de opdracht die u hebt gekopieerd in de vorige stap en druk vervolgens op **Enter** om de opdracht AzCopy te starten.  Nadat u de opdracht hebt start, worden de niet-Microsoft 365 geüpload naar de Azure Storage locatie die is voorbereid in stap 4.

   ![Niet-Microsoft 365 importeren: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > Zoals eerder vermeld, moet u AzCopy v8.1 gebruiken om de opdracht te kunnen gebruiken die is opgegeven op de pagina Upload **bestanden.** Als de opgegeven Opdracht AzCopy mislukt, raadpleegt u [AzCopy](troubleshooting-azcopy.md)oplossen in Advanced eDiscovery.

8. Ga terug naar het beveiligings- & compliancecentrum en klik op **Volgende: Bestanden** verwerken in de wizard.  Hiermee start u de verwerking, tekstextractie en indexering van de niet-Microsoft 365 bestanden die zijn geüpload naar de Azure Storage locatie.  

9. Volg de voortgang van het  verwerken van de  bestanden op de pagina Bestanden verwerken of op het tabblad Taken door een taak met de naam Niet-Microsoft 365 toevoegen aan **een revisieset weer te geven.**  Nadat de taak is voltooid, zijn de nieuwe bestanden beschikbaar in de revisieset.

   ![Niet-Microsoft 365 importeren: Bestanden verwerken](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. Nadat de verwerking is voltooid, kunt u de wizard sluiten.