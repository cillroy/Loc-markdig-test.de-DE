<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Anforderungen an die Anmeldeinformationen für Azure AD und Intune

Authentifizierung und Autorisierung basieren auf Azure AD-Anmeldeinformationen und rollenbasierter Zugriffssteuerung über Intune (RBAC). Alle globalen Administratoren und Intune-Serviceadministratoren für Ihren Mandanten haben standardmäßig Zugriff auf das Data Warehouse. Verwenden Sie Intune-Rollen, um den Zugriff für mehr Benutzer bereitzustellen, indem Sie Ihnen Zugriff auf die **Reporting resource** (Berichtsressource) gewähren.

Anforderungen für den Zugriff auf das Intune Data Warehouse (einschließlich der API):

  -  Intune-Lizenz muss dem Benutzer zugewiesen sein
  -  Benutzer muss eine der folgenden Rollen innehaben:
      -  Globaler Azure AD-Administrator
      -  Intune-Dienstadministrator
      -  Benutzer mit rollenbasiertem Zugriff auf die Ressource **Reports** (Berichte)