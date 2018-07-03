---
title: 控制架构应该让标头段处于正确的顺序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f38e8f-243a-467f-84bd-a232ef148b4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c86b8d66526c0406faedeac0aedbbe0e1b270ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967918"
---
# <a name="control-schema-should-have-header-segments-in-the-correct-order"></a>控制架构标头段的顺序应正确
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                           -                                            |
|  消息正文   |  控制架构应该让段处于以下顺序： ISA GS ST...SE GE IEA  |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道无法处理传入的交换，因为交换的标头和尾部、组和事务集在交换中的顺序不正确。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保 ISA、GS 和 ST 标头以及 SE、GE 和 IEA 尾部在交换中的顺序正确，然后重新发送交换。