---
title: 可接受 X12 交换控制编号已达到来宾设置的最大限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9737053d-6065-4c88-8dfa-5f69b48e0e82
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1145573dc5aec674e79cef960c4737ddfe6d5e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005950"
---
# <a name="max-limit-of-acceptable-x12-interchange-control-number-has-reached-for-guest-settings"></a>可接受 X12 交换控制编号已达到来宾设置的最大限制
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
| 产品版本 |                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                         |
|    事件 ID     |                                                                                                     -                                                                                                      |
|  事件源   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                           |
|    组件    |                                                                                                 EDI 引擎                                                                                                 |
|  符号名称  |                                                                                          GlobalX12IsaNumberError                                                                                           |
|  消息正文   | 已达到“来宾”设置的可接受 X12 交换控制编号最大限制。 导航到“全局”配置接收方角色屏幕、合作伙伴协议管理器中的字段 ISA 13 可重置计数器 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理传出的 X12 交换，因为在全局设置中指定的 ISA13 字段中的交换控制编号大于所允许的最大值。 交换控制编号的最大字符数为 9。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请按照如下方式重置交换控制编号：  
  
1.  在“EDI 全局属性”对话框中，打开“ISA 段定义”页。  
  
2.  单击与 ISA13 字段关联的“编辑”字段。  
  
3.  将交换控制编号设置为一个新值，以便该字段具有可接受的位数。