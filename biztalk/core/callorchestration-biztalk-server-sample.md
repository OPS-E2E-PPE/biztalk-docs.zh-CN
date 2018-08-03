---
title: CallOrchestration （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, calling
- examples, orchestrations
ms.assetid: 0c4194f0-c1e2-419a-8a1a-a3c96e8d2667
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 614cbb4531d0d7052263e5e4c7d73ec209e9b685
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021875"
---
# <a name="callorchestration-biztalk-server-sample"></a>CallOrchestration （BizTalk Server 示例）
CallOrchestration 示例演示如何从一个 BizTalk 业务流程调用另一个业务流程。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例演示一个业务流程如何调用另一个业务流程，其具体的操作步骤如下所示：  
  
1.  主业务流程接收采购订单 (PO) 消息。  
  
2.  主业务流程调用次业务流程来确定采购订单的发货价格。  
  
3.  次业务流程计算所请求的发货价格，并将其返回给主业务流程。  
  
4.  主业务流程用返回的发货价格更新采购订单消息。  
  
5.  主业务流程将更新后的采购订单消息放入一个文件夹备查。  
  
## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 本示例的主要目的是演示如何从一个业务流程调用另一个业务流程。 通过调用业务流程，可以将业务程序分成可重用的组件。 您可以将通用流程分解为独立的业务流程，以便其他人重用。  
  
 在此示例中，**调用业务流程**receivePO.odx 中的形状调用 findShippingPrice.odx，并等待嵌套的业务流程 findShippingPrice.odx 来计算并返回发货价格发送在购买前顺序。 业务流程 findShippingPrice.odx 使用以下逻辑来计算发货价格：  
  
```  
If ( weight * shippingRate ) < minShippingPrice Then  
    shippingPrice = minShippingPrice  
Else  
    shippingPrice = weight * shippingRate  
End If  
```  
  
 本示例的输入采购订单文件 InputPO.xml 指定权重为 20，这导致输出采购订单消息将其发货价格由 10 更改为 20。  
  
> [!NOTE]
>  不能从原子业务流程调用长期事务。  
  
> [!NOTE]
>  使用不同之处**调用业务流程**形状和**启动业务流程**形状是，在调用业务流程时，调用方等到嵌套的业务流程返回之前继续操作。 而从一个业务流程启动另一个业务流程时，调用方启动该操作之后，即继续执行处理流程的下一步操作。 调用方所调用的业务流程将独立运行，直到它完成处理流程。 有关详细信息，请参阅[如何配置调用业务流程形状](../core/how-to-configure-the-call-orchestration-shape.md)。 另请参阅[如何配置启动业务流程形状](../core/how-to-configure-the-start-orchestration-shape.md)。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\Orchestrations\CallOrchestration\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|CallOrchestration.btproj、CallOrchestration.sln|本示例的项目文件和解决方案文件。|  
|CallOrchestrationBinding.xml|用于如端口绑定之类的自动化设置。|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存中删除这些程序集。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|findShippingPrice.odx|作为次业务流程的 BizTalk 业务流程，从主业务流程 receivePO.odx 进行调用。|  
|InputPO.xml|与 PO.xsd 文件中定义的架构相符的示例输入采购订单消息。|  
|PO.xsd|一种架构，用于定义入站采购订单消息（如示例输入文件 InputPO.xml）的结构以及架构中所有三个元素的属性升级。|  
|PropertySchema.xsd|参与架构 PO.xsd 中所有三个元素的属性升级的属性架构文件。|  
|receivePO.odx|在本示例中充当主业务流程的 BizTalk 业务流程。 它首先从接收文件夹中检索采购订单消息，然后调用另一个业务流程 findShippingPrice.odx 来计算和更新发货价格。|  
|Setup.bat|用于生成和初始化本示例。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化本示例  
  
#### <a name="to-build-and-initialize-the-callorchestration-sample"></a>生成并初始化 CallOrchestration 示例  
  
1. 在命令窗口中，导航到下面的文件夹：  
  
    \<*示例路径*\>\Orchestrations\CallOrchestration\  
  
2. 运行 Setup.bat 文件，该文件将执行以下操作：  
  
   - 在 CallOrchestration 文件夹中，为本示例创建输入 (In) 和输出 (Out) 文件夹。  
  
   - 为本示例编译并部署 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目（包括这两个业务流程）。  
  
   - 创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。  
  
   - 启用接收位置并启动发送端口。  
  
> [!NOTE]
>  在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-callorchestration-sample"></a>运行 CallOrchestration 示例  
  
1.  将 InputPO.xml 文件的副本放到 In 文件夹中。  
  
2.  查看在 Out 文件夹中创建的已更新 XML 采购订单文件。 此文件包含原始采购订单消息，现在已修改为包含按前述方法计算出的发货费用。 此文件的名称的格式\< *MessageID*\>.xml，其中*\<MessageID\>* 生成的 GUID 来唯一标识消息.  
  
## <a name="uninstalling-this-sample"></a>卸载本示例  
  
#### <a name="to-uninstall-the-callorchestration-sample"></a>卸载 CallOrchestration 示例  
  
1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 命令窗口中，导航到以下文件夹：  
  
    \<*示例路径*\>\Orchestrations\CallOrchestration\  
  
2. 运行 Cleanup.bat。  
  
## <a name="see-also"></a>请参阅  
 [业务流程（BizTalk Server 示例文件夹）](../core/orchestrations-biztalk-server-samples-folder.md)