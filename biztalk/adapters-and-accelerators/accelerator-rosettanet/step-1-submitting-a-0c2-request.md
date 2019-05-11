---
title: 第 1 步：提交 0c2 请求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: 698c4a43-20b9-46b7-ab66-1dfa24232024
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bc9102198305d6f9ea92ca4d1462d1839c4f5aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281419"
---
# <a name="step-1-submitting-a-0c2-request"></a>第 1 步：提交请求 2
在此步骤中，将准备和提交 0c2-异步测试请求的使用合作伙伴接口流程 (PIP) 的请求。 此 PIP 可确保两个不同组织之间正常工作一个异步通信通道。 此 PIP 遵循相同的模式与其他异步双操作 Pip，例如 3A4-请求采购订单 PIP。  
  
### <a name="to-submit-a-0c2---asynchronous-test-request"></a>提交 0c2-异步测试请求  
  
1.  在 Fabrikam 计算机上，在 Internet Explorer 中，找到并打开 http://localhost/LOBWebApplication/default.aspx。  
  
2.  上**提交消息**页上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**本组织**|类型**FABRIKAM**。|  
    |**合作伙伴组织**|类型**CONTOSO**。|  
    |**Pip 代码**|类型**0c2**。|  
    |**Pip 版本**|类型**R01.02**。|  
    |**Pip 实例 ID**|类型**0C2_Test**。 **重要提示：** 必须确保**PIP**是唯一的提交以避免重复消息 ID 错误每条消息。 如果您运行 C 2 测试在将来，，必须更改本字段。|  
    |**消息类别**|类型**操作**。|  
  
3.  使用记事本或其他文本编辑器打开中的 0C2_Request.xml 文件\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances 文件夹，然后复制并粘贴到**服务内容**LOBWebApplication 中的字段。  
  
    > [!NOTE]
    >  若要删除服务内容提交消息窗体的字段中的现有文本，请将光标放在开头的文本，请按住**Shift**并**Ctrl**按钮，单击**结束**，然后单击**删除**。  
  
4.  单击**提交**若要提交给 Contoso 计算机 C 2 请求。  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a>若要验证 Fabrikam 计算机上的成功通信  
  
-   上**消息状态**LOBWebApplication 中的页上，确认已收到两条传入消息。  
  
    > [!NOTE]
    >  首先应收到类别 25 消息表明 Contoso 计算机的确认回执。 然后，应收到一类别 50 条消息，是从 Contoso 计算机的响应消息。 类别-99 之间消息表示发生错误。 可以使用**事件查看器**来确定实际的错误消息。  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a>若要验证 Contoso 计算机上的成功通信  
  
1.  单击 **“开始”**，依次指向 **“所有程序”** 和 **Microsoft SQL Server**，然后单击 **SQL Server Management Studio**。  
  
2.  在中**连接到服务器**对话框中**SQL Server**框中，键入**localhost**，选择**Windows 身份验证**，然后单击**连接**。  
  
    > [!NOTE]
    >  如果未启动 SQL Server 代理，右键单击它，然后依次**启动**。  
  
3.  在 Microsoft SQL Server Management Studio 中，单击**新查询**。  
  
4.  在中\<表\>文本对话框中，选择**BTARNDATA**从列表中，然后单击**确定**。  
  
5.  在 SQL 窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  上**查询**菜单上，单击**Execute**运行 SQL 语句。  
  
7.  在查询窗口中，在结果窗格中，验证看到两条传入消息。  
  
    > [!NOTE]
    >  首先应收到一类别为 10 条消息，代表 Fabrikam 计算机发送的原始请求。 然后，应收到条确认消息回执一类别 25 条消息。  
  
8.  在 SQL 窗口中，键入以下 SQL 语句：  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. 单击**Execute**运行 SQL 语句。  
  
10. 在查询窗口中，在结果窗格中，验证看到一条传出消息。  
  
    > [!NOTE]
    >  应看到类别 25 消息，表示从 Contoso 发送到 Fabrikam 计算机的确认回执消息。 您应看到类别为 50 的消息，表示从 Contoso 业务线 (LOB) 应用程序到 Fabrikam 计算机发送的响应。  
  
## <a name="see-also"></a>请参阅  
 [步骤 2：提交 4 查询](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md)   
 [BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)