---
title: DNS-records maken wanneer uw domein wordt beheerd door Google (eNom)
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
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Lees hoe u toegang kunt krijgen tot eNom en maak DNS via de pagina Google domains.
ms.openlocfilehash: 3294be667653c568fbbd1a911bcfab9b6ea7788b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656853"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>DNS-records maken wanneer uw domein wordt beheerd door Google (eNom)

 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
Als u uw e-mailaccounts wilt migreren naar Microsoft, moet u een DNS-record maken bij uw domeinregistratie.
  
Als u uw domein via Google hebt aangeschaft toen u zich aanmeldt voor uw **Google-Apps voor werk** , worden uw DNS-records beheerd door Google maar geregistreerd bij eNom. 
  
U kunt toegang krijgen tot eNom en DNS maken, via de pagina Google **Domains** . Voer gewoon de stappen in dit artikel uit. 
  
## <a name="create-the-dns-record"></a>De DNS-record maken

1. Selecteer **Aanmelden** in de [Google admin-console](https://www.google.com/work/apps/business).
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. Voer uw domeinnaam in en selecteer vervolgens **Go**.
    
    ![Knopafbeelding](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. Selecteer onder aan de pagina **meer besturingselementen**.
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. Selecteer **Domeinen**.
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. Selecteer **domeinen toevoegen/verwijderen** op de pagina **domeinen** .
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. Selecteer op de pagina **domeinen** de optie **Geavanceerde DNS-instellingen**.
    
    > [!NOTE]
    > Als u geen domeinnaam via Google hebt aangeschaft terwijl u zich registreerde voor uw account bij **Google Apps for Work**, hebt u geen **Geavanceerde DNS-instellingen** op uw pagina **Domeinen**. U moet dan rechtstreeks naar de website van uw domeinhost gaan voor toegang tot uw DNS-instellingen, en vervolgens deze en de volgende stappen uitvoeren. Zie [uw G suite-Domeininstellingen](https://support.google.com/a/answer/54693?hl=en) raadplegen voor meer informatie. 
  
    ![Google-Apps-eNom-configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. Selecteer op de pagina **Geavanceerde DNS-instellingen** de optie **Aanmelden bij de DNS-console**. Noteer de **aanmeldingsnaam** en het **wachtwoord**. U hebt deze nodig in de volgende stap. 
    
    ![Google-Apps-eNom-configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. Meld u op de pagina **Geavanceerde DNS-instellingen** aan bij **Domeinbeheer** van Google met de **aanmeldingsnaam** en het **wachtwoord**. 
    
    ![Google-Apps-eNom-configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. Selecteer op de pagina domain_name _ de optie **bewerken** ***in de sectie _* host records** .
    
    ![Google-Apps-eNom-configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. Selecteer in de sectie **host records** de optie **Add New**.
    
    ![Google-Apps-eNom-configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. Typ of kopieer en plak de waarden uit de volgende tabel in de vakken voor de nieuwe record.
    
    |**HOST**|**TXT VALUE**|**RECORD TYPE**|
    |:-----|:-----|:-----|
    |@  <br/> ||TXT  <br/> |

    > [!NOTE]
    > Dit is een voorbeeld. Gebruik hier de specifieke waarde voor **Doel of adres waarnaar wordt verwezen** uit de tabel. 
  
    [Hoe kan ik dit vinden?](../get-help-with-domains/information-for-dns-records.md)
  
12. Kies **Opslaan**.
    
    ![Google-Apps-eNom-configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. Selecteer **Save Changes**.
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  Het duurt gewoonlijk ongeveer 15 minuten voordat DNS-wijzigingen van kracht worden. Het kan echter soms wat langer duren voordat een wijziging die u hebt aangebracht, is bijgewerkt via het DNS-systeem op internet. Als u na het toevoegen van de DNS-records problemen hebt met het ontvangen of verzenden van e-mail, raadpleegt u [Problemen oplossen nadat u uw domeinnaam of DNS-records hebt gewijzigd](../get-help-with-domains/find-and-fix-issues.md). 
  
