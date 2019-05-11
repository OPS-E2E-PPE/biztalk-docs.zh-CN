---
title: 步骤 3：配置单向 FILE 发送端口 |Microsoft Docs
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
ms.openlocfilehash: 6ab2d37ba632b837e9ca13839cd5a1b8993f69bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392667"
---
# <a name="step-3-configure-a-one-way-file-send-port"></a>步骤 3：配置单向 FILE 发送端口
在此步骤中配置一个单向 FILE 发送端口使用从 REST 接口接收的响应消息并将其复制到某个文件位置。  

### <a name="to-configure-a-file-send-port"></a>若要配置 FILE 发送端口  

1. 从 BizTalk Server 管理控制台中下, **BizTalk Application 1**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  

2. 在常规选项卡上，执行以下步骤：  

   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**名称**|类型**SendPortOutAzureMarketPlaceData**。|  
   |**类型**|选择**文件**。|  
   |**发送处理程序**|选择“BizTalkServerApplication” 。|  
   |**发送管道**|选择**PassThruTransmit**。|  

    单击**配置**。  

3. 从文件传输属性中，执行以下步骤：  


   |      使用此选项      |                                                              执行的操作                                                               |
   |--------------------|---------------------------------------------------------------------------------------------------------------------------------------|
   | **接收文件夹** | 键入某一位置其中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将复制的响应消息。 |
   |   **文件名**    |                                                       保留 `%MessageID%.xml`                                                        |


4. 上**筛选器**选项卡上，指定要使用写入到的所有消息的筛选器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Messagebox 数据库中创建的接收端口通过[步骤 2:配置双向 Wcf-webhttp 发送端口](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md)。  


   |              |                                       |
   |--------------|---------------------------------------|
   | **属性** |         设置为**BTS。SPName**         |
   | **“运算符”** |             设置为 **==**             |
   |  **ReplTest1**   | 设置为 `SendPortRESTAzureMarketPlace` |


5. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [教程 5:调用 REST 接口使用 BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)