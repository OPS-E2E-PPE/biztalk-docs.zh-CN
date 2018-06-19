---
title: 动态解析示例的双向消息处理方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e89792f1-c725-46c4-946c-23211e2f892a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 852b1f203b693c7783c7eb461c521f3fbe0ceffe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296037"
---
# <a name="two-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a>动态解析示例的双向消息处理方案
本主题演示如何能够运行的双向消息传递方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]动态解析示例。  
  
 **若要运行的动态解析示例双向消息处理方案**  
  
1.  首次运行此示例之前，请确保接收位置 URL 指向适当的 Web 服务。 指定 Web 服务 URL /ESB。有关 DynamicResolutionReqResp_SOAP NorthAmericanServices/CustomerOrder.asmx 接收位置。 此外，请确保存在名为 DynamicResolutionSolicitResp 的动态发送端口。  
  
    > [!NOTE]
    >  动态解析示例使用动态解析将消息发送到，和从加拿大 Web 服务 (http://localhost/ESB.CanadianServices/SubmitPOService.asmx) 接收响应。 这是此示例未定义静态发送端口的原因。 动态解析组件解析检索的出站 URL 和适配器提供程序框架由 ESBReceiveXml 管道中，在 DynamicResolutionReqResp_SOAP 配置，则接收位置。 在某些双向消息传送示例，ESBMapSend 管道将解析和执行 Microsoft BizTalk 映射。  
  
2.  如果 GlobalBank.ESB 应用程序尚未运行，使用 BizTalk 管理控制台来启动它。  
  
3.  决定你想要执行的示例。 所有的双向消息传递方案使用 ESB。NorthAmericanServices Web 服务位于 http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx 将请求消息发布到 BizTalk，使用名为 DynamicResolutionReqResp_SOAP 接收位置。 有 10 双向消息传送示例，每个由唯一绑定文件。 下表列出了这些示例中，与其关联的绑定文件和说明。  
  
    |SOAP 到 SOAP 出站 （将订单操作） 的入站使用 BRE 冲突解决程序|  
    |---------------------------------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
  
    |SOAP 到 SOAP 出站 （将订单操作） 的入站终结点和转换解析使用 BRE 冲突解决程序|  
    |----------------------------------------------------------------------------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Routing_AND_ Transform_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |使用出站发送端口上的 ESB 调度程序组件管道和出站接收位置管道动态解析和执行映射。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
  
    |SOAP 到 SOAP 出站 （将订单操作） 的入站使用静态冲突解决程序|  
    |------------------------------------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |将地图静态处接收端口设置。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
  
    |SOAP 到 SOAP 出站 （将订单操作） 的入站使用 UDDI 冲突解决程序针对 Microsoft UDDI 服务器|  
    |--------------------------------------------------------------------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_MSFTREGISTRY_ Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |将地图静态处接收端口设置。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
  
    > [!NOTE]
    >  对于前面的示例中，你必须将绑定文件中的服务密钥更改为一个目标 UDDI 服务器上存在。  
  
    |SOAP 到 SOAP 出站 （将订单操作） 的入站使用 UDDI 冲突解决程序针对 SOA 软件 UDDI 服务器|  
    |-----------------------------------------------------------------------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_SOAREGISTRY_ Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |将地图静态处接收端口设置。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
  
    |SOAP 到 SOAP 出站 （将订单操作） 的入站使用 XPATH 冲突解决程序|  
    |-----------------------------------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_XPATH_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |将地图静态处接收端口设置。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
    |该消息包含的终结点配置 ID = http://localhost/ESB.CanadianServices/SubmitPOService.asmx 和 customerName = http://globalbank.esb.dynamicresolution.com/canadianservices/。|  
  
    |SOAP 到 SOAP 出站 (submitPurchase 操作) 的入站使用 BRE 冲突解决程序终结点和转换解析|  
    |---------------------------------------------------------------------------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_BRE_Routing_ AND_Transform_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |使用出站发送端口上的 ESB 调度程序组件管道和出站接收位置管道动态解析和执行映射。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
    |BRE 冲突解决程序更改**操作**从**将订单**到**submitPurchase**。|  
  
    |SOAP 到 SOAP 出站 (submitPurchase 操作) 的入站使用静态冲突解决程序|  
    |---------------------------------------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_STATIC_ Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |将地图静态处接收端口设置。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
    |静态解析程序更改**操作**从**将订单**到**submitPurchase**。|  
  
4.  导入你想要执行到 GlobalBank.ESB 应用程序的消息传送示例的绑定文件。  
  
5.  调用 NorthAmerican Web 服务使用 Microsoft InfoPath、.NET Web 服务 Studio 中或任何其他适当的机制。 请确保包括所需的操作的所有参数。  
  
6.  查找返回的消息响应。 如果你指定**将订单**操作，"提交 Order"的文本将前的值**ID**字段中返回的消息。 如果你指定**submitPurchase**操作，"提交购买"的文本将前的值**ID**字段中返回的消息。  
  
 若要了解该示例的 ESB 调度程序和 ESB 调度程序反汇编程序管道组件的使用，请参阅[动态解析示例的工作原理](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)。