---
title: UNA 段无效。 它不包含 6 个字段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c939d8d3-e6fb-4505-836d-31559fc5f1a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7aaa5714a3063ba5039c042fb24c5c6a9a28f7d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258660"
---
# <a name="una-segment-is-invalid-it-did-not-contain-6-fields"></a>UNA 段无效。 它不包含 6 个字段
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                             UnaDidNotContainSixDelimiters                              |
|  消息正文   |                  UNA 段无效。 它不包含 6 个字段                   |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的 EDIFACT 交换，因为 UNA 段包含的数据元素少于 6 个。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让交换的发送方确保 UNA 段包含 6 个数据元素，然后重新发送交换。