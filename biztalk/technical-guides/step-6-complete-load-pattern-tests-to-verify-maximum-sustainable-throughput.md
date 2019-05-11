---
title: 步骤 6：执行常量负载模式测试以确定最大可承受吞吐量 |Microsoft Docs
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
ms.openlocfilehash: 28b482c6202741353987a28d4a943154a933abbf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401217"
---
# <a name="step-6-perform-constant-load-pattern-tests-to-verify-maximum-sustainable-throughput"></a>步骤 6：执行常量负载模式测试以确定最大可承受吞吐量
负载测试使用 Visual Studio 2010 的 BizTalk Server 解决方案时，如中所述在确定近似最大可承受吞吐量 (MST) 的解决方案之后，应执行常量负载模式测试[步骤 5:执行分级负载模式测试以确定最大可承受吞吐量](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md)。 这应进行确认，MST 是实际上可承受随着时间的推移以及以便创建基线负载测试向前移动以评估应用于 BizTalk Server 应用程序或环境进行性能优化的效果。  
  
## <a name="create-and-run-a-constant-load-pattern-test"></a>创建和运行常量负载模式测试  
 若要创建使用相同的测试组合、 计数器集和使用的分级负载模式测试的计数器集映射的常量负载模式测试的最简单方法是只需保存分级负载模式测试"BTS_Messaging_Step.loadtest"作为"BTS_Messaging_Constant.loadtest"，然后使某些更改为"BTS_Messaging_Constant.loadtest"。 请遵循以下步骤创建常量负载模式测试，它基于现有的分级负载模式测试：  
  
1.  如果不是已打开，请打开 BTS_Messaging_Step.loadtest。  
  
2.  单击**文件**，然后选择**LoadTests\BTS_Messaging_Step.loadtest 另存为**。  
  
3.  在中**将文件另存为**对话框旁边**文件名**，输入 C:\Projects\LoadTest\BTSLoad\LoadTests\BTS_Messaging_Constant.loadtest，然后单击**保存**。  
  
4.  在负载测试编辑器中，重命名方案**BTS_Messaging_Step**到**BTS_Messaging_Constant**。 方案名称显示正下方**方案**文件夹。  
  
5.  将保留为值**测试组合**并**网络组合**保持不变，但单击以选择**分级负载模式**。  
  
6.  右键单击**分级负载模式**，然后选择**属性**。  
  
7.  在中**属性**部分中，在**负载模式**旁边单击下拉列表**模式**并将更改从模式**步骤**到**常量**。  
  
8.  在中**属性**部分中，在**参数**，更改的值**常数用户计数**略小于的用户数的值为分级负载模式测试已变得不可承受 (即为值**BizTalk:Messaging\Documents 收到每个 / Sec**开始一直超出的值为**BizTalk:Messaging\Documents 处理数/秒**和值**biztalk: Message Box: General Counters\Spool 大小**也开始增加不受限制)。  
  
9. 下**运行设置**文件夹中，右键单击**运行 Setting1 [Active]** ，然后选择**属性**。  
  
10. 向下滚动到的属性的列表**计时**部分，然后输入的值**运行持续时间**至少 10 分钟 (00: 10:00)，并验证的值**采样率**仍设置为 5 秒 (00: 00:05)。  
  
11. 通过右键单击测试名称 (例如 BTS_Messaging_Constant) 启动负载测试，然后单击**运行测试**菜单选项。