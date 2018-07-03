---
title: 无效的 Adler32 校验和遇到 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa47a208-0f33-496e-8dbe-b50be9979bf2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acaa60e9d6f1bda4161832cb5ddb34c4e2e9ae93
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987262"
---
# <a name="invalid-adler32-checksum-encountered"></a>遇到无效的 Adler32 校验和
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                     InvalidAdler32ChecksumInCompressedMessageError                     |
|  消息正文   |                          遇到无效的 Adler32 校验和                          |
  
## <a name="explanation"></a>解释  
 此错误是指压缩数据的 ASN.1 结构。 此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。  
  
## <a name="user-action"></a>用户操作  
 利用**遇到无效的 Adler32 校验和**指示篡改的可能性非常高。 如果您看到篡改检查**遇到无效的 Adler32 校验和**。