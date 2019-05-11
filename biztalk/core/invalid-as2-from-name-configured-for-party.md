---
title: 无效的 AS2-从配置为参与方名称 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cde739bd-f6f7-4e4a-8f02-9a99e9d82fc9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4db0fe98bcb04f662e4a827f4139e0cff81275
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331043"
---
# <a name="invalid-as2-from-name-configured-for-party"></a>无效的 AS2-从配置为参与方名称
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                           InvalidAS2FromNameConfiguredError                            |
|  消息正文   |              无效的 AS2-从为参与方配置的名称：{0}   值： {1}              |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 AS2 编码器或解码器无法处理 AS2 消息因为 as2-From 标头配置为标识的参与方不符合 AS2 RFC 4130 中的规范。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保 AS2-From 标头配置为参与方符合 AS2 RFC 4130 第，6.2 节中的规范，然后重新发送消息。