---
title: Naamservers wijzigen voor het instellen van Microsoft met Google-domeinen
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Meer informatie over hoe u Microsoft kunt instellen voor het beheren van de DNS-records van uw aangepaste domein bij Google domains.
ms.openlocfilehash: e475e222b6f1c9717008a49b172b0ecac5ec6fc7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658438"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a>Naamservers wijzigen voor het instellen van Microsoft met Google-domeinen

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
Voer de volgende instructies uit als u wilt dat Microsoft uw DNS-records voor u beheert. (Als u wilt, kunt u [al uw DNS-records bij Google domains beheren](create-dns-records-at-google-domains.md).)
  
    
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
>  Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Als u wilt beginnen, gaat u naar uw domeinen pagina bij Google domains via [deze koppeling](https://domains.google.com/registrar). U wordt gevraagd om u aan te melden. U gaat hiervoor als volgt te werk:
    
1. Selecteer **Aanmelden**.
    
2. Voer uw aanmeldingsreferenties in en selecteer **Aanmelden**.
    
2. Selecteer op **de pagina** domains in de sectie **Domain** de optie **configure DNS** voor het domein dat u wilt bewerken. 
    
3. Typ of kopieer en plak de waarden uit de volgende tabel in de sectie **Custom resource records** in de vakken voor de nieuwe record. 
    
    (Mogelijk moet u omlaag schuiven.)
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
|||||
|:-----|:-----|:-----|:-----|
|**Name** <br/> |**Type** <br/> |**TTL** <br/> |**Data** <br/> |
|@  <br/> |TXT  <br/> |1U  <br/> |MS=ms *XXXXXXXX* <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. Kies **Toevoegen**.
    
5. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistratie, gaat u terug naar Microsoft en vraagt u naar de record.
  
Wanneer in Microsoft de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het Microsoft-beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen

Om het instellen van uw domein met Microsoft te voltooien, kunt u de NS-records van uw domein bij uw domeinregistratie wijzigen zodat deze verwijzen naar de primaire en secundaire naamservers van Microsoft. Hierdoor wordt Microsoft zodanig geconfigureerd dat de DNS-records van het domein voor u worden bijgewerkt. We toevoegen alle records, zodat e-mail, Skype voor bedrijven online en uw openbare website met uw domein werken, en u bent klaar.
  
> [!CAUTION]
> Als u de naamserver records van uw domein wijzigt zodat ze verwijzen naar de Microsoft-naamservers, worden dit van invloed op alle services die op dat moment zijn gekoppeld aan uw domein. Alle e-mailberichten die naar uw domein zijn verzonden, zoals rob@ *your_domain.*  com) komt bij Microsoft binnen nadat u deze wijziging hebt aangebracht. 
  
> [!IMPORTANT]
> In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan. > Na het voltooien van de stappen in deze sectie, moeten alleen de volgende vier naamservers in de lijst staan: 
  
1. Ga eerst naar de pagina met domeinen bij Google Domains via [deze koppeling](https://domains.google.com/registrar). U wordt gevraagd om u aan te melden. U gaat hiervoor als volgt te werk:
    
1. Selecteer **Aanmelden**.
    
2. Voer uw aanmeldingsreferenties in en selecteer vervolgens **Aanmelden**.
    
2. Selecteer op **de pagina** domains in de sectie **Domain** de optie **configure DNS** voor het domein dat u wilt bewerken. 
    
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
   
   ![Met Google-domeinen 1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. Selecteer het besturingselement **+ (toevoegen)** om een lege rij te maken. 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. De andere drie naamserverrecords toevoegen.
    
    Maak in de sectie **Custom name servers gebruiken** een record met behulp van de waarden uit de volgende rij in de tabel en selecteer vervolgens het besturingselement **+ (toevoegen)** om een nieuwe rij toe te voegen. 
    
    Herhaal deze procedure totdat u alle vier de naamserverrecords hebt gemaakt.
    
4. Kies **Opslaan**.
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Als er WEL naamservers worden vermeld

1. Als er andere naamservers worden vermeld, selecteert u **bewerken**.
    
    > [!CAUTION]
    > Ga als volgt te werk als u een bestaande naamservers hebt dan de vier juiste naamservers. (Dat wil zeggen dat u alleen huidige naamservers met de  *naam* **ns1.BDM.microsoftonline.com**, **ns2.BDM.microsoftonline.com**, **ns3.BDM.microsoftonline.com** of **ns4.BDM.microsoftonline.com**) verwijdert. 
  
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
   
   ![Met Google-domeinen 1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. Selecteer het besturingselement **+ (toevoegen)** om een lege rij te maken. 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. Voer de andere twee naamserverrecords toe.
    
    Maak in de sectie **Custom name servers gebruiken** een record met behulp van de waarden uit de volgende rij in de tabel en selecteer vervolgens het besturingselement **+ (toevoegen)** om een nieuwe rij toe te voegen. 
    
    Herhaal deze procedure totdat u alle vier de naamserverrecords hebt gemaakt.
    
6. Kies **Opslaan**.
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services allemaal ingesteld voor gebruik met uw domein. 
  
