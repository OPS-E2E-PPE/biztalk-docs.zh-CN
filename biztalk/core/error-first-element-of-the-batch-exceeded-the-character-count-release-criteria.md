---
title: 批处理的第一个元素超出了字符计数释放条件集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4b06f8f-247d-4e93-8c4e-5e86e4ad70c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 880e29ceb2be1c574aeaec248ce47317e332e5a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972654"
---
# <a name="the-first-element-of-the-batch-exceeded-the-character-count-release-criteria-set"></a>批的第一个元素超出了字符计数释放条件集
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                         |
| 产品版本 |                                                                                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                                     |
|    事件 ID     |                                                                                                                                 -                                                                                                                                  |
|  事件源   |                                                                                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                                                       |
|    组件    |                                                                                                                          批处理引擎                                                                                                                           |
|  符号名称  |                                                                                                                   FirstElementExceededCharCount                                                                                                                    |
|  消息正文   | 批处理的第一个元素超出了字符计数释放条件集。 请更改字符计数释放条件，以便能处理此消息。 该消息需要在修改设置后重新发送到批处理系统 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明批处理业务流程无法生成批处理的交换，因为由批处理业务流程选取的第一个批处理元素中的字符数已超过批处理发布条件的“交换中的最大字符数量”属性中指定的字符数。 请注意，与最大数量相比，字符数并不包含信封中的字符数。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
1.  增加“作为交换接收方的参与方”的“EDI 属性”对话框的“交换批处理创建设置”页中“”属性。 为此，您必须停止业务流程实例，增加属性中的最大字符数，然后重新启动业务流程实例。 让发送方重新发送消息。  
  
2.  让发送方发送字符数低于最大字符数的事务集。