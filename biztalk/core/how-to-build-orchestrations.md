---
title: 如何生成业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building, orchestrations
- building, solutions
- building, projects
- solutions, building
- projects, building
- orchestrations, building
ms.assetid: f12d5da0-fbae-4f0e-85bf-1ca2e9bf7d62
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f755ea3b2aa01919d7f5d40a9eca92fd3529c629
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387076"
---
# <a name="how-to-build-orchestrations"></a>如何生成业务流程
完成业务流程绘图后，封装可执行业务流程的程序集生成 BizTalk 项目。  
  
 在生成过程中，BizTalk 业务流程设计器将检查以确定它是否是完整且正确，并报告错误的任务列表中，如果不是每个形状。  
  
 必须在 Visual Studio 中生成的几个选项：  
  
- 您可以构建您的业务流程所在的整个解决方案。  
  
- 可以生成解决方案中的单个项目。  
  
- 生成项目或解决方案时，可以跳过该业务流程。  
  
  如果想要生成其他组件，包括其他业务流程，但不是想生成特定的业务流程，你可以指示在业务流程的.odx 文件，您不想要生成它，并将跳过的文件属性。  
  
### <a name="to-build-an-orchestration"></a>若要生成业务流程  
  
-   在创建后您的业务流程，需要生成包含它，然后才能测试或使用该业务流程的 BizTalk 项目。 您可以构建整个解决方案中的单个项目。  
  
### <a name="to-build-a-solution"></a>若要生成的解决方案  
  
-   在解决方案资源管理器，右键单击解决方案并选择**生成解决方案**。  
  
### <a name="to-build-a-project"></a>若要生成项目  
  
-   右键单击项目并选择**生成**。  
  
### <a name="to-build-a-project-or-solution-without-compiling-a-particular-orchestration"></a>若要生成项目或解决方案而无需编译特定业务流程  
  
-   单击.odx 文件对应，向业务流程，并在属性窗口中，单击**生成操作**属性，然后选择**None**。