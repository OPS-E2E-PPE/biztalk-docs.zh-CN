---
title: 步骤 6： 执行常量负载模式测试来验证最大可持续吞吐量 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd790354-be9f-4278-bd15-493eac8970c9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6bfc0b9670366ab2f38046fcdc5497234b51ba5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302093"
---
# <a name="step-6-perform-constant-load-pattern-tests-to-verify-maximum-sustainable-throughput"></a>步骤 6： 执行常量负载模式测试来验证最大可持续吞吐量
负载测试使用 Visual Studio 2010 的 BizTalk Server 解决方案时，应执行的常量负载模式测试，近似最大可持续吞吐量 (MST) 的解决方案中所述在确定了后[第 5 步： 执行步骤加载模式测试，以确定最大可持续吞吐量](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md)。 应以确认 MST 事实上可持续随着时间的推移以及以便创建向前移动，若要评估的任何性能优化应用于 BizTalk Server 应用程序或环境效果基线负载测试完成此操作。  
  
## <a name="create-and-run-a-constant-load-pattern-test"></a>创建并运行常量负载模式测试  
 若要创建使用相同的测试组合、 计数器集和计数器集映射的分级负载模式测试使用的常量负载模式测试的最简单方法是只需保存分级负载模式测试"BTS_Messaging_Step.loadtest"作为"BTS_Messaging_Constant.loadtest"，然后使某些更改为"BTS_Messaging_Constant.loadtest"。 按照以下步骤创建具有常量负载模式，它是测试基于现有的分级负载模式测试：  
  
1.  如果它不是已打开，请打开 BTS_Messaging_Step.loadtest。  
  
2.  单击**文件**和选择**LoadTests\BTS_Messaging_Step.loadtest 另存为**。  
  
3.  在**文件另存为**对话框旁边**文件名**，输入 C:\Projects\LoadTest\BTSLoad\LoadTests\BTS_Messaging_Constant.loadtest，然后单击**保存**。  
  
4.  在负载测试编辑器中，将方案重命名**BTS_Messaging_Step**到**BTS_Messaging_Constant**。 方案名称显示直接在**方案**文件夹。  
  
5.  将保留为值**测试组合**和**网络组合**保持不变，但单击以选择**分级负载模式**。  
  
6.  右键单击**分级负载模式**和选择**属性**。  
  
7.  在**属性**だ い 鶼**负载模式**旁边单击下拉列表**模式**和更改中的模式，**步骤**到**常量**。  
  
8.  在**属性**部分下,**参数**，更改的值**常量用户计数**略小于从该处的用户数的值为分级负载模式测试已变得稳定 (即值**BizTalk:Messaging\Documents 接收每个 / 秒**开始不断超越的值**BizTalk:Messaging\Documents 处理数/秒**和的值**BizTalk:Message Box: General Counters\Spool 大小**开始增加不受限制)。  
  
9. 下**运行设置**文件夹中，右键单击**运行 Setting1 [Active]** 和选择**属性**。  
  
10. 向下滚动到的属性列表**计时**部分，然后输入的值**运行持续时间**至少 10 分钟 (00: 10:00)，并验证的值**采样速率**仍设置为 5 秒 (00: 00:05)。  
  
11. 通过右击测试名称 (例如 BTS_Messaging_Constant) 启动负载测试，然后单击**运行测试**菜单选项。