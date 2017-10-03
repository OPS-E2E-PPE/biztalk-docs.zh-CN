---
title: "如何构建业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- building, orchestrations
- building, solutions
- building, projects
- solutions, building
- projects, building
- orchestrations, building
ms.assetid: f12d5da0-fbae-4f0e-85bf-1ca2e9bf7d62
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79e91ec6ecfa061aa4621effba9a1f868cad5d96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-build-orchestrations"></a>如何生成业务流程
完成业务流程绘图后，可将 BizTalk 项目生成到包含可执行业务流程的程序集中。  
  
 在生成过程中，BizTalk 业务流程设计器将检查每个形状，以确定它是否完整并且正确，如果不完整或者不正确，则会在任务列表中报告错误。  
  
 在 Visual Studio 中生成时有几种选择：  
  
-   可以生成业务流程所在的整个解决方案。  
  
-   可以生成解决方案中的单个项目。  
  
-   生成项目或解决方案时可以跳过业务流程。  
  
 如果要生成其他组件（包括其他业务流程），但不想生成特定业务流程，则可以在业务流程的 .odx 文件的文件属性中指示您不想生成该业务流程，这样便会将其跳过。  
  
### <a name="to-build-an-orchestration"></a>生成业务流程  
  
-   创建业务流程后，需要先生成包含该业务流程的 BizTalk 项目，然后才能测试或使用该业务流程。 可以生成整个解决方案，也可以生成解决方案中的单个项目。  
  
### <a name="to-build-a-solution"></a>若要生成解决方案  
  
-   在解决方案资源管理器，右键单击该解决方案并选择**生成解决方案**。  
  
### <a name="to-build-a-project"></a>生成项目  
  
-   右键单击某个项目并选择**生成**。  
  
### <a name="to-build-a-project-or-solution-without-compiling-a-particular-orchestration"></a>在不编译特定业务流程的情况下生成项目或解决方案  
  
-   单击.odx 文件对应，业务流程，然后在属性窗口中，单击**生成操作**属性并选择**无**。