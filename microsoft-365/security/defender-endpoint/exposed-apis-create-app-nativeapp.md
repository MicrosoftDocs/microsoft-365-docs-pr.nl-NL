---
title: Microsoft Defender voor eindpunt-API's gebruiken
ms.reviewer: ''
description: Lees hoe u een inheems Windows-app ontwerpt om programmatische toegang te krijgen tot Microsoft Defender voor Eindpunt zonder een gebruiker.
keywords: api's, graph api, ondersteunde api's, actor, waarschuwingen, apparaat, gebruiker, domein, ip, bestand, geavanceerd zoeken, query
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5e59ff75a7933cf52af857f1a41b0925aa7bb47a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198893"
---
# <a name="use-microsoft-defender-for-endpoint-apis"></a>Microsoft Defender voor eindpunt-API's gebruiken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Op deze pagina wordt beschreven hoe u een toepassing maakt om namens een gebruiker programmatische toegang te krijgen tot Defender voor Eindpunt.

Als u programmatische toegang nodig hebt voor Microsoft Defender voor Eindpunt zonder een gebruiker, raadpleegt u Access Microsoft Defender voor Eindpunt [met toepassingscontext.](exposed-apis-create-app-webapp.md)

Als u niet zeker weet welke toegang u nodig hebt, leest u de [pagina Inleiding.](apis-intro.md)

In Microsoft Defender voor Eindpunt worden veel van de gegevens en acties via een set programmatische API's beschikbaar. Met deze API's kunt u werkstromen automatiseren en innoveren op basis van De mogelijkheden van Microsoft Defender voor eindpunten. Voor de API-toegang is OAuth2.0-verificatie vereist. Zie [OAuth 2.0 Autorisatiecodestroom](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)voor meer informatie.

Over het algemeen moet u de volgende stappen nemen om de API's te gebruiken:
- Een AAD-toepassing maken
- Een toegangs token krijgen met deze toepassing
- Het token gebruiken om toegang te krijgen tot Defender for Endpoint API

Op deze pagina wordt uitgelegd hoe u een AAD-toepassing maakt, toegang krijgt tot Microsoft Defender voor Eindpunt en het token valideert.

>[!NOTE]
> Wanneer u namens een gebruiker toegang hebt tot Microsoft Defender voor Endpoint API, hebt u de juiste machtigingen en gebruikersmachtigingen nodig.
> Als u niet bekend bent met gebruikersmachtigingen op Microsoft Defender voor Eindpunt, zie Portaltoegang beheren met behulp van op rollen [gebaseerd toegangsbeheer.](rbac.md)

>[!TIP]
> Als u de machtiging hebt om een actie uit te voeren in de portal, hebt u de machtiging om de actie uit te voeren in de API.

## <a name="create-an-app"></a>Een app maken

1. Meld u aan [bij Azure](https://portal.azure.com) met een gebruikersaccount met de rol **Globale beheerder.**

2. **Navigeer naar Azure Active Directory**  >  **App-registraties** Nieuwe  >  **registratie**. 

   ![Afbeelding van Microsoft Azure en navigatie naar toepassingsregistratie](images/atp-azure-new-app2.png)

3. Wanneer de **pagina Een toepassing registreren** wordt weergegeven, voert u de registratiegegevens van uw toepassing in:

   - **Naam:** voer een betekenisvolle toepassingsnaam in die wordt weergegeven voor gebruikers van de app.
   - **Ondersteunde accounttypen:** selecteer welke accounts u wilt dat uw toepassing ondersteunt.

       | Ondersteunde accounttypen | Beschrijving |
       |-------------------------|-------------|
       | **Accounts in deze organisatiemap alleen** | Selecteer deze optie als u een LOB-toepassing (Line-of-Business) bouwt. Deze optie is niet beschikbaar als u de toepassing niet registreert in een adreslijst.<br><br>Deze optie wordt alleen naar Azure AD met één tenant gemapt.<br><br>Dit is de standaardoptie, tenzij u de app buiten een adreslijst registreert. In gevallen waarin de app buiten een adreslijst is geregistreerd, zijn Azure AD-multi-tenant- en persoonlijke Microsoft-accounts de standaardinstelling. |
       | **Accounts in een organisatiemap** | Selecteer deze optie als u alle zakelijke en educatieve klanten wilt targeten.<br><br>Deze optie wordt alleen aan een Azure AD-multi-tenant toe te staan.<br><br>Als u de app hebt geregistreerd als alleen een enkele tenant van Azure AD, kunt u deze bijwerken als Azure AD-multi-tenant en terug naar een enkele tenant via het **verificatieblad.** |
       | **Accounts in een organisatiemap en persoonlijke Microsoft-accounts** | Selecteer deze optie om de meest uitgebreide set klanten te selecteren.<br><br>Deze optie wordt aan Azure AD-accounts met meerdere tenants en persoonlijke Microsoft-accounts toe te staan.<br><br>Als u de app hebt geregistreerd als Azure AD-multi-tenant en persoonlijke Microsoft-accounts, kunt u dit niet wijzigen in de gebruikersinterface. In plaats daarvan moet u de toepassingsmanifesteditor gebruiken om de ondersteunde accounttypen te wijzigen. |

   - URI omleiden **(optioneel)** - Selecteer het type app dat u maakt, **web-** of openbare **client (mobiele & desktop)** en voer vervolgens de omleidings-URI (of antwoord-URL) in voor uw toepassing.
       - Geef voor webtoepassingen de basis-URL van uw app op. Dit kan bijvoorbeeld `http://localhost:31544` de URL zijn voor een web-app die wordt uitgevoerd op uw lokale computer. Gebruikers gebruiken deze URL om zich aan te melden bij een webclienttoepassing.
       - Geef voor openbare clienttoepassingen de URI op die door Azure AD wordt gebruikt om tokenreacties te retourneren. Voer een waarde in die specifiek is voor uw toepassing, zoals `myapp://auth` .

     Bekijk onze [quickstarts](/azure/active-directory/develop/#quickstarts)voor specifieke voorbeelden voor webtoepassingen of native toepassingen.

     Wanneer u klaar bent, selecteert u **Registreren.**

4. Geef uw toepassing toegang tot Microsoft Defender voor Eindpunt en wijs deze machtiging 'Leeswaarschuwingen' toe:

    - Selecteer op uw **toepassingspagina API-machtigingen** Machtigingen toevoegen Api's die mijn organisatie gebruikt  >    >   > **WindowsDefenderATP** typen en selecteer op **WindowsDefenderATP**.

    - **Opmerking:** *WindowsDefenderATP* wordt niet weergegeven in de oorspronkelijke lijst. Begin met het schrijven van de naam in het tekstvak om deze weer te geven.

      ![machtiging toevoegen](images/add-permission.png)

    - Kies **Gedelegeerde machtigingen**  >  **Alert.Read** > selecteer **Machtigingen toevoegen**

      ![toepassingsmachtigingen](images/application-permissions-public-client.png)

    - **Belangrijke opmerking:** Selecteer de relevante machtigingen. Leeswaarschuwingen is slechts een voorbeeld.

      Bijvoorbeeld:

      - Als [u geavanceerde query's wilt uitvoeren,](run-advanced-query-api.md)selecteert u 'Geavanceerde query's uitvoeren' machtiging
      - Als [u een apparaat wilt isoleren,](isolate-machine.md)selecteert u machtiging 'Machine isoleren'.
      - Als u wilt bepalen welke machtiging u nodig hebt, bekijkt u de **sectie** Machtigingen in de API die u wilt bellen.

    - Selecteer **Toestemming verlenen**

      **Opmerking:** Telkens wanneer u machtigingen toevoegt, moet u toestemming **verlenen** selecteren om de nieuwe machtiging van kracht te laten worden.

      ![Afbeelding van machtigingen verlenen](images/grant-consent.png)

6. Schrijf uw toepassings-id en uw tenant-id op:

   - Ga op de toepassingspagina naar **Overzicht** en kopieer de volgende informatie:

   ![Afbeelding van gemaakte app-id](images/app-and-tenant-ids.png)


## <a name="get-an-access-token"></a>Een toegangs token krijgen

Zie [Zelfstudie](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds) voor Azure AD voor meer informatie over AAD-tokens

### <a name="using-c"></a>C gebruiken #

- Kopieer/plak de onderstaande klas in uw toepassing.
- Gebruik **acquireUserTokenAsync-methode** met uw toepassing-id, tenant-id, gebruikersnaam en wachtwoord om een token te verkrijgen.

    ```csharp
    namespace WindowsDefenderATP
    {
        using System.Net.Http;
        using System.Text;
        using System.Threading.Tasks;
        using Newtonsoft.Json.Linq;

        public static class WindowsDefenderATPUtils
        {
            private const string Authority = "https://login.microsoftonline.com";

            private const string WdatpResourceId = "https://api.securitycenter.microsoft.com";

            public static async Task<string> AcquireUserTokenAsync(string username, string password, string appId, string tenantId)
            {
                using (var httpClient = new HttpClient())
                {
                    var urlEncodedBody = $"resource={WdatpResourceId}&client_id={appId}&grant_type=password&username={username}&password={password}";

                    var stringContent = new StringContent(urlEncodedBody, Encoding.UTF8, "application/x-www-form-urlencoded");

                    using (var response = await httpClient.PostAsync($"{Authority}/{tenantId}/oauth2/token", stringContent).ConfigureAwait(false))
                    {
                        response.EnsureSuccessStatusCode();

                        var json = await response.Content.ReadAsStringAsync().ConfigureAwait(false);

                        var jObject = JObject.Parse(json);

                        return jObject["access_token"].Value<string>();
                    }
                }
            }
        }
    }
    ```

## <a name="validate-the-token"></a>Het token valideren

Controleer of u een correct token hebt:
- Kopieer/plak in [JWT](https://jwt.ms) het token dat u in de vorige stap hebt ontvangen om het te decoderen
- Valideren dat u een 'scp'-claim krijgt met de gewenste app-machtigingen
- In de onderstaande schermafbeelding ziet u een gedecodeerd token dat is verkregen uit de app in de zelfstudie:

![Afbeelding van tokenvalidatie](images/nativeapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>Het token gebruiken om toegang te krijgen tot Microsoft Defender voor Endpoint API

- Kies de API die u wilt gebruiken- Ondersteunde API's van [Microsoft Defender voor eindpunten](exposed-apis-list.md)
- De autorisatiekoptekst instellen in de HTTP-aanvraag die u verzendt naar 'Bearer {token}' (Aandrager is het autorisatieschema)
- De vervaldatum van het token is 1 uur (u kunt meerdere aanvragen met hetzelfde token verzenden)

- Voorbeeld van het verzenden van een aanvraag voor het ontvangen van een lijst met waarschuwingen **met C#** 

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a>Zie ook
- [Microsoft Defender voor eindpunt-API's](exposed-apis-list.md)
- [Toegang tot Microsoft Defender voor eindpunt met toepassingscontext](exposed-apis-create-app-webapp.md)
