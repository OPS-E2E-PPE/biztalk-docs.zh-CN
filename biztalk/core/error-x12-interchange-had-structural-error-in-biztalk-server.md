---
title: '交换发生了结构错误。 最后一个结构有效功能组 ID 是: |Microsoft 文档'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd62855b-ecc6-4cfd-be9c-0025348eb841
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 565a4865455cabef3cd53988d601a89ecf1549e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241405"
---
# <a name="the-interchange-had-structural-error-last-structurally-valid-functional-group-id-was"></a>交换发生了结构错误。 上一个具有有效结构的功能组 ID 为：
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12InterchangeStructuralErrorAfter1stGroup|  
|消息正文|Id 为"{0}"，发件人 id {1} 交换，接收方 id {2} 在结构化错误。 最后一个结构有效功能组 ID 为 {3}|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为指明功能组之后在该交换中发生了结构错误。 这可能出现了具有在错误上挂起的事务集，正在保存的交换。 由于此错误，包含此错误的事务集被挂起，但是作为保留的批处理的一部分对其余事务集进行处理。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让交换的发送方解决此结构错误，然后重新发送交换。