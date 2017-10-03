---
title: "步骤 7： 构建和部署 DoubleAction SDK 示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- deploying, solutions
- building solutions
- double action tutorial, deploying solutions
ms.assetid: f67f8aee-1004-48ee-a6fd-881097382888
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b503f423d736d9c5f08c7d04a84110a85564d11d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-building-and-deploying-the-doubleaction-sdk-sample"></a>步骤 7： 构建和部署 DoubleAction SDK 示例
DoubleAction.odx 示例显示了如何实现业务流程，以自动为双操作合作伙伴接口流程 (PIP) 0C2、0C4、3A2 和 3A4 生成响应。 你可将此示例项目扩展为支持其他双操作 PIP。  
  
 只要 Fabrikam 使用这四种 PIP 中的任意一种发出请求，此示例都可自动向 Fabrikam 发送响应。  
  
### <a name="to-build-and-initialize-the-doubleaction-sample"></a>生成和初始化 DoubleAction 示例  
  
1.  在 Contoso 计算机的命令提示符窗口中，转到以下文件夹：   
    *\<驱动器 >*: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本 > Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction\\。  
  
    > [!NOTE]
    >  在运行安装程序之前，用记事本打开 DoubleAction.sql 文件（位于上述文件夹中）。 上**文件**菜单上，单击**另存为**。 在**编码**框中，选择**ANSI**从下拉列表，然后单击**保存**。 单击**是**覆盖现有文件。  
  
2.  如果你安装的 [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] 运行在 SQL Server 2008 R2/2008 SP1 上，则运行同一文件夹中的 setupx64.bat。 该批处理文件将执行以下操作：  
  
    -   在 BTARNDATA 数据库中创建一个 SQL 存储过程 (`PipAutomationGetAction`)，用于从 MessagesToLOB 表中检索操作消息。  
  
    -   编译 HeaderHelper .NET 项目，并在全局程序集缓存中注册此程序集。  
  
    -   创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SQL 接收端口 (MessagesToLOB_Receive_Port)。  
  
    -   启用接收位置 (MessagesToLOB_Receive_Location)。  
  
    -   编译并部署双操作 PIPAutomation 业务流程 (DoubleAction.odx)。  
  
    -   绑定并启动 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 业务流程。  
  
        > [!NOTE]
        >  编译时示例将显示一些警告。 你可以忽略这些警告。  
  
        > [!NOTE]
        >  验证 DoubleAction.odx 已绑定到**MessagesToLOB_Receive_Port**，和业务流程已开始。  
  
3.  在[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]管理控制台中，展开**BizTalk 组**，**应用程序**，和**BizTalk 应用程序 1**节点。 单击**业务流程**节点。 右键单击**DoubleAction**业务流程，，然后单击**属性**。 在属性对话框中，单击**绑定**节点，再然后将其设置**主机**到**BizTalkServerApplication**并设置**接收端口**到**MessageToLOB_ReceivePort**。 单击 **“确定”**。 右键单击**DoubleAction**业务流程，，然后单击**启动**。  
  
## <a name="see-also"></a>另请参阅  
 [创建和配置 Fabrikam 解决方案](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-fabrikam-solution.md)