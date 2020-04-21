---
title: Naamservers wijzigen om Microsoft in te stellen met Namecheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Lees uw aangepaste Microsoft-domein met Namecheap als u wilt dat Microsoft uw DNS-records beheert. '
ms.openlocfilehash: 6fdec37e837c74666ada82af81d43faaa0a6d589
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629777"
---
# <a name="change-nameservers-to-set-up-microsoft-with-namecheap"></a>Naamservers wijzigen om Microsoft in te stellen met Namecheap

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.
  
Volg deze instructies als u wilt dat Microsoft uw DNS-records voor u beheert. (Als u dat liever hebt, u [al uw Microsoft DNS-records beheren bij Namecheap](create-dns-records-at-namecheap.md).)
  
    
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie

1. Ga eerst naar de domeinenpagina bij Namecheap via [deze koppeling](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). U wordt gevraagd u aan te melden en verder te gaan.
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. Kies op de **bestemmingspagina** onder **Account**de optie **Lijst met domeinen** in de vervolgkeuzelijst. 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. Zoek op de pagina **Domeinlijst** de naam van het domein dat u wilt bewerken en selecteer **Beheren**.
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Selecteer **Geavanceerde DNS**.
    
    ![Namecheap-BP-Configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. Selecteer IN de sectie **HOST RECORDS** de optie NIEUWE **RECORD TOEVOEGEN**.
    
    ![Namecheap-BP-Configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. Selecteer in de vervolgkeuzelijst **Type** de optie **TXT Record**.
    
    > [!NOTE]
    > De vervolgkeuzelijst **Type** wordt automatisch weergegeven wanneer u **NIEUWE RECORD TOEVOEGEN selecteert.**
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    (Kies de **TTL-waarde** in de vervolgkeuzelijst.) 
    
|**Type**|**Host**|**Waarde**|**TTL**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de waarde van uw specifieke **bestemming of adrespunt** in de tabel.           [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)          |30 min  <br/> |
   
   ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. Selecteer het besturingselement **Wijzigingen opslaan** (vinkje). 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u om een zoekopdracht naar de record.
  
Wanneer Microsoft de juiste TXT-record vindt, wordt uw domein geverifieerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
    
  
3. Kies **Start setup** op de pagina **Setup**.
    
    
  
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
    
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen

Als u het instellen van uw domein met Microsoft wilt voltooien, wijzigt u de NS-records van uw domein bij uw domeinregistrar om naar de primaire en secundaire naamservers van Microsoft te wijzen. Hiermee wordt Microsoft ingesteld om de DNS-records van het domein voor u bij te werken. We voegen alle records toe zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein werken en u helemaal klaar bent.
  
> [!CAUTION]
> Wanneer u de NS-records van uw domein wijzigt om naar de Microsoft-naamservers te wijzen, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed. Alle e-mail die naar uw *your_domain* domein wordt verzonden (zoals rob@ your_domain.com) wordt bijvoorbeeld naar Microsoft verzonden nadat u deze wijziging hebt gewijzigd. 
  
> [!IMPORTANT]
>  Na het voltooien van de stappen in deze sectie, moeten  *alleen*  de volgende vier naamservers in de lijst staan: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de  *juiste*  naamservers toevoegt als deze niet al in de lijst staan. 
  
1. Ga eerst naar de domeinenpagina bij Namecheap via [deze koppeling](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). U wordt gevraagd u aan te melden en verder te gaan.
    
    ![Namecheap-BP-Configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. Kies op de **bestemmingspagina** onder **Account**de optie **Lijst met domeinen** in de vervolgkeuzelijst. 
    
    ![Namecheap-BP-Configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. Zoek op de pagina **Domeinlijst** de naam van het domein dat u wilt bewerken en selecteer **Beheren**.
    
    ![Namecheap-BP-Configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Selecteer **Domein**.
    
    ![Namecheap-BP-Redelegate-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. Ga naar de sectie **NAMESERVERS** en selecteer **Custom** in de vervolgkeuzelijst **Namecheap Default**. 
    
    ![Namecheap-BP-Redelegate-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. Afhankelijk van het feit of er al nameservers op de pagina staan die nu wordt weergegeven, gaat u verder met een van de twee volgende procedures.
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Als er nog GEEN naamservers worden vermeld
<a name="BKMK_ProcedureWithOUT"> </a>

1. Selecteer **NaamSERVER toevoegen** twee maal om twee nieuwe rijen toe te voegen.
    
    ![Afbeelding van het lint](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. Typ of kopieer en plak de waarden uit de volgende tabel in de **Nameserver**-vakken.
    
|||
|:-----|:-----|
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Afbeelding van het lint](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. Selecteer het besturingselement **Opslaan** (vinkje). 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Als er WEL naamservers worden vermeld

> [!CAUTION]
> Voer deze stappen  *alleen*  uit als u andere bestaande naamservers hebt dan de vier  *juiste*  naamservers. (Dat wil zeggen, verwijder  *alleen*  huidige naamservers die een  *andere*  naam hebben dan **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** of **ns4.bdm.microsoftonline.com**.) 
  
1. Als er andere naamservers in de **Nameserver**-vakken worden vermeld, verwijdert u elke vermelding door deze te selecteren en op de toets **Delete** op het toetsenbord te drukken. 
    
    ![Namecheap-BP-Redelegate-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. Selecteer **NaamSERVER toevoegen** twee maal om twee nieuwe rijen toe te voegen. 
    
    ![Afbeelding van het lint](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. Typ of kopieer en plak de waarden uit de volgende tabel in de **Nameserver**-vakken.
 
    
|||
|:-----|:-----|
|**Name Server 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Name Server 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Afbeelding van het lint](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. Selecteer het besturingselement **Opslaan** (vinkje). 
    
    ![Namecheap-BP-Redelegate-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken.
