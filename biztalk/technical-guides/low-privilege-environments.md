---
title: 低特权环境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: abdc45d0-b63a-4b6c-80c4-1f8e87644cd9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 121655ecb70c084637f2fd481dc6bd2fce7a57cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396295"
---
# <a name="low-privilege-environments"></a>低特权环境
多个工作流所含[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包需要提升的权限来执行某些操作。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理包，可在低特权环境中执行基本的监视功能。 有两种管理角色： BizTalk Server 管理器和 BizTalk Server 操作员。 BizTalk Server 管理员是高权限角色，有权访问配置数据和跟踪数据。 BizTalk Server 管理员可以执行所有密钥管理任务，此类登记和启动项目。 BizTalk Server 操作员是低权限角色，仅有权监视和故障排除操作。 有关详细信息，请参阅[最低安全用户权限](http://technet.microsoft.com/library/aa559845\(BTS.80\).aspx)。  
  
 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包：  
  
-   BizTalk Server Operators 组的成员可以执行以下操作：  
  
    -   发生错误，查询挂起的消息 \ 实例，查看配置的监视器 BizTalk Server。  
  
    -   监视 BizTalk Server 安装和项目。  
  
    -   查看服务状态和消息流。  
  
    -   启动或停止应用程序和项目，例如业务流程、 发送端口或发送端口组处于登记状态。  
  
    -   启用或禁用接收位置。 更改不会生效直到下一步的缓存刷新间隔为 60 秒，这是默认设置。 在 BizTalk Server 组级别设置缓存刷新间隔。  
  
-   BizTalk Server Operators 组的成员不能执行以下操作：  
  
    -   修改 BizTalk Server 的配置。  
  
    -   查看被归类为个人身份信息 (PII) 或消息正文的消息上下文属性。  
  
    -   修改消息路由，例如删除或将新的订阅添加到正在运行的系统，包括能够将消息发布到 BizTalk Server 运行时的过程。  
  
> [!NOTE]  
>  若要执行如重新启动 BTSNTSvc.exe 服务的管理包提供的所有监视任务，必须是 BizTalk 服务器上的本地管理员组的成员。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [监视](../technical-guides/monitoring.md)  
  
-   [发现](../technical-guides/discoveries.md)