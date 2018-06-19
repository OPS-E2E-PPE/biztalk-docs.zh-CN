---
title: 在业务流程管理解决方案中有效地使用 SSO |Microsoft 文档
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
ms.openlocfilehash: 99575e54b887124bfa4c33fc5257cd057ea818fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288517"
---
# <a name="using-sso-efficiently-in-the-business-process-management-solution"></a>在业务流程管理解决方案中有效地使用 SSO
与面向服务的解决方案类似，业务流程管理解决方案使用企业单一登录 (SSO) 来存储配置值，例如订单处理阶段数。 由于只要安装 BizTalk 就会存在密钥存储区，因此该解决方案将使用密钥存储区；SSO 将缓存配置信息以便随时可以使用这些值，并且可以保护诸如数据库连接字符串和密码之类的信息。 由于上述这些原因，因此密钥存储区是配置信息的适当位置，即使不将单一登录用于管理指向后端应用程序的连接。  
  
 为缩短延迟时间，该解决方案使用本地缓存来存储配置值。 该解决方案每隔五分钟刷新一次缓存。  
  
 本主题将介绍该解决方案使用的缓存机制。 此解决方案采用的 SSO 缓存方法与面向服务的解决方案采用的方法略有不同。 有关如何面向解决方案服务的说明缓存 SSO 值，请参阅[服务面向解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-service-oriented-solution.md)。  
  
## <a name="caching-configuration-values-locally"></a>在本地缓存配置值  
 业务流程管理解决方案使用单一对象的属性来提供对 SSO 值的访问。  
  
> [!NOTE]
>  请注意，单一对象是只能具有一个实例的对象。 有关单一实例对象并在 C# 中创建它们的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=58806](http://go.microsoft.com/fwlink/?LinkId=58806)。  
  
 在解决方案中，业务流程首先检索单一实例对象，并随后引用通过对象的属性的值。 以下是从代码**OrderManager**业务流程：  
  
```  
configData = Microsoft.Samples.BizTalk.SouthridgeVideo.Utilities  
                .SsoConfigHelper.Singleton;  
numStages = configData.TotalStages;  
```  
  
 业务流程调用**Singleton**方法**SsoConfigHelper**对象才能访问对象的一个副本。 业务流程与中现有对象，检索的数目处理阶段**TotalStages**。  
  
 解决方案遵循创建单一实例的常见方法： 将设为私有构造函数，必须创建自身的一个实例和分配给一个私有变量，并通过方法或属性中，提供该变量的值的访问的对象。 **SsoConfigHelper**对象使用属性， **Singleton**，以提供对其自身的单个副本的访问。  
  
> [!NOTE]
>  **SsoConfigHelper**对象使用的静态构造函数来从 SSO 缓存中获取初始值以及设置刷新机制。 由于无法调用静态构造函数，因此该函数将保留单一设计。 有关静态构造函数的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=59142](http://go.microsoft.com/fwlink/?LinkId=59142)。  
  
 业务流程引用（无论是直接还是间接引用）的所有对象都必须是可序列化的。 有关详细信息，请参阅"序列化"[持久性和业务流程引擎](../core/persistence-and-the-orchestration-engine.md)。 尽管**SsoConfigHelper**对象是一定可序列化，如果引擎 dehydrates 业务流程，当它仍将业务流程 rehydrates 使用单个对象的当前实例。 有关序列化和 BizTalk Server 变量的详细信息，请参阅[Orchestration 变量类型](../core/orchestration-variable-types.md)。  
  
> [!NOTE]
>  面向服务的解决方案中的对象上的所有公共方法都是静态的。 因此，该业务流程不需要向变量分配实例，也不需要对类进行序列化。  
  
 **SsoConfigHelper**对象使用了相同的机制来检索和面向服务解决方案一样刷新配置值。 也使用相同的锁定模式。 有关这些机制的详细信息，请参阅[服务面向解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-service-oriented-solution.md)和的源代码**SsoConfigHelper**。  
  
 业务流程管理解决方案上单一登录缓存在面向服务解决方案中执行，如实现**IPropertyBag**接口从**Microsoft.BizTalk.SSOClient.Interop**命名空间来存储的值。 业务流程管理解决方案使用**HybridDictionary**对象而不是**NameValueCollection**对象。  
  
 与面向服务的解决方案不同，业务流程管理解决方案公开了一个具有对应于配置数据的属性的对象。 这样，业务流程就不必处理消息类型之间的差异。  
  
## <a name="see-also"></a>另请参阅  
 [实现突出显示的业务流程管理解决方案](../core/implementation-highlights-of-the-business-process-management-solution.md)