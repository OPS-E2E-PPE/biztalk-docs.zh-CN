---
title: 如何运行端口配置向导 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Port Configuration Wizard [Orchestration Designer], starting
- Port Configuration Wizard [Orchestration Designer], how to
- Port Configuration Wizard [Orchestration Designer], about Port Configuration Wizard
- ports, Port Configuration Wizard [Orchestration Designer]
- Port Configuration Wizard [Orchestration Designer]
ms.assetid: 8035ce32-5ed4-49cb-b6f0-998b0460751e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbdb5843eb8011478f13c0de6443bb1ded177378
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255789"
---
# <a name="how-to-run-the-port-configuration-wizard"></a>如何运行端口配置向导
您可以使用端口配置向导在业务流程设计器中创建和配置端口。 端口必须具有与之关联的端口类型，您可以使用该向导来选择现有的端口类型或创建新的端口类型。 有关端口和端口类型的详细信息，请参阅[在业务流程中使用端口](../core/using-ports-in-orchestrations.md)。  
  
### <a name="to-start-the-wizard"></a>若要启动向导  
  
1.  右键单击一个端口 （设计图面上或业务流程视图窗口中），单击**配置端口**。  
  
2.  运行其关联操作会导致创建端口的智能标记项。  
  
3.  选择**新配置端口参数**Orchestration 视图窗口中的业务流程参数文件夹的快捷菜单命令。  
  
### <a name="to-run-the-wizard"></a>若要运行向导  
  
1.  打开端口配置向导。  
  
2.  指定端口信息。 向导将显示若干页以协助您执行操作。 完成每个页后，将其迁移到以下通过单击**下一步**，或将移动到前一次通过单击**回**。  
  
    -   **端口属性**。 为端口键入名称。  
  
    -   **选择端口类型。** 在此页上，你首先选择你是否想**新端口类型**或**现有端口类型**。 如果你选择**现有端口类型**，然后使用树控件选择要分配的现有端口类型。  
  
         如果你选择**新端口类型**，然后需要键入的名称中的端口类型**名称**文本框中，或接受建议的默认名称。 还需要选择端口类型的通信模式（单向或请求响应）以及针对新端口类型的任何访问限制。  
  
    -   **端口绑定**。 此页上你指定的方向的通信，也称为*极性*，和端口的绑定类型。  
  
         你所做的极性选择部分取决于你在向导的上一页中选择的端口类型的通信模式**选择端口类型**。 下表对这些选项进行了概括介绍：  
  
        |端口方向|通信模式|要在“端口绑定”页上选择的通信方向|  
        |--------------------|---------------------------|---------------------------------------------------------------|  
        |Send|单向|我将始终发送消息上此端口。|  
        |Receive|单向|始终在此端口上接收消息。|  
        |发送-接收|请求作出响应|我将发送请求并接收响应。|  
        |接收-发送|请求-响应|我将接收请求并发送响应。|  
  
         您可以从四种不同的绑定类型中选择：“以后指定”、“立即指定”、“动态”和“直接”。 每个选项显示一组不同的配置选项，如下所述：  
  
         **指定更高版本。** 在选择此选项之后，在本向导中将不用再选择配置，因为绑定信息不是在设计时确定的。 通常，它由管理员在部署时添加。  
  
         **指定现在。** 您可以在设计时指定一个 URI，该 URI 将定义该端口要绑定到的实体。 您还需要从传输类型（包括 BizTalk 消息队列、FILE、SMTP、HTTP 和 SOAP）列表中进行选择。 此列表是用于业务流程设计器中的早期绑定的硬编码列表；因此，其他传输类型不包含在此列表中。 最后，从可用管道列表中选择接收管道和发送管道。 每个列表中当前的项目以及从引用的程序集，其中显示了选择管道的选项包括所有管道**选择项目类型**对话框。  
  
         **动态。** 此选项具有类似于选择**现在指定**，但它是仅适用于发送端口。 您可以指定要使用的发送管道。 你可以指定在单独的端口**表达式**调整，以便在运行时分配。  
  
         **直接。** 对于直接绑定，您可以选择要连接到的端口、要基于筛选器表达式对 MessageBox 数据库中的传入消息进行路由的端口，或者要成为自相关端口的端口。 您可以从下拉列表框中选择端口。  
  
         有关详细信息，请参阅[端口绑定](../core/port-bindings.md)。  
  
3.  完成向导。 标题为在端口配置向导的最后一页**完成端口向导**，显示你所做的选择在前面的页上，以便可以将更改提交之前进行验证。 如果所做的更改是否正确，请单击**完成**。 否则，请单击**回**重新输入你想要更改的任何信息。 然后再次将完成该向导并单击**完成**最后一页上显示的信息匹配需要进行的更改时。  
  
    > [!NOTE]
    >  如果你要创建一个新的端口，并且你单击**取消**在任何时间之前完成端口配置时向导中，该端口未创建。 如果是使用该向导来修改现有向导，则取消向导将会撤消之前所做的所有更改。 否则为如果你单击**取消**在向导中，仍创建该适配器，但未设置其属性。 您可以在端口的“属性”窗口中手动设置端口属性，也可以重新运行本向导。  
  
## <a name="see-also"></a>另请参阅  
 [使用在业务流程中的端口](../core/using-ports-in-orchestrations.md)