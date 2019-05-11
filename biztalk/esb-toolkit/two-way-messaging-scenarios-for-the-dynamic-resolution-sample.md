---
title: 动态解析示例的双向消息传送方案 |Microsoft Docs
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
ms.openlocfilehash: 6141ccc31943844c87182a6682a705a62bf06382
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396545"
---
# <a name="two-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a>动态解析示例的双向消息传送方案
本主题演示如何运行的双向消息传送方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]动态解析示例。  

 **若要运行动态解析示例的双向消息传送方案**  

1. 第一次运行此示例之前，请确保接收位置 URL 指向适当的 Web 服务。 指定 Web 服务 URL /ESB。有关 DynamicResolutionReqResp_SOAP NorthAmericanServices/CustomerOrder.asmx 接收位置。 此外，请确保存在名为 DynamicResolutionSolicitResp 的动态发送端口。  

   > [!NOTE]
   >  动态解析示例使用动态解析发送邮件，并接收来自加拿大的 Web 服务响应 (http://localhost/ESB.CanadianServices/SubmitPOService.asmx)。 这就是原因本示例未定义静态发送端口。 动态解析组件解决方法从检索的出站 URL 和适配器提供程序框架调用 ESBReceiveXml 管道，在 DynamicResolutionReqResp_SOAP 中配置的接收位置。 在某些双向消息传送示例中，ESBMapSend 管道解析和执行 Microsoft BizTalk 映射。  

2. 如果尚未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。  

3. 决定你想要执行的示例。 所有的双向消息传送方案使用 ESB。NorthAmericanServices Web 服务位于 http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx 将请求消息发布到 BizTalk，使用名为 DynamicResolutionReqResp_SOAP 的接收位置。 有 10 个双向消息传送示例，每个唯一绑定文件表示。 下表列出了这些示例中，使用其关联的绑定文件和说明。  

   |SOAP 到 SOAP 出站 (submitOrder 操作) 的入站使用 BRE 冲突解决程序|  
   |---------------------------------------------------------------------------------|  
   |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
   |使用 ESB 调度程序在接收位置的终结点解析。|  

   |SOAP 到 SOAP 出站 (submitOrder 操作) 的入站终结点和转换解析使用 BRE 冲突解决程序|  
   |----------------------------------------------------------------------------------------------------------------------------|  
   |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Routing_AND_ Transform_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
   |使用出站发送端口上的 ESB 调度程序组件的管道和出站接收位置管道动态解析和执行映射。|  
   |使用 ESB 调度程序在接收位置的终结点解析。|  

   |SOAP 到 SOAP 出站 (submitOrder 操作) 的入站使用静态的冲突解决程序|  
   |------------------------------------------------------------------------------------|  
   |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
   |在接收端口以静态方式设置这些映射。|  
   |使用 ESB 调度程序在接收位置的终结点解析。|  

   |SOAP 到 SOAP 出站 (submitOrder 操作) 的入站使用 UDDI 解析程序对 Microsoft UDDI 服务器|  
   |--------------------------------------------------------------------------------------------------------------------|  
   |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_MSFTREGISTRY_ Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
   |在接收端口以静态方式设置这些映射。|  
   |使用 ESB 调度程序在接收位置的终结点解析。|  

   > [!NOTE]
   >  对于上述示例中，必须更改绑定文件中的服务密钥为其中一个目标 UDDI 服务器上存在。  

   |SOAP 到 SOAP 出站 (submitOrder 操作) 的入站使用 UDDI 解析程序针对 SOA 软件 UDDI 服务器|  
   |-----------------------------------------------------------------------------------------------------------------------|  
   |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_SOAREGISTRY_ Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
   |在接收端口以静态方式设置这些映射。|  
   |使用 ESB 调度程序在接收位置的终结点解析。|  

   |                                                            SOAP 到 SOAP 出站 (submitOrder 操作) 的入站使用 XPATH 冲突解决程序                                                            |
   |---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                 使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_XPATH_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。                  |
   |                                                                           在接收端口以静态方式设置这些映射。                                                                           |
   |                                                             使用 ESB 调度程序在接收位置的终结点解析。                                                              |
   | 该消息包含的终结点配置 ID =<http://localhost/ESB.CanadianServices/SubmitPOService.asmx>和 customerName =<http://globalbank.esb.dynamicresolution.com/canadianservices/>。 |

   |SOAP 到 SOAP 出站 (submitPurchase 操作) 的入站使用 BRE 冲突解决程序终结点和转换解析|  
   |---------------------------------------------------------------------------------------------------------------------------|  
   |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_BRE_Routing_ AND_Transform_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
   |使用出站发送端口上的 ESB 调度程序组件的管道和出站接收位置管道动态解析和执行映射。|  
   |使用 ESB 调度程序在接收位置的终结点解析。|  
   |BRE 冲突解决程序更改**操作**从**submitOrder**到**submitPurchase**。|  

   |                                              SOAP 到 SOAP 出站 (submitPurchase 操作) 的入站使用静态的冲突解决程序                                               |
   |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | 使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_STATIC_ Bindings.xml 的绑定文件来设置接收位置和发送端口属性。 |
   |                                                               在接收端口以静态方式设置这些映射。                                                                |
   |                                                  使用 ESB 调度程序在接收位置的终结点解析。                                                  |
   |                                           静态解析程序更改**操作**从**submitOrder**到**submitPurchase**。                                           |


4. 导入绑定文件对于您要执行到 GlobalBank.ESB 应用程序的消息传送示例。  

5. 调用 NorthAmerican Web 服务使用 Microsoft InfoPath、.NET Web 服务 Studio 或任何其他适当的机制。 请确保包含该操作所需的所有参数。  

6. 查找返回的消息响应。 如果指定了**submitOrder**操作，"提交订单"的文本将在之前的值**ID**字段中返回的消息。 如果指定了**submitPurchase**操作，"提交购买"的文本将在之前的值**ID**字段中返回的消息。  

   若要了解此示例如何使用 ESB 调度程序和 ESB 调度程序反汇编程序管道组件，请参阅[动态解析示例的工作原理](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)。