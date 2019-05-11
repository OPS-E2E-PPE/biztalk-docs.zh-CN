---
title: 失败的控制编号重置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64e83c07-1569-4433-b882-a26784b7bb0f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fad552f984f183031c8d7f25f5dd922c1871389
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255158"
---
# <a name="reset-for-control-number-failed"></a>失败的控制编号重置
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                              EdiControlNumberResetFailed                               |
|  消息正文   |                                 重置{0}失败。                                  |
  
 **{0}**：事务集控制编号 / 组控制编号 / 交换控制编号  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 不能重置控制编号。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请重新打开该 UI，然后重试。