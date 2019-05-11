---
title: 无效的 AS2-从处理过程中遇到的名称 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba658119-9171-4851-835c-72c188275b73
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9d007b4c20a21606b83395ef1a4d2226cca8508
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381381"
---
# <a name="invalid-as2-from-name-encountered-during-processing"></a>无效的 AS2-从处理过程中遇到的名称
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                           InvalidAS2FromNameEncounteredError                           |
|  消息正文   |            无效的 AS2-从处理过程中遇到的名称。  值： {0}            |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明的接收管道无法处理传入的交换或发送管道无法处理传出的交换，因为 as2-From 标头不符合AS2 RFC 4130 中的规范。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保 AS2-From 中传入或传出消息的标头符合 AS2 RFC 4130 第，6.2 节中的规范，然后重新发送消息。