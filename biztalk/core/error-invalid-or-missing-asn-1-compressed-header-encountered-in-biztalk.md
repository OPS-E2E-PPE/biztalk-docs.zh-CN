---
title: "无效或缺少 ASN.1 压缩的标头解压缩处理过程中遇到 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e59afea-436c-42c0-b424-0b72dd9db9a8
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5847e077958a334704248bbc9c8cc21c2bb03d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-or-missing-asn1-compressed-header-encountered-during-decompression-processing"></a>无效或缺少 ASN.1 压缩解压缩处理过程中遇到的标头
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|-|  
|消息正文|无效或缺少 ASN.1 压缩解压缩处理过程中遇到的标头|  
  
## <a name="explanation"></a>解释  
 此错误是指压缩数据的 ASN.1 结构。 此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。  
  
## <a name="user-action"></a>用户操作  
 查看压缩数据的结构并检查是否对消息进行了篡改。