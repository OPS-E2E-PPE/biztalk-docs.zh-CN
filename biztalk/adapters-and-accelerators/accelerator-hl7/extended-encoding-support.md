---
title: 扩展的编码支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a40fa6-d0da-416e-97fb-675ddde3f005
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41275124cdf0db7329751c5973bbde0685bd49ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255294"
---
# <a name="extended-encoding-support"></a>扩展的编码支持
默认情况下，接收 HL7 管道，BTAHL72X，仅支持 ASCII 编码。 这意味着，具有等效值大于 127 将替换为输入消息中的任何字符"？"。 这是因为不表示 ASCII 字符集中具有等效值大于 127 个字符。  
  
 [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] 为两个新编码提供支持：  
  
- 西欧语  
  
- UTF-8  
  
  创建并生成一个自定义管道组件以实现扩展编码的支持。 自定义管道组件使用 BTAHL7 2.X 拆装器。 创建使用自定义管道来处理消息的接收位置。 若要测试的接收位置和自定义管道，您可以创建使用 BTAHL7 2.XSendPipeline 的发送端口。  
  
### <a name="to-create-a-custom-pipeline"></a>若要创建自定义管道  
  
1. 在中[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]，添加一个新**空的 BizTalk Server 项目**。  
  
2. 在解决方案资源管理器，右键单击新项目中，单击**外**，然后单击**新项**。  
  
3. 在中**添加新项**对话框框中，添加一个新**接收管道**。  
  
4. 从管道工具箱拖动**BTAHL7 2.X 反汇编程序**到管道编辑器并将其拖到放置**拆装**阶段**拖至此处**目标。  
  
   > [!NOTE]
   >  如果 BTAHL7 2.7 拆装器不在工具箱中，在工具箱中，右键单击，然后单击**选择项**。 在中**选择工具箱项**对话框中，在**BizTalk 管道组件**选项卡上，选择**BTAHL7 2.X 拆装器**复选框，然后依次**确定**.  
  
5. 中的属性窗格**BTAHL7 2.X 反汇编程序**，从**编码字符集**下拉列表中，选择**西欧语言**或**UTF8**编码。  
  
   > [!NOTE]
   >  HL7 仅支持 ASCII （默认值）、 西欧和 UTF8 编码。 不要选择其他编码选项，因为 HL7 不支持它们。  
  
6. 在“文件”  菜单上，单击“全部保存” 。  
  
7. 部署项目。  
  
    创建新接收位置以继续。  
  
### <a name="to-create-a-receive-location-that-uses-the-custom-pipeline"></a>若要创建使用自定义管道的接收位置  
  
1. 上**启动**菜单上，单击**程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，展开应用程序指定为管道程序集 (默认情况下**BizTalk Application 1**)，右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。  
  
3. 在中**接收位置属性**对话框中**接收管道**下拉列表中，选择的自定义名称你创建的管道。 (这是自定义管道对象，不 BTAHL7 名称 2 倍的管道。)  
  
### <a name="to-create-a-send-port-to-test-the-receive-location-and-pipeline"></a>若要创建用于测试的接收位置和管道的发送端口  
  
1. 上**启动**菜单上，单击**程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，展开应用程序指定为管道程序集 (默认情况下**BizTalk Application 1**)，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
3. 在中**发送端口属性**对话框中**发送管道**下拉列表中，选择**BTAHL72XSendPipeline**。  
  
### <a name="to-test-the-receive-location-and-pipeline"></a>若要测试的接收位置和管道  
  
-   删除包含特殊字符和保存具有相同的编码到指定接收位置中的位置指定自定义管道中的文件。 输出位置上的文件应保留的特殊字符。  
  
    > [!NOTE]
    >  如果你尝试使用不受支持编码将文件处理 （请记住，支持仅 ASCII、 西欧和 UTF8），并出现错误 ID 在应用程序事件查看器中记录错误：5633.  
  
    > [!NOTE]
    >  如果要测试配置为 UTF8 编码的自定义管道，您应将字节顺序标记 (BOM) 字符附加到要传递的消息。 如果要测试配置为西欧语言编码的自定义管道，不附加 BOM 字符。