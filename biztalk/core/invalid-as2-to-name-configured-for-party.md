---
title: 无效的 AS2-到配置为参与方名称 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a203e5f2-d1d9-433f-b2bb-d679bb8fea58
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fdf3f4c307d8985df7e79ca1b8b45c569b76966
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381451"
---
# <a name="invalid-as2-to-name-configured-for-party"></a>无效的 AS2-到配置为参与方名称
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                            InvalidAS2ToNameConfiguredError                             |
|  消息正文   |               无效的 AS2-到为参与方配置的名称：{0}   值： {1}               |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 AS2 编码器或解码器无法处理 AS2 消息因为 as2-To 标头配置为标识的参与方不符合 AS2 RFC 4130 中的规范。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保 AS2-To 标头配置为参与方符合 AS2 RFC 4130 第 6.2 节中的规范。