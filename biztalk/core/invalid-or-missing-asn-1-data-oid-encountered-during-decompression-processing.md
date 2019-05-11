---
title: 解压缩处理期间遇到无效或缺失 ASN.1 数据 OID |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 243062ae-19df-4989-b8d9-109e789f8335
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b41205b44447b447ce0ce39222e49e7b65988112
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330748"
---
# <a name="invalid-or-missing-asn1-data-oid-encountered-during-decompression-processing"></a>解压缩处理期间 ASN.1 数据 OID 无效或缺失
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                                           -                                            |
|  消息正文   |     解压缩处理期间 ASN.1 数据 OID 无效或缺失      |
  
## <a name="explanation"></a>解释  
 此错误是指压缩数据的 ASN.1 结构。 此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。  
  
## <a name="user-action"></a>用户操作  
 查看压缩数据的结构并检查是否对消息进行了篡改。