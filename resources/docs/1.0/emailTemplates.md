# BlueRockTEL
---

# Emails types

BlueRockTEL vous permet de configurer des emails types, qui seront ensuite intégrés à vos suivis d'installation.

## Variables disponibles

Dans vos modèles types, vous pouvez utiliser des variables des modèles **suivi d'installation (customerFileSetup)**, **dossier de facturation (customerFile)** et **client (customer)**.

Pour accéder à une variable à l'intérieur d'un modèle, la syntaxe à utiliser est de type :

```
{ { $model->variable } } 
```

Par exemple, pour afficher la variable 'site' du modèle 'customerFile', vous devrez écrire ;

```
 { { $customerFile->site } } 
```

Une particularité concernant les dates, vous pourrez les formater de la façon qui vous convient, par exemple : 

```
{ { $customerFileSetup->portabilityDate } } 
```

### Suivi d'installation (customerFileSetup)

**requestedInstallationDate** : date d'installation demandée ou prévue

**portabilityDate** : date de portabilité

**deliveryDate** : date de livraison

**nextActionDate** : date de la prochaine action dans le process

### Dossier de facturation (customerFile)

**site** : nom du site identifiant le dossier

**siteId** : identifiant du site (par exemple un code ayant une signification pour votre client)

**addressLine1** : première ligne d'adresse du site

**addressLine2** : seconde ligne d'adresse du site

**postalCode** : code postal

**city** : ville

**country** : pays

**mandateIdentification** : référence du mandat de prélèvement bancaire mis en place au niveau du dossier

**mandateSignatureDate** : date de signature du mandat de prélèvement

**servicesStart** : date de début des services (au niveau du dossier, sachant que les services peuvent individuellement avoir des dates de début différentes)

**servicesStop** : date de fin des services (au niveau du dossier, sachant que les services peuvent individuellement avoir des dates de fin différentes)

**billingFrequency** : fréquence de facturation (nombre entier représentant le nombre de mois entre 2 factures)

**credit** : solde créditeur du dossier client

### Client (customer)

**brand** : si vous gérez plusieurs marques dans l'application, la marque dont dépend votre client,

**customerAccount** : le compte client

**accountsReference** : le compte comptable

**registrationNumber** : le numéro d'identification de l'entreprise cliente (SIRET en France)

**taxRegistrationNumber** : le numéro de TVA intracommunautaire de l'entreprise cliente

**mainContactFirstName** : le prénom du contact principal de l'entreprise cliente,

**mainContactLastName** : le nom du contact principal de l'entreprise cliente,

**type** : le type d'entreprise

**capital** : le capital de l'entreprise

**activityCode** : le code d'activité de l'entreprise cliente (NAF ou APE en France)

**mainAddressLine1** : première ligne d'adresse

**mainAddressLine2** : seconde ligne d'adresse

**mainAddressPostalCode** : code postal

**mainAddressCity** : ville

**mainAddressCountry** : pays

**emailAddress** : adresse email principale de l'entreprise

**website** : adresse du site Web de l'entreprise

**phone** : numéro de téléphone principal de l'entreprise

**fax** : numéro de fax

