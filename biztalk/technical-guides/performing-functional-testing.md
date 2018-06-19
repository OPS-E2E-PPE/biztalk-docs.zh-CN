---
title: 执行功能测试 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b9c8c95-5a25-4255-a4c2-e26c67b7a620
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f17c2701d6aa90393b8839bafc933bea2fba5746
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302317"
---
# <a name="performing-functional-testing"></a>执行功能测试
使用功能的测试来测试特定的 BizTalk 应用程序的上下文中的特定的端到端方案或给定的用例。 功能测试应涵盖通过给定的方案，包括故障路径的所有可能路径。 故障路径应进行评估，以确保应用程序适当地处理故障条件。  
  
 应调用 （如业务流程、 自定义管道组件和自定义程序集） 的所有项目，并且应该以及测试通过这些对象的所有代码分支。 必须小心的消息的所有可能组合，以确保消息正确流过系统。 若要确保应用程序做出反应，在发生错误预期的方式，若要测试的业务流程和自定义组件的所有异常块中包含的代码，应以及测试的无效消息。  
  
## <a name="automating-functional-testing"></a>自动执行功能测试  
 你应自动执行功能测试，以便它快，以便可以重复，且，以便它将避免人为失误。 **BizUnit**是一个声明性测试框架，旨在使开发人员能够快速设计测试用例。 事实上，XML 配置文件调用 BizUnit XML 测试用例是不足以定义应如何执行测试。 若要运行测试你可以创建你自己的自定义驱动程序或更多方便地利用**Visual Studio 单元测试**或**NUnit**承载和运行测试。  
  
 每个 BizUnit XML 测试用例包含三个阶段： **TestSetup**， **TestExecution**，和**TestCleanup**。 每个阶段可以包含零个或多个测试步骤。 每个步骤表示的工作单元，并实现为旨在执行某项任务的.NET 类。 此框架提供了一套丰富的组件。 如果你需要实现专用的组件以满足特定要求，但是，你可以编写自己的自定义测试步骤的组件。 有关这些工具的详细信息，请参阅[测试工具](~/technical-guides/tools-for-testing.md)。  
  
> [!NOTE]  
>  使用此工具不支持由 Microsoft 和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。  
  
## <a name="see-also"></a>另请参阅  
 [清单： 测试操作的准备情况](../technical-guides/checklist-testing-operational-readiness.md)