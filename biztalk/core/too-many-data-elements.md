---
title: 数据元素太多 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5000577d-5748-4e81-a394-86b2a780d70f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cb05cc31331dcc2633b7dc398c8f77a369c3f28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395426"
---
# <a name="too-many-data-elements"></a>数据元素太多
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                          X12DeTooManyDataElementsDescription                           |
|  消息正文   |                                 数据元素太多                                 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换或发送管道无法处理传入的交换，因为交换中的某个段包含的数据元素多于文档架构或服务架构所允许的数据元素。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让交换的发送方确保该段包含所需数量的数据元素，如有必要从该段中删除多余的数据元素，直到该段符合架构。