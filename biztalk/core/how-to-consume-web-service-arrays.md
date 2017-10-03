---
title: "如何使用 Web 服务数组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP adapters, Web services
- Web services, arrays
- orchestrations, Web services
- orchestrations, Web ports
ms.assetid: 29ecaaed-aa8a-4cf9-a7c8-4b0d6dd412ac
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e78f12405c9c331a888a268d39e2a1520c84fdc8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-consume-web-service-arrays"></a>如何使用 Web 服务数组
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了从 BizTalk 业务流程使用在 Web Services 中公开的数组的功能。  
  
 **配置业务流程来使用数组中的 Web 服务公开：**  
  
 确定公开数组的 Web Services 的 URL。 它通常是列出了 Web Services 支持的操作的 asmx 网页。 例如： http://localhost/ArrayWS/ArraySvc.asmx。  
  
1.  在业务流程所在的 Visual Studio 项目中添加对此 URL 的 Web 引用：  
  
    -   在解决方案资源管理器，右键单击**引用**，然后单击**添加服务引用**。  
  
    -   在**添加服务引用**对话框中，单击**高级**。  
  
    -   在**服务引用设置**对话框中，单击**添加 Web 引用**中**兼容性**部分。  
  
    -   在**添加 Web 引用**对话框框中，输入到 Web 服务的 URL **URL**文本中，然后单击**转**。  
  
    -   输入到该 Web 引用的名称**Web 引用名称**文本框中，然后单击**添加引用**按钮。  
  
    -   Web 引用将出现在**Web 引用**在解决方案资源管理器。  
  
        > [!TIP]
        >  Web 引用添加到项目中，一旦**添加 Web 引用**右键单击项目名称时，命令时直接可用或**引用**或**Web 引用**.  
  
2.  将 Web 端口添加到您的业务流程：  
  
    -   拖动**端口**从工具箱拖到某个端口的形状呈现在业务流程设计器中以启动**端口配置向导**。 单击**下一步**按钮**端口配置向导**以显示**端口属性**对话框。  
  
    -   输入一个值**名称**文本框中，以确定该端口，并单击**下一步**按钮以显示**选择端口类型**对话框。  
  
    -   选择该选项以**使用现有的端口类型**，选择 Web 端口类型对应于 Web 引用你添加，并单击**下一步**按钮以显示**端口绑定**对话框。  
  
    -   在**端口绑定**对话框选择相应**端口绑定**选项，然后单击**下一步**按钮，然后单击**完成**按钮。 现在，你应有包括 Web 服务支持的操作的业务流程设计器中显示的 Web 端口。  
  
3.  添加**发送**和**接收**根据您的业务流程的形状：  
  
    -   拖动**发送**从工具箱拖到连接线配置业务流程将请求消息发送到 Web 端口的业务流程设计器图面中的形状。 如果连接**发送**形状上的与 Web 端口之一请求消息连接器时，BizTalk 将自动创建适当类型的消息，用于将请求消息发送到此端口。  
  
    -   拖动**接收**从工具箱拖到连接线的业务流程设计器图面，配置业务流程，用于从 Web 端口接收响应消息中的形状。 如果连接**接收**形状 Web 端口响应消息连接器之一，BizTalk 将自动创建适当类型的消息，用于接收来自此端口的响应消息。  
  
> [!NOTE]
>  使用 SOAP 适配器向 Web Services 发送消息或者接收来自 Web Services 的消息。 有关配置 SOAP 适配器的详细信息请参阅[配置 SOAP 适配器](../core/configuring-the-soap-adapter.md)。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程引擎支持使用由 Web Services 公开的一维和交错数组。 如果添加对公开数组的 Web Services 的 Web 引用，业务流程设计器将生成用于描述相应数组的 Web 消息类型。 然后，您就可以像收发任何其他消息一样，收发此种类型的消息。 BizTalk Server 并不是只允许将包含数组的 Web 消息发送到 Web 端口。  
  
 使用 Web 服务数组的示例，请参阅 SDK 示例"使用 Web 服务"和"使用 Web 服务与数组参数"在[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
## <a name="see-also"></a>另请参阅  
 [在业务流程中使用消息](../core/using-messages-in-orchestrations.md)