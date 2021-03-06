---
title: 在执行升级批处理业务流程期间发生了异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2221a498-98aa-43ab-bc4e-34dcbd92dcf0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df73d4fa4d8d59caed5c8e8f34e52d2b60d4c7cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348436"
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-upgrade-batch-orchestration"></a>在执行升级批处理业务流程期间出现异常
## <a name="details"></a>详细信息  
  
|                 |                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------|
|  产品名称   |          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| 产品版本 |                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    事件 ID     |                                                   -                                                   |
|  事件源   |                                          BizTalk Server EDI                                           |
|    组件    |                                            批处理引擎                                            |
|  符号名称  |                                     ExceptionOccuredDuringUpgrade                                     |
|  消息正文   | 在执行升级批处理业务流程期间发生了异常。 错误消息 = {0} |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明升级批处理业务流程无法正确处理消息，因为在 ErrorMessage 字段中指明了错误条件。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确定 ErrorMessage 字段中的错误条件，解决此错误，然后重新提交消息。