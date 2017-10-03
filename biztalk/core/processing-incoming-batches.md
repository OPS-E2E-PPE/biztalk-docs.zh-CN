---
title: "处理传入的批次 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98f47903-933a-4bde-b320-f7689c3d8366
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca3781d9b7c1ed2190a8334f272c04d304669ace
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="processing-incoming-batches"></a>处理传入批
当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 收到批处理 EDI 交换时，它可以将交换拆分为事务集，然后对每一个事务集分别加以处理，也可以保留交换，将所有事务集作为一个组进行处理。  
  
 确定在批处理**本地主机设置**页中的单向协议选项卡**协议属性**X12 和 EDIFACT 协议的对话框。 当保留交换时，如果出现错误，则可以选择挂起相应的交换或事务集。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [拆分批处理的 EDI 交换](../core/splitting-a-batched-edi-interchange.md)  
  
-   [拆分 HIPAA 子文档](../core/splitting-hipaa-subdocuments.md)  
  
-   [保留已收到批处理的 EDI 交换](../core/preserving-a-received-batched-edi-interchange.md)