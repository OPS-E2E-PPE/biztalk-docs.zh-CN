---
title: 扩展编码支持 |Microsoft 文档
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
ms.openlocfilehash: 9e36c3baff4ac33f2878295791bb3f6615c1b25d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204829"
---
# <a name="extended-encoding-support"></a>扩展编码的支持
默认情况下，HL7 接收管道，BTAHL72X，仅支持 ASCII 编码。 这意味着，具有等效值大于 127 都将替换输入消息中的任何字符"？"。 这是因为在 ASCII 字符集中未表示具有等效值大于 127 个字符。  
  
 [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]为这两个新的编码提供支持：  
  
-   西欧语言  
  
-   UTF-8  
  
 创建并生成要实现扩展的编码支持的自定义管道组件。 自定义管道组件使用 BTAHL7 2.X 反汇编程序。 创建使用自定义管道处理消息的接收位置。 若要测试的接收位置和自定义管道，你可以创建使用 BTAHL7 2.XSendPipeline 发送端口。  
  
### <a name="to-create-a-custom-pipeline"></a>若要创建的自定义管道  
  
1.  在[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]，添加新**空 BizTalk 服务器项目**。  
  
2.  在解决方案资源管理器，右键单击新项目，单击**添加**，然后单击**新项**。  
  
3.  在**添加新项**对话框框中，添加一个新**接收管道**。  
  
4.  从管道工具箱中，将**BTAHL7 2.X 反汇编程序**到管道编辑器拖放到**拆卸**阶段**拖至此处**目标。  
  
    > [!NOTE]
    >  如果 BTAHL7 2.7 反汇编程序不在工具箱中，在工具箱中，右键单击，然后单击**选择项**。 在**选择工具箱项**对话框中，在**BizTalk 管道组件**选项卡上，选择**BTAHL7 2.X 反汇编程序**复选框，并依次**确定**.  
  
5.  在为属性窗格中**BTAHL7 2.X 反汇编程序**，从**编码 charset**下拉列表中，选择**西欧**或**UTF8**编码。  
  
    > [!NOTE]
    >  HL7 仅支持 ASCII （默认）、 西欧，和 UTF8 编码。 由于 HL7 不支持它们，则无法选择其他的编码选项。  
  
6.  在“文件”  菜单上，单击“全部保存” 。  
  
7.  部署该项目。  
  
     创建一个新接收位置以继续。  
  
### <a name="to-create-a-receive-location-that-uses-the-custom-pipeline"></a>若要创建使用自定义管道接收位置  
  
1.  上**启动**菜单上，单击**程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，展开应用程序指定管道程序集 (默认情况下， **BizTalk 应用程序 1**)，右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。  
  
3.  在**接收位置属性**对话框中，在**接收管道**下拉列表中，选择自定义的名称管道你创建。 (这是自定义管道对象，不 BTAHL7 名称 2 X 管道。)  
  
### <a name="to-create-a-send-port-to-test-the-receive-location-and-pipeline"></a>若要创建要测试的接收位置和管道发送端口  
  
1.  上**启动**菜单上，单击**程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，展开应用程序指定管道程序集 (默认情况下， **BizTalk 应用程序 1**)，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
3.  在**发送端口属性**对话框中，在**发送管道**下拉列表中，选择**BTAHL72XSendPipeline**。  
  
### <a name="to-test-the-receive-location-and-pipeline"></a>若要测试的接收位置和管道  
  
-   删除包含特殊字符，且使用相同的编码到在接收位置中指定的位置指定自定义管道中保存的文件。 输出位置上的文件应保留的特殊字符。  
  
    > [!NOTE]
    >  如果你尝试处理使用不受支持编码的文件 （请记住，支持仅 ASCII、 西欧和 UTF8），一个错误记录在应用程序事件查看器，并出现错误 ID: 5633。  
  
    > [!NOTE]
    >  如果你要测试配置为 UTF8 编码的自定义管道，你应该附加到您要传递的消息的字节顺序标记 (BOM) 字符。 如果你要测试配置为西欧字符编码的自定义管道，不要将连接 BOM 字符。