---
title: Edifact 交换应该包含 UNA 或 UNB 作为第一个段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc43fd17-31d0-48df-93cd-524b40034764
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 196b589ff886bed005e251c7172a3fd720d88868
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530739"
---
# <a name="edifact-interchange-should-have-contained-una-or-unb-as-the-first-segment"></a>Edifact 交换应该包含 UNA 或 UNB 作为第一个段
## <a name="details"></a>详细信息  
  
|                 |                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------|
|  产品名称   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]        |
| 产品版本 |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                    |
|    事件 ID     |                                                -                                                 |
|  事件源   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI      |
|    组件    |                                            EDI 引擎                                            |
|  符号名称  |                                                -                                                 |
|  消息正文   | Edifact 交换应该包含 UNA 或 UNB 作为第一个段。 而是{0}找 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道无法处理传入的 EDIFACT 交换，因为第一个段既不是 UNA，也不是 UNB 段。 UNA 段是可选的；UNB 段是必需的。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换的发送方包含 UNA 或 UNB 段作为交换的第一个段，然后重新发送交换。