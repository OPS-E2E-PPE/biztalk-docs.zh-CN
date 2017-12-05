---
title: "创建 BizTalk 项目时的注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects, size
- map type name
- projects, naming conventions
- projects, planning
ms.assetid: f6c3dc71-105f-46af-9e6e-9a4c3b982d8c
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0302d2329f848352f55d15f0c6e21bbdf72b0ca
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="considerations-when-creating-biztalk-projects"></a>创建 BizTalk 项目时的注意事项
本部分提供在创建 BizTalk 项目使用时应考虑的信息[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
## <a name="avoid-compilation-errors-caused-by-projects-that-are-too-large"></a>避免由于项目过大而导致的编译错误  
 如果 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 编译器生成的程序集大于 75 MB，则该编译器将不能成功地编译项目。 当编译器达到大小约束它将发出错误 CS0013"元数据写入文件的意外的错误\<filename\>"停止。  
  
 若要避免出现此问题，建议项目不要超过 10 MB，除非确实有此必要。 原因是什么？  
  
-   项目越小，所需的部署步骤就越少，因此部署可能会越简单。 此外，对于较小的项目，这些步骤之间的关联可能会更加紧密（管理贸易合作伙伴折扣或处理 RFP 的折扣）。  
  
-   使用的项目越小，就越容易解决错误、部署问题及其他问题。 与在仅包含 10 个架构和少量自定义映射和脚本的项目中查找错误相比，在包含 140 个架构和许多自定义映射和脚本的项目中查找错误会困难得多。  
  
-   将一个大项目分成几个较小的项目可以降低复杂性。 项目越小，就越容易管理。  
  
-   项目越小，编译速度就越快。  
  
-   将包含多个不相关架构的大项目拆分成只包含紧密相关的架构的较小项目，可以提高性能。 这是因为只有某些程序集将加载一次。  
  
## <a name="avoid-using-the-project-name-as-the-map-type-name"></a>避免将项目名称用作映射类型名称  
 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中向 BizTalk 项目添加新映射时，请不要将项目名称用作类型名称。 如果这样做，则编译器将生成一个或多个错误类似于"的类型名称\<名称\>类型中不存在"。  
  
 若要更改从 BizTalk 项目中的映射的类型名称，单击解决方案资源管理器窗格中中的映射，然后检查属性窗格中的类型名称属性。 如果名称相同，则需要对其进行修改，以确保更改依赖于此名称的所有配置。  
  
## <a name="visual-studio-team-system-support"></a>Visual Studio Team System 支持  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的 BizTalk 项目不直接支持 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Team System 的所有功能。 源代码管理功能的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]Team System 支持 BizTalk Server。 Visual SourceSafe 也完全支持对 BizTalk 项目进行跟踪和版本控制。