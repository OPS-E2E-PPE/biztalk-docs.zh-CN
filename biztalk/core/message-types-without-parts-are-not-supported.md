---
title: 消息类型不支持部分没有 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0bfb042-feda-4282-a7fa-c13be4ff6254
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef2ef118aab93f10d766aeaf34af74a23908822
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394537"
---
# <a name="message-types-without-parts-are-not-supported"></a>不支持没有部分消息类型
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| 产品版本 |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    事件 ID     |                                                             0                                                             |
|  事件源   |                                                             0                                                             |
|    组件    |                                                             0                                                             |
|  符号名称  |                                                             0                                                             |
|  消息正文   | 不支持没有部分的消息类型。 更正服务说明"{0}"消息类型"{1}"，然后重新运行该向导。 |
  
## <a name="explanation"></a>解释  
 此错误表示尝试使用该服务不具有定义的消息类型。  
  
## <a name="user-action"></a>用户操作  
 更正服务与相应的消息类型，然后尝试使用 （如果您拥有要尝试使用的 WCF 服务）。 否则，请联系服务提供商。  有关消息的其他信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  
  
-   [构造 Web 消息](../core/constructing-web-messages.md)