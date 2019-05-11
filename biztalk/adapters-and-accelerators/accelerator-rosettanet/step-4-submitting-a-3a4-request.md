---
title: 步骤 4：提交 3A4 请求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: 2d812cbc-51bc-48d5-b0b2-3698d33664ec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6589a46665edf6e446483b673fd4228dd471bbd3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280929"
---
# <a name="step-4-submitting-a-3a4-request"></a>步骤 4：提交 3A4 请求
在此步骤中，将准备和提交 3a4-请求采购订单使用合作伙伴接口流程 (PIP) 的请求。 此 PIP，买方组织提交给供应商的采购订单请求。 通常情况下，你请求 3A4-请求采购订单在运行使用 3A2-请求价格与可用性 PIP 的产品可用性查询之后。 3A4 PIP 是发送确认回执的异步 PIP。  
  
 ![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a4flow.gif "RN3_Intro_EETut_3A4Flow")  
  
### <a name="to-submit-a-3a4---request-purchase-order"></a>若要提交 3A4-请求采购订单  
  
1.  在 Fabrikam 计算机上，在 Internet Explorer 中，找到并打开 http://localhost/LOBWebApplication/default.aspx。  
  
2.  上**提交消息**页上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**本组织**|类型**FABRIKAM**。|  
    |**合作伙伴组织**|类型**Contoso**。|  
    |**Pip 代码**|类型**3A4**。|  
    |**Pip 版本**|类型**V02.02.00**。|  
    |**Pip 实例 ID**|类型**3A4_Test**。 **重要提示：** 若要避免重复消息 ID 错误，您必须确保**Pip 实例 ID**是唯一的提交的每条消息。 如果在以后运行 3A4 测试，将需要更改此字段。|  
    |**消息类别**|类型**操作**。|  
  
3.  使用记事本或其他文本编辑器打开中的 3A4_Request.xml 文件\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances 文件夹，然后复制并粘贴到**服务内容**LOBWebApplication 中的字段。  
  
4.  单击**提交**3A4 请求提交给 Contoso 计算机。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>若要验证 Fabrikam 计算机上的成功通信  
  
-   上**消息状态**LOBWebApplication 中的页上，确认已收到两条传入消息。  
  
    > [!NOTE]
    >  首先应收到类别 25 消息表明 Contoso 计算机的确认回执。 然后，应收到一类别 50 条消息，是从 Contoso 计算机的响应消息。 类别-99 之间消息表示发生错误。 可以使用**事件查看器**来确定实际的错误消息。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>若要验证 Contoso 计算机上的成功通信  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在中**连接到服务器**对话框中**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**。  
  
3.  在 Microsoft SQL Server Management Studio 中，单击**新查询**。  
  
4.  在中\<表\>文本对话框中，选择**BTARNDATA**从列表中。  
  
5.  在 SQL 窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  单击**Execute**运行 SQL 语句。  
  
7.  在查询窗口中，在结果窗格中，验证看到两条传入消息。  
  
    > [!NOTE]
    >  首先应收到一类别为 10 条消息，代表 Fabrikam 计算机发送的原始请求。 然后，应收到表明回执 acknowledegment 消息一类别 25 条消息。  
  
8.  在 SQL 窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. 单击**Execute**运行 SQL 语句。  
  
10. 在查询窗口中，在**结果**窗格中，验证是否能看到一条传出消息。  
  
    > [!NOTE]
    >  应看到类别 25 消息，表示从 Contoso 发送到 Fabrikam 计算机的确认回执消息。 您应看到类别为 50 的消息，表示从 Contoso 业务线 (LOB) 应用程序到 Fabrikam 计算机发送的响应。  
  
## <a name="see-also"></a>请参阅  
 [双操作教程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-tutorial.md)   
 [BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)