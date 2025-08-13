# Structure des dossiers

## Structure globale

<note>Un projet comporte deux parties distinctes, le code du framework ainsi que le code source de l'utilisateur.</note>

- <code>EagleCore</code> dossier contenant l'entièreté du framework
- <code>Src</code> dossier contenant les sources utilisateur
- <code>.htaccess</code> fichier servant à la redirection de routing
- <code>composer.json + composer.lock</code> fichiers du gestionnaire composer
- <code>configs</code> contient les différents fichiers de configuration du framework
- <code>public</code> contient les ressources publiques de l'application
- <code>eagle</code> utilitaire de ligne de commandes <note>ce fichier est un fichier php sans l'extension</note>

## Focus sur le dossier *Src*

- <code>Controllers</code> contient les différents 'controllers' de l'application
  <note>L'emplacement des 'controllers' dépend de l'auto-loading psr-4</note>
- <code>Models</code> contient les différents 'models' de l'application
    <note>L'emplacement des 'models' dépend de l'auto-loading psr-4</note>
- <code>Routes</code> contient les fichiers d'enregistrement des routes de l'application
- <code>storage</code> dossier de stockage interne de l'application
- <code>Treatment</code> contient les class de traitement d'actions
- <code>views</code> contient les éléments de (vue, mails) 
