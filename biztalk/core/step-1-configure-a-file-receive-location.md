---
title: 第 1 步：配置一个 FILE 接收位置 |Microsoft Docs
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
ms.openlocfilehash: 2ae1bb74c162a0a61521392fc4cd75e99ba26297
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392832"
---
# <a name="step-1-configure-a-file-receive-location"></a>第 1 步：配置一个 FILE 接收位置
在本主题中，配置文件接收位置使用你存放至文件夹来调用发送端口的虚拟请求消息。  
  
> [!NOTE]
>  在本教程中的步骤假定你使用默认应用程序 (**BizTalk Application 1**) 来创建解决方案。 您还可以创建另一个应用程序和该应用程序中任何执行相同的步骤。  
  
### <a name="to-configure-a-file-receive-location"></a>若要配置 FILE 接收位置  
  
1.  从 BizTalk Server 管理控制台中下, **BizTalk Application 1**节点，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
2.  在常规选项卡上，执行以下步骤：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**ReceivePortRestAzureMarketPlace**。|  
    |**为失败消息启用路由功能**|（清除）|  
  
3.  单击**接收位置**，然后单击**新建**。  
  
4.  从接收位置 1 – 接收位置属性，请执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**ReceiveLocationAzureMarketPlace**。|  
    |**类型**|选择**文件**。|  
    |**接收处理程序**|选择“BizTalkServerApplication” 。|  
    |**接收管道**|选择**PassThruReceive**。|  
  
5.  单击**配置**。  
  
6.  从文件传输属性中，执行以下步骤：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**接收文件夹**|键入将存放虚拟请求消息的位置。|  
    |**文件名**|保留 `*.xml`|  
  
7.  单击**确定**直到您退出所有对话框。  
  
## <a name="see-also"></a>请参阅  
 [教程 5:调用 REST 接口使用 BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)