---
title: 业务服务操作的消息架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message schemas, for business service methods
ms.assetid: ba23248b-5d73-4de0-9f7c-987cd88a4b63
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0062b8e6b6ce3961c937e9e5bece81cb24281049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222293"
---
# <a name="message-schemas-for-business-service-operations"></a>业务服务操作的消息架构
Siebel 业务服务是可以直接调用 Siebel 系统的业务方法的集合。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]呈现 Siebel 业务服务的业务方法作为操作。  
  
## <a name="message-schemas-for-siebel-business-service-method-operations"></a>Siebel 业务服务方法操作的的消息架构  
 下表显示 Siebel 业务服务方法操作显示的消息架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
|运算|XML 结构|Description|  
|---------------|-------------------|-----------------|  
|[Business_Service_METHOD_NAME]|业务服务方法请求消息：<br /><br /> `<[METHOD_NAME] xmlns="[VERSION]/BusinessServices/[Business Service]/Operation">   <[METHOD_NAME]RequestRecord>     <[I_PRM1_NAME]>value1</[I_PRM1_NAME]>     <[I_PRM2_NAME]>value2</[I_PRM2_NAME]>     …   </[METHOD_NAME]RequestRecord>   <[METHOD_NAME]InOutRecord>     <[IO_PRM1_NAME]>value1</[IO_PRM1_NAME]>     <[IO_PRM2_NAME]>value2</[IO_PRM2_NAME]>     …   </[METHOD_NAME]InOutRecord> </[METHOD_NAME]>`<br /><br /> [VERSION] = 消息版本字符串;例如，"http://Microsoft.LobServices.Siebel/2007/03"。<br /><br /> [业务服务] = 业务服务; 的名称例如，ExtractDataService。<br /><br /> [METHOD_NAME] = 业务服务方法; 的名称例如，ExecuteNext。<br /><br /> [I_PRM_NAME] = 名称的 IN 参数。<br /><br /> [IO_PRM_NAME] = 名称的 IN OUT 参数。<br /><br /> 业务服务方法响应消息：<br /><br /> `<[METHOD_NAME]Response xmlns="[VERSION]/BusinessServices/[Business Service]/Operation">   <[METHOD_NAME]Result>     <[O_PRM1_NAME]>value1</[O_PRM1_NAME]>     <[O_PRM2_NAME]>value2</[O_PRM2_NAME]>     …   </[METHOD_NAME]Result>   <[METHOD_NAME]InOutRecord>     <[IO_PRM1_NAME]>value1</[IO_PRM1_NAME]>     <[IO_PRM2_NAME]>value2</[IO_PRM2_NAME]>     …   </[METHOD_NAME]InOutRecord > </[METHOD_NAME]Response>`<br /><br /> [VERSION] = 消息版本字符串;例如，"http://Microsoft.LobServices.Siebel/2007/03"。<br /><br /> [业务服务] = 业务服务; 的名称例如，ExtractDataService。<br /><br /> [METHOD_NAME] = 业务服务方法; 的名称例如，ExecuteNext。<br /><br /> [O_PRM_NAME] = 的名称 OUT 参数。<br /><br /> [IO_PRM_NAME] = INOUT 名称参数。<br /><br /> **重要说明：** IN OUT 和 OUT 参数始终被标记为可选中元数据，即使 Siebel 系统需要使用它们。 因此，如果参数标记为可选但按 Siebel 系统所需的元数据中，该适配器将引发`TargetSystemException`接收到来自 Siebel 和 not `XmlReaderParsingException`。|Siebel 业务服务方法呈现为操作名称。<br /><br /> -在中，在输出和输出参数支持。<br /><br /> 的作为字符串中加以表示层次结构的类型。 Siebel 适配器不会验证这些字符串的传递的值。 如果 Siebel 系统所需的架构不符合这些值，则会生成运行时异常。|  
  
## <a name="message-actions-for-siebel-business-service-method-operations"></a>Siebel 业务服务方法操作的的消息操作  
 下表显示如何构成 Siebel 业务服务方法的 SOAP 操作。 仅用于请求消息的操作显示，操作的响应消息通过追加形成"/ 响应"到请求消息操作;例如，"[VERSION] / BusinessServices/ExtractDataService/ExecuteNext/响应"。  
  
|运算|操作|Description|  
|---------------|------------|-----------------|  
|[Business_Service_METHOD_NAME]|[VERSION] /BusinessServices/ [业务服务] / [Business_Service_METHOD_NAME]|[VERSION] / BusinessServices/ExtractDataService/ExecuteNext|  
  
 [VERSION] = 消息版本字符串;例如，"http://Microsoft.LobServices.Siebel/2007/03"。  
  
 [业务服务] = 业务服务; 的名称例如，ExtractDataService。  
  
 [Business_Service_METHOD_NAME] = 业务服务方法; 的名称例如，ExecuteNext。  
  
 使用时，必须显式指定的消息操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]BizTalk Server 解决方案中或通过使用 WCF 通道模型。 有关详细信息，请参阅[开发应用程序 Siebel](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)。  
  
## <a name="siebel-business-service-wcf-client-methods"></a>Siebel 业务服务 WCF 客户端方法  
 下表显示[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]由生成的服务模型方法签名[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]Siebel 业务服务方法。  
  
|运算|WCF 服务模型方法|  
|---------------|------------------------------|  
|[Business_Service_METHOD_NAME]|`[Business_Service_METHOD_NAME]ResponseRecord client.[Business_Service_METHOD_NAME]([Business_Service_METHOD_NAME]RequestRecord);`<br /><br /> [Business_Service_METHOD_NAME] = 业务服务方法名称;例如，ExecuteNext。|  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 Siebel eBusiness Applications 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)