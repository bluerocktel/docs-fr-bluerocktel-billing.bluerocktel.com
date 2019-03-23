Les emails types de [BlueRockTEL](https://fr.bluerocktel.com) sont des modèles d'emails que vous pouvez appeler depuis vos installations types. Un cas courant : le fait de renseigner la date de portabilité du dossier envoie automatiquement un email d'information au client.

## Création des emails types et insertion de variables

Vous pourrez accéder aux emails types depuis le menu "Configuration / Emails types". Depuis l'index, vous pouvez créer un nouvel email type, éditer ou supprimer un modèle existant. Il est également possible de dupliquer un email type, ce qui permet de gagner du temps de configuration.

![Emails types BlueRockTEL : vue générale](http://assets.bluerocktel.net/images/emailTemplates-index-fr.png)

Outre le texte de l'email type, vous devrez configurer les destinataires, à la fois dans votre entreprise et dans l'entreprise cliente. Dans votre entreprise, il peut s'agir du technicien, du commercial ou de l'ADV en charge du dossier, mais également du manager de facturation ou du manager technique. Dans l'entreprise cliente, il peut s'agir des destinataires des factures, des contacts techniques ou des signataires du contrat.

![Emails types BlueRockTEL : détail](http://assets.bluerocktel.net/images/emailTemplates-edit2-fr.png)

Pour personnaliser vos emails types, vous pouvez insérer des variables provenant des modèles :   
* Client (customer)
* Dossier de Facturation (customerFile)
* Suivi d'installation (customerFileSetup)
* Organisation (organisation)

Pour appeler une variable d'un modèle, la syntaxe à utiliser est de type:

```
{ { $model->variable } }
``` 

Par exemple, pour appeler la variable 'site' du modèle 'customerFile', vous écrirez dans votre email type : 

```
{ { $customerFile->site } }
``` 

Vous pourrez formater les dates de la façon qui vous convient le mieux, par exemple :

```
Nous vous confirmons votre date de portabilité le { { $customerFileSetup->portabilityDate->format('d/m/Y') } }
```

ou, si vous voulez indiquer le jour et l'heure :

```
Nous vous confirmons votre date de portabilité le { { $customerFileSetup->portabilityDate->format('d/m/Y') } } à { { $customerFileSetup->portabilityDate->format('H:i') } }
```

## Lexique des variables disponibles

### Modèle "Client" (customer)

* **brand** : marque dont dépend votre client, si vous avez configuré plusieurs marques dans BlueRockTEL (branding)
* **name** : raison sociale du client
* **customerAccount** : compte client, par défaut de type "CL001"
* **accountsReference** : compte client en comptabilité, si différente
* **registrationNumber** : numéro d'identification de l'entreprise, SIRET en France
* **taxRegistrationNumber** : numéro de TVA intracommunautaire
* **mainContactFirstName** : prénom du contact principal de l'entreprise cliente
* **mainContactLastName** : nom du contact principal
* **type** : type d'entreprise
* **capital** : capital de l'entreprise
* **activityCode** : code activité
* **mainAddressLine1** : première ligne de l'adresse postale
* **mainAddressLine2** : seconde ligne de l'adresse
* **mainAddressPostalCode** : code postal
* **mainAddressCity** : ville
* **mainAddressCountry** : pays
* **emailAddress** : adresse email principale de l'entreprise
* **website** : site web
* **phone** : téléphone
* **fax** : fax

### Modèle "Dossier de facturation" (customerFile)

* **site** : site installé
* **siteId** : un identifiant du site, le cas échéant, souvent une information provenant du client lui-même
* **addressLine1** : première ligne de l'adresse postale du site
* **addressLine2** : seconde ligne de l'adresse
* **postalCode** : code postal
* **city** : ville
* **country** : pays
* **mandateIdentification** : référence unique du mandat (RUM) sur lequel les prélèvements bancaires SEPA seront effectués
* **mandateSignatureDate** : date de signature du mandat SEPA
* **servicesStart** : date de début des services (au niveau du dossier, sachant que les services peuvent individuellement avoir des dates de début différentes)
* **servicesStop** : date de fin des services (au niveau du dossier, sachant que les services peuvent individuellement avoir des dates de fin différentes)
* **billingFrequency** : nombre de mois représentant la fréquence de facturation du dossier
* **credit** : solde créditeur du dossier client

### Modèle "Suivi d'installation" (customerFileSetup)

* **requestedInstallationDate** : date d'installation demandée puis prévue
* **portabilityDate** : date de portabilité
* **deliveryDate** : date de livraison

### Modèle "Organisation" (organisation)

* **name** : raison sociale
* **registrationNumber** : numéro d'identification de votre entreprise, SIRET en France
* **taxRegistrationNumber** : numéro de TVA intracommunautaire
* **mainContactFirstName** : prénom du contact principal
* **mainContactLastName** : nom du contact principal
* **accountantFirstName** : prénom du comptable
* **accountantLastName** : nom du comptable
* **organisationType** : type d'organisation
* **currency** : devise principale
* **capital** : capital de l'entreprise
* **activityCode** : code activité
* **iban** : votre IBAN
* **bic** : votre BIC
* **ics** : votre identifiant de créancier SEPA
* **mainAddressLine1** : première ligne de votre adresse postale
* **mainAddressLine2** : seconde ligne d'adresse
* **mainAddressPostalCode** : code postal
* **mainAddressCity** : ville
* **mainAddressCountry** : pays
* **website** : site web
* **phone** : téléphone principal de l'entreprise
* **fax** : fax

