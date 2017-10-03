---
title: "BizUnit 测试用例的阶段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed0e725f-2c52-43f7-ae30-343413a703c2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ff435fd1c69118112b0121bf68b38ae3151885f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="stages-of-a-bizunit-test-case"></a>BizUnit 测试用例的阶段
每个 BizUnit 测试用例包括三个阶段： **TestSetup**， **TestExecution**，和**TestCleanup**。 每个阶段包含负责执行的工作; 单个离散单元的一个或多个测试步骤例如， **FileCreateStep**负责在给定文件名指定的位置中创建一个文件。  BizUnit 包括超过 70 测试步骤，并提供扩展功能，使新的测试步骤，以可轻松添加到框架。 能够将新的步骤添加到框架允许 BizUnit 方案的广泛使用。 本主题介绍 BizUnit 测试阶段中详细说明。  
  
## <a name="setup-stage"></a>安装程序阶段  
 此安装程序阶段准备以便进行测试的平台。 例如，可以运行特定测试之前，文件可能需要复制为文件放置在实际执行测试准备。 你也可以使用此阶段清理任何文件位置或将测试中使用的数据库表。 与一样 BizUnit 中的每个阶段，可以添加的测试步骤的数量没有限制，它提供了处理复杂的方案所需的灵活性。  
  
## <a name="execution-stage"></a>执行阶段  
 执行阶段是实际运行该测试时。 这是系统的进行实际测试的验证函数。  
  
## <a name="cleanup-stage"></a>清理阶段  
 清理阶段是测试步骤返回到之前运行测试的一致状态的平台的容器。 始终执行这一阶段，即使在执行阶段发生错误。 平台应返回到起始点的原因是为了防止一个测试用例干扰另一，以便每个测试用例自主运行作为测试套件的一部分。 在此阶段确保系统完全清除是用于与 BizUnit 有效测试的指导原则之一。  
  
 下图演示了包含三个阶段中的测试步骤将示例测试用例的格式： 安装程序、 执行和清理。 请务必始终遵循以下结构定义测试用例和 BizUnit 时。  
  
 ![BizUnit 测试阶段](../technical-guides/media/0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4.gif "0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4")  
BizUnit 测试的阶段  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizUnit 以便于自动测试](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)