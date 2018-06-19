---
title: 如何配置 BAM WCF 截获 |Microsoft 文档
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
ms.openlocfilehash: e90577a73abc0291635bf4b7d9bad34a11d1f806
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249205"
---
# <a name="how-to-configure-the-bam-wcf-interception"></a>如何配置 BAM WCF 侦听
若要配置用于 WCF 侦听的 BAM，必须修改侦听器配置文件，以便访问事件源的相应程序集清单。  
  
 配置事件时必须指定格式正确[XPath](../core/xpath.md)的操作的表达式。  
  
 你可以创建格式正确[XPath](../core/xpath.md)表达式使用在侦听器配置中通过启用 WCF 跟踪和运行应用程序来生成示例 WCF 日志，其中包含该消息。 你可以使用**Microsoft 服务跟踪查看器**(SvcTraceViewer.exe) 查看日志和提取消息。 该查看器包含在 WCF SDK 中。 所需[XPath](../core/xpath.md)表达式然后可以在消息形成基于并应用于的侦听器配置。  
  
 配置 BAM WCF 侦听时，machine.config 文件中使用的行为扩展名应与在接收位置的自定义行为配置中使用的扩展名匹配，这一点非常重要。 在 machine.config 文件中更改已配置的接收位置的扩展名将导致无法加载行为。 此外，接收位置的配置 UI 将失败。  
  
 就群集方案而言，由于自定义行为仅配置一次，因此必须确保群集中计算机上的所有 machine.config 文件都指定相同文件扩展名。  
  
### <a name="to-set-the-manifest"></a>设置清单  
  
1.  将侦听配置中 EventSource 中的清单设置为“Microsoft.BizTalk.Adapter.Wcf.Runtime.ITwoWayAsyncVoid, Microsoft.BizTalk.Adapter.Wcf.Runtime, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35”  
  
    > [!NOTE]
    >  接口基于使用的服务/接收端口的类型发生更改。 根据下表更改清单行，以反映正在使用的端口类型。  
  
    |端口类型|改用|  
    |---------------|---------|  
    |双向端口|ITwoWayAsync|  
    |带有本质上为两个双向绑定的单向端口（例如 HTTP）。|ITwoWayAsyncVoid|  
    |带有本质上为事务的两个双向绑定的单向端口。|ITwoWayAsyncVoidTxn|  
    |单向绑定（例如 MSMQ）。|IOneWayAsync|  
    |事务的单向绑定。|IOneWayAsyncTxn|  
  
    > [!IMPORTANT]
    >  在筛选器，而不是使用[GetOperationName](../core/getoperationname.md)操作，作为在下面的示例中突出显示使用 XPath 操作。 对于泛型协定，所有消息都在某一泛型操作中到达，此时，消息将基于消息本身路由到特定操作（“操作”属性）。  
  
2.  此时，操作名称始终相同。 就使用泛型协定的 WCF 适配器而言，采用的方法为 BizTalkSubmit。 您可以使用“操作”节点的 XPath（而不是 GetOperationName）来检索操作名称。 然后可对操作名称进行筛选。  
  
## <a name="sample-interceptor-configurations"></a>示例侦听器配置  
 本示例显示如何使用 WCF 适配器的 ServiceRequest 和 ServiceReply。 突出显示部分中[XPath](../core/xpath.md)操作的表达式用于筛选而不是使用操作[GetOperationName](../core/getoperationname.md)。 同样，您还可以筛选答复，但只能在 ITwoWayAsync 情况下筛选。 所有其他接口不会返回任何内容，或者返回空。  
  
### <a name="servicerequest"></a>serviceRequest  
  
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
  
## <a name="see-also"></a>另请参阅  
 [配置 WCF 适配器以截获 BAM 数据](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)