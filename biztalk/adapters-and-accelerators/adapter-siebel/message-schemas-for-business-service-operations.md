---
title: 为业务服务操作消息架构 |Microsoft Docs
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
ms.openlocfilehash: edb01e8179dada40b3f2996cc2d1918ef117dd0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371391"
---
# <a name="message-schemas-for-business-service-operations"></a>业务服务操作的消息架构
Siebel 业务服务是可以直接调用 Siebel 系统的业务方法的集合。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel 业务服务的业务方法作为操作的图面。  

## <a name="message-schemas-for-siebel-business-service-method-operations"></a>Siebel 业务服务方法操作的消息架构  
 下表显示了显示的 Siebel 业务服务方法操作的消息架构[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  


|           操作            |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    XML 结构                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                       Description                                                                                                                                                                                        |
|--------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Business_Service_METHOD_NAME] | 业务服务方法请求消息：<br /><br /> `<[METHOD_NAME] xmlns="[VERSION]/BusinessServices/[Business Service]/Operation">   <[METHOD_NAME]RequestRecord>     <[I_PRM1_NAME]>value1</[I_PRM1_NAME]>     <[I_PRM2_NAME]>value2</[I_PRM2_NAME]>     …   </[METHOD_NAME]RequestRecord>   <[METHOD_NAME]InOutRecord>     <[IO_PRM1_NAME]>value1</[IO_PRM1_NAME]>     <[IO_PRM2_NAME]>value2</[IO_PRM2_NAME]>     …   </[METHOD_NAME]InOutRecord> </[METHOD_NAME]>`<br /><br /> [VERSION] = 消息版本字符串;例如，"<http://Microsoft.LobServices.Siebel/2007/03>"。<br /><br /> [业务服务] = 业务服务; 的名称例如，ExtractDataService。<br /><br /> [METHOD_NAME] = 业务服务方法的名称;例如，ExecuteNext。<br /><br /> [I_PRM_NAME] = 名称的 IN 参数。<br /><br /> [IO_PRM_NAME] = 名称的在 OUT 参数。<br /><br /> 业务服务方法响应消息：<br /><br /> `<[METHOD_NAME]Response xmlns="[VERSION]/BusinessServices/[Business Service]/Operation">   <[METHOD_NAME]Result>     <[O_PRM1_NAME]>value1</[O_PRM1_NAME]>     <[O_PRM2_NAME]>value2</[O_PRM2_NAME]>     …   </[METHOD_NAME]Result>   <[METHOD_NAME]InOutRecord>     <[IO_PRM1_NAME]>value1</[IO_PRM1_NAME]>     <[IO_PRM2_NAME]>value2</[IO_PRM2_NAME]>     …   </[METHOD_NAME]InOutRecord > </[METHOD_NAME]Response>`<br /><br /> [VERSION] = 消息版本字符串;例如，"<http://Microsoft.LobServices.Siebel/2007/03>"。<br /><br /> [业务服务] = 业务服务; 的名称例如，ExtractDataService。<br /><br /> [METHOD_NAME] = 业务服务方法; 的名称例如，ExecuteNext。<br /><br /> [O_PRM_NAME] = 的名称 OUT 参数。<br /><br /> [IO_PRM_NAME] = INOUT 名称参数。<br /><br /> **重要提示：** 即使它们所必需的 Siebel 系统中查看和 OUT 参数始终标记为可选的元数据中。 因此，如果一个参数被标记为可选但 Siebel 系统所需的元数据中，适配器将引发`TargetSystemException`从 Siebel 接收，而不`XmlReaderParsingException`。 | Siebel 业务服务方法作为操作名称。<br /><br /> -在中，在输出和输出参数支持。<br /><br /> 的以字符串形式显示层次结构的类型。 Siebel 适配器不会验证这些字符串传递的值。 如果这些值不符合所需的 Siebel 系统的架构，将生成运行时异常。 |

## <a name="message-actions-for-siebel-business-service-method-operations"></a>Siebel 业务服务方法操作的消息操作  
 下表显示了如何构成 Siebel 业务服务方法的 SOAP 操作。 仅用于请求消息的操作显示，该操作的响应消息由构成"/ 响应"到请求的消息操作;例如，"[VERSION] / BusinessServices/ExtractDataService/ExecuteNext/响应"。  

|操作|操作|Description|  
|---------------|------------|-----------------|  
|[Business_Service_METHOD_NAME]|[VERSION]/BusinessServices/[Business Service]/[Business_Service_METHOD_NAME]|[VERSION]/BusinessServices/ExtractDataService/ExecuteNext|  

 [VERSION] = 消息版本字符串;例如，"<http://Microsoft.LobServices.Siebel/2007/03>"。  

 [业务服务] = 业务服务; 的名称例如，ExtractDataService。  

 [Business_Service_METHOD_NAME] = 业务服务方法的名称;例如，ExecuteNext。  

 当使用时，必须显式指定的消息操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]在 BizTalk Server 解决方案或通过使用 WCF 通道模型。 有关详细信息，请参阅[开发 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)。  

## <a name="siebel-business-service-wcf-client-methods"></a>Siebel 业务服务 WCF 客户端方法  
 下表显示[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]生成的服务模型方法签名[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]Siebel 业务服务方法。  

|操作|WCF 服务模型方法|  
|---------------|------------------------------|  
|[Business_Service_METHOD_NAME]|`[Business_Service_METHOD_NAME]ResponseRecord client.[Business_Service_METHOD_NAME]([Business_Service_METHOD_NAME]RequestRecord);`<br /><br /> [Business_Service_METHOD_NAME] = 业务服务方法名称;例如，ExecuteNext。|  

## <a name="see-also"></a>请参阅  
 [消息和用于 Siebel eBusiness 应用程序的 BizTalk 适配器的消息架构](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)