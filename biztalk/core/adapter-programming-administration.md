---
title: 适配器编程管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38563b3c-6d52-4e4e-ac6e-74f46ce22c6a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c81d056e9775ec0e9273f01aa11be384f632647
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361344"
---
# <a name="adapter-programming-administration"></a>适配器编程管理
适配器是一种特殊的配置存储应用程序： 即适配器是与其他单一登录和配置应用商店应用程序共享命名空间的组件。 因此，您可以访问有关适配器使用 ISSOConfigStore 的信息。 但与不同的配置应用商店应用程序，您在使用 ISSOAdmin 接口的适配器不执行管理功能。 相反，你管理通过 issopsadmin 来适配器。 专用的适配器管理界面的原因是，以便系统能够协调与配置存储的其他活动。  
  
## <a name="see-also"></a>请参阅  
 [适配器编程配置](../core/adapter-programming-configuration.md)   
 [适配器组和组适配器](../core/adapter-groups-and-group-adapters.md)   
 [密码同步适配器](../core/password-sync-adapters.md)