---
title: 步骤 9：测试 EDI 解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7a44e0f-496c-462f-bf03-1c2f842d13b6
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d07bc0d28bf7d983a70c2f5ec7ee5e0329da714
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244221"
---
# <a name="step-9-test-the-edi-solution"></a>步骤 9：测试 EDI 解决方案
![步骤 9 的 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")  
  
 在本主题将测试入站的处理和查看的处理信息的 EDI 交换状态报告。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="testing-the-solution"></a>测试解决方案  
  
1. 在 Windows 资源管理器，转到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations。 复制**SamplePO.txt**文件。  
  
2. 粘贴**SamplePO.txt**文件到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM 文件夹。  
  
3. 将移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 界面开发人员 Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem 文件夹。 确认文件夹中含有一个 txt 输出文件。  
  
4. 打开输出文件中的[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 界面开发人员 Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem 和中的 SamplePO.txt 输入的文件[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations。 验证输出消息中的数据相对应的数据在原始**SamplePO.txt**文件。  
  
   > [!NOTE]
   >  你可以验证，输出文件中的数据已从输入文件中的数据转换通过在 Visual Studio 中打开 Inbound4010850_to_OrderFile.btm 文件并检查映射。  
  
5. 将移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 界面开发人员 Tutorial\ProcessEDI_TestLocations\Scenario A\toTHEM_997 文件夹。 确认该文件夹包含输出 997 确认 txt 文件，在其中 ST01 数据元素是"997"。  
  
6. 在控制台树中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**BizTalk 组**。 在右窗格的底部，单击**EDI 交换和相关 ACK 状态**。  
  
7. 查询表达式中的运算符更改**状态**字段**等于**并更改**值**字段**状态**字段**所有**。 删除**交换日期时间字段**（选择行并按键盘上的 DELETE）。  
  
8. 单击**运行查询**。  
  
9. 验证两个消息显示在状态报告中，从 THEM (Fabrikam) 到 US (OrderSystem) （850 消息），另一种从 US (OrderSystem) 到 THEM (Fabrikam) （997 确认） 的发送方向接收方向的其中一个。  
  
10. 双击从 THEM 到 US 的消息。 在中**交换状态和确认详细信息**对话框框中，验证交换的详细信息是否显示在右窗格中。  
  
11. 单击**功能确认**。 验证确认的报告详细信息显示在右窗格中。  
  
12. 关闭交换状态和确认详细信息对话框。  
  
13. 在中**交换 /ACK 状态**窗格中，右键单击从 THEM 到 US 的消息，然后单击**事务集详细信息**。 右键单击中的条目**查询结果**窗格中，，然后单击**查看事务集内容**。 验证事务集数据是否显示在**消息的详细信息**对话框。 在 Windows 资源管理器中打开中的 SamplePO.txt 文件[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations。 验证事务集显示在**消息的详细信息**对话框输入消息，且没有交换和组标头和尾部中是相同的。  
  
## <a name="next-steps"></a>后续步骤  
 已完成 EDI 接口开发人员教程。  
  
## <a name="see-also"></a>请参阅  
 [教程 2：EDI 接口开发人员教程](../core/tutorial-2-edi-interface-developer-tutorial.md)   
 [步骤 1：EDI 接口开发人员教程的准备工作](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)