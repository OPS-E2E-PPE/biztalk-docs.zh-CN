---
title: "步骤 6： 创建发送端口，以提供 ADT ^ 到 RX 系统使用了文件适配器 A03 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- creating, send ports
- send ports, creating
ms.assetid: 66c4b524-c8ff-43b5-9c44-6d7bc759ae2c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c25a348fb739f4558f1507eda0d46d209cd44c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-create-a-send-port-to-deliver-the-adta03-message-to-the-rx-system-using-the-file-adapter"></a>步骤 6： 创建发送端口，以提供 ADT ^ 到 RX 系统使用了文件适配器 A03 消息
在此步骤中，你创建发送端口文件适配器时为药房系统 (RX)。  
  
### <a name="to-create-the-tutorialsendmsgrx-send-port"></a>若要创建 Tutorial_sendMsg_RX 发送端口  
  
1.  在[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在**发送端口属性**对话框框中，执行以下操作，然后单击**确定**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**Tutorial_sendMsg_RX**。|  
    |**传输类型**|选择**文件**从下拉列表。|  
    |**配置**|单击**配置**以打开**文件传输属性**对话框。|  
  
3.  在文件传输属性对话框中，执行以下操作，然后单击**确定**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**目标文件夹**|浏览到 **\<** *驱动器***: > files\microsoft BizTalk\<版本 > HL7\SDK\End 端到端 Tutorial\Tutorial_sendMsg_RX 快捷键**.|  
    |**文件名**|类型**%MessageID%.txt** （替换为.xml 扩展名.txt 扩展名）。|  
  
4.  在**发送端口属性**对话框中，为**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。  
  
5.  在左窗格中，选择**筛选器**，然后执行以下操作。 单击 **“确定”** 继续。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性**（首行）|选择**BTS。MessageType**从下拉列表。|  
    |**运算符**|选择**！ =**从下拉列表。|  
    |**值**|类型**http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**。|  
    |**分组依据**|选择**或**从下拉列表。|  
    |**属性**（第二个行）|单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。|  
    |**运算符**|选择**！ =**从下拉列表。|  
    |**值**|类型**http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF。**|  
    |**分组依据**|选择**AND**从下拉列表。|  
    |**属性**（第三个行）|选择**BTAHL7Schemas.MSH3_1**。|  
    |**运算符**|选择 **==** 从下拉列表。|  
    |**值**|类型**Tutorial_ADTSystem**。|  
  
    > [!NOTE]
    >  第一个筛选器意味着医院信息系统 (HIS) 璹一条消息，不确认。 第二个筛选器意味着他订阅其源是许可释放和传输 (ADT) 系统的消息。  
  
    > [!NOTE]
    >  BTAHL7 在文件放置位置将删除该消息\<*驱动器*>： 程序 FilesMicrosoft BizTalk <version> HL7SDKEnd 端到端 TutorialTutorial_sendMsg_RX 快捷键。  
  
6.  单击**应用**，然后单击**确定。**  
  
7.  在管理控制台中，单击**发送端口**，右键单击**Tutorial_sendMsg_RX**，然后单击**启动**。  
  
 继续执行[步骤 7： 创建发送端口，以提供 ADT ^ A03 消息到他使用 MLLP 适配器](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)。