---
title: 对实时超时的时间无效 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2ddb6de-8c3b-4dee-a984-980e1caea95e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9171fd311a07317c0480e6e4d1ef35742e0e8bcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262093"
---
# <a name="invalid-time-to-live-timeout"></a>对实时超时的时间无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|对实时超时的时间无效。 有效范围： 0 到 23 小时、 介于 0 和 59 分钟、 和 0 到 59 秒|  
  
## <a name="explanation"></a>解释  
  
## <a name="user-action"></a>用户操作  
 使用以下过程配置超时范围。  
  
#### <a name="to-configure-the-timeout-range"></a>配置超时范围的步骤  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  找到应用程序，然后找到您的传输。  
  
4.  右键单击传输名称。  
  
5.  单击 **“属性”**。  
  
6.  在端口**类型**列表中，选择**WCF NetMsmq**。  
  
7.  单击**配置**。  
  
8.  在**WCF NetMsmq 传输属性**对话框中，单击**绑定**选项卡。  
  
9. 在**队列设置**部分中，确保**消息到实时的 (dd:hh:mm:ss) 的时间**范围是否有效。 可接受的值包括：0 到 23 小时、0 到 59 分钟和 0 到 59 秒。