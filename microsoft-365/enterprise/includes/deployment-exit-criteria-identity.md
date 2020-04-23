Zie ook [Vereisten](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites) voor extra aanbevelingen voor de identiteitsinfrastructuur.

<a name="crit-identity-global-admin"></a>
### <a name="required-your-global-administrator-accounts-are-protected"></a>Vereist: uw globale-beheerdersaccounts worden beveiligd 

U hebt [uw globale-beheerdersaccounts beveiligd](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) om misbruik van referenties door kwaadwillende gebruikers en een inbreuk op uw abonnement op Microsoft 365 te voorkomen.

Als u deze vereiste overslaat, kunnen uw globale-beheerdersaccounts gevoelig zijn voor aanvallen en misbruik, waardoor een kwaadwillende gebruiker toegang kan krijgen tot uw gegevens voor verzameling, vernietiging of digitale gijzeling.

Via [Stap 1](../identity-create-protect-global-admins.md#identity-global-admin) kunt u zo nodig aan deze vereisten voldoen.

#### <a name="how-to-test"></a>Testen

Gebruik de volgende stappen om te controleren of u uw globale-beheerdersaccounts hebt beveiligd:

1. Voer de volgende Azure Active Directory PowerShell voor Graph-opdracht uit na de PowerShell-opdrachtprompt. U krijgt alleen de lijst met toegewezen globale-beheerdersaccounts te zien.
   ```powershell
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. Meld u aan met een van de accounts uit stap 1. Voor elke aanmelding moeten Azure Multi-Factor Authentication en de sterkste vormen van secundaire verificatie in uw organisatie worden gebruikt.

> [!Note]
> Zie [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) (Verbinding maken met Office 365 PowerShell) voor instructies over het installeren van de Azure Active Directory PowerShell for Graph-module en het aanmelden bij Office 365.

<a name="crit-identity-pim"></a>
### <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a>Optioneel: u hebt Privileged Identity Management ingesteld voor ondersteuning van toewijzing op aanvraag van de rol globale beheerder.

U hebt de instructies in [ Azure AD Privileged Identity Management (PIM) configureren](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) gebruikt om PIM in te schakelen in de Azure AD-tenant en uw globale-beheerdersaccounts geconfigureerd als in aanmerking komende beheerders.

U hebt ook de aanbevelingen gebruikt in [Geprivilegieerde toegang voor hybride en cloudimplementaties in Azure AD beveiligen](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) om een routekaart te ontwikkelen waarmee geprivilegieerde toegang wordt beveiligd tegen cyberaanvallers.

Als u deze optie overslaat, lopen uw globale-beheerdersaccounts het risico dat er misbruik van wordt gemaakt via een online aanval, zodat een kwaadwillende gebruiker gevoelige informatie kan verzamelen, vernietigen of in bewaring houden om daarvoor losgeld te vragen.

[Stap 1](../identity-create-protect-global-admins.md#identity-pim) kan u bij deze optie desgewenst helpen.

<a name="crit-identity-pam"></a>
### <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a>Optioneel: u hebt Privileged Access Management geconfigureerd in Office 365

U hebt de informatie in [Privileged Access Management (bevoegd toegangsbeheer) in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) gebruikt om Privileged Access Management in te schakelen en een of meer beleidsregels voor geprivilegieerde toegang in uw organisatie te maken. U hebt deze beleidsregels geconfigureerd en just-in-time-toegang is ingeschakeld voor toegang tot gevoelige gegevens of kritieke configuratie-instellingen.

Via [Stap 1](../identity-create-protect-global-admins.md#identity-pam) kunt u zo nodig aan deze vereisten voldoen. 

<a name="crit-password-prot"></a>
### <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a>Optioneel: Azure AD-wachtwoordbeveiliging voorkomt het gebruik van zwakke wachtwoorden

U hebt het bannen van ongeldige wachtwoorden [in de cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) en voor de [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) ingeschakeld voor algemene, gebande wachtwoorden en eventueel voor aangepaste termen.

[Stap 2](../identity-secure-your-passwords.md#identity-password-prot) kan u bij deze optie desgewenst helpen.

<a name="crit-identity-pw-reset"></a>
### <a name="optional-users-can-reset-their-own-passwords"></a>Optioneel: gebruikers kunnen hun eigen wachtwoord opnieuw instellen

U hebt [ Snelle implementatie van Azure AD-self-service voor wachtwoordherstl](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) gebruikt om het opnieuw instellen van wachtwoorden voor uw gebruikers te configureren.

Als u niet aan deze voorwaarde voldoet, zijn gebruikers afhankelijk van beheerders van gebruikersaccounts om hun wachtwoord opnieuw in te stellen. Hierdoor worden IT-beheerders extra belast.

[Stap 2](../identity-secure-your-passwords.md#identity-pw-reset) kan u bij deze optie desgewenst helpen.

<a name="crit-identity-sso"></a>
### <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a>Optioneel: gebruikers kunnen zich aanmelden met naadloze eenmalige aanmelding van Azure AD

U hebt [Azure AD Connect: naadloze eenmalige aanmelding](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) voor uw organisatie ingeschakeld om het aanmelden van gebruikers bij cloud-toepassingen te vereenvoudigen, bijvoorbeeld bij Office 365.

Als u deze optie overslaat, kan aan uw gebruikers worden gevraagd referenties op te geven wanneer ze toegang willen hebben tot aanvullende toepassingen die gebruikmaken van de Azure AD-tenant.

[Stap 2](../identity-secure-your-passwords.md#identity-sso) kan u bij deze optie desgewenst helpen.

<a name="crit-identity-custom-sign-in"></a>
### <a name="optional-the-sign-in-screen-is-personalized-for-your-organization"></a>Optioneel: het aanmeldingsscherm is aangepast voor uw organisatie.

U hebt [Huisstijl toevoegen aan de aanmeldingspagina en de pagina Toegangsvenster](https://aka.ms/aadpaddbranding) gebruikt om de huisstijl van uw organisatie toe te voegen aan de aanmeldingspagina.

Als u deze optie overslaat, zien uw gebruikers een algemeen aanmeldingsscherm en zijn ze mogelijk wantrouwig om zich aan te melden bij de site van uw organisatie.

[Stap 2](../identity-secure-your-passwords.md#identity-custom-sign-in) kan u bij deze optie desgewenst helpen.


<a name="crit-identity-mfa"></a>
### <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a>Optioneel: Azure Multi-Factor Authentication is ingeschakeld voor uw gebruikers

U hebt [Plannen voor Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) en [Beleid voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) gebruikt om Azure Multi-Factor Authentication (MFA) in te schakelen voor uw gebruikersaccounts.

Als u deze optie overslaat, zijn uw gebruikersaccounts kwetsbaar voor inbreuken op de referenties door cyberaanvallers. Als misbruik is gemaakt van het wachtwoord van een account, heeft de aanvaller toegang tot alle bronnen en mogelijkheden met betrekking tot dit account, bijvoorbeeld beheerdersrollen. Hierdoor kan de aanvaller interne documenten en andere gegevens kopiëren, vernietigen of in bewaring houden om losgeld te kunnen vragen.

[Stap 3](../identity-secure-user-sign-ins.md#identity-mfa) kan u bij deze optie desgewenst helpen.

#### <a name="how-to-test"></a>Testen

1.  Een testgebruikersaccount maken en hieraan een licentie toewijzen. 
2.  Configureer Azure Multi-Factor Authentication voor het testgebruikersaccount met de extra verificatiemethode die u gebruikt voor feitelijke gebruikersaccounts, zoals voor het verzenden van een sms-bericht naar uw telefoon. 
3.  Meld u aan bij de Office 365-portal met het testgebruikersaccount.
4.  Controleer of MFA u bij een geslaagde verificatie vraagt om de extra verificatiegegevens en de resultaten. 
5.  Verwijder het testgebruikersaccount.

<a name="crit-identity-ident-prot"></a>
### <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-e5-only"></a>Optioneel: Azure AD Identity Protection is ingeschakeld voor bescherming tegen inbreuk op referenties (alleen Microsoft 365 E5)

U hebt Azure AD Identity Protection ingeschakeld om:

- Mogelijke beveiligingslekken met een identiteit aan te pakken.
- Mogelijke inbreuk op referenties op te sporen.
- Voortdurende, verdachte identiteitsincidenten te onderzoeken en aan te pakken.

Als u deze optie overslaat, is het niet mogelijk om inbreuken op referenties automatisch te detecteren of uit te schakelen of om beveiligingsincidenten met betrekking tot identiteiten te onderzoeken. Hierdoor is uw organisatie mogelijk kwetsbaar voor een inbreuk op referenties en met als gevolg misbruik van gegevens van uw organisatie.

[Stap 3](../identity-secure-user-sign-ins.md#identity-ident-prot) kan u bij deze optie desgewenst helpen.


#### <a name="how-to-test"></a>Testen

1. Maak een testgebruikersaccount met een oorspronkelijk wachtwoord.
2. Gebruik de stappen in [Gebruikers hun eigen wachtwoorden opnieuw laten instellen in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) om het wachtwoord opnieuw in te stellen voor het testgebruikersaccount.
3. Meld u af en meld u vervolgens aan bij het testgebruikersaccount met het opnieuw ingestelde wachtwoord.
4. Verwijder het testgebruikersaccount.

<a name="crit-identity-sync"></a>
### <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a>Vereist voor hybride identiteit: gebruikers en groepen worden gesynchroniseerd met Azure AD

Als u al over on-premises Active Directory Domain Services (AD DS) beschikt, hebt u Azure AD Connect gebruikt voor het synchroniseren van gebruikersaccounts en -groepen uit uw on-premises AD DS met de Azure AD-tenant.

Met adreslijstsynchronisatie kunnen uw gebruikers zich aanmelden bij Office 365 en andere Microsoft-cloudservices met dezelfde referenties die ze gebruiken om zich aan te melden bij hun computers en toegang te krijgen tot on-premises resources.

Via [Stap 4](../identity-add-user-accounts.md#identity-sync) kunt u zo nodig aan deze vereisten voldoen.

Als u deze vereiste overslaat, hebt u twee sets gebruikersaccounts en -groepen:

- Gebruikersaccounts en -groepen die voorkomen in uw on-premises AD DS
- Gebruikersaccounts en -groepen die voorkomen in uw AD DS-tenant

In deze staat moeten de twee sets gebruikersaccounts en -groepen handmatig worden onderhouden door IT-beheerders en gebruikers. Dit leidt onvermijdelijk tot niet-gesynchroniseerde accounts, de bijbehorende wachtwoorden en groepen.

#### <a name="how-to-test"></a>Testen
Als u wilt controleren of verificatie met on-premises referenties correct werkt, meldt u zich aan bij de Office-portal met uw on-premises referenties.

Ga als volgt te werk om te controleren of adreslijstsynchronisatie goed werkt:

1.  Maak een nieuwe testgroep in AD DS.
2.  Wacht totdat de synchronisatie voorbij is.
3.  Controleer de Azure AD-tenant om te controleren of de naam van de nieuwe testgroep wordt weergegeven.

<a name="crit-identity-sync-health"></a>
### <a name="optional-directory-synchronization-is-monitored"></a>Optioneel: adreslijstsynchronisatie wordt bewaakt

U hebt gebruikgemaakt van [Azure AD Connect Health met synchronisatie](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (voor wachtwoordsynchronisatie) of [Azure AD Connect Health gebruiken met AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (voor federatieve verificatie) en Azure AD Connect Health geïmplementeerd. Dit houdt in:

- Installeren van de Azure AD Connect Health-agent op elk van uw on-premises identiteitsservers.
- Gebruikmaken van de Azure AD Connect Health-portal om de status van de doorlopende synchronisatie te controleren.

Als u deze optie overslaat, kunt u de status van de infrastructuur van de op de cloud gebaseerde identiteit nauwkeuriger vaststellen.

[Stap 4](../identity-add-user-accounts.md#identity-sync-health) kan u bij deze optie desgewenst helpen.

#### <a name="how-to-test"></a>Testen
De Azure AD Connect Health-portal toont de huidige en juiste status van uw on-premises domeincontrollers en de doorlopende synchronisatie.


<a name="crit-identity-pw-writeback"></a>
### <a name="optional-password-writeback-is-enabled-for-your-users"></a>Optioneel: Wachtwoord terugschrijven is ingeschakeld voor uw gebruikers

U hebt de instructies in [Azure AD SSPR met wachtwoord terugschrijven](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) gebruikt om wachtwoord terugschrijven in te schakelen voor de Azure AD-tenant van uw Microsoft 365 Enterprise-abonnement.

Als u deze optie overslaat, moeten gebruikers die niet zijn verbonden met uw on-premises netwerk, hun AD DS-wachtwoorden opnieuw laten instellen of ontgrendelen door een IT-beheerder.

[Stap 4](../identity-add-user-accounts.md#identity-pw-writeback) kan u bij deze optie desgewenst helpen.

>[!Note]
>Wachtwoord terugschrijven is vereist om volledig gebruik te kunnen maken van de functies van Azure AD Identity Protection, zoals vereisen dat gebruikers hun on-premises wachtwoorden moeten wijzigen wanneer Azure AD een hoog risico op inbreuk van accounts heeft gedetecteerd.
>

#### <a name="how-to-test"></a>Testen

U test wachtwoord terugschrijven door uw wachtwoord te wijzigen in Office 365. U moet uw account en het nieuwe wachtwoord kunnen gebruiken om toegang te krijgen tot on-premises AD DS-resources.

1. Maak een testgebruikersaccount in uw on-premises AD DS, sta adreslijstsynchronisatie toe en verleen vervolgens een Microsoft 365 Enterprise-licentie in het Microsoft 365-beheercentrum.
2. Meld u vanaf een externe computer die lid is van uw on-premises AD DS-domein aan bij de computer en de Office-portal met de referenties van het testgebruikersaccount.
3. Selecteer **Instellingen > Office 365-instellingen > Wachtwoord > Wachtwoord wijzigen**.
4. Typ het huidige wachtwoord, typ een nieuw wachtwoord en bevestig het.
5. Meld u af bij de Office-portal en de externe computer en meld u vervolgens bij de computer aan met het testgebruikersaccount en het nieuwe wachtwoord. Dit betekent dat u het wachtwoord van een on-premises AD DS-gebruikersaccount kunt wijzigen met behulp van de Azure AD-tenant.

#### <a name="how-to-test"></a>Testen

Meld u aan bij de Office 365-portal met de naam van uw gebruikersaccount en Azure Multi-Factor Authentication. U ziet nu de aangepaste huisstijlelementen op de aanmeldingspagina.


<a name="crit-identity-self-service-groups"></a>
### <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-microsoft-365-groups"></a>Optioneel: self-servicegroepsbeheer is ingeschakeld voor specifieke Azure AD-beveiligingsgroepen en Microsoft 365-groepen

U hebt vastgesteld welke groepen geschikt zijn voor self-servicebeheer, de eigenaren ervan geïnstrueerd over workflow en verantwoordelijkheden van groepsbeheer, en voor die groepen [self-servicebeheer ingesteld in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

Als u deze optie overslaat, moeten alle groepsbeheertaken van Azure AD door IT-beheerders worden uitgevoerd.

[Stap 5](../identity-use-group-management.md#identity-self-service-groups) kan u bij deze optie desgewenst helpen.

#### <a name="how-to-test"></a>Testen
1.  Maak een testgebruikersaccount in Azure AD via Azure Portal.
2.  Meld u aan met het testgebruikersaccount en maak een Azure AD-beveiligingstestgroep.
3.  Meld u af en meld u vervolgens aan met uw IT-beheerdersaccount.
4.  Configureer de beveiligingstestgroep test voor self-servicebeheer voor het testgebruikersaccount.
5.  Meld u af en meld u vervolgens aan met uw testgebruikersaccount.
6.  Gebruik Azure Portal om leden toe te voegen aan de beveiligingstestgroep.
7.  Verwijder de beveiligingstestgroep en het testgebruikersaccount.

<a name="crit-identity-dyn-groups"></a>
### <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a>Optioneel: met de instellingen van het dynamische groepslidmaatschap worden gebruikersaccounts automatisch aan groepen toegevoegd op basis van kenmerken van gebruikersaccounts

U hebt de set met dynamische Azure AD-groepen vastgesteld en de instructies in [Op kenmerken gebaseerd dynamisch groepslidmaatschap in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) gebruikt voor het maken van de groepen en regels waarmee de set kenmerken van het gebruikersaccount en waarden voor het groepslidmaatschap worden vastgesteld.

Als u deze optie overslaat, moet groepslidmaatschap handmatig worden uitgevoerd wanneer er nieuwe accounts worden toegevoegd of als de kenmerken van gebruikersaccounts in de loop der tijd veranderen. Als iemand bijvoorbeeld van de afdeling Verkoop naar de afdeling Boekhouding overstapt, moet u het volgende doen:

- Werk de waarde van het kenmerk Afdeling voor dat gebruikersaccount bij.
- Verwijder deze handmatig uit de groep Verkoop.
- Voeg deze handmatig toe aan de groep Boekhouding.

Als de groepen Verkoop en Boekhouding dynamisch zouden zijn, zou u alleen de waarde Afdeling van het gebruikersaccount hoeven te wijzigen.

[Stap 5](../identity-use-group-management.md#identity-dyn-groups) kan u bij deze optie desgewenst helpen.

#### <a name="how-to-test"></a>Testen

1. Maak een dynamische testgroep in Azure AD via Azure Portal en configureer een regel voor Afdeling die gelijk is aan 'test1'.
2. Maak een testgebruikersaccount in Azure AD en stel de eigenschap Afdeling in op 'test1'.
3. Bekijk de eigenschappen van het gebruikersaccount om te controleren of het nu een lid is van de dynamische testgroep.
4. Wijzig de waarde van de eigenschap Afdeling voor het testgebruikersaccount in 'test2'.
5. Bekijk de eigenschappen van het gebruikersaccount om te controleren of het niet langer een lid is van de dynamische testgroep.
6. Verwijder de dynamische testgroep en het testgebruikersaccount.

<a name="crit-identity-group-license"></a>
### <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a>Optioneel: licenties op basis van groepen om automatisch licenties toe te wijzen aan en te verwijderen uit gebruikersaccounts op basis van groepslidmaatschap

U hebt [licenties toewijzen op basis van groepen ingeschakeld](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) voor de desbetreffende Azure AD-beveiligingsgroepen, zodat uw Microsoft 365 Enterprise-licenties automatisch worden toegewezen (of dat toegewezen licenties ongedaan worden gemaakt).

Als u deze optie overslaat, moet u het volgende handmatig doen:

- Wijs licenties toe aan nieuwe gebruikers aan wie u toegang wilt verlenen.
- Maak de toewijzing ongedaan van licenties aan gebruikers die niet langer deel uitmaken van uw organisatie en geen toegang hebben.

[Stap 5](../identity-use-group-management.md#identity-group-license) kan u bij deze optie desgewenst helpen.

#### <a name="how-to-test"></a>Testen

1. Maak een beveiligingstestgroep in Azure AD via Azure Portal en configureer op groepen gebaseerde licenties om licenties voor Microsoft 365 Enterprise toe te wijzen.
2. Maak een testgebruikersaccount in Azure AD en voeg het toe aan de beveiligingstestgroep.
3. Bekijk de eigenschappen van het gebruikersaccount in het Microsoft 365-beheercentrum om te controleren of het aan de Microsoft 365 Enterprise-licentie is toegewezen.
4. Verwijder het testgebruikersaccount uit de beveiligingstestgroep.
5. Bekijk de eigenschappen van het gebruikersaccount om te controleren of de Microsoft 365 Enterprise-licentie er niet langer aan is toegewezen.
6. Verwijder de beveiligingstestgroep en het testgebruikersaccount.


<a name="crit-identity-access-reviews"></a>
### <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a>Optioneel: toegangsbeoordelingen die zijn geconfigureerd en worden gebruikt om toegang te bewaken

U hebt deze artikelen gebruikt om verschillende soorten toegangsbeoordelingen te configureren om groepslidmaatschappen, toegang tot bedrijfstoepassingen en roltoewijzingen te beheren:

- [Groepen en apps](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD-rollen](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure-resourcerollen](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

[Stap 6](../identity-configure-identity-governance.md#identity-access-reviews) kan u bij deze optie desgewenst helpen.
