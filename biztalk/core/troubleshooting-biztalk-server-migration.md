---
title: BizTalk Server 迁移疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6eddc0a-2403-4bcd-9327-23f51ce7d57b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 931dd72f3c6ffc73209fca61a1c75becd30151c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398680"
---
# <a name="troubleshooting-biztalk-server-migration"></a>BizTalk Server 迁移疑难解答
本部分提供有关从应用程序迁移 BizTalk 时遇到的常见问题的信息的一个集中的位置[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2009 升级到 BizTalk Server。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="custom-applications-might-not-work-while-upgrading"></a>自定义应用程序可能无法工作时升级  
  
##### <a name="problem"></a>问题  
 从升级时[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2009 升级到 BizTalk Server 中，某些自定义应用程序可能无法工作。  
  
##### <a name="cause"></a>原因  
 所有 BizTalk 都托管代码组件在 CLR 4.0 上运行。 这些组件编译针对[!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]，他们需要一个配置文件用于在 CLR 4.0 上运行。  
  
##### <a name="solution"></a>解决方案  
 若要解决此问题，请更新配置文件。  
  
```  
<configuration>  
<startup useLegacyV2RuntimeActivationPolicy="true">  
<supportedRuntime version="v4.0" />  
</startup>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 [故障排除](../core/troubleshooting.md)