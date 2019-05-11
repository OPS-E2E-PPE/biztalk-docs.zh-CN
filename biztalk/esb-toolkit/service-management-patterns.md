---
title: 服务管理模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fea915c-0074-472e-909b-fbbd88d7359c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ec777e46dada4a47f00cff666b6924e448ef8b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392034"
---
# <a name="service-management-patterns"></a>服务管理模式
## <a name="repair-and-resubmit"></a>修复和重新提交  
 修复和重新提交模式定义在其中一项服务无法处理消息并且需要正常外部化其在失败消息的窗体中状态，从而使消息内容为可用于修复，然后将其重新提交到服务的解决方案若要继续处理消息。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] 包括以下哪些 Microsoft biztalk 消息传送和业务流程的异常可以规范化和公开其他操作的机制。 设计 ESB 解决方案时，时，重要的帐户将如何处理异常。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括 ESB 管理门户应用程序示例演示如何查看和管理异常。 有关修复和重新提交使用 ESB 管理门户示例应用程序的异常的详细信息，请参阅[正在修复和重新提交消息](../esb-toolkit/repairing-and-resubmitting-messages.md)。