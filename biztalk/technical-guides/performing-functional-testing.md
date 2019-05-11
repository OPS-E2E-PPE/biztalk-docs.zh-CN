---
title: 执行功能测试 |Microsoft Docs
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
ms.openlocfilehash: e0f1736ddc0956de470ebdc1f3f1a6adaa2f8f94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291333"
---
# <a name="performing-functional-testing"></a>执行功能测试
使用功能测试来测试特定的 BizTalk 应用程序的上下文中的一个特定的端到端方案或给定的用例。 功能测试应涵盖通过给定方案中，包括故障路径的所有可能路径。 故障路径应进行评估，以确保应用程序适当地处理故障条件。  
  
 应调用 （如业务流程、 自定义管道组件和自定义程序集） 的所有项目，并且还应测试通过这些对象的所有代码分支。 必须小心的消息的所有可能组合，以确保消息正确流过系统。 请确保在发生错误时预期的方式做出响应应用程序并进行测试的业务流程和自定义组件的所有异常块中包含的代码应以及测试无效消息。  
  
## <a name="automating-functional-testing"></a>自动执行功能测试  
 您应当自动完成功能测试，以便它速度快，以便可以重复，并它将避免人为错误。 **BizUnit**是一个声明性的测试框架，旨在让开发人员快速设计测试用例。 实际上，XML 配置文件调用 BizUnit XML 测试用例就足以定义应如何执行测试。 若要运行测试可以创建自定义驱动程序或更多方便地利用**Visual Studio 单元测试**或**NUnit**托管和运行测试。  
  
 每个 XML BizUnit 测试用例包含三个阶段：**TestSetup**， **TestExecution**，和**TestCleanup**。 每个阶段可以包含零个或多个测试步骤。 每个步骤表示的工作单元，并作为设计为执行特定任务的.NET 类实现。 此框架提供了一套丰富的组件。 如果您需要意识到专用的组件，以满足特定要求，但是，可以编写您自己的自定义测试步骤组件。 有关这些工具的详细信息，请参阅[用于测试工具](~/technical-guides/tools-for-testing.md)。  
  
> [!NOTE]  
>  使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。 使用此程序是完全由您自己承担。  
  
## <a name="see-also"></a>请参阅  
 [清单：测试操作准备情况](../technical-guides/checklist-testing-operational-readiness.md)