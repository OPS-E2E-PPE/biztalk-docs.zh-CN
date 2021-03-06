---
title: 如何配置 BAM WCF 侦听 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d85aa130-3219-4df1-8974-a44a51a15002
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51eb7a1a5e7fc8ac6c94af3f16051d85dd8731b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341225"
---
# <a name="how-to-configure-the-bam-wcf-interception"></a>如何配置 BAM WCF 侦听
若要配置 BAM WCF 侦听，必须修改侦听器配置文件来访问正确的程序集清单的事件源。  
  
 配置事件时必须指定正确格式[XPath](../core/xpath.md)的操作的表达式。  
  
 您可以创建格式正确[XPath](../core/xpath.md)表达式要在中使用的侦听器配置启用 WCF 跟踪并运行应用程序生成的示例 WCF 日志，其中包含的消息。 可以使用**Microsoft Service Trace Viewer** (SvcTraceViewer.exe) 来查看日志并提取消息。 该查看器包含在 WCF sdk。 所需[XPath](../core/xpath.md)可根据消息构成和应用于侦听器配置表达式。  
  
 在配置 BAM WCF 侦听时，很重要的 machine.config 文件中使用的行为扩展与接收位置的自定义行为配置中使用的扩展名匹配。 更改扩展名称的一个已配置接收位置在 machine.config 文件会导致无法加载的行为。 此外，接收位置的配置 UI 将失败。  
  
 对于群集方案中，由于自定义行为仅配置一次，您必须确保群集中的计算机上的所有 machine.config 文件都指定相同的文件扩展名。  
  
### <a name="to-set-the-manifest"></a>若要设置清单  
  
1.  设置在清单中 eventsource 中侦听配置到 Microsoft.BizTalk.Adapter.Wcf.Runtime.ITwoWayAsyncVoid，Microsoft.BizTalk.Adapter.Wcf.Runtime，版本 = 3.0.1.0，区域性 = 中性，PublicKeyToken = 31bf3856ad364e35  
  
    > [!NOTE]
    >  界面更改使用的服务/接收端口的类型。 更改清单行，以反映根据下表使用的端口的类型。  
  
    |端口类型|改用|  
    |---------------|---------|  
    |双向端口|ITwoWayAsync|  
    |单向端口与绑定，它本质上是两个 2 方法 (例如，HTTP)。|ITwoWayAsyncVoid|  
    |单向端口与绑定，它本质上是两个双向事务。|ITwoWayAsyncVoidTxn|  
    |是一种方式 (例如，MSMQ) 的绑定。|IOneWayAsync|  
    |事务的单向绑定。|IOneWayAsyncTxn|  
  
    > [!IMPORTANT]
    >  中的筛选器，而不是使用[GetOperationName](../core/getoperationname.md)操作，在下面的示例中突出显示的那样使用 XPath 操作。 对于泛型协定的所有消息都到达某一泛型操作，此时它们会路由到基于消息本身 （操作属性） 的特定操作。  
  
2.  操作名称将始终是相同的此位置。 （它使用泛型协定） 的 WCF 适配器使用的方法为 BizTalkSubmit。 可以使用而不是 GetOperationName 操作节点的 XPath 来检索操作名称。 然后可以对操作名称进行筛选。  
  
## <a name="sample-interceptor-configurations"></a>示例侦听器配置  
 此示例演示 WCF 适配器的 ServiceRequest 和 ServiceReply 的使用情况。 在突出显示部分[XPath](../core/xpath.md)要执行的操作的表达式用于筛选而不是使用操作[GetOperationName](../core/getoperationname.md)。 您可以筛选答复，但只能在 ITwoWayAsync 情况下。 所有其他接口不返回任何内容，或者返回空。  
  
### <a name="servicerequest"></a>ServiceRequest  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="WCFServiceRequest" Source="WCFService">  
      <ic:Filter>  
        <ic:Expression>  
          <wcf:Operation Name="GetServiceContractCallPoint"/>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>ServiceRequest</ic:Argument>  
          </ic:Operation>  
          <ic:Operation Name ="Equals" />  
          <wcf:Operation Name ="XPath">  
            <wcf:Argument>//s:Header/a:Action</wcf:Argument>  
          </wcf:Operation>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>Operation1</ic:Argument>  
          </ic:Operation>  
          <ic:Operation Name ="Equals" />  
          <ic:Operation Name ="And" />  
        </ic:Expression>  
      </ic:Filter>  
  
      <ic:CorrelationID>  
        <ic:Expression>  
          <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
        </ic:Expression>  
      </ic:CorrelationID>  
  
      <ic:Update DataItemName ="Activity Date" Type ="DATETIME">  
        <ic:Expression>  
          <wcf:Operation Name ="GetContextProperty">  
            <wcf:Argument>EventTime</wcf:Argument>  
          </wcf:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
      <ic:Update DataItemName ="Source" Type ="NVARCHAR">  
        <ic:Expression>  
          <ic:Operation Name="Constant">  
            <ic:Argument>WcfAdapter_ServiceRequest</ic:Argument>  
          </ic:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
    </ic:OnEvent>  
```  
  
### <a name="servicereply"></a>ServiceReply  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="WCFServiceReply" Source="WCFService">  
      <ic:Filter>  
        <ic:Expression>  
          <wcf:Operation Name="GetServiceContractCallPoint"/>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>ServiceReply</ic:Argument>  
          </ic:Operation>  
          <ic:Operation Name ="Equals" />  
        </ic:Expression>  
      </ic:Filter>  
  
      <ic:CorrelationID>  
        <ic:Expression>  
          <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
        </ic:Expression>  
      </ic:CorrelationID>  
  
      <ic:Update DataItemName ="Activity Date" Type ="DATETIME">  
        <ic:Expression>  
          <wcf:Operation Name ="GetContextProperty">  
            <wcf:Argument>EventTime</wcf:Argument>  
          </wcf:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
      <ic:Update DataItemName ="Name" Type ="NVARCHAR">  
        <ic:Expression>  
          <ic:Operation Name="Constant">  
            <ic:Argument>WcfAdapter_ServiceReply</ic:Argument>  
          </ic:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
    </ic:OnEvent>  
```  
  
## <a name="see-also"></a>请参阅  
 [配置 WCF 适配器以侦听 BAM 数据](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)