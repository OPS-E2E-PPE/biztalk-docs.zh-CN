---
title: 解压缩处理过程中遇到无效或缺少 ASN.1 ZLib OID |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb41e0fe-2fdd-4dfc-830f-c28dfe6efac8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9d1c0f0cf6f79517479332656e257644e19b88f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257533"
---
# <a name="invalid-or-missing-asn1-zlib-oid-encountered-during-decompression-processing"></a>解压缩处理期间 ASN.1 ZLib OID 无效或缺失
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|-|  
|消息正文|解压缩处理期间 ASN.1 ZLib OID 无效或缺失|  
  
## <a name="explanation"></a>解释  
 此错误是指压缩数据的 ASN.1 结构。 此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。  
  
## <a name="user-action"></a>用户操作  
 查看压缩数据的结构并检查是否对消息进行了篡改。