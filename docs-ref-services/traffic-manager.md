---
title: Modules Azure Traffic Manager pour Node.js
description: Références pour les modules Azure Traffic Manager pour Node.js
author: KumudD
ms.author: kumud
manager: jeconnoc
ms.date: 07/18/2017
ms.topic: article
ms.prod: azure
ms.technology: azure
ms.devlang: nodejs
ms.service: Traffic Manager
ms.openlocfilehash: 904a6693f557b90f5a1eeeea2367b56f8dfe3ff1
ms.sourcegitcommit: 75051fec38cc3be4cb7d7cb6fc695c162fc0e91b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2018
---
# <a name="azure-traffic-manager-modules-for-nodejs"></a>Modules Azure Traffic Manager pour Node.js

## <a name="overview"></a>Vue d'ensemble

Microsoft Azure Traffic Manager vous permet de contrôler la répartition du trafic utilisateur pour les points de terminaison de service dans différents centres de données. Les points de terminaison de service pris en charge par Traffic Manager incluent des machines virtuelles Azure, des applications web et des services cloud. Vous pouvez également utiliser Traffic Manager avec des points de terminaison externes non-Azure.

En savoir plus sur [Azure Traffic Manager](https://docs.microsoft.com/azure/traffic-manager/traffic-manager-overview).

## <a name="management-package"></a>Gestion des packages

### <a name="install-the-npm-module"></a>Installer le module npm

Installer le module npm Azure Traffic Manager

```bash
npm install azure-arm-trafficmanager
```

### <a name="example"></a>Exemples

Cet exemple répertorie tous les gestionnaires de trafic pour un groupe de ressources donné.

```javascript
const msRestAzure = require('ms-rest-azure');
const trafficManager = require('azure-arm-trafficmanager');

const subscriptionId = 'your-subscription-id';

msRestAzure.interactiveLogin().then(credentials => {
  const client = new trafficManager(credentials, subscriptionId);
  const resourceGroupName = 'resource-group-name';
  client.profiles.listAllInResourceGroup(resourceGroupName).then(profiles => {
    profiles.map(profile => {
      console.log(`found profile : ${profile.name}`);
    });
  });
});
```

## <a name="samples"></a>Exemples

Découvrez d’autres [exemples de code Node.js](https://azure.microsoft.com/resources/samples/?platform=nodejs) à utiliser dans vos applications.
