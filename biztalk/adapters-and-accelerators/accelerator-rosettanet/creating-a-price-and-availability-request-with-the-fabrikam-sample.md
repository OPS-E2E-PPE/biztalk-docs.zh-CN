---
title: 创建价格与可用性请求使用 Fabrikam 示例 |Microsoft Docs
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
ms.openlocfilehash: 37ace1e92767b5eee040cd3c0e11cd747846f5ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284670"
---
# <a name="creating-a-price-and-availability-request-with-the-fabrikam-sample"></a>使用 Fabrikam 示例创建价格与可用性请求
在此步骤中，您创建 3A2 价格与可用性请求使用 LOBWebApplication 工具。  
  
### <a name="to-submit-a-3a2-price-and-availability-request-to-contoso"></a>若要提交到 Contoso 3A2 价格与可用性请求  
  
1.  在 Internet Explorer 中，转到 http://\<*fabrikam_computername*\>/LOBWebApplication/default.aspx。  
  
2.  上**LOBWebApplication**页上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**本组织**|类型**FABRIKAM**。|  
    |**合作伙伴组织**|类型**CONTOSO**。|  
    |**PIP 代码**|类型**3A2**。|  
    |**PIP 版本**|类型**R02.00.00A**。|  
    |**消息类别**|类型**操作**。|  
  
3.  使用记事本或其他文本编辑器，打开**3A2_Request.xml**文件在 C:\Program Files\Microsoft BizTalk\<版本\>RosettaNet\SDK\LOBApplication\SampleInstancesfolder 的快捷键然后复制并粘贴到文本**服务内容**LOBWebApplication 工具中的字段。  
  
4.  单击**提交**3A2 请求提交给 Contoso。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>若要验证 Fabrikam 计算机上的成功通信  
  
1.  上**消息状态**LOBWebApplication 中的页上，确认已收到两条传入消息。  
  
    > [!NOTE]
    >  首先应收到类别 25 消息表明 Contoso 计算机的确认回执。 然后，应收到一类别 50 条消息，是从 Contoso 计算机的响应消息。 类别-99 之间消息表示发生错误。 可以使用**事件查看器**来确定实际的错误消息。  
  
2.  单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
3.  在连接到服务器对话框，在**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**Connect**.  
  
4.  在 Microsoft SQL Server Management Studio 中，单击**新查询**。  
  
5.  在中**\<表\>文本**对话框中，选择**BTARNDATA**从列表中。  
  
6.  在中**SQL**窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
7.  单击**Execute**运行 SQL 语句。  
  
8.  在查询窗口中，在结果窗格中，验证看到两条传入消息。  
  
    > [!NOTE]
    >  应看到类别 25 消息，表示从 Contoso 发送到 Fabrikam 计算机的确认回执消息。 您应看到类别为 50 的消息，表示从 Contoso 业务线 (LOB) 应用程序到 Fabrikam 计算机发送的响应。 此外可以使用 ServiceContent 字段来验证响应。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>若要验证 Contoso 计算机上的成功通信  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在连接到服务器对话框，在**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**Connect**.  
  
3.  在 Microsoft SQL Server Management Studio 中，单击**新查询**。  
  
4.  在中**\<表\>文本**对话框中，选择**BTARNDATA**从列表中。  
  
5.  在中**SQL**窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  单击**Execute**运行 SQL 语句。  
  
7.  在查询窗口中，在结果窗格中，验证看到两条传入消息。  
  
    > [!NOTE]
    >  首先应收到一类别为 10 条消息，代表 Fabrikam 计算机发送的原始请求。 然后，应收到条确认消息回执一类别 25 条消息。  
  
8.  在中**SQL**窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. 单击**Execute**运行 SQL 语句。  
  
10. 在查询窗口中，在结果窗格中，验证看到一条传出消息。  
  
    > [!NOTE]
    >  应看到类别 25 消息，表示从 Contoso 发送到 Fabrikam 计算机的确认回执消息。 您应看到类别为 50 的消息，表示从 Contoso 业务线 (LOB) 应用程序到 Fabrikam 计算机发送的响应。  
  
## <a name="see-also"></a>请参阅  
 [私有流程教程](../../adapters-and-accelerators/accelerator-rosettanet/private-process-tutorial.md)