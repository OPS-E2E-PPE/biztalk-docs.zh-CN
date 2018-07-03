---
title: 必需数据元素缺失 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 510d54b3-13de-4735-92ec-04fd4b9d460e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a44e4824805a137121bf1f5bd030cb16329484d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966486"
---
# <a name="mandatory-data-element-missing"></a>必需数据元素缺失
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                      X12DeMandatoryDataElementMissingDescription                       |
|  消息正文   |                             必需数据元素缺失                             |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为交换不包含消息架构（其 minOccurs 大于 0）所需的数据元素。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换包含消息架构所需的所有数据元素，然后重新发送消息。