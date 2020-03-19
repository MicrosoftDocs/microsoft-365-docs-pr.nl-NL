---
title: Naamservers wijzigen voor het instellen van Office 365 bij MyDomain
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Meer informatie over hoe u Office 365 instellen om de DNS-records van uw aangepaste domein te beheren op MyDomain.
ms.openlocfilehash: 90f1469bdf2f281be14e2a9e15a9fe7ac4a8cbee
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42809944"
---
# <a name="change-nameservers-to-set-up-office-365-with-mydomain"></a>Naamservers wijzigen voor het instellen van Office 365 bij MyDomain

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.
  
Volg deze instructies als u wilt dat Office 365 uw DNS-records voor Office 365 voor u beheert. (Als u wilt, kunt u [al uw DNS-records voor Office 365 bij MyDomain beheren](create-dns-records-at-mydomain.md).)
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie

Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer In de sectie **Mijn favorieten** de optie **Domein Centraal**.
    
3. Selecteer onder **Domein**de naam van het domein dat u wilt bewerken.
    
4. Selecteer **DNS**in de rij **Overzicht.**
    
5. Kies in de vervolgkeuzelijst **Modify** de optie **TXT/SPF Record**.
    
6. Typ of kopieer en plak de waarden uit de volgende tabel in het vak voor de nieuwe record onder **Content**.
    
||
|:-----|
|**Content** <br/> |
|MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Selecteer **Toevoegen**.
    
8. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.
  
Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**

    
2. Selecteer op de pagina **Domeinen** het domein dat u verifieert. 
    
3. Selecteer op de pagina **Setup** de optie **Startsetup**.
    
4. Selecteer op de pagina **Domein verifiëren** de optie **Verifiëren**.
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen

U voltooit het instellen van uw domein met Office 365 door de NS-records van uw domein bij uw domeinregistrar te wijzigen, zodat deze verwijzen naar de primaire en secundaire naamservers van Office 365. Hiermee wordt Office 365 zo ingesteld dat de DNS-records van het domein voor u worden bijgewerkt. Alle benodigde records worden toegevoegd zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein kunnen werken. Daarna bent u klaar.
  
> [!CAUTION]
> Als u de NS-records van uw domein laat verwijzen naar de naamservers van Office 365, is dit van invloed op alle services die momenteel aan uw domein zijn gekoppeld. Bijvoorbeeld alle e-mail die naar uw domein wordt verzonden (zoals rob@ *your_domain.* com) zal beginnen te komen naar Office 365 nadat u deze wijziging. 
  
> [!IMPORTANT]
> In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan.<br/> Wanneer u de stappen in deze sectie hebt voltooid, zijn de enige nameservers die moeten worden vermeld, de volgende vier:
  
1. Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer In de sectie **Mijn favorieten** de optie **Domein Centraal**.
    
3. Selecteer onder **Domein**de naam van het domein dat u wilt bewerken.
    
4. Selecteer **Nameservers**in de rij **Overzicht.**
    
    ![Afbeelding van het lint](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. Selecteer in de sectie **Update Name Servers** de optie **Use different name servers**.
    
    ![Afbeelding van het lint](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. Afhankelijk van of er al nameservers op de pagina staan die nu worden weergegeven, ga je verder naar een van de twee volgende procedures.
    
### <a name="if-the-correct-nameservers-are-already-listed"></a>Als de correcte naamservers WEL worden vermeld

- Als de correcte naamservers al worden vermeld, kunt u deze stap overslaan.
    
    ![Afbeelding van het lint](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a>Als de correcte naamservers NIET worden vermeld

> [!CAUTION]
> Volg deze stappen alleen als u bestaande naamservers hebt, anders dan de vier juiste naamservers. (Dat wil zeggen, verwijder alleen de huidige naamservers die *niet* **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**of **ns4.bdm.microsoftonline.com**.) 
  
1. Verwijder de bestaande naamservers door elke vermelding te selecteren in het veld **Nameserver 1:** en vervolgens op de toets **Delete** op het toetsenbord te drukken. 
    
    ![Afbeelding van het lint](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. Selecteer Twee keer **meer toevoegen** om twee nieuwe nameserverrijen toe te voegen. 
    
    ![Afbeelding van het lint](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. Typ of kopieer en plak de naamserverwaarden uit de volgende tabel in de vakken voor de records.
    
|||
|:-----|:-----|
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Afbeelding van het lint](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. Kies **Opslaan**.
    
    ![Afbeelding van het lint](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein. 
