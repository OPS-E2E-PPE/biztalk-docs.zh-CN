---
title: 无法创建绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbe1bd54-6031-4f90-a445-c1647b382a1a
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7910cf4c6e16d5af75e49bb829f1418a5e1455c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528209"
---
# <a name="cannot-create-binding"></a>无法创建绑定
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                               |
| 产品版本 |                                           [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                           |
|    事件 ID     |                                                                       0                                                                        |
|  事件源   |                                                                       0                                                                        |
|    组件    |                                                                       0                                                                        |
|  符号名称  |                                                                       0                                                                        |
|  消息正文   | 无法创建绑定，因为未指定绑定类型。 指定绑定类型，例如"basicHttpBinding"、"wsHttpBinding"或"customBinding |
  
## <a name="explanation"></a>解释  
 未不在代码中将 BindingType 属性设置在配置 Wcf-custom 或 Wcf-customisolated 传输之后。 或者，问题可能是在其他代码路径中。 绑定设置的用户界面中，必须具有一个值。 查看你的配置，并确保绑定类型从接收位置属性区域中的下拉列表中选择。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请查看配置 Wcf-custom 或 Wcf-customisolated 传输的代码。 絋粄**BindingType**中的 XML 数据的属性**TransportTypeData** ITransportInfo 接口的属性已正确设置。  
  
 此外，指定绑定类型，例如**basicHttpBinding**， **wsHttpBinding**，或**customBinding**。  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 找到你的应用程序，然后找到您的传输。  
  
4. 右键单击传输名称。  
  
5. 单击 **“属性”**。  
  
6. 在端口**类型**列表中，选择正确的端口。  
  
7. 单击**配置**。  
  
8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**绑定**选项卡。  
  
9. 确保在指定了值**绑定类型**列表。  
  
   有关配置绑定的其他信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  
  
-   [如何配置 Wcf-customisolated 接收位置](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [如何配置 WCF 自定义接收位置](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [如何配置 Wcf-custom 发送端口](../core/how-to-configure-a-wcf-custom-send-port.md)