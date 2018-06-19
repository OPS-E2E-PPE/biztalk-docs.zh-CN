---
title: 冲突的绑定属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b08c317e-a617-464b-9ee4-007fb41d99b2
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6202385127a676d1f2714b2c3644d135a3d6a7a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233237"
---
# <a name="conflicting-binding-properties"></a>绑定属性冲突
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|冲突的绑定属性： MsmqAuthenticationMode = {0} 和而 MsmqProtectionLevel = \ {1 \} 无效。 更改其中一个属性可解决冲突|  
  
## <a name="explanation"></a>解释  
 WCF NetMsmq 传输的 MSMQ 保护级别属性设置为**登录**或**EncryptAndSign**为无 MSMQ 身份验证模式。  
  
## <a name="user-action"></a>用户操作  
 将“MSMQ 保护级别”或“MSMQ 身份验证模式”属性更改为与“MSMQ 保护级别”属性一致。  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  找到应用程序，然后找到您的传输。  
  
4.  右键单击传输名称。  
  
5.  单击 **“属性”**。  
  
6.  在端口**类型**列表中，选择正确的端口。  
  
7.  单击**配置**。  
  
8.  在**WCF NetMsmq 传输属性**对话框中，单击**安全**选项卡。  
  
9. 检查 MSMQ 中的值**身份验证模式**列表和**MSMQ 保护级别**列表。  
  
 有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  
  
-   [如何配置 WCF NetMsmq 发送端口](../core/how-to-configure-a-wcf-netmsmq-send-port.md)  
  
-   [如何配置 WCF NetMsmq 接收位置](../core/how-to-configure-a-wcf-netmsmq-receive-location.md)