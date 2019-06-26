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
ms.openlocfilehash: 64c0481242c86038cde10a0505b5a12f039ec9bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357659"
---
# <a name="callorchestration-biztalk-server-sample"></a>CallOrchestration （BizTalk Server 示例）
CallOrchestration 示例演示如何从另一个业务流程调用一个 BizTalk 业务流程。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例演示一个业务流程调用另一个业务流程使用以下步骤序列：  
  
1.  主业务流程接收采购订单 (PO) 消息。  
  
2.  主业务流程调用次业务流程来确定采购订单的发货价格。  
  
3.  次业务流程计算请求的发货价格，并将其返回给主业务流程。  
  
4.  主业务流程使用返回的发货价格更新采购订单消息。  
  
5.  主业务流程将更新后的采购订单消息放入文件夹备查。  
  
## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 此示例的主要目的是说明如何调用另一个业务流程内的从业务流程。 调用业务流程的能力，可以将您的业务流程划分为可重用的组件。 您可以分解到不同的其他人重复使用的业务流程将通用流程。  
  
 在此示例中，**调用业务流程**receivePO.odx 中的形状调用 findShippingPrice.odx，并等待嵌套的业务流程 findShippingPrice.odx 来计算并返回发货价格发送在购买前顺序。 业务流程 findShippingPrice.odx 使用以下逻辑来计算发货价格：  
  
```  
If ( weight * shippingRate ) < minShippingPrice Then  
    shippingPrice = minShippingPrice  
Else  
    shippingPrice = weight * shippingRate  
End If  
```  
  
 示例输入采购订单文件 InputPO.xml 指定权重为 20，从而导致输出采购订单消息将其发货价格由 10 更改为 20。  
  
> [!NOTE]
>  不能从原子业务流程调用长期事务。  
  
> [!NOTE]
>  使用不同之处**调用业务流程**形状和**启动业务流程**形状是，在调用业务流程时，调用方等到嵌套的业务流程返回之前继续操作。 当从业务流程中，启动业务流程，调用方启动该操作后，调用方将向前移动到处理流程的下一步。 调用方已调用的业务流程独立运行，直到它完成处理流程。 有关详细信息，请参阅[如何配置调用业务流程形状](../core/how-to-configure-the-call-orchestration-shape.md)。 另请参阅[如何配置启动业务流程形状](../core/how-to-configure-the-start-orchestration-shape.md)。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*Samples Path*\>\Orchestrations\CallOrchestration\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|CallOrchestration.btproj, CallOrchestration.sln|本示例的项目和解决方案文件。|  
|CallOrchestrationBinding.xml|用于如端口绑定之类的自动化设置。|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存中删除。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|findShippingPrice.odx|从主业务流程调用可作为次业务流程的 BizTalk 业务流程 receivepo.odx 进行。|  
|InputPO.xml|示例输入采购订单消息符合 PO.xsd 文件中定义的架构。|  
|PO.xsd|定义如示例输入文件 InputPO.xml 的入站采购订单消息的结构并在架构中定义的属性升级的所有三个元素的架构。|  
|PropertySchema.xsd|参与架构 PO.xsd 中所有三个元素的属性升级的属性架构文件。|  
|receivePO.odx|充当主业务流程，在此示例中的 BizTalk 业务流程。 它从接收文件夹检索采购订单消息，然后调用其他业务流程 findShippingPrice.odx 来计算和更新发货价格。|  
|Setup.bat|用于生成和初始化本示例。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
#### <a name="to-build-and-initialize-the-callorchestration-sample"></a>若要生成并初始化 CallOrchestration 示例  
  
1. 在命令窗口中，导航到以下文件夹：  
  
    \<*Samples Path*\>\Orchestrations\CallOrchestration\  
  
2. 运行文件 Setup.bat，以执行以下操作：  
  
   - 创建输入 (In) 和输出 (Out) 文件夹中，为此示例在 CallOrchestration 文件夹。  
  
   - 编译并部署[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]包含两个业务流程，此示例的项目。  
  
   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收端口。  
  
   - 启用该接收位置，并启动发送端口。  
  
> [!NOTE]
>  您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-callorchestration-sample"></a>若要运行 CallOrchestration 示例  
  
1.  将 InputPO.xml 文件的副本放到 In 文件夹。  
  
2.  查看在 Out 文件夹中创建的已更新的 XML 采购订单文件。 它包含原始采购订单消息，修改为包含计算如前面所述的发货费用。 此文件的名称的格式\< *MessageID*\>.xml，其中 *\<MessageID\>* 生成的 GUID 来唯一标识消息.  
  
## <a name="uninstalling-this-sample"></a>卸载本示例  
  
#### <a name="to-uninstall-the-callorchestration-sample"></a>若要卸载 CallOrchestration 示例  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令窗口中，导航到以下文件夹：  
  
    \<*Samples Path*\>\Orchestrations\CallOrchestration\  
  
2. 运行 Cleanup.bat。  
  
## <a name="see-also"></a>请参阅  
 [业务流程（BizTalk Server 示例文件夹）](../core/orchestrations-biztalk-server-samples-folder.md)