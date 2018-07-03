---
title: 未找到批处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e967e1a-b87f-4c87-a157-a6f63ba96d78
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fab810e4cfadc77c8fafe34b5cb78aaa417dfe5c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015062"
---
# <a name="the-batch-was-not-found"></a>未找到批处理
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                   Err_BatchNotFound                                    |
|  消息正文   |                                未找到批处理。                                |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 在启动/停止批处理期间或者在批处理业务流程尝试对消息进行批处理时未找到批处理。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保所包含协议的“协议”属性中存在相应的批处理。