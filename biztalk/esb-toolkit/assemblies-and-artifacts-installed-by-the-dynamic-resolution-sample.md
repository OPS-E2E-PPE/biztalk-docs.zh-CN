---
title: 程序集和动态解析示例安装的项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d9ffdc4-1721-4202-839c-04e5bffe8668
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc2c8bf9dbf6458c347e0136e49d88a6ee970d24
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392293"
---
# <a name="assemblies-and-artifacts-installed-by-the-dynamic-resolution-sample"></a>程序集和动态解析示例安装的项目
下表列出的程序集和项目安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]动态解析示例。  
  
|Location|Category|名称和版本的组件|  
|--------------|--------------|---------------------------------------|  
|BizTalk 应用程序 GlobalBank.ESB|业务流程|（无）|  
|BizTalk 应用程序 GlobalBank.ESB|发送端口|DynamicResolutionSolicitResp|  
|||DynamicResolutionOneWay|  
|BizTalk 应用程序 GlobalBank.ESB|接收端口|DynamicResolutionReqResp|  
|||DynamicResolution|  
|BizTalk 应用程序 GlobalBank.ESB|接收位置|DynamicResolutionReqResp_SOAP<br /><br /> DynamicResolution_FILE|  
|BizTalk 应用程序 GlobalBank.ESB|架构|GlobalBank.ESB.DynamicResolution.Schemas.CNPurchaseOrderResponse Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.NAOrderResponse 版本 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNOrderDoc Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNOrderResponse Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas.CNPurchaseOrderDoc Version 2.0.0.0|  
|BizTalk 应用程序 GlobalBank.ESB|管道|GlobalBank.ESB.DynamicResolution.Pipelines.ESBReceiveSendXMLXML Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Pipelines.ESBReceiveXML Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Pipelines.ESBPassThrough 版本 2.0.0.0|  
|BizTalk 应用程序 GlobalBank.ESB|资源|GlobalBank.ESB.DynamicResolution.Pipelines Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Transforms Version 2.0.0.0|  
|BizTalk 应用程序 GlobalBank.ESB|策略|CanadaSubmitOrderMaps.xml|  
|||GetCanadaEndPoint.xml|  
|||GetCanadaPurchaseEndPoint.xml|  
|||ResolveMap.xml|  
|||ResolveEndPoint.xml|  
|BizTalk 应用程序 GlobalBank.ESB|词汇|DynamicRunTimeDocSpecs.xml<br /><br /> DynamicRunTimeEndPoints.xml<br /><br /> DynamicRunTimeMapTypes.xml<br /><br /> DynamicRunTimeServiceActions.xml|  
|BizTalk 应用程序 GlobalBank.ESB|地图|GlobalBank.ESB.DynamicResolution.Transforms.SubmitPurchaseOrderResponseCN_To_SubmitOrderResponseNA Version=2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN Version=2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitPurchaseOrderRequestCN Version=2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderResponseCN_To_SubmitOrderResponseNA Version=2.0.0.0|  
|全局程序集缓存|程序集|GlobalBank.ESB.DynamicResolution.Pipelines Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Schemas Version 2.0.0.0|  
|||GlobalBank.ESB.DynamicResolution.Transforms Version 2.0.0.0|  
|%Program Files %\\BizTalk Server\Pipeline 组件|管道组件|（无）|