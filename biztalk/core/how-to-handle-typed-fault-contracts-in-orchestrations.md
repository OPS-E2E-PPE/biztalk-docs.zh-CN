---
title: "如何处理类型化的错误协定在业务流程中 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typed fault contracts [orchestrations]
- WCF services, orchestrations
- orchestrations, typed fault contracts
- orchestrations, WCF services
ms.assetid: 5a1a7d22-b0ff-4d09-bebf-4995229784b0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a7643c4a39785018368572d721eed3ef6545c6b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-handle-typed-fault-contracts-in-orchestrations"></a>如何在业务流程中处理类型化错误协定
本主题介绍从业务流程内部使用 WCF 服务时应如何处理类型化错误协定。 若要处理在业务流程中的类型化的错误异常，你使用的 WCF 服务必须具有**FaultContractAttribute**应用于服务操作; 因此，可以通过使用引发错误**FaultException**\<T\>其中 T 可以是任何有效的数据协定或通过 WCF 服务的可序列化类型。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-handle-typed-fault-contracts-in-orchestrations"></a>若要处理在业务流程中的类型化的错误协定  
  
1.  在你的 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk 项目，请在解决方案资源管理器，右键单击你的项目，单击**添加**，然后单击**添加生成的项**。  
  
2.  在**添加生成的项的\<** *项目名称* **\>** 对话框中，在**模板**部分中，选择**使用 WCF 服务**，然后单击**添加**。  
  
3.  上**欢迎 BizTalk WCF 服务使用向导**页上，单击**下一步**。  
  
4.  上**元数据源**页上，选择**元数据交换 (MEX) 终结点**，然后单击**下一步**。  
  
5.  上**元数据终结点**页上，指定正在运行的服务，通过 WS 元数据交换或 Http Get 的下载可提供元数据的 URL — 例如，http://localhost:8005。 若要从 URL 中获取的元数据文档，请单击**获取**。 如果正在运行的服务要求具有基本身份验证方案的用户凭据，请单击**编辑**以打开**BizTalk WCF 服务使用向导**对话框中，你可以在其中提供的用户名和访问正在运行的服务时要使用的密码。 单击 **“下一步”**。  
  
6.  上**导入 WCF 服务元数据摘要**页上，查看你的设置。 你可以单击**回**需进行任何更改。 然后单击**导入**创建 BizTalk 项目和要用于使用 WCF 服务的类型。  
  
7.  上**完成 BizTalk WCF 服务使用向导**页上，单击**完成**。  
  
8.  假设您正在使用的 WCF 服务引发以下错误异常：  
  
    ```  
    throw new FaultException<MyOperationException>(divideException);  
    ```  
  
     发送端口上的错误操作需要类型的消息的**MyOperationException**，但 WCF 响应消息包含整个错误正文。 因此，你需要提取**MyOperationException**一部分从通过配置消息**入站 BizTalk 消息正文**传输的属性对话框中的选项。 例如：  
  
    -   选择**路径--由正文路径定位的内容**。  
  
    -   设置正文路径表达式，如下所示：  
  
        ```  
        /*[local-name()='Fault']/*[local-name()='Detail']/* | /*[local-name()='DivideResponse']  
        ```  
  
    -   选择**Xml**从**节点编码**下拉列表。  
  
9. 在业务流程中，您需要添加一个作用域和两个异常处理程序。 一个异常处理程序是错误的操作，类似于**MyOperationException**显示在前面的示例; 其他异常处理程序是用于捕获泛型**SOAPExceptions**。  
  
## <a name="see-also"></a>另请参阅  
 [如何从作为 WCF 服务发布的业务流程引发错误异常](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)   
 [如何通过 BizTalk WCF 服务使用向导来使用 WCF 服务](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)