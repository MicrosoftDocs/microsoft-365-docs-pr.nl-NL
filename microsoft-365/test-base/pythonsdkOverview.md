---
title: Test Base SDK voor Python
description: Meer informatie over het begrijpen van SDK voor Python van Test Base
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: c7f2d4b7b600e84b2ed35cce320dcb7d7191ecfc
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322796"
---
# <a name="test-base-sdk-for-python"></a><span data-ttu-id="1b4d9-103">Test Base SDK voor Python</span><span class="sxs-lookup"><span data-stu-id="1b4d9-103">Test Base SDK for Python</span></span>

## <a name="overview"></a><span data-ttu-id="1b4d9-104">Overzicht</span><span class="sxs-lookup"><span data-stu-id="1b4d9-104">Overview</span></span>
<span data-ttu-id="1b4d9-105">De Test Base SDK kan worden gebruikt voor interactie met de Azure-testbasisbron.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-105">The Test Base SDK can be used to interact with the Azure test base resource.</span></span> <span data-ttu-id="1b4d9-106">(dat wil zeggen uw toepassingspakket beheren, pakket maken, pakket bewerken en verwijderen)</span><span class="sxs-lookup"><span data-stu-id="1b4d9-106">(i.e. manage your application package, include create package, edit package and delete package)</span></span>

<span data-ttu-id="1b4d9-107">Met de SDK, het testoverzicht en het analyseresultaat dat u kunt krijgen, zijn: scriptExecution, betrouwbaarheid, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-107">With the SDK, the test summary and Analysis Result which can be gotten include : scriptExecution, reliability, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span></span>

<span data-ttu-id="1b4d9-108">Met de Test Base SDK kunt u de testbasis integreren in uw CI/CD-pijplijn.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-108">With the Test Base SDK, you can integrate test base in your CI/CD pipeline.</span></span>

## <a name="client-library"></a><span data-ttu-id="1b4d9-109">Clientbibliotheek</span><span class="sxs-lookup"><span data-stu-id="1b4d9-109">Client Library</span></span>

<span data-ttu-id="1b4d9-110">Installeer het testbasispakket met pip.</span><span class="sxs-lookup"><span data-stu-id="1b4d9-110">Install the test base package with pip.</span></span>

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a><span data-ttu-id="1b4d9-111">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="1b4d9-111">Example</span></span>
