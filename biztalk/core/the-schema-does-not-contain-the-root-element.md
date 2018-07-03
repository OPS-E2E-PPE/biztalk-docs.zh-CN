---
title: 架构不包含根元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efc33f2b-9e14-4d2e-8c8a-32b7696f80ea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc2191a5d9ea891efa285d8fc5006f243319fde5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008438"
---
# <a name="the-schema-does-not-contain-the-root-element"></a>架构不包含根元素
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                             SchemaCode102ENullRootElement                              |
|  消息正文   |                    架构不包含根元素 {0}                    |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入消息或发送管道无法处理传出消息，因为用来验证消息的架构不包含根元素。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，取消部署文档架构，将根元素添加到架构，然后重新部署架构。