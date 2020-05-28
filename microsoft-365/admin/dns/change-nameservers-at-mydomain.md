---
title: Naamservers wijzigen om Microsoft in te stellen met MyDomain
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Meer informatie over hoe u Microsoft instellen voor het beheren van de DNS-records van uw aangepaste domein op MyDomain.
ms.openlocfilehash: d8fc61c3adbe8b5b865bd82b8c4e0944198921e7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400627"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a>Naamservers wijzigen om Microsoft in te stellen met MyDomain

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.
  
Volg deze instructies als u wilt dat Microsoft uw DNS-records voor u beheert. (Als u dat liever hebt, u [al uw Microsoft DNS-records beheren bij MyDomain](create-dns-records-at-mydomain.md).)
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.
    
2. Kies in de sectie **Mijn favorieten** de optie **Domain Central**.
    
3. Kies onder **Domein** de naam van het domein dat u wilt bewerken.
    
4. Kies in de rij **Overzicht** de optie **DNS**.
    
5. Kies in de vervolgkeuzelijst **Wijzigen** de optie **TXT/SPF-record**.
    
6. Typ of kopieer en plak de waarden uit de volgende tabel in het vak voor de nieuwe record onder **Content**.
    
||
|:-----|
|**Content** <br/> |
|MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Kies **Toevoegen**.
    
8. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Microsoft 365 en vraagt u of Microsoft 365 naar de record wil zoeken.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen

Als u het instellen van uw domein met Microsoft wilt voltooien, wijzigt u de NS-records van uw domein bij uw domeinregistrar om naar de primaire en secundaire naamservers van Microsoft te wijzen. Hiermee wordt Microsoft ingesteld om de DNS-records van het domein voor u bij te werken. We voegen alle records toe zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein werken en u helemaal klaar bent.
  
> [!CAUTION]
> Wanneer u de NS-records van uw domein wijzigt om naar de Microsoft-naamservers te wijzen, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed. Bijvoorbeeld alle e-mail die naar uw domein wordt verzonden (zoals rob@ *your_domain.* com) zal beginnen te komen naar Microsoft nadat u deze wijziging. 
  
> [!IMPORTANT]
> In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan.<br/> Wanneer u de stappen in deze sectie hebt voltooid, zijn de enige nameservers die moeten worden vermeld:
  
1. Ga eerst naar de pagina met domeinen bij MyDomain via [deze koppeling](https://www.mydomain.com/controlpanel). U wordt gevraagd u eerst aan te melden.
    
2. Kies in de sectie **Mijn favorieten** de optie **Domain Central**.
    
3. Kies onder **Domein** de naam van het domein dat u wilt bewerken.
    
4. Selecteer **naamservers**in de rij **Overzicht** .
    
    ![Afbeelding van het lint](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. Selecteer in de sectie **Update Name Servers** de optie **Use different name servers**.
    
    ![Afbeelding van het lint](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. Afhankelijk van het feit of er al nameservers op de pagina staan die nu wordt weergegeven, gaat u verder met een van de twee volgende procedures.
    
### <a name="if-the-correct-nameservers-are-already-listed"></a>Als de correcte naamservers WEL worden vermeld

- Als de correcte naamservers al worden vermeld, kunt u deze stap overslaan.
    
    ![Afbeelding van het lint](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a>Als de correcte naamservers NIET worden vermeld

> [!CAUTION]
> Volg deze stappen alleen als u bestaande naamservers hebt, andere dan de vier juiste naamservers. (Dat wil zeggen, alleen huidige naamservers verwijderen die *geen* naam hebben **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com**of **ns4.bdm.microsoftonline.com**.) 
  
1. Verwijder de bestaande naamservers door elke vermelding te selecteren in het veld **Nameserver 1:** en vervolgens op de toets **Delete** op het toetsenbord te drukken. 
    
    ![Afbeelding van het lint](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. Selecteer Twee maal **meer toevoegen** om twee nieuwe naamserverrijen toe te voegen. 
    
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
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken. 
