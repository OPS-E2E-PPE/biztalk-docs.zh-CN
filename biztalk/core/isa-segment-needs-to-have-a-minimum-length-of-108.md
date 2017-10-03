---
title: "ISA 段需要具有最小长度为 108 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57641445-cebb-4219-998d-54038d7ddf19
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ecd5c6761c6dbcc59ad6353efa2772b9eecf387
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="isa-segment-needs-to-have-a-minimum-length-of-108"></a>ISA 段需要具有最小长度为 108
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|NseIsaSuffix1LFDescription|  
|消息正文|ISA 段需要具有最小长度为 108、 实例具有 {0}|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示接收管道不无法处理传入的交换，因为交换中的 ISA 段不符合到的位数由服务架构 (X12ServiceSchema 或EdifactServiceSchema BaseArtifacts.dll 中)。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，确保每个的 ISA 段 （ISA16 到 ISA01) 中的字段具有所需最少数字个数。 可以通过打开 BizTalk Server 管理控制台；打开“BizTalk 组”节点、“应用程序”节点、“BizTalk EDI 应用程序”节点，然后是架构节点；打开根节点为 ISA 的 Microsoft.BizTalk.Edi.BaseArtifacts.X12ServiceSchema；然后单击“架构视图”来查看最小位数。