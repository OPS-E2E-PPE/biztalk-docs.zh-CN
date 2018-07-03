---
title: 准备灾难恢复 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14c2c25d-30c5-4e90-a744-f084befa2c1d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f9d806f3f757200e425b2f922032cb8f8d26bc6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981566"
---
# <a name="preparing-the-disaster-recovery-biztalk-servers"></a>准备灾难恢复 BizTalk Server
安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在按照中的建议进行灾难恢复站点的运行时服务器[BizTalk Server 2010 安装和升级指南](http://go.microsoft.com/fwlink/?LinkID=194815)(<http://go.microsoft.com/fwlink/?LinkID=194815>)。 配置这些[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 BizTalk 配置向导以将它们加入到生产 BizTalk 组的运行时服务器。 配置时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在灾难恢复站点 （包括灾难恢复企业单一登录主密钥服务器） 的运行时服务器，请确保为：  
  
- 选择**否**"这是主密钥服务器？"问题  
  
- 选择**联接**问题"是否要创建或加入 BizTalk Server 组？"  
  
  配置后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行灾难恢复服务器的对应于生产站点主机实例，但不是会启动这些主机实例的灾难恢复站点上创建 BizTalk 主机实例。 例如，如果生产站点具有三个主机**发送**，**接收**，并**业务流程**上 server1 和 server2，server3 实例，创建了三个相对应DRserver1，DRserver2，DRserver3 上的主机实例。  
  
> [!NOTE]
>  所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的相关 Windows 服务等的 BizTalk 主机实例和在灾难恢复站点的规则引擎服务应设置为"已禁用"在服务管理器以防止执行任何处理灾难恢复站点。  
  
 可以安装和配置不同数目的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]灾难恢复站点不是在生产中运行的运行时服务器。 但是，采用这种方法，以避免重载灾难恢复站点中的服务器，如果发生灾难恢复事件时要格外小心。 完全还原的数据库集所表示该 BizTalk 组，并执行所有必需的系统更改为 BizTalk 组后，可以运行脚本以加入[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 BizTalk 组的运行时服务器。