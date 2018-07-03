---
title: 消息类型不允许作为协议的一部分 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 829f8230-33b8-4b5f-a56a-d0c1d3a17271
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ed9c1e4891a3365484b60e51848a998f2d152b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982366"
---
# <a name="message-type-is-not-allowed-as-part-of-the-agreement"></a>不允许将消息类型作为协议的一部分
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                          TransactionSetNotAllowedDescription                           |
|  消息正文   |               消息类型{0}不允许作为协议的一部分。                |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 能够处理文档，因为不允许该文档的消息类型是协议的一部分。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请查看允许是协议的一部分以及不允许是协议的一部分的消息类型。