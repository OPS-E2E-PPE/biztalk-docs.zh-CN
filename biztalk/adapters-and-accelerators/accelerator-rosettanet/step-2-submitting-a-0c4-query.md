---
title: 步骤 2： 提交 0 C 4 查询 |Microsoft 文档
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
ms.openlocfilehash: 88c621b6891b816f72603202bd6f2214882eb4b5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965675"
---
# <a name="step-2-submitting-a-0c4-query"></a>步骤 2： 提交 0 C 4 查询
在此步骤中，将使用 0C4 - 同步测试查询的合作伙伴接口流程 (PIP) 准备并提交请求。 RosettaNet 对此 PIP 进行定义，以确保在两个不同的组织间能够正常运行成功的同步通信通道。 此 PIP 有一个同步通信模式，因此 [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 不会发送确认回执。 此 PIP 遵循与其他同步双操作 PIP（例如，PIP 2A9 - 查询技术产品信息）相同的模式。  
  
### <a name="to-submit-a-0c4---synchronous-test-query"></a>提交 0C4 - 同步测试查询  
  
1.  在 Fabrikam 计算机上的 Internet Explorer 中，找到并打开 http://localhost/LOBWebApplication/default.aspx。  
  
2.  上**提交消息**页上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**本组织**|类型**FABRIKAM**。|  
    |**伙伴组织**|类型**CONTOSO**。|  
    |**Pip 代码**|类型**0 C 4**。|  
    |**Pip 版本**|类型**R01.02**。|  
    |**Pip 实例 ID**|类型**0C4_Test**。 **重要说明：** 若要避免重复的消息 ID 错误，你必须确保**PIP**对于你提交每条消息是唯一的。 如果以后运行 0C4 测试，则必须更改此字段。|  
    |**消息类别**|类型**操作**。|  
  
3.  使用记事本或其他文本编辑器中打开该 0C4_Request.xml 文件*\<驱动器\>*: files\microsoft BizTalk 2009 Accelerator RosettaNet\SDK\LOBApplication\SampleInstances 文件夹然后复制并粘贴到的内容**服务内容**LOBWebApplication 字段。  
  
4.  单击**提交**若要提交 0 到 Contoso 计算机 C 4 查询。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>检验 Fabrikam 计算机上的通信是否成功  
  
-   上**消息状态**LOBWebApplication 在页上，请验证是否接收两个传入消息。  
  
    > [!NOTE]
    >  您应收到一条类别为 50 的消息，该消息为 Contoso 计算机的响应消息。 类别为 -99 的消息表示发生错误。 可以使用“事件查看器”来确定实际的错误消息。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>检验 Contoso 计算机上的通信是否成功  
  
1.  单击 **“开始”**，依次指向 **“所有程序”** 和 **Microsoft SQL Server**，然后单击 **SQL Server Management Studio**。  
  
2.  在**连接到服务器**对话框中，在**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**。  
  
    > [!NOTE]
    >  如果未启动 SQL Server 代理，右键单击它，并依次**启动**。  
  
3.  在 Microsoft SQL Server Management Studio 中，单击**新查询**。  
  
4.  在\<表\>文本框中，选择**BTARNDATA**从列表中。  
  
5.  在“SQL”窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  单击**执行**运行 SQL 语句。  
  
7.  在“查询”窗口的“结果”窗格中，检验您是否能看到一条传入消息。  
  
    > [!NOTE]
    >  您应看到一条类别为 10 的消息，该消息代表 Fabrikam 计算机发送的原始请求。  
  
8.  在“SQL”窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. 单击**执行**运行 SQL 语句。  
  
10. 在“查询”窗口的“结果”窗格中，检验你是否看到一条传出消息。  
  
    > [!NOTE]
    >  您应看到一条类别为 50 的消息，该消息代表 Fabrikam 发送的针对 PIP 0C4 查询的 Contoso 响应。 在双操作同步方案中，响应方计算机不会向发起方计算机发送确认消息以响应初始查询消息。 而是以响应消息作为确认消息。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3： 提交 3A2 请求](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md)   
 [BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)