---
title: 无效的代理地址 （用于发送处理程序和发送端口） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccedd23e-7d44-4419-b519-e04511e1f176
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdfa5951ed261d3e8bd63811764595d1b7e3858c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330621"
---
# <a name="invalid-proxy-address-for-send-handler-and-send-port"></a>无效的代理地址 （用于发送处理程序和发送端口）
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                             无效的代理地址： {0}                             |
  
## <a name="explanation"></a>解释  
 未提供 WCF 发送处理程序或 WCF 发送端口使用有效的代理地址。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程来配置代理地址。  
  
#### <a name="to-configure-a-proxy-address"></a>若要配置的代理地址  
  
1. 单击**启动**，单击**所有程序**，单击**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**代理**选项卡。  
  
9. 验证中的代理地址**代理设置**部分已正确配置。  
  
   发送端口和发送处理程序的其他信息，请参阅以下资源：  
  
-   [如何配置 Wcf-wshttp 发送端口](../core/how-to-configure-a-wcf-wshttp-send-port.md)  
  
-   [如何配置 Wcf-basichttp 发送端口](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f)  
  
-   [如何配置 wcf-basichttp: Wcf-basichttp 发送处理程序](http://msdn.microsoft.com/library/18dcc616-4732-42f8-bd64-e55a5ebbaa49)  
  
-   [如何配置 Wcf-wshttp 发送处理程序](../core/how-to-configure-a-wcf-wshttp-send-handler.md)  
  
-   [如何配置 Wcf-custom 发送端口](../core/how-to-configure-a-wcf-custom-send-port.md)