---
title: 使用 ESB 异常管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de6ce411-2d34-4fd8-9644-6fbc9cec266d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17f3f44f7575c42b4719e6b05431178212c36210
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396433"
---
# <a name="using-esb-exception-management"></a>使用 ESB 异常管理
在一组的上下文，并在 ESB 在不同的处理阶段数期间可能出现错误和异常。 本部分提供有关处理异常的信息，并描述如何发布通过 ESB 管理门户的详细信息。  
  
## <a name="overview"></a>概述  
 有许多方法来处理 BizTalk Server 解决方案，包括如 Enterprise Library 使用框架中的异常。 但是，当使用 ESB 和 BizTalk Server 进行开发，基于消息的环境中工作。 在 BizTalk 解决方案中的所有内容都是面向消息，BizTalk 开发人员认为面向消息的方式。 因此，[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]实现异常处理的面向消息的方法。  
  
 ESB 异常管理框架遵循一种设计模式，以便提供异常监视的灵活方法，并使错误响应，为来自外部解决方案 — 可能是在业务部门级别。  
  
 以下主题讨论 ESB 异常管理框架中更多详细信息：  
  
-   [ESB 异常管理框架设计](../esb-toolkit/design-of-the-esb-exception-management-framework.md)  
  
-   [异常管理框架组件](../esb-toolkit/the-components-of-the-exception-management-framework.md)  
  
-   [使用异常管理框架](../esb-toolkit/using-the-exception-management-framework.md)  
  
-   [创建自定义异常处理程序](../esb-toolkit/creating-custom-exception-handlers.md)