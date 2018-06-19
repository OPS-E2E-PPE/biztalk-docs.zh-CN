---
title: 步骤 1： 配置文件接收位置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df591263-964a-4ad8-bc3a-a553de8dae4f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78f8bccc187bf310b8426fc3d5fee36add44a9f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278253"
---
# <a name="step-1-configure-a-file-receive-location"></a>步骤 1： 配置文件接收位置
在本主题中，配置文件接收使用放到一个文件夹来调用发送端口 dummy 请求消息的位置。  
  
> [!NOTE]
>  在本教程中的步骤假定你使用默认应用程序 (**BizTalk 应用程序 1**) 来创建解决方案。 你还可以创建另一个应用程序并在该应用程序中执行相同步骤。  
  
### <a name="to-configure-a-file-receive-location"></a>配置 FILE 接收位置的步骤  
  
1.  从 BizTalk Server 管理控制台，在**BizTalk 应用程序 1**节点，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
2.  在“常规”选项卡上，执行下列操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**ReceivePortRestAzureMarketPlace**。|  
    |**启用路由失败消息**|（清除）|  
  
3.  单击**接收位置**，然后单击**新建**。  
  
4.  从接收位置 1 – 接收位置属性，请执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**ReceiveLocationAzureMarketPlace**。|  
    |**类型**|选择**文件**。|  
    |**接收处理程序**|选择“BizTalkServerApplication” 。|  
    |**接收管道**|选择**PassThruReceive**。|  
  
5.  单击**配置**。  
  
6.  从文件传输属性，请执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**接收文件夹**|键入将存放虚拟请求消息的位置。|  
    |**文件名**|保留`*.xml`|  
  
7.  单击**确定**直到退出所有对话框。  
  
## <a name="see-also"></a>另请参阅  
 [教程 5： 调用 REST 接口使用 BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)