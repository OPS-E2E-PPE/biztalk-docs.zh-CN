---
title: 修复和重新提交消息使用 ESB 管理门户 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43091cbd-77d1-4cbd-9190-2d423ce7d4df
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5648213d459cbfbacef6db580f44efd5e2f46b3d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400219"
---
# <a name="repairing-and-resubmitting-messages-using-the-esb-management-portal"></a>修复和重新提交消息使用 ESB 管理门户
在此用例，预先配置发送端口使用 ESB 故障处理器发送管道以接收生成的业务流程或生成的 Microsoft BizTalk 中的失败消息路由机制的错误消息中的异常处理程序到 ESB 的错误消息服务器。 ESB 故障处理器将规范化，使其更加丰富，并将其路由到 ESB 管理门户数据库。 在门户监视传入的错误消息的数据库，并可以生成通知的处理失败的订阅的用户的警报。 用户可以在门户故障查看器中打开的错误消息、 编辑消息内容和重新提交邮件以进行处理，如图 1 中所示。  
  
 ![修复消息](../esb-toolkit/media/ch3-repairingmessages.gif "Ch3-RepairingMessages")  
  
 **图 1**  
  
 **修复和重新提交消息使用 ESB 管理门户**  
  
 ESB 管理门户作为示例包含[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 它提供完整的图形环境用于编辑和重新提交消息;它还支持警报、 通知和消息重新提交审核。  
  
 有关详细信息，请参阅[处理的异常和错误消息](../esb-toolkit/working-with-exceptions-and-fault-messages.md)。