---
title: Versleuteling in Microsoft Dynamics 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Lees hoe Microsoft versleutelingstechnologie gebruikt om klantgegevens in Microsoft Dynamics 365 te beschermen terwijl ze in een Microsoft-database en onderweg zijn.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b1c55c4ac233c61f7a583f4f1a94222133f1d7c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162116"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Versleuteling in Microsoft Dynamics 365

Microsoft gebruikt versleutelingstechnologie om klantgegevens in Dynamics 365 te beschermen terwijl ze zich in een Microsoft-database bevinden en onderweg zijn tussen gebruikersapparaten en onze datacenters. Verbindingen tussen klanten en Microsoft-datacenters worden versleuteld en alle openbare eindpunten worden beveiligd met gebruik van branchestandaard TLS. Met TLS wordt een door de beveiliging verbeterde verbinding tussen browser en server gemaakt om de vertrouwelijkheid en integriteit van gegevens tussen desktops en datacenters te waarborgen. Nadat gegevensversleuteling is geactiveerd, kan deze niet worden uitgeschakeld. Zie Gegevensversleuteling op veldniveau voor [meer informatie.](/previous-versions/dynamicscrm-2016/developers-guide/dn481562(v=crm.8))

Dynamics 365 gebruikt standaardversleuteling Microsoft SQL Server celniveau voor een set standaardentiteitskenmerken die gevoelige informatie bevatten, zoals gebruikersnamen en e-mailwachtwoorden. Met deze functie kunnen organisaties voldoen aan de nalevingsvereisten die zijn gekoppeld aan FIPS 140-2. Gegevensversleuteling op veldniveau is vooral belangrijk in scenario's waarin gebruik wordt gemaakt van de [e-mailrouter Microsoft Dynamics CRM,](/previous-versions/dynamicscrm-2016/administering-dynamics-365/hh699800(v=crm.8))waarin gebruikersnamen en wachtwoorden moeten worden opgeslagen om integratie tussen een Dynamics 365-exemplaar en een e-mailservice mogelijk te maken. 

Alle exemplaren van Dynamics 365 gebruiken [Microsoft SQL Server Transparent Data Encryption](/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017) (TDE) om realtime versleuteling van gegevens uit te voeren wanneer deze op schijf worden geschreven (in rust). TDE versleutelt SQL Server, Azure SQL Database en Azure SQL Data Warehouse-gegevensbestanden. Standaard worden door Microsoft de databaseversleutelingssleutels voor uw exemplaren van Dynamics 365 opgeslagen en beheert. (De sleutels die worden gebruikt door Dynamics 365 voor Financiële instellingen worden gegenereerd door de .NET Framework Data Protection API.) 

De functie Sleutels beheren in het Dynamics 365-beheercentrum biedt beheerders de mogelijkheid om zelf de databaseversleutelingssleutels te beheren die zijn gekoppeld aan exemplaren van Dynamics 365. (Zelf beheerde databaseversleutelingssleutels zijn alleen beschikbaar in de update van januari 2017 voor Microsoft Dynamics 365 en zijn mogelijk niet beschikbaar voor latere versies. Zie De [versleutelingssleutels voor uw Dynamics 365-exemplaar (online)](/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)beheren voor meer informatie .) De sleutelbeheerfunctie ondersteunt zowel PFX- als BYOK-versleutelingssleutelbestanden, zoals bestanden die zijn opgeslagen in een HSM. (Zie [HSM-beveiligde](/azure/key-vault/key-vault-hsm-protected-keys)sleutels genereren en overdragen voor Azure Key Vault voor meer informatie over het genereren en overdragen van een met HSM beveiligde sleutel via internet.) 

Als u de optie uploadversleutelingssleutel wilt gebruiken, hebt u zowel de openbare als de persoonlijke versleutelingssleutel nodig.

De sleutelbeheerfunctie haalt de complexiteit uit het beheer van versleutelingssleutels door Azure Key Vault te gebruiken om versleutelingssleutels veilig op te slaan. Azure Key Vault helpt bij het beveiligen van cryptografische sleutels en geheimen die worden gebruikt door cloudtoepassingen en -services. De sleutelbeheerfunctie vereist niet dat u een Azure Key Vault-abonnement hebt en in de meeste situaties is het niet nodig om toegang te krijgen tot versleutelingssleutels die worden gebruikt voor Dynamics 365 in de kluis.