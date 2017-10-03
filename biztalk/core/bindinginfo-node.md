---
title: "绑定信息节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: BindingInfo node [binding file]
ms.assetid: a71d100c-cf8b-4a54-b239-ee0ca2d8148c
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3dc15cbfe4bb3a98e17a894c5a763c0ca18bdcb3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="bindinginfo-node"></a>BindingInfo 节点
**绑定信息**绑定文件的节点是绑定文件的根节点，并且包含适用于所有绑定文件中的项的信息以及有关 BizTalk Server 的信息的绑定文件导出从。  
  
## <a name="nodes-in-the-bindinginfo-node"></a>BindingInfo 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Assembly|Attribute|xs:string|指定创建绑定文件时 Microsoft.BizTalk.Deployment dll 使用的信息。 包括此程序集的用逗号分隔的 Version、Culture 和 PublicKeyToken 属性。|必需|默认值： **"Microsoft.BizTalk.Deployment，Version = 3.0.1.0，区域性 = neutral，PublicKeyToken = 31bf3856ad364e35"**|  
|版本|Attribute|xs:string|指定在其上生成绑定文件的 BizTalk Server 的版本。|必需|默认值： **3.5.1.0**|  
|BindingStatus|Attribute|BindingState (SimpleType)|指定与绑定文件一起导出的项目的绑定状态。|必需|默认值： 无<br /><br /> 有效值：<br /><br /> -未知<br />-NoBindings<br />-未绑定<br />-PartiallyBound<br />-FullyBound|  
|BoundEndpoints|Attribute|xs:int|指定绑定文件中绑定端点的数目。|必需|默认值： **0**|  
|TotalEndpoints|Attribute|xs:int|指定绑定文件中端点的总数。|必需|默认值： **0**|  
|Description|元素|xs:string|指定绑定文件中 BindingInfo 部分的文本说明。|可选|默认值：空|  
|时间戳|元素|xs:dateTime|指定导出绑定文件的时间。|必需|默认值： 上的 BizTalk server 时的绑定文件导出时间。|  
|[ModuleRefCollection 节点](../core/modulerefcollection-node.md)|录制|ArrayOfModuleRef (ComplexType)|与绑定文件一起导出的 .NET 程序集的容器节点。|可选|默认值：无|  
|[SendPortCollection 节点](../core/sendportcollection-node.md)|录制|ArrayOfSendPort (ComplexType)|与绑定文件一起导出的发送端口的容器节点。|可选|默认值：无|  
|[DistributionListCollection 节点](../core/distributionlistcollection-node.md)|录制|ArrayOfDistributionList (ComplexType)|与绑定文件一起导出的分发列表的容器节点。|可选|默认值：无|  
|[ReceivePortCollection 节点](../core/receiveportcollection-node.md)|录制|ArrayOfReceivePort (ComplexType)|与绑定文件一起导出的接收端口的容器节点。|可选|默认值：无|  
  
 下面的代码显示了在绑定文件的 BindingInfo  节点中使用的 XML 的格式：  
  
```  
<BindingInfo xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
Assembly="Microsoft.BizTalk.Deployment, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
Version="3.5.1.0" BindingStatus="FullyBound"   
BoundEndpoints="12"   
TotalEndpoints="12">  
<Description/>  
<Timestamp>2005-08-23T16:27:40.5948205-07:00</Timestamp>  
```  
  
## <a name="see-also"></a>另请参阅  
 [自定义绑定文件](../core/customizing-binding-files.md)