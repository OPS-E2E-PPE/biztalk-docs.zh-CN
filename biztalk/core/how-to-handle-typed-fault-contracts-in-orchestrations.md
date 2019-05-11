---
title: 在业务流程中如何处理类型化的错误协定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- typed fault contracts [orchestrations]
- WCF services, orchestrations
- orchestrations, typed fault contracts
- orchestrations, WCF services
ms.assetid: 5a1a7d22-b0ff-4d09-bebf-4995229784b0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a27a220e649b513ba70d3934bc0c74b71b865bea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337341"
---
# <a name="how-to-handle-typed-fault-contracts-in-orchestrations"></a>如何处理业务流程中的类型化的错误协定
本主题介绍如何使用从业务流程中的 WCF 服务时处理类型化的错误协定。 若要处理业务流程中的类型化的错误异常，您正在使用的 WCF 服务必须具有**FaultContractAttribute**应用于服务操作; 因此，可以通过引发错误**FaultException**\<T\>其中 T 可以是任何有效的数据协定或可序列化类型从 WCF 服务。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-handle-typed-fault-contracts-in-orchestrations"></a>若要处理业务流程中的类型化的错误协定  
  
1. 在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk 项目，请在解决方案资源管理器，右键单击你的项目，单击**添加**，然后单击**添加生成的项**。  
  
2. 在中**添加生成的项- \<** <em>项目名称</em>**\>** 对话框中，在**模板**部分中，选择**使用 WCF 服务**，然后单击**添加**。  
  
3. 上**欢迎使用 BizTalk WCF 服务使用向导**页上，单击**下一步**。  
  
4. 上**元数据来源**页上，选择**元数据交换 (MEX) 终结点**，然后单击**下一步**。  
  
5. 上**元数据终结点**页上，指定正在运行的服务，提供通过 WS-元数据交换或 Http-get 下载的元数据的 URL — 例如， http://localhost:8005。 若要从该 URL 获取元数据文档，请单击**获取**。 如果正在运行的服务需要使用基本身份验证方案的用户凭据，请单击**编辑**以打开**BizTalk WCF 服务使用向导**对话框可以在其中提供的用户名和若要访问正在运行的服务时使用的密码。 单击“下一步” 。  
  
6. 上**导入 WCF 服务元数据摘要**页上，查看你的设置。 可以单击**回**需进行任何更改。 然后单击**导入**创建 BizTalk 项目和类型用于使用 WCF 服务。  
  
7. 上**完成 BizTalk WCF 服务使用向导**页上，单击**完成**。  
  
8. 假设您正在使用的 WCF 服务将引发以下错误异常：  
  
   ```  
   throw new FaultException<MyOperationException>(divideException);  
   ```  
  
    发送端口上的错误操作要求类型的消息**MyOperationException**，但 WCF 响应消息包含整个错误正文。 因此，您需要提取**MyOperationException**部分来配置从消息**入站 BizTalk 消息正文**传输属性对话框中的选项。 例如，  
  
   -   选择**路径-按正文路径定位内容**。  
  
   -   设置正文路径表达式所示：  
  
       ```  
       /*[local-name()='Fault']/*[local-name()='Detail']/* | /*[local-name()='DivideResponse']  
       ```  
  
   -   选择**Xml**从**节点编码**下拉列表。  
  
9. 在业务流程，需要将添加一个作用域和两个异常处理程序。 一个异常处理程序用于错误操作，类似于**MyOperationException**显示在前面的示例; 其他异常处理程序用于捕捉一般**SOAPExceptions**。  
  
## <a name="see-also"></a>请参阅  
 [如何从发布为 WCF 服务的业务流程引发错误异常](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)   
 [如何使用 BizTalk WCF 服务使用向导来使用 WCF 服务](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)