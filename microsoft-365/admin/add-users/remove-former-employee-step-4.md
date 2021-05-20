---
title: 'Stap 4: een andere werknemer toegang geven tot OneDrive en Outlook gegevens'
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Volg de stappen in dit artikel om een andere werknemer toegang te geven tot de OneDrive en Outlook werknemers.
ms.openlocfilehash: cb5c27cbc7f1c184af8f0d1ad32b822660e93791
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582690"
---
# <a name="step-4---give-another-employee-access-to-onedrive-and-outlook-data"></a>Stap 4: een andere werknemer toegang geven tot OneDrive en Outlook gegevens

Wanneer een werknemer uw organisatie verlaat, wilt u toegang krijgen tot de OneDrive en Outlook gegevens, een back-up maken en kiezen of u deze aan een andere werknemer wilt geven.
  
## <a name="access-a-former-users-onedrive-documents"></a>De documenten van een voormalige gebruiker OneDrive openen

Als u de licentie van een gebruiker verwijdert, maar het account niet verwijdert, kunt u uzelf toegang geven tot de inhoud in de OneDrive. Als u het account van de gebruiker verwijdert, hebt u standaard 30 dagen de tijd om toegang te krijgen tot de gegevens van OneDrive gebruiker. [Meer informatie over het instellen van de OneDrive voor verwijderde gebruikers.](/onedrive/set-retention) Als u een [gebruikersaccount niet binnen deze](/office365/admin/add-users/restore-user) tijd herstelt, wordt de OneDrive verwijderd.

Als u de bestanden van een voormalige gebruiker OneDrive wilt behouden, geeft u uzelf eerst toegang tot hun OneDrive en verplaatst u vervolgens de bestanden die u wilt bewaren.

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.  

2. Selecteer een gebruiker.

3. Selecteer in het **rechterdeelvenster OneDrive.** Selecteer **onder Toegang tot bestanden krijgen** de optie Koppeling maken naar **bestanden.**

4. Selecteer de koppeling om de bestandslocatie te openen. Download de bestanden naar uw computer of selecteer **Verplaatsen** naar of Kopiëren **om** ze te verplaatsen of te kopiëren naar uw eigen OneDrive of naar een gedeelde bibliotheek.

> [!NOTE]
> U kunt maximaal 500 MB aan bestanden en mappen tegelijk verplaatsen of kopiëren.<br/>
> Wanneer u documenten met versiegeschiedenis verplaatst of kopieert, wordt alleen de nieuwste versie verplaatst.  

### <a name="revoke-admin-access-to-a-users-onedrive"></a>Beheerderstoegang tot de gebruikersaccounts intrekken OneDrive

U kunt uzelf toegang geven tot de inhoud in de OneDrive van een gebruiker, maar mogelijk wilt u uw toegang verwijderen wanneer u deze niet meer nodig hebt.

1. Meld u aan bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">het beheercentrum</a> als globale beheerder of SharePoint beheerder.

    Als u een bericht krijgt dat u geen toegang hebt tot het beheercentrum, hebt u geen beheerdersmachtigingen in uw organisatie.

2. Selecteer beheercentra in  het \> **linkerdeelvenster SharePoint.** (Mogelijk moet u Alles tonen **selecteren om** de lijst met beheercentra weer te geven.)

3. Als het klassieke SharePoint wordt weergegeven,  selecteert u Nu openen boven aan de pagina om het SharePoint openen.

4. Selecteer meer functies in **het linkerdeelvenster.**

5. Selecteer **onder Gebruikersprofielen** de optie **Openen.**

6. Selecteer **onder Personen** de optie **Gebruikersprofielen beheren.**

7. Voer de naam van de gebruiker in en selecteer **Zoeken**.

8. Klik met de rechtermuisknop op de gebruiker en kies **siteverzamelingseigenaren beheren.**

9. Verwijder de persoon die geen toegang meer nodig heeft tot de gegevens van de gebruiker en selecteer **OK.**

## <a name="access-the-outlook-data-of-a-former-user"></a>Toegang tot Outlook gegevens van een voormalige gebruiker

Als u de e-mailberichten, agenda, taken en contactpersonen van de voormalige werknemer wilt behouden, exporteert u de gegevens naar een Outlook-gegevensbestand (.pst).
  
1. [Voeg de e-mail van](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) de voormalige werknemer toe aan uw Outlook (Als u het wachtwoord van de gebruiker opnieuw in [stelt,](reset-passwords.md)kunt u het instellen op iets dat alleen u kent.)

2. Selecteer Outlook **bestand**.

    ![Zo ziet het lint eruit in Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. Selecteer **Exporteren &amp; openen** \> **Import/Export**.

    ![De opdracht Importeren/exporteren in de weergave Backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. Selecteer **Exporteren naar een bestand** en selecteer vervolgens **Volgende**.

    ![De optie Exporteren naar bestand in de wizard Importeren en exporteren](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. Selecteer **Outlook Gegevensbestand (.pst)** en selecteer vervolgens **Volgende**.

6. Selecteer het account dat u wilt exporteren door de naam of het e-mailadres te selecteren, zoals Postvak - Anne Weiler of anne@contoso.com. Als u alles in het account wilt exporteren, inclusief e-mail, de agenda, contactpersonen, taken en notities, moet het selectievakje **Inclusief submappen** zijn ingeschakeld.

    > [!NOTE]
    > U kunt slechts één account tegelijkertijd exporteren. Als u meerdere accounts wilt exporteren, herhaalt u deze stappen voor de volgende accounts.
  
    ![Het dialoogvenster Outlook-gegevensbestand exporteren met de bovenste map geselecteerd en Inclusief submappen ingeschakeld](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. Selecteer **Volgende**.

8. Selecteer **Bladeren** om te selecteren waar u het Outlook gegevensbestand (.pst) wilt opslaan. Typ een  *bestandsnaam* en selecteer **OK om door** te gaan.

    > [!NOTE]
    > Als u de exportfunctie eerder hebt gebruikt, worden de vorige maplocatie en bestandsnaam weergegeven. Typ een *andere bestandsnaam voordat* u **OK selecteert.**
  
9. Als u naar een bestaand Outlook-gegevensbestand (.pst) exporteert, geeft u onder **Opties** aan wat er moet gebeuren wanneer items worden geëxporteerd die al in het bestand bestaan.

10. Klik op **Voltooien**.

De export wordt direct gestart in Outlook, tenzij er een nieuw Outlook-gegevensbestand (.pst) wordt gemaakt of een bestand wordt gebruikt dat met een wachtwoord is beveiligd.
  
- Als u een Outlook-gegevensbestand (.pst) maakt, kunt u het bestand desgewenst met een wachtwoord beveiligen. Wanneer het **dialoogvenster Outlook gegevensbestand** maken wordt weergegeven, typt  u het wachtwoord *in* de vakken Wachtwoord en Wachtwoord verifiëren en selecteert u  **OK.** Typ in **Outlook dialoogvenster Wachtwoord voor** gegevensbestand het *wachtwoord* en selecteer **OK.**

- Als u exporteert naar een bestaand Outlook-gegevensbestand (.pst) dat met een wachtwoord is beveiligd, typt u in het dialoogvenster Wachtwoord voor gegevensbestand **Outlook** het wachtwoord *en* selecteert u **OK**.

Bekijk hoe u [e-mail,](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) contactpersonen en agenda exporteert of back-upt naar Outlook PST-bestand in Outlook 2010.

  > [!NOTE]
  > Standaard is uw e-mail offline beschikbaar voor een periode van 12 maanden. Zie indien nodig hoe u de offline beschikbare [gegevens kunt vergroten.](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)

### <a name="give-another-user-access-to-a-former-users-email"></a>Een andere gebruiker toegang geven tot e-mail van een voormalige gebruiker

Als u toegang wilt geven tot de e-mailberichten, agenda, taken en contactpersonen van de voormalige werknemer aan een andere werknemer, importeert u de gegevens in het postvak OUTLOOK van een andere werknemer.

> [!NOTE]
> U kunt ook [het postvak van](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) de voormalige gebruiker converteren naar een gedeeld postvak of het e-mailbericht van een voormalige werknemer doorsturen naar een andere [werknemer.](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)

1. Ga Outlook naar **Exportbestand** \> **openen &amp;** \> Import/Export.

    Hiermee wordt de wizard Importeren en exporteren gestart.

2. Selecteer **Importeren uit een ander programma of bestand** en selecteer vervolgens **Volgende.**

    ![Wizard Importeren en exporteren](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. Selecteer **Outlook Gegevensbestand (.pst)** en selecteer **Volgende**.

4. Blader naar het PST-bestand dat u wilt importeren.

5. Kies onder **Opties** hoe u dubbele contactpersonen wilt verwerken.

6. Selecteer **Volgende**.

7. Als een wachtwoord is toegewezen aan het Outlook (.pst), voert u het wachtwoord in en selecteert u **OK.**

8. Stel de opties voor het importeren van items in. De standaardinstellingen hoeft u meestal niet te wijzigen.

9. Klik op **Voltooien**.

> [!NOTE]
> De stappen blijven hetzelfde voor het openen van de OneDrive en e-mailgegevens van een bestaande gebruiker.

> [!TIP]
> Als u slechts een paar items uit een Outlook gegevensbestand (.pst) wilt importeren of herstellen, kunt u het Outlook gegevensbestand openen. Sleep vervolgens in het navigatiedeelvenster de items van Outlook mappen met gegevensbestand naar uw bestaande Outlook mappen. 

## <a name="related-content"></a>Verwante inhoud

[Beheerders toevoegen en verwijderen op een OneDrive account](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive) (artikel)

[Een verwijderde OneDrive](/onedrive/restore-deleted-onedrive) herstellen (artikel)
  
[OneDrive bewaren en verwijderen](/onedrive/retention-and-deletion) (artikel)
