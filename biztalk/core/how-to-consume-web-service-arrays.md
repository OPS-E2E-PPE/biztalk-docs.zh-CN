---
title: 如何使用 Web 服务数组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, Web services
- Web services, arrays
- orchestrations, Web services
- orchestrations, Web ports
ms.assetid: 29ecaaed-aa8a-4cf9-a7c8-4b0d6dd412ac
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f783c8521d1fbfbf3ffa9297f970ab54e90ce313
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385674"
---
# <a name="how-to-consume-web-service-arrays"></a>如何使用 Web 服务数组
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以使用在 BizTalk 业务流程中的 Web services 中公开的数组。  
  
 **若要配置的业务流程，以使用 Web 服务中公开的数组：**  
  
 确定公开数组的 Web 服务的 URL。 这通常是 asmx Web 页，其中列出了支持 Web 服务的操作。 例如： http://localhost/ArrayWS/ArraySvc.asmx。  
  
1.  在包含您的业务流程的 Visual Studio 项目中添加 Web 引用到此 URL:  
  
    -   在解决方案资源管理器，右键单击**引用**，然后单击**添加服务引用**。  
  
    -   在中**添加服务引用**对话框中，单击**高级**。  
  
    -   在中**服务引用设置**对话框中，单击**添加 Web 引用**中**兼容性**部分。  
  
    -   在中**添加 Web 引用**对话框框中，输入到 Web 服务 URL **URL**文本框中，然后单击**转**。  
  
    -   输入 Web 引用的名称**Web 引用名**文本框中，然后单击**添加引用**按钮。  
  
    -   Web 引用将显示下**Web 引用**在解决方案资源管理器。  
  
        > [!TIP]
        >  添加到项目中，Web 引用后**添加 Web 引用**当您右键单击项目名称时，才直接可用命令或**引用**或**的Web引用**.  
  
2.  向业务流程添加 Web 端口：  
  
    -   拖动**端口**以启动在业务流程设计器中的形状从工具箱拖到一个端口图面**端口配置向导**。 单击**下一步**按钮**端口配置向导**以显示**端口属性**对话框。  
  
    -   输入一个值**名称**文本框中，用于标识的端口，然后单击**下一步**按钮以显示**选择端口类型**对话框。  
  
    -   选择选项**使用现有端口类型**，选择 Web 端口类型对应于 Web 引用添加，并单击**下一步**按钮以显示**端口绑定**对话框。  
  
    -   在中**端口绑定**对话框中选择相应**端口绑定**选项，然后单击**下一步**按钮，然后单击**完成**按钮。 现在应具有包含 Web 服务支持的操作的业务流程设计器中显示的 Web 端口。  
  
3.  添加**发送**并**接收**向相应的业务流程的形状：  
  
    -   拖动**发送**形状从工具箱拖到业务流程设计器图面，若要配置业务流程，以将请求消息发送到 Web 端口中的连接线。 如果连接**发送**形状添加到其中一个 Web 端口请求消息连接器，BizTalk 将自动创建向此端口发送请求消息时要使用的相应类型的消息。  
  
    -   拖动**接收**形状从工具箱拖到业务流程设计器图面，若要配置为接收来自 Web 端口的响应消息的业务流程中的连接线。 如果连接**接收**形状到其中一个 Web 端口响应消息连接器，BizTalk 将自动创建接收来自此端口的响应消息时要使用的相应类型的消息。  
  
> [!NOTE]
>  使用 SOAP 适配器将消息发送到或从 Web 服务接收消息。 有关配置 SOAP 适配器的详细信息请参阅[配置 SOAP 适配器](../core/configuring-the-soap-adapter.md)。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程引擎使用一维和交错数组公开的 Web 服务提供支持。 如果添加对公开数组的 Web 服务的 Web 引用时，业务流程设计器将生成 Web 消息类型用于描述相应数组。 然后，您可以发送和接收方式与任何其他消息类似此类型的消息。 BizTalk Server 不会限制的 Web 消息包含数组到仅 Web 端口发送。  
  
 有关使用 Web 服务数组的示例，请参阅 SDK 示例"使用 Web 服务"和"使用 Web 服务与数组参数"网址[ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
## <a name="see-also"></a>请参阅  
 [在业务流程中使用消息](../core/using-messages-in-orchestrations.md)