---
title: 冲突的绑定属性 |Microsoft Docs
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
ms.openlocfilehash: cacdbd24b6c9dd72ab1e123cc5990ba35d274c30
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354955"
---
# <a name="conflicting-binding-properties"></a>绑定属性冲突
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                    |
| 产品版本 |                                               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                |
|    事件 ID     |                                                                            0                                                                            |
|  事件源   |                                                                            0                                                                            |
|    组件    |                                                                            0                                                                            |
|  符号名称  |                                                                            0                                                                            |
|  消息正文   | 绑定属性冲突：MsmqAuthenticationMode ={0}和 MsmqProtectionLevel ={1}无效。 更改其中一个属性来解决冲突 |
  
## <a name="explanation"></a>解释  
 Wcf-netmsmq 传输的 MSMQ 保护级别属性设置为**符号**或**EncryptAndSign**为无 MSMQ 身份验证模式。  
  
## <a name="user-action"></a>用户操作  
 更改 MSMQ 保护级别或 MSMQ 身份验证模式属性以与 MSMQ 保护级别属性保持一致。  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在中**Wcf-netmsmq 传输属性**对话框中，单击**安全**选项卡。  
  
9. 检查在 MSMQ 中的值**身份验证模式**列表和**MSMQ 保护级别**列表。  
  
   有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  
  
-   [如何配置 Wcf-netmsmq 发送端口](../core/how-to-configure-a-wcf-netmsmq-send-port.md)  
  
-   [如何配置 Wcf-netmsmq 接收位置](../core/how-to-configure-a-wcf-netmsmq-receive-location.md)