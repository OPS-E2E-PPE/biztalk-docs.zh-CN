---
title: "步骤 7： 创建发送端口将响应消息传递 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: interrogative tutorial, send ports
ms.assetid: 5edaefb6-72f2-4317-9477-f3a0d0027e0c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1260772f3b3df5f0dea96b0aa66023e107b9aa6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-create-a-send-port-to-deliver-response-messages"></a>步骤 7： 创建发送端口将响应消息传递
在此步骤中，创建要将传送回许可、 放电和传输 (ADT) 的查询响应的发送端口系统。  
  
### <a name="to-create-the-adtsend-send-port"></a>若要创建 ADT_Send 发送端口  
  
1.  在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后选择**静态单向发送端口**。  
  
2.  在“发送端口属性”对话框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|类型**ADT_Send**。|  
    |**传输类型**|选择**MLLP**。|  
    |**配置**|单击**配置**右侧的按钮**类型**。|  
  
3.  在 MLLP 传输属性对话框中，输入以下信息，，然后单击**确定**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**连接名称**|类型**ADT_SendMLLP**。|  
    |**主机**|类型**localhost**。|  
    |**端口**|类型**25000**。|  
  
4.  在发送端口属性对话框中，为**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。  
  
5.  在控制台树中，单击**筛选器**，然后执行以下：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性**|选择**BTS。MessageType**。|  
    |**运算符**|选择 **==** 从下拉列表。|  
    |**值**|类型**http://microsoft.com/HealthCare/HL7/2X#DSR_Q01_24_GLO_DEF**。|  
    |**分组依据**|选择**AND**从下拉列表。|  
    |**属性**|在第一个属性，单击空白框中，然后选择**BTAHL7Schemas.MSH5_1**。|  
    |**运算符**|选择 **==** 从下拉列表。|  
    |**值**|类型**ADT**。|  
  
    > [!NOTE]
    >  第一个筛选器指定发送端口仅选择消息符合 DSR ^ 步骤 3A 中创建的 Q01 架构。 第二个筛选器指定到的目标[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎将发送这些消息。  
  
6.  单击 **“确定”**。  
  
7.  在管理控制台中，单击**发送端口**，右键单击**ADT_Send**，然后单击**启动**。  
  
 继续执行[第 8 步： 配置当事方信息](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md)。