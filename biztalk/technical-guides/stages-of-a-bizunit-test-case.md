---
title: BizUnit 测试用例的阶段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed0e725f-2c52-43f7-ae30-343413a703c2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b67f9211c6525ca64afcd40d2155169af138026
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305509"
---
# <a name="stages-of-a-bizunit-test-case"></a>BizUnit 测试用例的阶段
每个 BizUnit 测试用例包括三个阶段：**TestSetup**， **TestExecution**，和**TestCleanup**。 每个阶段包含一个或多个测试步骤的是负责执行的工作; 单个离散单元例如， **FileCreateStep**负责在使用给定的文件名指定的位置中创建一个文件。  BizUnit 包括 70 多个测试步骤，并且还提供扩展功能，这允许新的测试步骤要轻松地添加到框架。 能够将新的步骤添加到该框架允许 BizUnit 用于跨各种方案。 本主题介绍更多详细信息中的 BizUnit 测试阶段。  
  
## <a name="setup-stage"></a>安装程序阶段  
 此安装程序阶段准备用于测试平台。 例如，可以运行特定测试之前，文件可能需要复制到文件放置在实际执行测试的准备。 任何文件位置或将在测试中使用的数据库表，也可以使用此清除阶段。 由于使用 BizUnit 中每个阶段，是可以添加的测试步骤数没有限制，它提供处理复杂的方案所需的灵活性。  
  
## <a name="execution-stage"></a>执行阶段  
 执行阶段是实际运行测试。 这是系统的进行实际测试的验证函数。  
  
## <a name="cleanup-stage"></a>清理阶段  
 清理阶段是测试步骤返回到运行测试前的一致状态的平台的容器。 始终执行此阶段，即使在执行阶段中出现错误。 平台应返回到起始点的原因是为了防止一个测试用例干扰另一个，以便每个测试用例自主运行作为测试套件的一部分。 在此阶段确保系统的完全清除是一个用于有效使用 BizUnit 测试的指导原则。  
  
 下图演示了示例测试用例，其中包含三个阶段中的测试步骤的格式： 安装程序、 执行和清理。 请务必定义具有 BizUnit 测试用例时始终遵循此结构。  
  
 ![BizUnit 测试阶段](../technical-guides/media/0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4.gif "0a3e2e30-8329-4e87-ae83-f50f7b6aa0a4")  
BizUnit 测试的阶段  
  
## <a name="see-also"></a>请参阅  
 [使用 BizUnit 优化自动测试](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)