---
title: 准备灾难恢复 BizTalk 服务器 |Microsoft 文档
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
ms.openlocfilehash: 9379136f0845c7c4c987170747a28bd3c50206c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302141"
---
# <a name="preparing-the-disaster-recovery-biztalk-servers"></a>准备灾难恢复 BizTalk 服务器
安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在灾难恢复站点按照中的建议的运行时服务器[BizTalk Server 2010 安装和升级指南](http://go.microsoft.com/fwlink/?LinkID=194815)(http://go.microsoft.com/fwlink/?LinkID=194815)。 配置这些[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 BizTalk 配置向导以将它们加入到生产 BizTalk 组的运行时服务器。 配置时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在灾难恢复站点 （包括灾难恢复企业单一登录在主密钥服务器） 的运行时服务器，请确保为：  
  
-   选择**否**问题"这是主密钥服务器？"  
  
-   选择**联接**问题"是否要创建或加入 BizTalk Server 组？"  
  
 配置后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时灾难恢复服务器，请在对应于生产站点主机实例，但不是会开始这些主机实例的灾难恢复站点上创建 BizTalk 主机实例。 例如，如果生产站点具有三个主机**发送**，**接收**，和**Orchestration**上 server1 和 server2，服务器 3 的实例，创建三个对应DRserver1，DRserver2，DRserver3 上的主机实例。  
  
> [!NOTE]  
>  所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的相关 Windows 服务，如 BizTalk 主机实例和在灾难恢复站点的规则引擎服务应设置为"已禁用"在服务管理器以防止灾难恢复站点执行任何处理。  
  
 你可以安装和配置不同数量的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在灾难恢复站点不是在生产中运行的运行时服务器。 但是，采用这种方法，以避免重载灾难恢复站点中的服务器，如果发生灾难恢复事件时要格外小心。 一旦完全还原 BizTalk 组所表示的组的数据库，并且所有所需的系统更改执行 BizTalk 组，可以运行脚本以加入[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 BizTalk 组的运行时服务器。