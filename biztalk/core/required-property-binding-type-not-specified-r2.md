---
title: 所需的未指定属性绑定类型 (R2) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8e45783-6454-44e2-867e-e30092725f51
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e959b7e3e0a48dea0d18a73a898d2c39bfd576e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267604"
---
# <a name="required-property-binding-type-not-specified-r2"></a>必需的属性绑定类型未指定 (R2)
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                    所需的属性未指定的绑定类型                    |
  
## <a name="explanation"></a>解释  
 配置 Wcf-custom 或 Wcf-customisolated 传输时未设置的绑定类型属性。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程配置绑定类型属性。  
  
#### <a name="to-configure-the-binding-type-property"></a>若要配置的绑定类型属性  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在中**WCF-[**<em>传输类型</em>**] 传输属性**对话框中，单击**绑定**选项卡。  
  
9. 中指定一个值**绑定类型**列表。  
  
   有关配置绑定的其他信息，请参阅以下资源：  
  
-   [如何配置 Wcf-customisolated 接收位置](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [如何配置 WCF 自定义接收位置](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [如何配置 Wcf-custom 发送端口](../core/how-to-configure-a-wcf-custom-send-port.md)