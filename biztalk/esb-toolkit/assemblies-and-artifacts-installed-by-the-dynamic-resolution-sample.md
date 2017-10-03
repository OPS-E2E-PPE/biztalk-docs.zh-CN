---
title: "程序集和项目安装动态解析示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d9ffdc4-1721-4202-839c-04e5bffe8668
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f564d2faceca0753d37bd9c045e403f5f016734
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="assemblies-and-artifacts-installed-by-the-dynamic-resolution-sample"></a>程序集和项目安装动态解析示例
下表列出的程序集和项目安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]动态解析示例。  
  
|位置|类别|名称和版本的组件|  
|--------------|--------------|---------------------------------------|  
|BizTalk 应用程序 GlobalBank.ESB|业务流程|（无）|  
|BizTalk 应用程序 GlobalBank.ESB|发送端口|DynamicResolutionSolicitResp|  
|||DynamicResolutionOneWay|  
|BizTalk 应用程序 GlobalBank.ESB|接收端口|DynamicResolutionReqResp|  
|||DynamicResolution|  
|BizTalk 应用程序 GlobalBank.ESB|接收位置|DynamicResolutionReqResp_SOAP<br /><br /> DynamicResolution_FILE|  
|BizTalk 应用程序 GlobalBank.ESB|架构|GlobalBank.ESB.DynamicResolution.Schemas.CNPurchaseOrderResponse 版本 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc 版本 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.NAOrderResponse 版本 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNOrderDoc 版本 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNOrderResponse 版本 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNPurchaseOrderDoc 版本 2.0.0.0|  
|BizTalk 应用程序 GlobalBank.ESB|管道|GlobalBank.ESB.DynamicResolution.Pipelines.ESBReceiveSendXMLXML 版本 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Pipelines.ESBReceiveXML 版本 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Pipelines.ESBPassThrough 版本 2.0.0.0|  
|BizTalk 应用程序 GlobalBank.ESB|Resources|GlobalBank.ESB.DynamicResolution.Pipelines 版本 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas 版本 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Transforms 版本 2.0.0.0|  
|BizTalk 应用程序 GlobalBank.ESB|策略|CanadaSubmitOrderMaps.xml|  
|||GetCanadaEndPoint.xml|  
|||GetCanadaPurchaseEndPoint.xml|  
|||ResolveMap.xml|  
|||ResolveEndPoint.xml|  
|BizTalk 应用程序 GlobalBank.ESB|词汇表|DynamicRunTimeDocSpecs.xml<br /><br /> DynamicRunTimeEndPoints.xml<br /><br /> DynamicRunTimeMapTypes.xml<br /><br /> DynamicRunTimeServiceActions.xml|  
|BizTalk 应用程序 GlobalBank.ESB|地图|GlobalBank.ESB.DynamicResolution.Transforms.SubmitPurchaseOrderResponseCN_To_SubmitOrderResponseNA 版本 = 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN 版本 = 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitPurchaseOrderRequestCN 版本 = 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderResponseCN_To_SubmitOrderResponseNA 版本 = 2.0.0.0|  
|全局程序集缓存|程序集|GlobalBank.ESB.DynamicResolution.Pipelines 版本 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas 版本 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Transforms 版本 2.0.0.0|  
|%Program 文件 %\\[!INCLUDE[prague](../includes/prague-md.md)]\Pipeline 组件|管道组件|（无）|