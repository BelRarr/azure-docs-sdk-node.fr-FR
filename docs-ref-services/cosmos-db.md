---
title: Modules Azure Cosmos DB pour Node.js
description: Références pour les modules Azure Cosmos DB pour Node.js
author: SnehaGunda
ms.author: sngun
manager: kfile
ms.date: 03/20/2018
ms.topic: article
ms.prod: azure
ms.technology: azure
ms.devlang: nodejs
ms.service: Cosmos DB
ms.openlocfilehash: 4064f9f6c0e1369c8d6261a70709102e7492b340
ms.sourcegitcommit: 75051fec38cc3be4cb7d7cb6fc695c162fc0e91b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2018
---
# <a name="azure-cosmos-db-modules-for-nodejs"></a>Modules Azure Cosmos DB pour Node.js

Azure Cosmos DB est un service de base de données multimodèle mondialement distribué de Microsoft. Azure Cosmos DB vous permet de faire évoluer en toute flexibilité et de façon indépendante le débit et le stockage sur n’importe quel nombre de régions géographiques Azure. Il offre des garanties en termes de débit, de latence, de disponibilité et de cohérence avec des contrats SLA complets, ce qu’aucun autre service de base de données ne peut offrir.

Azure Cosmos DB contient un moteur de base de données non basé sur un schéma, régi par les ressources et optimisé pour les écritures. Celui-ci prend en charge plusieurs modèles de données : clé-valeur, documents, graphiques et colonnes. Il prend également en charge de nombreuses API permettant d’accéder aux données, notamment MongoDB, SQL, Gremlin/Graph, Tables Azure et Cassandra (préversion) d’une manière extensible.

## <a name="management-package"></a>Gestion des packages

### <a name="install-the-npm-module"></a>Installer le module npm 

Installer le module npm Azure Cosmos DB.

```bash
npm install azure-arm-documentdb
```

### <a name="example"></a>Exemples

Cet exemple répertorie tous les comptes Azure Cosmos DB.

```javascript
const msRestAzure = require('ms-rest-azure');
const documentDBManagementClient = require('azure-arm-documentdb');

const subscriptionId = 'your-subscription-id';

msRestAzure.interactiveLogin().then(credentials => {
  const documentDbClient = new documentDBManagementClient(credentials, subscriptionId);
  documentDbClient.databaseAccounts
    .list()
    .then(databaseAccounts => console.log('Retrieved database accounts: ', databaseAccounts));
});
```

## <a name="samples"></a>Exemples

* [Développement d’une application Node.js en utilisant Azure Cosmos DB](https://azure.microsoft.com/resources/samples/azure-cosmos-db-documentdb-nodejs-getting-started/)
* [Développement d’une application Node.js en utilisant Azure Cosmos DB - Gremlin](https://azure.microsoft.com/resources/samples/azure-cosmos-db-graph-nodejs-getting-started/)

Découvrez d’autres [exemples de code Node.js](https://azure.microsoft.com/resources/samples/?platform=nodejs) à utiliser dans vos applications.
