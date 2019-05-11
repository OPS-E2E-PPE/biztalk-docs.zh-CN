---
title: 数据元素太长 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf608cc1-d482-4e19-8f56-10d9e03feb79
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a143fcba207cff6c6941012e728993f03e5731b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390001"
---
# <a name="data-element-too-long"></a>数据元素太长
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                           -                                            |
|  消息正文   |                                 数据元素太长                                  |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道或 EDI 发送管道无法处理传入的交换，因为数据元素的长度大于架构指定的最大长度。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请缩短时间过长，因此它低于最大限制在交换中的数据元素。 若要确定的最大长度，打开 \XSD_Schema 文件夹中的架构、 数据元素 id，搜索和确定 maxLength 值。