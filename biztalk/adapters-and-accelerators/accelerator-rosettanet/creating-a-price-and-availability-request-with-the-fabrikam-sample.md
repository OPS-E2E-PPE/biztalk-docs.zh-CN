---
title: 创建价格和可用性请求 Fabrikam 示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating requests
ms.assetid: 6e4f4589-8f01-4b9e-93ee-c9371f32e04a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0619dc77496fd1547505221ff2f437bf486fb8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965915"
---
# <a name="creating-a-price-and-availability-request-with-the-fabrikam-sample"></a>创建具有 Fabrikam 示例的价格和可用性请求
在此步骤中，将使用 LOBWebApplication 工具创建 3A2 价格与可用性请求。  
  
### <a name="to-submit-a-3a2-price-and-availability-request-to-contoso"></a>向 Contoso 提交 3A2 价格与可用性请求  
  
1.  在 Internet Explorer 中，移动到 http://\<*fabrikam_computername*\>/LOBWebApplication/default.aspx。  
  
2.  上**LOBWebApplication**页上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**本组织**|类型**FABRIKAM**。|  
    |**伙伴组织**|类型**CONTOSO**。|  
    |**PIP 代码**|类型**3A2**。|  
    |**PIP 版本**|类型**R02.00.00A**。|  
    |**消息类别**|类型**操作**。|  
  
3.  使用记事本或其他文本编辑器，打开**3A2_Request.xml**文件在 C:\Program Files\Microsoft BizTalk\<版本\>RosettaNet\SDK\LOBApplication\SampleInstancesfolder 快捷键复制并粘贴到文本**服务内容**字段 LOBWebApplication 工具。  
  
4.  单击**提交**以提交到 Contoso 3A2 请求。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>检验 Fabrikam 计算机上的通信是否成功  
  
1.  上**消息状态**LOBWebApplication 在页上，请验证是否接收两个传入消息。  
  
    > [!NOTE]
    >  首先应收到一条类别为 25 的消息，该消息为 Contoso 计算机的确认回执。 然后，应收到一条类别为 50 的消息，该消息为 Contoso 计算机的响应消息。 类别为 -99 的消息表示发生错误。 你可以使用**事件查看器**以确定实际错误消息。  
  
2.  单击**启动**，指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
3.  在连接到服务器对话框中，在**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**.  
  
4.  在 Microsoft SQL Server Management Studio 中，单击**新查询**。  
  
5.  在**\<表\>文本**对话框中，选择**BTARNDATA**从列表中。  
  
6.  在**SQL**窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
7.  单击**执行**运行 SQL 语句。  
  
8.  在“查询”窗口的“结果”窗格中，检验你是否看到两条传入消息。  
  
    > [!NOTE]
    >  应看到类别为 25 的消息，该消息代表从 Contoso 计算机发送到 Fabrikam 计算机的确认回执。 还应看到类别为 50 的消息，该消息代表从 Contoso 业务线 (LOB) 应用程序发送到 Fabrikam 计算机的响应。 还可以使用 ServiceContent 字段来验证响应。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>检验 Contoso 计算机上的通信是否成功  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在连接到服务器对话框中，在**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**.  
  
3.  在 Microsoft SQL Server Management Studio 中，单击**新查询**。  
  
4.  在**\<表\>文本**对话框中，选择**BTARNDATA**从列表中。  
  
5.  在**SQL**窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  单击**执行**运行 SQL 语句。  
  
7.  在“查询”窗口的“结果”窗格中，检验你是否看到两条传入消息。  
  
    > [!NOTE]
    >  首先应收到一条类别为 10 的消息，该消息代表 Fabrikam 计算机发送的原始请求。 然后，应收到一条类别为 25 的消息，该消息为确认消息回执。  
  
8.  在**SQL**窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. 单击**执行**运行 SQL 语句。  
  
10. 在“查询”窗口的“结果”窗格中，检验你是否看到一条传出消息。  
  
    > [!NOTE]
    >  应看到类别为 25 的消息，该消息代表从 Contoso 计算机发送到 Fabrikam 计算机的确认回执。 还应看到类别为 50 的消息，该消息代表从 Contoso 业务线 (LOB) 应用程序发送到 Fabrikam 计算机的响应。  
  
## <a name="see-also"></a>另请参阅  
 [私有流程教程](../../adapters-and-accelerators/accelerator-rosettanet/private-process-tutorial.md)