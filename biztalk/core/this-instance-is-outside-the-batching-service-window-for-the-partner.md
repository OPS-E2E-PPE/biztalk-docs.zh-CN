---
title: 此实例是合作伙伴的批处理服务窗口之外 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e420d75-11fd-4221-9d97-814ca6e48c81
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a741439b5d6691a3218811568087450f2008b0ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966478"
---
# <a name="this-instance-is-outside-the-batching-service-window-for-the-partner"></a>此实例在合作伙伴的“批处理服务”窗口之外
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                    批处理引擎                                     |
|  符号名称  |                              OutsideBatchingServiceWindow                              |
|  消息正文   |          此实例在合作伙伴的“批处理服务”窗口之外          |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明批处理业务流程的一个实例无法启动，因为该实例在参与方的激活范围之外。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请打开参与方的“EDI 属性”的“交换批处理创建设置”页，并确保该业务流程实例在激活范围之内。 如果没有，请更改开始时间属性，然后单击**启动**。