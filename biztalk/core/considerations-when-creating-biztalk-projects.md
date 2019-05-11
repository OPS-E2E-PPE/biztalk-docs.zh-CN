---
title: 创建 BizTalk 项目时的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, size
- map type name
- projects, naming conventions
- projects, planning
ms.assetid: f6c3dc71-105f-46af-9e6e-9a4c3b982d8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59b8749928891f963f3ca75032cc133c0ddf7848
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390358"
---
# <a name="considerations-when-creating-biztalk-projects"></a>创建 BizTalk 项目时的注意事项
本部分提供创建 BizTalk 项目使用时应考虑的信息[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
## <a name="avoid-compilation-errors-caused-by-projects-that-are-too-large"></a>避免太大的项目所导致的编译错误  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编译器将不能成功编译项目这是如果这会导致在程序集大于 75 兆字节为单位。 该编译器达到大小限制时它会发出错误 CS0013"将元数据写入到文件的意外的错误\<文件名\>"并停止。  
  
 若要避免此问题，我们建议项目不要超过 10 兆字节，除非绝对必要。 原因是什么？  
  
-   较小的项目是可能会越简单部署，因为有更少的部署步骤。 并使用较小的项目的步骤是更有可能密切相关-管理贸易合作伙伴折扣或处理 Rfp。  
  
-   它很容易隔离 bug、 部署问题和其他问题时使用较小的项目。 使用 140 个架构和许多自定义映射和脚本项目中查找错误将会比只有 10 个架构和少量自定义映射和脚本项目中查找更加困难。  
  
-   将一个大项目分成较小的项目可以降低复杂性。 较小的项目是更易于管理。  
  
-   较小的项目编译速度更快。  
  
-   将具有多个不相关架构的大项目拆分为较小的项目与紧密相关的架构可能会导致更好的性能。 这是因为只有某些程序集将加载一次。  
  
## <a name="avoid-using-the-project-name-as-the-map-type-name"></a>避免将项目名称用作映射类型名称  
 将新的映射添加到的 BizTalk 项目中时[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]不使用作为类型名称的项目名称。 如果这样做，编译器将生成一个或多个错误类似于"的类型名称\<名称\>类型中不存在"。  
  
 若要更改从 BizTalk 项目中的映射的类型名称，单击解决方案资源管理器窗格中的映射，然后验证属性窗格中的类型名称属性。 如果它是相同的您需要修改它以确保更改依赖于它的所有配置。  
  
## <a name="visual-studio-team-system-support"></a>Visual Studio Team System 支持  
 中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]进行不直接支持的所有功能[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Team System。 源代码管理功能的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Team System 支持 BizTalk server。 Visual SourceSafe 也完全支持跟踪和版本控制的 BizTalk 项目。