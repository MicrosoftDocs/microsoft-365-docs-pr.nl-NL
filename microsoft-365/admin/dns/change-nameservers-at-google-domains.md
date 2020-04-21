---
title: Naamservers wijzigen om Microsoft in te stellen met Google Domains
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Meer informatie over hoe u Microsoft instellen voor het beheren van de DNS-records van uw aangepaste domein bij Google Domains.
ms.openlocfilehash: ac2f98a6ff783917d88a2bd8d28e8242e0ba41a8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629897"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a>Naamservers wijzigen om Microsoft in te stellen met Google Domains

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Volg deze instructies als u wilt dat Microsoft uw DNS-records voor u beheert. (Als u dat liever hebt, u [al uw DNS-records beheren bij Google Domains](create-dns-records-at-google-domains.md).)
  
    
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie

Voordat u uw domein bij Microsoft gebruikt, moeten we ervoor zorgen dat u eigenaar bent. Uw mogelijkheid om in te loggen op uw account bij uw domeinregistrar en de DNS-record te maken bewijst microsoft dat u eigenaar bent van het domein.
  
> [!NOTE]
>  Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Om aan de slag te gaan, ga je naar je domeinenpagina bij Google Domains via [deze link.](https://domains.google.com/registrar) U wordt gevraagd om u aan te melden. U gaat hiervoor als volgt te werk:
    
1. Selecteer **Aanmelden**.
    
2. Voer uw inloggegevens **in**en selecteer Opnieuw Aanmelden .
    
2. Selecteer **op** de pagina Domeinen in de sectie **Domein** de optie **DNS configureren** voor het domein dat u wilt bewerken. 
    
3. Typ of kopieer en plak de waarden uit de volgende tabel in de sectie **Custom resource records** in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**Type** <br/> |**TTL** <br/> |**Data** <br/> |
|@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX* <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. Kies **Toevoegen**.
    
5. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u om een zoekopdracht naar de record.
  
Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.
  
1. Ga in het Microsoft-beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Instellingendomeinen.</a> **Settings**

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Zie Problemen zoeken en oplossen na het toevoegen van [uw domein- of DNS-records](../get-help-with-domains/find-and-fix-issues.md)als u problemen ondervindt met e-mailstroom of andere problemen na het toevoegen van DNS-records. 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen

Als u het instellen van uw domein met Microsoft wilt voltooien, wijzigt u de NS-records van uw domein bij uw domeinregistrar om naar de primaire en secundaire naamservers van Microsoft te wijzen. Hiermee wordt Microsoft ingesteld om de DNS-records van het domein voor u bij te werken. We voegen alle records toe zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein werken en u helemaal klaar bent.
  
> [!CAUTION]
> Wanneer u de NS-records van uw domein wijzigt om naar de Microsoft-naamservers te wijzen, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed. Bijvoorbeeld alle e-mail die naar uw domein wordt verzonden (zoals rob@ *your_domain.*  com) zal beginnen te komen naar Microsoft nadat u deze wijziging. 
  
> [!IMPORTANT]
> In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan. > Na het voltooien van de stappen in deze sectie, moeten alleen de volgende vier naamservers in de lijst staan: 
  
1. Ga eerst naar de pagina met domeinen bij Google Domains via [deze koppeling](https://domains.google.com/registrar). U wordt gevraagd om u aan te melden. U gaat hiervoor als volgt te werk:
    
1. Selecteer **Aanmelden**.
    
2. Voer uw inloggegevens in en selecteer **Opnieuw Aanmelden**.
    
2. Selecteer **op** de pagina Domeinen in de sectie **Domein** de optie **DNS configureren** voor het domein dat u wilt bewerken. 
    
3. Selecteer op de pagina **Domains** in de sectie **Name servers** de optie **Use custom name servers**.
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. Afhankelijk van of er al naamservers worden vermeld op de pagina die wordt weergegeven, gaat u op een van de volgende twee manieren verder:
    
  - Als er nog **GEEN** naamservers worden vermeld, [Als er nog GEEN naamservers worden vermeld](#if-there-are-no-nameservers-already-listed).
    
  - Als er **WEL** naamservers worden vermeld, [Als er WEL naamservers worden vermeld](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Als er nog GEEN naamservers worden vermeld

1. Voeg de eerste naamserver toe.
    
    In de sectie **Name servers** typt of kopieert en plakt u in het vak **NAME SERVER** de eerste waarde uit de volgende tabel. 
    
|||
|:-----|:-----|
|**First name server** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Second name server** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Derde naamserver** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Vierde naamserver** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Afbeelding van het lint](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. Selecteer het **besturingselement + (toevoegen)** om een lege rij te maken. 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. De andere drie naamserverrecords toevoegen.
    
    Maak in de sectie **Aangepaste naamservers gebruiken** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens het **besturingselement + (toevoegen)** om een andere rij toe te voegen. 
    
    Herhaal deze procedure totdat u alle vier de naamserverrecords hebt gemaakt.
    
4. Kies **Opslaan**.
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Als er WEL naamservers worden vermeld

1. Als er andere naamservers worden vermeld, selecteert u **Bewerken**.
    
    > [!CAUTION]
    > Volg deze stappen alleen als u bestaande naamservers hebt, andere dan de vier juiste naamservers. (Dat wil zeggen, alleen huidige naamservers verwijderen die *geen* naam hebben **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com**of **ns4.bdm.microsoftonline.com**.) 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. Verwijder vervolgens elk item door het te selecteren en op de toets **Delete** op het toetsenbord te drukken. 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. In de sectie **Name servers** typt of kopieert en plakt u de waarden uit de volgende tabel in de rijen **NAME SERVER**. 
    
|||
|:-----|:-----|
|**First name server** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Second name server** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Derde naamserver** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Vierde naamserver** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Afbeelding van het lint](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. Selecteer het besturingselement **+(toevoegen)** om een lege rij te maken. 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. Voer de andere twee naamserverrecords toe.
    
    Maak in de sectie **Aangepaste naamservers gebruiken** een record met de waarden uit de volgende rij in de tabel en selecteer vervolgens het besturingselement **+(toevoegen)** om een andere rij toe te voegen. 
    
    Herhaal deze procedure totdat u alle vier de naamserverrecords hebt gemaakt.
    
6. Kies **Opslaan**.
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken. 
  
