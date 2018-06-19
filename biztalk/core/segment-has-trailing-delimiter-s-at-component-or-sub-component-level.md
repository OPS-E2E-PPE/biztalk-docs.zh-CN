---
title: 段具有在组件或子组件级别的尾随 delimiter(s) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 517f1cfc-66c1-47e6-be94-2c76c1f89230
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eede2923da1ed206a897b879b7b6be589800e4c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269661"
---
# <a name="segment-has-trailing-delimiters-at-component-or-sub-component-level"></a>段在组件或子组件级别上具有尾部分隔符
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12SeSegmentHasTrailingDelimiterDescription|  
|消息正文|段在组件或子组件级别上具有尾部分隔符|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为该交换包含尾部分隔符，但没有为“作为交换发送方的参与方”启用尾部分隔符。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请按照如下方式启用尾部分隔符：  
  
1.  打开 BizTalk Server 管理控制台，移动到“参与方”文件夹，打开该参与方的“EDI 属性”。  
  
2.  对于 X12 或 EDIFACT，根据需要移动到“验证和 ACK 生成”页。  
  
3.  单击“允许尾部分隔符”。