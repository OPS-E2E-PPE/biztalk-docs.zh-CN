---
title: 控制编号重复 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 331ad173-29b3-427c-8104-60d80c580a5a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3f4e58a6a26390b10d5cc3b4956c1b2fd0864c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350764"
---
# <a name="duplicate-control-number"></a>重复控制编号
## <a name="details"></a>详细信息  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                           -                                            |
|  消息正文   |                                重复控制编号                                |

## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道可以不处理传入的交换由于具有相同的交换、 组或事务集控制编号与以前接收的交换。 这将导致失败，只要启用了相应的重复控制编号检查。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  

- 请确保的交换发送到 BizTalk Server 不会不具有相同的交换、 组或事务集控制编号与之前交换，如果启用了相应的重复控制编号检查。  

- 禁用重复控制编号检查。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击相应的一方，然后打开 EDIFACT 交换处理属性或 X12 作为交换发送方的参与方的交换处理属性对话框。 若要禁用 EDIFACT 交换检查，请清除检查重复的 UNB5 （交换控制编号），检查重复的 ung5 （组控制编号） 中的交换或检查是否有重复的 UNH1 （事务集参考编号） 组属性中。 若要禁用 x12 检查交换，请清除检查重复的 ISA13 （交换控制编号），检查重复的 gs6 （组控制编号） 中的交换或检查是否有重复的 ST2 （事务集控制编号） 组属性中。
