---
title: Naamservers wijzigen voor het instellen van Office 365 bij Bluehost
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Meer informatie over hoe u Office 365 instellen om uw DNS-records te beheren bij Bluehost. '
ms.openlocfilehash: dbd06791df2e7f8e6ca085b82dc880e9626c065c
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212339"
---
# <a name="change-nameservers-to-set-up-office-365-with-bluehost"></a>Naamservers wijzigen voor het instellen van Office 365 bij Bluehost

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Volg deze instructies als u wilt dat Office 365 uw DNS-records voor Office 365 voor u beheert. (Als u wilt, kunt u [al uw DNS-records voor Office 365 bij Bluehost beheren](create-dns-records-at-bluehost.md).)
  
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie

Voordat u uw domein met Office 365 kunt gaan gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Office 365 bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm). U wordt gevraagd u eerst aan te melden.
    
2. Op de pagina **Domains**, in het gebied **domain**, zoekt u de rij voor het domein dat u wilt wijzigen, en schakelt u vervolgens het selectievakje in voor dat domein. 
    
    (Mogelijk moet u omlaag schuiven.) 
    
3. Selecteer **dns-records beheren**in het **domain_name-gebied** in de rij **DNS-zoneeditor** .
    
4. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Add DNS Record** in de vakken voor de nieuwe record op de pagina DNS Zone Editor. 
    
    (Kies in de vervolgkeuzelijst de waarde **Type**). 
    
|||||
|:-----|:-----|:-----|:-----|
|**Host Record** <br/> |**TTL** <br/> |**Type** <br/> |**TXT Value** <br/> |
|@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX* <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel in Office 365. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. Selecteer **Record toevoegen**.
    
6. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record hebt toegevoegd aan de site van uw domeinregistrar, gaat u terug naar Office 365 en vraagt u of Office 365 naar de record wil zoeken.
  
Wanneer in Office 365 de juiste TXT-record is gevonden, is uw domein gecontroleerd.
  
1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

    
2. Kies op de pagina **Domeinen** de naam van het domein dat u verifieert. 
    
3. Kies **Start setup** op de pagina **Setup**.
    
4. Kies **Verifiëren** op de pagina **Domein verifiëren**.
    
> [!NOTE]
> Het duurt meestal ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen opsporen en oplossen nadat u uw domein of DNS-records hebt toegevoegd in Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>De naamserverrecords (NS-records) van uw domein wijzigen

U voltooit het instellen van uw domein met Office 365 door de NS-records van uw domein bij uw domeinregistrar te wijzigen, zodat deze verwijzen naar de primaire en secundaire naamservers van Office 365. Hiermee wordt Office 365 zo ingesteld dat de DNS-records van het domein voor u worden bijgewerkt. Alle benodigde records worden toegevoegd zodat e-mail, Skype voor Bedrijven Online en uw openbare website met uw domein kunnen werken. Daarna bent u klaar.
  
> [!CAUTION]
> Als u de NS-records van uw domein laat verwijzen naar de naamservers van Office 365, is dit van invloed op alle services die momenteel aan uw domein zijn gekoppeld. Zo wordt bijvoorbeeld alle e-mail die naar uw domein wordt verzonden (zoals william@ *uw_domein*  .com), naar Office 365 verzonden zodra u deze wijziging hebt aangebracht. 
  
> [!IMPORTANT]
>  In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan. >  Na het voltooien van de stappen in deze sectie, moeten alleen de volgende vier naamservers in de lijst staan: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com 
  
1. Ga eerst naar de pagina met domeinen bij Bluehost via [deze koppeling](https://my.bluehost.com/cgi/dm). U wordt gevraagd u eerst aan te melden.
    
2. Schakel op de **pagina domeinen** in het **domain_name-gebied** het selectievakje voor uw domein in en selecteer **vervolgens naamservers**.
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. Selecteer aangepaste **naamservers gebruiken**in het **domain_name-gebied** .
    
    ![Verbeterde animatiepaden](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. Afhankelijk van of er al naamservers worden vermeld op de pagina die wordt weergegeven, gaat u op een van de volgende twee manieren verder:
    
  - Als er nog **GEEN** naamservers worden vermeld, [Als er nog GEEN naamservers worden vermeld](#if-there-are-no-nameservers-already-listed).
    
  - Als er **WEL** naamservers worden vermeld, [Als er WEL naamservers worden vermeld](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Als er nog GEEN naamservers worden vermeld

1. Typ of kopieer en plak in de sectie **Use Custom Nameservers** de waarden uit de volgende tabel. 
    
|||
|:-----|:-----|
|**Eerste lege rij** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Tweede lege rij** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Afbeelding van het lint](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. Selecteer **Rij toevoegen**.
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. Terwijl u zich nog in de sectie **Use Custom Nameservers** bevindt, typt of kopieert en plakt u de waarden uit de eerste rij van de volgende tabel in de nieuwe, lege rij. 
    
|||
|:-----|:-----|
|**Derde lege rij** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Vierde lege rij** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. Als u de vierde Nameserver-record wilt toevoegen, selecteert u Rij opnieuw **toevoegen** en maakt u een record met de waarden uit de laatste rij van de bovenstaande tabel. 
    
5. Selecteer **naamserverinstellingen opslaan**.
    
    ![Theta](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Als er WEL naamservers worden vermeld

> [!CAUTION]
> Volg deze stappen alleen als u bestaande naamservers hebt, andere dan de vier juiste naamservers. (Dat wil zeggen, alleen huidige naamservers verwijderen die *geen* naam hebben **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com**of **ns4.bdm.microsoftonline.com**.) 
  
1. Als er andere naamservers worden vermeld, verwijdert u elke vermelding door deze te selecteren en vervolgens te drukken op de toets **Delete** op het toetsenbord. 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. Terwijl u zich nog in de sectie **Use Custom Nameservers** bevindt, typt of kopieert en plakt u de waarden uit de volgende tabel. 
    
|||
|:-----|:-----|
|**Eerste lege rij** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Tweede lege rij** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Afbeelding van het lint](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. Selecteer **Rij toevoegen**.
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. Terwijl u zich nog in de sectie **Use Custom Nameservers** bevindt, typt of kopieert en plakt u de waarden uit de eerste rij van de volgende tabel in de nieuwe, lege rij. 
    
|||
|:-----|:-----|
|**Derde lege rij** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Vierde lege rij** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Afbeelding van het lint](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. Als u de vierde Nameserver-record wilt toevoegen, selecteert u Rij opnieuw **toevoegen** en maakt u een record met de waarden uit de laatste rij van de bovenstaande tabel. 
    
6. Selecteer **naamserverinstellingen opslaan**.
    
    ![Theta](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens worden uw e-mail voor Office 365 en andere services ingesteld voor gebruik met uw domein. 
  
