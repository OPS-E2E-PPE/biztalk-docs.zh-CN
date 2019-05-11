---
title: 解压缩处理期间无效或缺失尾部 ASN.1 CMS 压缩结构字节 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b73ce58-d827-4ffc-b2d7-78836298efc8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6fd6f7e3d40b9f7f28d58642d85dd0f00d25f02
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347956"
---
# <a name="invalid-or-missing-trailing-asn1-cms-compressed-structure-bytes-during-decompression-processing"></a>解压缩处理期间尾部 ASN.1 CMS 压缩结构字节无效或缺失
## <a name="details"></a>详细信息  
  
|                 |                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------|
|  产品名称   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]        |
| 产品版本 |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                    |
|    事件 ID     |                                                -                                                 |
|  事件源   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI      |
|    组件    |                                            AS2 引擎                                            |
|  符号名称  |                                                -                                                 |
|  消息正文   | 解压缩处理期间尾部 ASN.1 CMS 压缩结构字节无效或缺失 |
  
## <a name="explanation"></a>解释  
 此错误是指压缩数据的 ASN.1 结构。 此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。  
  
## <a name="user-action"></a>用户操作  
 查看压缩数据的结构并检查是否对消息进行了篡改。