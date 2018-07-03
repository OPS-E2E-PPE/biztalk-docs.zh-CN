---
title: 处理事务集，因为找不到事务集的开始元素后遇到错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5380aee-1632-4cdf-98a1-aff87574ce4f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74ea9b059ed75d88a8f48287d553e670d2c7d755
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984478"
---
# <a name="error-encountered-after-processing-transaction-sets-because-the-start-element-of-a-transaction-set-could-not-be-found"></a>处理事务集后遇到错误，因为找不到事务集的 Start 元素
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| 产品版本 |                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                             |
|    事件 ID     |                                                         -                                                         |
|  事件源   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI               |
|    组件    |                                                    EDI 引擎                                                     |
|  符号名称  |                                             InvalidEfactBiboXmlFormat                                             |
|  消息正文   | 在处理后遇到错误{0}事务集。 找不到事务集的开始元素。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道无法处理传入的事务集，因为接收管道找不到 ST 或 UNH 标头。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请与交换的发送方联系，让他们确保出错的事务集从 ST01 或 UNH1 段开始。