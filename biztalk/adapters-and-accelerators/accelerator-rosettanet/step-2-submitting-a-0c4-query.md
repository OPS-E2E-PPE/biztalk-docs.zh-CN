---
title: 第 2 步：提交 0c4 查询 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: ce50b892-c87c-414a-94c5-b40947fec68f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd5ea963049d8d7a53c0098c1a53ae54784e0653
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281298"
---
# <a name="step-2-submitting-a-0c4-query"></a>第 2 步：提交 4 查询
在此步骤中，将准备和提交 0c4-同步测试查询的使用合作伙伴接口流程 (PIP) 的请求。 RosettaNet 定义此 PIP，以确保两个不同组织之间成功的同步通信通道正常工作。 此 PIP 有一个同步通信模式，因为[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]不会发送确认回执。 此 PIP 遵循相同的模式与其他同步双操作 Pip，例如，PIP 2A9-查询技术产品信息。  
  
### <a name="to-submit-a-0c4---synchronous-test-query"></a>若要提交 0c4-同步测试查询  
  
1.  在 Fabrikam 计算机上，在 Internet Explorer 中，找到并打开 http://localhost/LOBWebApplication/default.aspx。  
  
2.  上**提交消息**页上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**本组织**|类型**FABRIKAM**。|  
    |**合作伙伴组织**|类型**CONTOSO**。|  
    |**Pip 代码**|类型**0c4**。|  
    |**Pip 版本**|类型**R01.02**。|  
    |**Pip 实例 ID**|类型**0C4_Test**。 **重要提示：** 若要避免重复消息 ID 错误，您必须确保**PIP**是唯一的提交的每条消息。 如果您运行 C 4 测试在将来，，必须更改本字段。|  
    |**消息类别**|类型**操作**。|  
  
3.  使用记事本或其他文本编辑器打开中的文件 0C4_Request.xml *\<驱动器\>*: files\microsoft BizTalk 2009 Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances 文件夹然后复制并粘贴到**服务内容**LOBWebApplication 中的字段。  
  
4.  单击**提交**若要提交给 Contoso 计算机 C 4 查询。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>若要验证 Fabrikam 计算机上的成功通信  
  
-   上**消息状态**LOBWebApplication 中的页上，确认已收到两条传入消息。  
  
    > [!NOTE]
    >  应收到一类别 50 条消息，是从 Contoso 计算机的响应消息。 类别-99 之间消息表示发生错误。 可以使用事件查看器来确定实际的错误消息。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>若要验证 Contoso 计算机上的成功通信  
  
1.  单击 **“开始”**，依次指向 **“所有程序”** 和 **Microsoft SQL Server**，然后单击 **SQL Server Management Studio**。  
  
2.  在中**连接到服务器**对话框中**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**。  
  
    > [!NOTE]
    >  如果未启动 SQL Server 代理，右键单击它，然后依次**启动**。  
  
3.  在 Microsoft SQL Server Management Studio 中，单击**新查询**。  
  
4.  在中\<表\>文本框中，选择**BTARNDATA**从列表中。  
  
5.  在 SQL 窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  单击**Execute**运行 SQL 语句。  
  
7.  在查询窗口中，在结果窗格中，验证看到一条传入消息。  
  
    > [!NOTE]
    >  应看到类别为 10 表示消息的 Fabrikam 计算机发送的原始请求。  
  
8.  在 SQL 窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. 单击**Execute**运行 SQL 语句。  
  
10. 在查询窗口中，在结果窗格中，验证看到一条传出消息。  
  
    > [!NOTE]
    >  你应会看到类别为 50 消息表示的 Contoso 响应的针对 PIP 0c4 查询 Fabrikam 发送。 在双操作同步方案中，响应方计算机不会发送到发起方计算机以响应初始查询消息的确认。 响应消息作为确认。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：提交 3A2 请求](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md)   
 [BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)