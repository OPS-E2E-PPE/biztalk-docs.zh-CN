---
title: 在业务流程管理解决方案中有效使用 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, process management solutions
- SSO, configuration values
- caching, configuration values [SSO]
- SSO, caching
- process management solution tutorial, SSO
ms.assetid: 39fbc42d-caa4-4003-a13b-5cde578eb5e1
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eda9b88ceb99e6487562ecc03f8f7009b09f533e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321679"
---
# <a name="using-sso-efficiently-in-the-business-process-management-solution"></a>在业务流程管理解决方案中有效使用 SSO
面向服务的解决方案，如业务流程管理解决方案使用企业单一登录 (SSO) 来存储配置值，例如订单处理阶段数。 它使用机密存储，因为它是只要安装 BizTalk 就存在，SSO 将缓存配置信息，以便值随时可用，并且它可以保护数据库连接字符串和密码等信息。 所有这些原因，密钥存储区是配置信息的好地方即使单一登录不用于管理指向后端应用程序的连接。  
  
 若要减少延迟，解决方案时，可使用本地缓存来存储配置值。 该解决方案在每隔五分钟刷新的缓存。  
  
 本主题介绍该解决方案使用的缓存机制。 此解决方案采用稍有不同的方法来 SSO 缓存面向服务的解决方案。 有关如何面向服务的解决方案的说明将缓存 SSO 值，请参阅[面向服务的解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-service-oriented-solution.md)。  
  
## <a name="caching-configuration-values-locally"></a>本地缓存配置值  
 业务流程管理解决方案使用单一对象的属性来提供对 SSO 值的访问。  
  
> [!NOTE]
>  请注意，单一实例对象是一个对象，可以只有一个实例。 有关单一对象和中创建它们的详细信息C#，请参阅[ http://go.microsoft.com/fwlink/?LinkId=58806 ](http://go.microsoft.com/fwlink/?LinkId=58806)。  
  
 在解决方案中，业务流程首先检索单一对象，然后引用通过对象的属性的值。 下面是从代码**OrderManager**业务流程：  
  
```  
configData = Microsoft.Samples.BizTalk.SouthridgeVideo.Utilities  
                .SsoConfigHelper.Singleton;  
numStages = configData.TotalStages;  
```  
  
 业务流程调用**Singleton**方法**SsoConfigHelper**对象有权访问的对象的一个副本。 手中的对象，该业务流程检索处理阶段数**TotalStages**。  
  
 该解决方案按照通用方法来创建单一实例： 将构造函数设置为私有，要求该对象创建自身的实例和将其分配给私有变量，并通过方法或属性，提供对该变量的值的访问。 **SsoConfigHelper**对象使用一个属性**单独**，以提供对其自身的单个副本的访问权限。  
  
> [!NOTE]
>  **SsoConfigHelper**对象使用静态构造函数来从 SSO 缓存中获取的初始值并设置刷新机制。 由于不能调用静态构造函数，它将保留单一设计。 有关静态构造函数的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=59142 ](http://go.microsoft.com/fwlink/?LinkId=59142)。  
  
 业务流程引用，无论是直接还是间接的所有对象必须都可序列化。 详细信息，请参阅"序列化"中[持久化和业务流程引擎](../core/persistence-and-the-orchestration-engine.md)。 尽管**SsoConfigHelper**对象是一定是可序列化，如果引擎冻结业务流程中，当业务流程解除冻结后，将仍然使用单个对象的当前实例。 有关序列化和 BizTalk Server 变量的详细信息，请参阅[业务流程变量类型](../core/orchestration-variable-types.md)。  
  
> [!NOTE]
>  面向服务的解决方案中的对象上的所有公共方法是静态的。 因此该业务流程不需要将实例分配给一个变量，并且没有要进行序列化的类不需要。  
  
 **SsoConfigHelper**对象使用的相同机制来检索和刷新配置值，如面向服务的解决方案。 此外使用相同的锁定模式。 有关这些机制的详细信息，请参阅[面向服务的解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-service-oriented-solution.md)和的源代码**SsoConfigHelper**。  
  
 在面向服务的解决方案中执行单一登录缓存，如业务流程管理解决方案实现**IPropertyBag**接口从**Microsoft.BizTalk.SSOClient.Interop**命名空间来存储的值。 使用业务流程管理解决方案**HybridDictionary**对象而非**NameValueCollection**对象。  
  
 与面向服务的解决方案，不同的业务流程管理解决方案公开的对象具有对应于配置数据的属性。 这样，业务流程就不必处理消息类型之间的差异。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案的实施重点](../core/implementation-highlights-of-the-business-process-management-solution.md)