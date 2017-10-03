---
title: "无效的关闭超时 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4510329-9fd9-428f-91a3-d72723e9a5e4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b86a75ab524a91ddf7fab7b6e764557150d55606
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-close-timeout"></a>关闭超时无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|关闭超时值无效。 有效范围： 0 到 23 小时、 介于 0 和 59 分钟、 和 0 到 59 秒。|  
  
## <a name="explanation"></a>解释  
  
## <a name="user-action"></a>用户操作  
 使用以下过程配置超时范围。  
  
#### <a name="to-configure-the-timeout-range"></a>配置超时范围的步骤  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  找到应用程序，然后找到您的传输。  
  
4.  右键单击传输名称。  
  
5.  单击 **“属性”**。  
  
6.  在端口**类型**列表中，选择正确的端口。  
  
7.  单击**配置**。  
  
8.  在**WCF [***传输类型***] 属性**对话框中，单击**绑定**选项卡。  
  
9. 确保超时值范围有效。 可接受的值包括：0 到 23 小时、0 到 59 分钟和 0 到 59 秒。