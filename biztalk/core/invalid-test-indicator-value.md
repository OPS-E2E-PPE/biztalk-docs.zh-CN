---
title: 无效的测试指示器值 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d81d501-4020-4ff9-955c-5674a99d250b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89245453e7b1b7d8c40e33bf25a3ab3aac1933db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991022"
---
# <a name="invalid-test-indicator-value"></a>测试指示器值无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                       X12Ta1InvalidTestIndicatorValueDescription                       |
|  消息正文   |                              测试指示器值无效                              |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 UNB11 字段中的测试指示器不符合服务架构（BaseArtifacts.dll 中的 X12ServiceSchema 或 EdifactServiceSchema）建立的数据类型和位数。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保 UNB11 字段为 EDIFACT_N 数据类型并且长度为 1 个字符。 然后重新发送交换。