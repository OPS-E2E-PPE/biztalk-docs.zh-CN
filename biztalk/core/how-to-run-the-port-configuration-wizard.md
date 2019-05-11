---
title: 如何运行端口配置向导 |Microsoft Docs
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
ms.openlocfilehash: a12efffbcf7d5f283fd4c42547b628e77af08bcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334893"
---
# <a name="how-to-run-the-port-configuration-wizard"></a>如何运行端口配置向导
使用端口配置向导来创建和配置端口在业务流程设计器中。 端口必须具有与其关联的端口类型和您使用向导来选择现有端口类型或创建新的端口类型。 有关端口和端口类型的详细信息，请参阅[业务流程中使用端口](../core/using-ports-in-orchestrations.md)。  
  
### <a name="to-start-the-wizard"></a>若要启动向导  
  
1.  右键单击端口 （在设计图面上或在业务流程视图窗口中），单击**配置端口**。  
  
2.  运行其关联的操作会导致一个端口，以创建智能标记项。  
  
3.  选择**新配置的端口参数**命令从业务流程视图窗口中的业务流程参数文件夹的快捷菜单。  
  
### <a name="to-run-the-wizard"></a>若要运行向导  
  
1.  打开端口配置向导。  
  
2.  指定的端口信息。 为了帮助您，向导将显示多个页面。 完成每个页后，迁移到以下通过单击**下一步**，或将移动到通过单击前一次**回**。  
  
    -   **端口属性**。 键入端口的名称。  
  
    -   **选择端口类型。** 在此页上，您首先选择是否想**新建端口类型**或**现有端口类型**。 如果选择**现有端口类型**，然后使用树控件来选择要分配现有端口类型。  
  
         如果选择**新建端口类型**，然后，你需要键入的名称中的端口类型**名称**文本，或接受建议的默认名称。 您还选择端口类型的通信模式 (单向或请求-响应) 和任何访问限制在新建端口类型。  
  
    -   **端口绑定**。 此页上，指定的方向的通信，也称为*极性*，以及该端口的绑定类型。  
  
         您所做的极性选择部分取决于您在向导的上一页选择的端口类型的通信模式**选择端口类型**。 下表总结了你的选择：  
  
        |端口方向|通信模式|若要选择端口绑定页面上的通信方向|  
        |--------------------|---------------------------|---------------------------------------------------------------|  
        |Send|单向|我将始终在发送消息此端口上。|  
        |Receive|单向|我始终将接收此端口上的消息。|  
        |发送接收|要求响应|我将发送请求并接收响应。|  
        |接收发送|请求-响应|我将接收请求并发送响应。|  
  
         有四个不同的绑定类型的选择：以后指定、 立即指定、 动态和直接。 每个选项显示一组不同的配置选项，如下所述：  
  
         **指定更高版本。** 选择此选项后，您无需再配置向导中做出选择因为在设计时不确定的绑定信息。 通常它是由管理员在部署时添加。  
  
         **立即指定。** 可以在设计时指定一个 URI，定义的端口是要绑定的实体。 此外需要从包含 BizTalk 消息队列、 文件、 SMTP、 HTTP 和 SOAP 传输类型的列表中选择。 这是为了在业务流程设计器中; 早期绑定的硬编码列表因此，其他传输不可用在此列表中。 最后，选择接收管道和发送管道中的可用管道列表。 每个列表中包括的所有管道中当前的项目以及从引用的程序集，其中显示了选择管道的选项**选择项目类型**对话框。  
  
         **动态。** 此选项具有类似的选项**立即指定**，但仅适用于发送端口。 您可以指定要使用的发送管道。 可以指定的端口中单独**表达式**形状，以便在运行时分配。  
  
         **直接。** 对于直接绑定，您可以选择连接到，若要进行路由基于筛选器表达式对 MessageBox 数据库中传入的消息或使它成为自相关端口的端口。 可以从下拉列表框中选择的端口。  
  
         有关详细信息，请参阅[端口绑定](../core/port-bindings.md)。  
  
3.  完成向导。 端口配置向导，标题为的最后一页**完成端口向导**，显示你所做的选择在前面的页面，以便可以在提交更改之前进行验证。 如果所做的更改是否正确，请单击**完成**。 否则，请单击**回**重新输入你想要更改的任何信息。 然后再次将通过该向导并单击**完成**时想要进行的更改相匹配的最后一页上显示的信息。  
  
    > [!NOTE]
    >  如果你要创建一个新的端口并且单击**取消**在任何时间之前完成端口配置向导中，该端口未创建。 如果已使用向导来修改现有的端口，取消向导撤消所做的任何更改。 否则为如果您单击**取消**在向导中，仍然会创建适配器，但未设置其属性。 您可以手动设置端口属性作为端口，在属性窗口中也可以再次运行向导。  
  
## <a name="see-also"></a>请参阅  
 [在业务流程中使用端口](../core/using-ports-in-orchestrations.md)