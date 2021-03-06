---
title: 中从 ISA 数据读取分隔符时遇到错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8cb60abd-53c8-45e1-a840-d27dc974aad7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e99412ee1d0048aa3d7d6db373d20fe9af0ac57e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348493"
---
# <a name="error-encountered-in-reading-delimiters-from-isa-data"></a>读取 ISA 数据中的分隔符时遇到错误
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                     InvalidIsaData                                     |
|  消息正文   |                 读取 ISA 数据中的分隔符时遇到错误                  |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道在处理传入的 X12 交换时遇到错误，因为它无法解析 ISA 段中的分隔符。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请验证传入交换的 ISA 段中的分隔符是否唯一且有效。 如果不是，则交换的发送方在每个分隔符字段（重复分隔符的 ISA11 段和组件分隔符的 ISA16 段）输入唯一且有效的值，然后重新发送交换。