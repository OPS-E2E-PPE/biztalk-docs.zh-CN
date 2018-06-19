---
title: 服务管理模式 |Microsoft 文档
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
ms.openlocfilehash: a48639fb2a540b5b2597b34ad95ee390b4382c34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294621"
---
# <a name="service-management-patterns"></a>服务管理模式
## <a name="repair-and-resubmit"></a>修复并重新提交  
 修复并重新提交模式定义一个解决方案，在其中一项服务无法处理消息，并需要正常外部化形式的失败的消息其状态，从而使消息内容才可用于修复，然后将其重新提交到服务若要继续处理消息。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括由哪些 Microsoft BizTalk 消息传送和业务流程的异常可以为规范化，并公开其他操作的机制。 设计 ESB 解决方案时，务必将如何处理异常的帐户。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括的示例 ESB 管理门户应用程序演示了如何查看和管理异常。 有关修复和重新提交使用 ESB 管理门户示例应用程序的异常的详细信息，请参阅[修复和重新提交消息](../esb-toolkit/repairing-and-resubmitting-messages.md)。