---
title: "BizTalk Server 迁移的疑难解答 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6eddc0a-2403-4bcd-9327-23f51ce7d57b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ddb6d9780a86183de5a09791de44adda5d57dab
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshooting-biztalk-server-migration"></a>BizTalk Server 迁移疑难解答
本部分提供有关从迁移 BizTalk 应用程序时遇到的常见问题的信息的一个集中的位置[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]给 BizTalk Server 2009。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="custom-applications-might-not-work-while-upgrading"></a>自定义应用程序可能无法升级时  
  
##### <a name="problem"></a>问题  
 从升级时[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]给 BizTalk Server 2009 某些自定义应用程序可能无法工作。  
  
##### <a name="cause"></a>原因  
 所有 BizTalk 都托管在 CLR 4.0 上运行的代码组件。 由于这些组件是针对 [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] 而编译的，所以它们需要有 config 文件才能在 CLR 4.0 上运行。  
  
##### <a name="solution"></a>解决方案  
 若要解决此问题，更新配置文件。  
  
```  
<configuration>  
<startup useLegacyV2RuntimeActivationPolicy="true">  
<supportedRuntime version="v4.0" />  
</startup>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅  
 [故障排除](../core/troubleshooting.md)