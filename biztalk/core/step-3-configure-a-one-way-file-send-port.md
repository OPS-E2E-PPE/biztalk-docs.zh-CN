---
title: 步骤 3： 配置单向的文件发送端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c52c6b6b-6f9c-48f2-8732-450fe3a15eae
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ceb055f0d4d41eb82eb79cb549b082212fd1bbd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277325"
---
# <a name="step-3-configure-a-one-way-file-send-port"></a>步骤 3： 配置单向的文件发送端口
在此步骤中，你将配置一个单向 FILE 发送端口，该端口使用从 REST 接口接收的响应消息并将其复制到一个文件位置。  
  
### <a name="to-configure-a-file-send-port"></a>配置 FILE 发送端口的步骤  
  
1.  从 BizTalk Server 管理控制台，在**BizTalk 应用程序 1**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在“常规”选项卡上，执行下列操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**SendPortOutAzureMarketPlaceData**。|  
    |**类型**|选择**文件**。|  
    |**发送处理程序**|选择“BizTalkServerApplication” 。|  
    |**发送管道**|选择**PassThruTransmit**。|  
  
     单击**配置**。  
  
3.  从文件传输属性，请执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**接收文件夹**|键入 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将响应消息复制到的位置。|  
    |**文件名**|保留`%MessageID%.xml`|  
  
4.  上**筛选器**选项卡上，指定要使用写入到的所有消息的筛选器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息框数据库中创建的接收端口[步骤 2： 配置 WCF WebHttp 双向发送端口](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md).  
  
    |||  
    |-|-|  
    |**属性**|设置为**BTS。SPName**|  
    |**运算符**|设置为**==**|  
    |**值**|设置为`SendPortRESTAzureMarketPlace`|  
  
5.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [教程 5： 调用 REST 接口使用 BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)