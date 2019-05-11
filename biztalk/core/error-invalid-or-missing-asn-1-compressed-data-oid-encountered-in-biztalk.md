---
title: 无效或缺失的 ASN.1 压缩数据 OID 解压缩处理期间遇到 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0171daa8-289a-43f1-8cbf-d779ef9dc2ea
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d65dbf7d41612d6060516c20864d131207e7720
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388778"
---
# <a name="invalid-or-missing-asn1-compressed-data-oid-encountered-during-decompression-processing"></a>解压缩处理期间 ASN.1 压缩数据 OID 无效或缺失
## <a name="details"></a>详细信息  
  
|                 |                                                                                          |
|-----------------|------------------------------------------------------------------------------------------|
|  产品名称   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| 产品版本 |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                |
|    事件 ID     |                                            -                                             |
|  事件源   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI  |
|    组件    |                                        AS2 引擎                                        |
|  符号名称  |                                            -                                             |
|  消息正文   | 解压缩处理期间 ASN.1 压缩数据 OID 无效或缺失 |
  
## <a name="explanation"></a>解释  
 此错误是指压缩数据的 ASN.1 结构。 此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。  
  
## <a name="user-action"></a>用户操作  
 查看压缩数据的结构并检查是否对消息进行了篡改。