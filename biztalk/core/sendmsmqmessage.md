---
title: SendMSMQMessage |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, examples
- examples, MSMQ adapters
ms.assetid: 398bc396-0c66-4d55-886a-0d9bdab6476f
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a48cbb333a724d2f60141f0f67ef3feccb1d3954
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975507"
---
# <a name="sendmsmqmessage"></a>SendMSMQMessage
SendMSMQMessage 示例演示如何从基于 .NET 的应用程序向 MSMQ 端口发送消息。 它还提供有关如何配置 Microsoft 说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为了使用 MSMQ 接收位置。  
  
 应注意消息队列中的许多操作都是异步的。 也就是说，许多 MSMQ API 调用 (例如， **System.Messaging.MessageQueue.Send**) 返回到调用方完全完成请求的操作之前。 MSMQ 提供了一种在操作完成之后将反馈传送到应用程序的机制。 此机制涉及“管理队列”的使用。 MSMQ 将反馈以管理队列中的消息的形式返回。 MSMQ 将向其返回反馈的管理队列是在进行原始 MSMQ API 调用时指定的。 因此，举例来说，当发送消息使用**System.Messaging.MessageQueue.Send** API，应用程序可以指定管理队列的名称，通过使用**PROPID_M_ADMIN_QUEUE** message 属性对消息传递的调用中**System.Messaging.MessageQueue.Send**。 即使应用程序可能会成功的返回代码在**System.Messaging.MessageQueue.Send**调用时，如果该消息的发送操作随后失败，MSMQ 将消息针对此效果写入指定的管理队列。 如果应用程序未指定管理队列，发送失败将导致丢失消息和捕获任何诊断-实际上，该消息消失但没有任何证据。 有大量的错误可能会导致这种情况，例如，执行非事务性的 MSMQ 中的情况下将发送到事务性队列。  
  
 在此示例的上下文，很重要这段代码的调用中指定的事务类型**System.Messaging.MessageQueue.Send**是一致与为队列消息是指定的事务支持发送。 如果未完成此和未管理员指定队列 （就是在此示例中这种情况），如果 MSMQ 放弃时，它还执行该操作没有指示发送的消息 （即，没有错误代码返回给应用程序事件日志中写入任何诊断依此类推)。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<示例路径\>\AdaptersUsage\SendMSMQMessage\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|-----------|-----------------|  
|App.ico、AssemblyInfo.cs、SendMSMQMessage.csproj、SendMSMQMessage.sln|提供项目、 解决方案和简单图形应用程序，此示例的相关的文件。|  
|Form1.cs、Form1.resx|为本示例的简单图形应用程序提供 Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].NET 源文件和表单文件。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 可以将本示例随附的简单图形应用程序中的代码用作以下过程的一个例子：将消息从诸如 Microsoft Office 之类的启用了 .NET 的应用程序、ASP.NET 页或其他地方发送到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 内的 MSMQ 接收位置。  
  
## <a name="building-and-initializing-the-sample"></a>生成并初始化本示例  
  
#### <a name="to-build-the-sample-executable"></a>生成示例可执行文件  
  
1.  使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 SendMSMQMessage.sln。  
  
2.  在“生成”  菜单上，单击“生成解决方案” 。  
  
## <a name="configuring-biztalk-server-and-creating-the-msmq-queue"></a>配置 BizTalk Server 和创建 MSMQ 队列  
 使用以下过程配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 并创建 MSMQ 队列以运行示例。  
  
#### <a name="to-create-the-msmq-queue-in-windows-server-2008-r2-or-windows-server-2008-sp2"></a>在 Windows Server 2008 R2 或 Windows Server 2008 SP2 中创建 MSMQ 队列的步骤  
  
1.  单击**启动**，右键单击**计算机**，然后单击**管理**。  
  
2.  展开**功能**节点。  如果**消息队列**是未安装，请右键单击**功能**和选择**添加功能**。  检查**消息队列**，单击**下一步**，然后单击**安装**该系统上安装 MSMQ。  
  
3.  展开**消息队列**节点。  
  
4.  右键单击**专用队列**节点，单击**新建**，然后单击**专用队列**。  
  
5.  下**队列名称**，输入`test`。 确保**事务**复选框处于选中状态。  
  
6.  单击 **“确定”**。  
  
#### <a name="to-create-the-msmq-queue-in-windows-7-or-windows-vista-sp2"></a>在 Windows 7 或 Windows Vista SP2 中创建 MSMQ 队列的步骤  
  
1.  单击**启动**，右键单击**计算机**，然后单击**管理**。  
  
2.  展开**服务和应用程序**，然后展开**消息队列**节点。  
  
    > [!NOTE]
    >  如果**消息队列**未安装在计算机上，转到**控制面板 > 程序 > 程序和功能**，然后选择**打开或关闭 Windows 功能**。 检查下的所有功能**Microsoft Message Queue (MSMQ) 服务器**，然后单击**确定**。  
  
3.  右键单击**专用队列**节点，单击**新建**，然后单击**专用队列**。  
  
4.  下**队列名称**，输入**测试**。 确保**事务**复选框处于选中状态。  
  
5.  单击 **“确定”**。  
  
#### <a name="to-configure-biztalk-server"></a>若要配置 BizTalk Server  
  
1.  选择存放接收消息的文件夹。 以下步骤假定您选择了 C:\Demo\Report，但如有必要，可调整这些步骤来使用其他文件夹。  
  
2.  打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
3.  创建新的应用程序名为**MSMQSample**。  
  
4.  右键单击**接收端口**，单击**新建**，然后单击**单向接收端口**。  
  
5.  在**接收端口属性**对话框中，在**名称**框中输入**MyReceivePort**，然后单击**确定**。  
  
6.  右键单击**接收位置**，单击**新建**，然后单击**单向接收位置**。 在**选择接收端口**对话框中，选择你刚接收端口创建，然后单击**确定**。  
  
7.  在**接收位置属性**对话框中，在**名称**框中，键入接收端口的名称，如**MSMQReceiveLocation**。  
  
8.  在**接收位置属性**对话框中，对于传输类型中，选择**MSMQ** 。  
  
9. 单击**配置**以打开**MSMQ 传输属性**对话框。 设置**队列**到`localhost\private$\test`，将其设置**事务**到`True`，然后单击**确定**。  
  
10. 展开应用程序，选择**发送端口**，选择**新建**，选择**静态单向发送端口**。  
  
11. 在**发送端口属性**对话框中，在**名称**框中，键入发送端口的名称，如**MySendPort**。  
  
12. 设置**传输类型**属性**文件**。  
  
13. 单击**配置**以打开**文件传输属性**对话框。  
  
14. 在**文件传输属性**对话框中，设置**目标文件夹**属性**C:\Demo\Report**，保留其他属性的默认设置，然后单击**确定**。  
  
15. 选择**筛选器**，然后通过设置中添加新行**属性**到**BTS。ReceivePortName**。 保留**运算符**列设置为 **==** ，将其设置**值**列**MyReceivePort**，然后单击**确定**。  
  
16. 右键单击新发送端口，然后单击**Enlist**。  
  
17. 右键单击新发送端口试，然后单击**启动**。  
  
18. 右键单击新接收位置，然后单击**启用**。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]现在已准备好要使用此示例。  
  
## <a name="running-the-sample"></a>运行示例  
 使用以下过程运行 SendMSMQMessage 示例。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<示例路径\>\AdaptersUsage\SendMSMQMessage\bin\Debug  
  
2.  运行文件 SendMSMQMessage.exe，这将启动提供本示例的用户界面的图形应用程序。  
  
3.  在图形应用程序中**BizTalk 计算机名称**框中，键入本地计算机的名称。  
  
4.  请尝试**发送包装**选项：  
  
    1.  （可选） 更改中的文本**消息正文**框。  
  
    2.  单击**发送已包装**。  
  
     如果操作成功，则将看到以下内容：  
  
    -   Word**成功**立即上方的按钮的框中的红色字体显示。  
  
    -   将在目标文件夹 C:\Demo\Reports 中显示一个文件。 此文件包含中的文本**消息正文**包装在简单的 XML 标记，由.NET 消息队列库中的框。  
  
     如果操作失败，则将在按钮上方紧挨的框中显示一条错误消息。  
  
5.  请尝试**发送确切**选项：  
  
    1.  （可选） 更改中的文本**消息正文**框。  
  
    2.  单击**发送确切**。  
  
     如果操作成功，则将看到以下内容：  
  
    -   Word**成功**立即上方的按钮的框中的红色字体显示。  
  
    -   将在目标文件夹 C:\Demo\Reports 中显示一个文件。 此文件包含中的文本**消息正文**框中的文本框中显示的完全相同。  
  
     如果操作失败，则将在按钮上方紧挨的框中显示一条错误消息。  
  
## <a name="see-also"></a>另请参阅  
 [适配器示例 - 用法](../core/adapter-samples-usage.md)