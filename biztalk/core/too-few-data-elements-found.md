---
title: 找到的数据元素过少 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6eca6c1-73ee-4b9a-be84-461051eda963
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89d82a5015d2285437363f178f88c165e3ba6333
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984774"
---
# <a name="too-few-data-elements-found"></a>找到的数据元素过少
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                        X12FeTooFewDataElementsFoundDescription                         |
|  消息正文   |                              找到的数据元素过少                               |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换或发送管道无法处理传入的交换，因为交换中的某个段包含的数据元素少于文档架构或服务架构所需的数据元素。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让交换的发送方确保段包含所需的数据元素数，然后重新发送交换。