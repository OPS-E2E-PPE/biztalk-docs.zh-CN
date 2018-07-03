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
ms.openlocfilehash: 567b3d88ced85f427fde492cd3e68cefaaf47394
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999200"
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
|  消息正文   | 由于未指定绑定类型，因此无法创建绑定。 指定绑定类型，例如“basicHttpBinding”、“wsHttpBinding”或“customBinding” |
  
## <a name="explanation"></a>解释  
 配置 WCF-Custom 或 WCF-CustomIsolated 传输之后，未设置代码中的 BindingType 属性。 或者问题可能存在于其他代码路径中。 必须将用户界面中的值作为绑定设置。 在接收位置“属性”区域中查看您的配置，并确保已从下拉列表中选择绑定类型。  
  
## <a name="user-action"></a>用户操作  
 要解决此问题，请查看用于配置 WCF-Custom 或 WCF-CustomIsolated 传输的代码。 絋粄**BindingType**中的 XML 数据的属性**TransportTypeData** ITransportInfo 接口的属性已正确设置。  
  
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
  
   有关配置绑定的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [如何配置 Wcf-customisolated 接收位置](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [如何配置 WCF 自定义接收位置](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [如何配置 Wcf-custom 发送端口](../core/how-to-configure-a-wcf-custom-send-port.md)