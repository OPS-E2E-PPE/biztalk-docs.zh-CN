---
title: "步骤 9： 测试 EDI 解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7a44e0f-496c-462f-bf03-1c2f842d13b6
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6e308ae230ea2d78ff03ed02a81310c38fbcabc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-9-test-the-edi-solution"></a>步骤 9： 测试 EDI 解决方案
![步骤 9 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")  
  
 在本主题中，您将测试入站处理和查看有关处理信息的 EDI 交换状态报告。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="testing-the-solution"></a>测试解决方案  
  
1.  在 Windows 资源管理器中，将移动到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\EDI 界面开发工具 Tutorial\ProcessEDI_TestLocations。 复制**SamplePO.txt**文件。  
  
2.  粘贴**SamplePO.txt**文件到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 接口开发人员 Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM 文件夹。  
  
3.  将移动到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\EDI 界面开发人员 Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem 文件夹中。 确认此文件夹中含有一个 txt 输出文件。  
  
4.  打开 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 界面开发人员 Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem 中的输出文件，以及 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations 中的 SamplePO.txt 输入文件。 验证输出消息中的数据对应于在原始数据**SamplePO.txt**文件。  
  
    > [!NOTE]
    >  可以通过在 Visual Studio 中打开 Inbound4010850_to_OrderFile.btm 文件并检查映射，验证输出文件中的数据是否是从输出文件中的数据转换过来的。  
  
5.  将移动到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\EDI 界面开发人员 Tutorial\ProcessEDI_TestLocations\Scenario A\toTHEM_997 文件夹中。 确认该文件夹包含输出 997 确认 txt 文件，且其中 ST01 数据元素是“997”。  
  
6.  在控制台树中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**BizTalk 组**。 在右窗格的底部，单击**EDI 交换和关联 ACK 状态**。  
  
7.  在查询表达式中，更改的运算符**状态**字段**等于**和更改**值**字段**状态**字段**所有**。 删除**交换日期时间字段**（选择行，然后按 DELETE 键板上）。  
  
8.  单击**运行查询**。  
  
9. 验证是否有两条消息显示在状态报告中，一条为从 THEM (Fabrikam) 到 US (OrderSystem) 的接收方向的消息（850 消息），另一条为从 US (OrderSystem) 到 THEM (Fabrikam) 的发送方向的消息（997 确认）。  
  
10. 双击从 THEM 到 US 的消息。 在**交换状态和 ACK 详细信息**对话框框中，验证该交换的细节将显示在右窗格中。  
  
11. 单击**功能 ACK(s)**。 验证确认的报告详细信息是否显示在右窗格中。  
  
12. 关闭“交换状态和确认详细信息”对话框。  
  
13. 在**交换/ACK 状态**窗格中，右键单击到美国，从这些消息，然后单击**设置事务的详细信息**。 右键单击中的条目**查询结果**窗格中，，然后单击**查看事务设置内容**。 验证事务集数据显示在**消息详细信息**对话框。 在 Windows 资源管理器中，打开 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\ProcessEDI_TestLocations 中的 SamplePO.txt 文件。 验证事务集显示在**消息详细信息**对话框处于相同输入消息，而无需交换和组标头和拖车安排。  
  
## <a name="next-steps"></a>后续步骤  
 您已完成 EDI 接口开发人员教程。  
  
## <a name="see-also"></a>另请参阅  
 [教程 2: EDI 接口开发人员教程](../core/tutorial-2-edi-interface-developer-tutorial.md)   
 [步骤 1： 准备 EDI 接口开发人员教程](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)