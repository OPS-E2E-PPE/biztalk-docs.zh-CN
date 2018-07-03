---
title: 尝试进行解码的 AS2 消息时遇到 BTS MIME 错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65cb5ece-78e4-4b83-b126-4d8c588b2c61
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 629e09e950a6c49263230f23725002eee9be905b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985918"
---
# <a name="a-bts-mime-error-was-encountered-when-attempting-to-decode-an-as2-message"></a>尝试对 AS2 消息进行解码时遇到 BTS MIME 错误
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                         |
| 产品版本 |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                     |
|    事件 ID     |                                                                 -                                                                  |
|  事件源   |                                                         BizTalk Server EDI                                                         |
|    组件    |                                                             AS2 引擎                                                             |
|  符号名称  |                                                                 -                                                                  |
|  消息正文   | 尝试对 AS2 消息进行解码时遇到 BTS MIME 错误。  AS2-从： {0}，AS2-到： {1}，MessageId: {2}，错误： {3} |
  
## <a name="explanation"></a>解释  
 使用 BizTalk MIME 组件处理 MIME 处理的一部分时遇到此错误。  
  
## <a name="user-action"></a>用户操作  
 完整的错误消息提供了有关 MIME 组件所遇到的问题的信息。 请参阅 BTS MIME 错误信息有关的问题的诊断 （这是因为 AS2 组件对 MIME 处理的一部分使用 BizTalk MIME 组件）。