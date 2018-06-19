---
title: 务必测试的原因 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce91aca5-56d3-4fb8-abe2-af0039804706
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 433a5de8d1f90c02c5b06287252b49fd7209e07b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302301"
---
# <a name="why-it-is-important-to-test"></a>为什么很重要向测试
本主题提供的思维方式导致的不足测试概述介绍与失败测试 BizTalk 解决方案关联的风险，并将进行比较的自动测试的好处的手动测试缺陷。  
  
## <a name="testing-as-overhead"></a>测试作为"开销"  
 遗憾的是，与渐增的投资回报 (ROI) 的需求，一个项目的测试阶段往往因为可以将项目计划的第一个方面之一缩放后。  
  
 针对测试 BizTalk 解决方案的一个参数是:"我们不需要可以测试我们的解决方案，因为 Microsoft 已完全测试 BizTalk Server。" 尽管为 true，Microsoft 全面测试 BizTalk Server，不同的使用方案都要求几乎无数的业务需求的排列数之一吞吐量、 高可用性、 适配器使用率、 滞后时间，跟踪要求，业务流程使用情况和自定义代码。 因为 BizTalk Server 极其灵活并且可以适应这么多不同的使用情况，不只是能预测和测试所有它们。 此外，还应优化在 BizTalk Server 环境中应用的默认设置，以适应每种使用方案。 确定特定使用方案的最优设置的唯一方法是测试解决方案、 测量各种参数、 优化环境，和重新测试。 请考虑下图描绘了 BizTalk Server 解决方案示例物理体系结构。  
  
 ![BizTalk Server 部署的体系结构](../technical-guides/media/5359cf00-e285-4168-a988-8d3b677eb6ba.gif "5359cf00-e285-4168-a988-8d3b677eb6ba")  
示例物理 BizTalk 体系结构  
  
 你可以看到在上面的图示 BizTalk Server 解决方案包含多个包括多台计算机运行 BizTalk Server 中，运行 SQL Server、 服务器群集节点和 Active Directory 域的计算机的移动部件。 系统启动并运行后，将应用于优化每个业务要求，并最大程度提高解决方案的总体投资回报应用程序的许多配置优化。 此单个方案显示了在 play 中有许多变量。 除了环境的物理体系结构，请考虑下图描绘了 BizTalk Server 通过一条消息的流。  
  
 ![流的任何消息通过 BizTalk Server](../technical-guides/media/dea79a42-5f60-49a1-abdb-870988784ffe.gif "dea79a42-5f60-49a1-abdb-870988784ffe")  
示例逻辑 BizTalk 消息流  
  
 当我们看一下消息流经 BizTalk Server 逻辑关系图中时，我们看到需要每个项目测试，包括自定义发送和接收管道组件和可以从 BizTalk 业务流程调用的自定义类的其他变量。 假设类型复杂性和使用自定义组件和 BizTalk 组件各不相同项目到项目，它将成为更明显非常重要执行每种特定使用方案对进行测试的原因。  
  
## <a name="testing-methodology-and-timelines"></a>测试方法和时间线  
 若要确保有效地执行测试，测试工具应该是完全自动; 因此它是可轻松重现和最大程度减少人为错误的可能性。 此外，有足够的时间应分配给测试计划项目时。 测试的最低要求方法将包含类似于以下手动步骤：  
  
1.  将一个或多个消息手动加载到接收终结点，例如文件拖放或通过使用 SOAP 客户端能够调用 Web 服务。  
  
2.  手动验证正确的内容和消息的结构。 由于多个架构常常存在于项目中，消息可能平面文件和 XML 的组合，也可以包含交叉字段依赖关系。  
  
    > [!NOTE]  
    >  此示例将涉及 SWIFT 消息的任何项目。 这些是具有交叉字段依赖项的平面文件消息。 也就是说，依赖于另一个字段的值 – 简单的 XSD 验证将不在此处执行操作;因此 SWIFT 快捷键将使用的消息验证 BizTalk 规则引擎。 有关详细信息[SWIFT 快捷键](http://go.microsoft.com/fwlink/?LinkID=79657)，请参阅[SWIFT 快捷键](http://go.microsoft.com/fwlink/?LinkID=79657)(http://go.microsoft.com/fwlink/?LinkID=79657)。  
  
3.  手动检查有错误的 BizTalk Server 计算机上的事件日志。  
  
4.  手动检查 BAM 数据库 （如果使用） 来验证正确记录活动信息。  
  
 使用手动过程，如测试是主观上面所述，而且容易出错。 请考虑无需检查上百行 SWIFT 消息与跨 10 个不同的测试用例字段依赖关系。 开发人员将不能为或即使它们是可以的将不倾向可靠而准确地参与此类任务的大多数项目。 主观、 手动错误不易测试过程的实现添加到项目的风险，并提高故障的可能性。  
  
 项目规划未包含足够的时间进行测试的时间线通常放大出现故障的风险。 所有过于频繁，测试策略枢轴上这是通过单个手动测试的项目计划一周左右上线日期之前。 这种有限测试使项目面临风险。 给定的测试，这种有限的时间线，如果检测到任何问题，然后项目可能会延迟，因为没有时间已分配，若要解决问题。 此外，如果发现问题，并且将其固定，可能有足够的时间留出之前在系统投入执行后续测试通过。  
  
 "单个最终生成、 通过单个测试、 take 项目 live"的实际情况之前测试是，它通常会导致正在延迟项目、 预算，或甚至是借助于项目、 项目完全失败 ！ 对于任务关键型系统，这种测试方法是更多信息的待势而发的灾难。  
  
## <a name="testing-effectively-and-efficiently"></a>有效地测试  
 通常被视为昂贵 luxury 而不是整型要求相应的测试，因为它是所有过于频繁附加在项目的结尾处。 考虑到在异类企业环境中使用的软件和硬件堆栈的复杂性，这种方法是不现实。 可以按需重新运行自动的测试方法的实现是有效和高效地测试的最佳方法，且是必不可少的组成部分的最终与业务带来极好的投资回报率的成功项目。 ： 投资开头的项目中的每个代码路径到整个系统的完整的端到端功能测试的生成测试资产。 这些资产以便的获益，提高了测试有效性和效率更高版本需要投资 （即开发时间）。 为了最大程度减少需要从项目派生此类框架的投资我们建议你利用 Visual Studio 2010 负载测试框架。 Visual Studio 2010 包括的大多数测试成功所需的常见测试步骤和在本指南中的更高版本的测试方案中使用该框架。  
  
## <a name="see-also"></a>另请参阅  
 [实现自动测试](../technical-guides/implementing-automated-testing.md)