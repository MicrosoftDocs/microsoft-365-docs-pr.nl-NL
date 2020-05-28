---
title: Naamservers wijzigen om Microsoft in te stellen met Amazon Web Services (AWS)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Meer informatie over hoe u Microsoft instellen om uw DNS-records te beheren bij Amazon Web Services (AWS). '
ms.openlocfilehash: 6efe06400652783ffbc6732b5c6327067c5c484c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400675"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a>Naamservers wijzigen om Microsoft in te stellen met Amazon Web Services (AWS)

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Volg deze instructies als u wilt dat Microsoft uw DNS-records voor u beheert. (Als u dat liever hebt, u [al uw Microsoft DNS-records beheren bij AWS](create-dns-records-at-aws.md).)
  
    
## <a name="add-a-txt-record-for-verification"></a>Een TXT-record toevoegen voor verificatie

Voordat u uw domein met Microsoft kunt gebruiken, moet worden gecontroleerd dat u de eigenaar bent van het domein. Als u zich bij uw account bij de domeinregistrar kunt aanmelden en de DNS-record kunt maken, is dit voor Microsoft bewezen.
  
> [!NOTE]
> Deze record wordt alleen gebruikt om te verifiëren dat u de eigenaar van uw domein bent. Dit heeft verder geen invloed. U kunt deze record later desgewenst verwijderen. 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Resources** de optie **Gehoste zones**.
    
3. Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken. 
    
4. Selecteer **Recordset maken**.
    
5. Typ of kopieer en plak de waarden uit de volgende tabel in het gebied **Create Record Set** in de vakken voor de nieuwe record. 
    
    (Kies in de vervolgkeuzelijsten de waarden **Type** en **Routing Policy**.) 
    
    > [!TIP]
    > De aanhalingstekens die zijn vereist volgens de instructies op het scherm, worden automatisch ingevoegd. U hoeft deze niet handmatig te typen. 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Name** <br/> |**Type** <br/> |**Alias** <br/> |**TTL (Seconds)** <br/> |**Value** <br/> |**Routing Policy** <br/> |
|(Laat dit veld leeg)  <br/> |TXT - Text  <br/> |No  <br/> |300  <br/> |MS=ms *XXXXXXXX* <br/> **Opmerking:** Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)  <br/>  |Simple <br/> |
   
6. Selecteer **Maken**.
    
7. Wacht enkele minuten voordat u verder gaat, zodat de record die u zojuist hebt gemaakt via internet kan worden bijgewerkt.
    
Nu u de record op de site van uw domeinregistrar hebt toegevoegd, gaat u terug naar Microsoft en vraagt u om een zoekopdracht naar de record.
  
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
> Wanneer u de NS-records van uw domein wijzigt om naar de Microsoft-naamservers te wijzen, worden alle services die momenteel aan uw domein zijn gekoppeld, beïnvloed. Alle e-mail die naar uw *your_domain* domein wordt verzonden (zoals rob@ your_domain.com) wordt bijvoorbeeld naar Microsoft verzonden nadat u deze wijziging hebt gewijzigd. 
  
> [!IMPORTANT]
>  In de volgende procedure kunt u zien hoe u andere, ongewenste naamservers uit de lijst verwijdert en hoe u de juiste naamservers toevoegt als deze niet al in de lijst staan. >  Na het voltooien van de stappen in deze sectie, moeten alleen de volgende vier naamservers in de lijst staan: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com 
  
1. Als u wilt beginnen, gaat u naar uw domeinenpagina bij AWS via [deze koppeling](https://console.aws.amazon.com/route53/home). U wordt gevraagd u eerst aan te melden.
    
2. Selecteer op de pagina **Resources** de optie **Gehoste zones**.
    
3. Selecteer op de pagina **Gehoste zones** in de kolom **Domeinnaam** de naam van het domein dat u wilt bewerken. 
    
4. Selecteer de **Nameserver**-recordset. 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. Verwijder in de recordset **NS - Name server** in het vak **Value** alle naamservers door ze allemaal te selecteren en op de toets **Delete** op het toetsenbord te drukken. 
    
    > [!CAUTION]
    > Volg deze stappen alleen als u bestaande naamservers hebt, andere dan de vier juiste naamservers. (Dat wil zeggen, alleen huidige naamservers verwijderen die *geen* naam hebben **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com**of **ns4.bdm.microsoftonline.com**.) 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. Selecteer 1 uur in het gebied **TTL (Seconden):** **1uur** (1 uur). 
    
    ![Selecteer 1Uur voor een uur](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. In de recordset **NS - Name server** en het vak **Value** typt of kopieert en plakt u bovendien de waarde uit **Eerste regel** uit de volgende tabel, drukt u op **Enter** op het toetsenbord en typt of kopieert en plakt u de waarde van de volgende **regel**. 
    
    > [!IMPORTANT]
    > Elke naamserverwaarde  *moet*  op een afzonderlijke regel in het vak **Value** staan, zoals wordt weergegeven in de volgende afbeelding. 
  
|||
|:-----|:-----|
|**Eerste regel** <br/> |ns1.bdm.microsoftonline.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
|**Tweede regel** <br/> |ns2.bdm.microsoftonline.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
|**Derde regel** <br/> |ns3.bdm.microsoftonline.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
|**Vierde regel** <br/> |ns4.bdm.microsoftonline.com.  <br/> **Deze waarde MOET eindigen op een punt (.)** <br/> |
   
   ![De waarde Eerste regel typen of plakken in het vak Waarde](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. Selecteer **Recordset opslaan**.
    
    ![Recordset opslaan selecteren](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> Het kan enige uren duren voordat de updates van uw naamserverrecords via het DNS-systeem op internet zijn doorgevoerd. Vervolgens zijn uw Microsoft-e-mail en andere services helemaal klaar om met uw domein te werken. 
