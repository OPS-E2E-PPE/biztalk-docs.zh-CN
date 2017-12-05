---
title: "步骤 1： 提交 0 C 2 请求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, submitting requests
ms.assetid: 698c4a43-20b9-46b7-ab66-1dfa24232024
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f05aa5200bd1df6207a962849cd776a03fe71805
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-submitting-a-0c2-request"></a>步骤 1： 提交 0 C 2 请求
在此步骤中，将使用 0C2 - 异步测试请求的合作伙伴接口流程 (PIP) 准备并提交请求。 此 PIP 可确保两个不同组织间的异步通信通道能够正常运转。 此 PIP 遵循与其他异步双操作 PIP（例如，“3A4 - 请求采购订单 PIP”）相同的模式。  
  
### <a name="to-submit-a-0c2---asynchronous-test-request"></a>提交 0C2 - 异步测试请求  
  
1.  在 Fabrikam 计算机上的 Internet Explorer 中，找到并打开 http://localhost/LOBWebApplication/default.aspx。  
  
2.  上**提交消息**页上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**本组织**|类型**FABRIKAM**。|  
    |**伙伴组织**|类型**CONTOSO**。|  
    |**Pip 代码**|类型**0 C 2**。|  
    |**Pip 版本**|类型**R01.02**。|  
    |**Pip 实例 ID**|类型**0C2_Test**。 **重要说明：**必须确保**PIP**对于提交以避免重复的消息 ID 错误每条消息是唯一的。 如果以后运行 0C2 测试，则必须更改本字段。|  
    |**消息类别**|类型**操作**。|  
  
3.  使用记事本或其他文本编辑器中打开该 0C2_Request.xml 文件\<*驱动器*\>: files\microsoft BizTalk\<版本\>RosettaNet\SDK\ 快捷键LOBApplication\SampleInstances 文件夹，然后复制并粘贴到的内容**服务内容**LOBWebApplication 字段。  
  
    > [!NOTE]
    >  若要删除提交邮件窗体服务内容字段中的现有文本，请将光标置于开头的文本，请按住**Shift**和**Ctrl**按钮，单击**结束**，然后单击**删除**。  
  
4.  单击**提交**提交 0 到 Contoso 计算机 C 2 请求。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>检验 Fabrikam 计算机上的通信是否成功  
  
-   上**消息状态**LOBWebApplication 在页上，请验证是否接收两个传入消息。  
  
    > [!NOTE]
    >  首先应收到一条类别为 25 的消息，该消息为 Contoso 计算机的确认回执。 然后，应收到一条类别为 50 的消息，该消息为 Contoso 计算机的响应消息。 类别为 -99 的消息表示发生错误。 你可以使用**事件查看器**以确定实际错误消息。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>检验 Contoso 计算机上的通信是否成功  
  
1.  单击 **“开始”**，依次指向 **“所有程序”**和 **Microsoft SQL Server**，然后单击 **SQL Server Management Studio**。  
  
2.  在**连接到服务器**对话框中，在**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**。  
  
    > [!NOTE]
    >  如果未启动 SQL Server 代理，右键单击它，并依次**启动**。  
  
3.  在 Microsoft SQL Server Management Studio 中，单击**新查询**。  
  
4.  在\<表\>文本对话框中，选择**BTARNDATA**从列表，然后单击**确定**。  
  
5.  在“SQL”窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  上**查询**菜单上，单击**执行**运行 SQL 语句。  
  
7.  在“查询”窗口的“结果”窗格中，检验你是否看到两条传入消息。  
  
    > [!NOTE]
    >  首先应收到一条类别为 10 的消息，该消息代表 Fabrikam 计算机发送的原始请求。 然后，应收到一条类别为 25 的消息，该消息为确认消息回执。  
  
8.  在“SQL”窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. 单击**执行**运行 SQL 语句。  
  
10. 在“查询”窗口的“结果”窗格中，检验你是否看到一条传出消息。  
  
    > [!NOTE]
    >  应看到类别为 25 的消息，该消息代表从 Contoso 计算机发送到 Fabrikam 计算机的确认回执。 还应看到类别为 50 的消息，该消息代表从 Contoso 业务线 (LOB) 应用程序发送到 Fabrikam 计算机的响应。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 2： 提交 0 C 4 查询](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md)   
 [BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)