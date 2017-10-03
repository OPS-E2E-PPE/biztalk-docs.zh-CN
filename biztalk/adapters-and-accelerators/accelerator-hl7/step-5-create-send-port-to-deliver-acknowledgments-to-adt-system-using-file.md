---
title: "步骤 5： 创建发送端口将确认传递到使用文件适配器的 ADT 系统 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: 565a2adf-fd86-46e3-8035-7e4748aefffc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 926a13d443e7002a71e2b9f6509c3a377f0af0be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-create-a-send-port-to-deliver-acknowledgments-to-the-adt-system-using-the-file-adapter"></a>步骤 5： 创建发送端口将确认传递到使用文件适配器的 ADT 系统
在此步骤中，你可以创建发送端口以生成使用了文件适配器的确认。  
  
### <a name="to-create-the-tutorialsendackadt-send-port"></a>若要创建 Tutorial_sendAck_ADT 发送端口  
  
1.  使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，创建\<*驱动器*: > files\microsoft BizTalk\<版本 > Accelerator for HL7\SDK\End 端到端 Tutorial\Tutorial_sendAck_ADT 文件夹。  
  
2.  在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
3.  在“发送端口属性”对话框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**Tutorial_sendAck_ADT**。|  
    |**传输类型**|选择**文件**从下拉列表。|  
    |**配置**|单击**配置**以打开**文件传输属性**对话框。|  
  
4.  在文件传输属性对话框中，执行以下操作，然后单击**确定**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**目标文件夹**|浏览到 **\<** *驱动器***: > files\microsoft BizTalk\<版本 > HL7\SDK\End 端到端 Tutorial\Tutorial_sendAck_ADT 快捷键**.|  
    |**文件名**|类型**%MessageID%.txt** （替换为.xml 扩展名.txt 扩展名）。|  
  
5.  在发送端口属性对话框中，为**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。  
  
6.  在左窗格中，单击**筛选器**，然后执行以下：  
  
    > [!NOTE]
    >  第一个筛选器意味着你要订阅的确认消息。 第二个筛选器意味着你要订阅到发布服务器 Tutorial_ADTSystem 发送到该确认。  
  
     单击**确定**当你准备好继续。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性**|单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。|  
    |**运算符**|选择 **==** 从下拉列表。|  
    |**值**|类型**http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**。|  
    |**分组依据**|选择**或**从下拉列表。|  
    |**属性 （第二个行）**|单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。|  
    |**运算符**|选择 **==** 从下拉列表。|  
    |**值**|类型**http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF。**|  
    |**分组依据**|选择**AND**从下拉列表。|  
    |**属性**|在第一个属性，单击空白框中，然后选择**BTAHL7Schemas.MSH5_1**。|  
    |**运算符**|选择 **==** 从下拉列表。|  
    |**值**|类型**Tutorial_ADTSystem**。|  
  
    > [!NOTE]
    >  发送端口 Tutorial_sendAck_ADT，BTAHL7 删除确认在文件放置位置\<*驱动器*>： 程序 FilesMicrosoft BizTalk <version> HL7SDKEnd 端到端 TutorialTutorial 快捷键_sendAck_ADT。  
  
7.  单击**应用**，然后单击**确定。**  
  
8.  在管理控制台中，单击**发送端口**，右键单击**Tutorial_sendAck_ADT**，然后单击**启动**。  
  
 继续执行[步骤 6： 创建发送端口，以提供 ADT ^ A03 消息到 RX 系统使用了文件适配器](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)。