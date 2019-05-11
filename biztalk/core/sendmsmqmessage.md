---
title: SendMSMQMessage | Microsoft Docs
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
ms.openlocfilehash: f3088405a46be194c899684ebef63c33b6592a37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398995"
---
# <a name="sendmsmqmessage"></a>SendMSMQMessage
SendMSMQMessage 示例演示如何向 MSMQ 端口发送消息。基于 NET 的应用程序。 它还提供了有关如何配置 Microsoft 说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 MSMQ 接收位置。  

 您应注意消息队列中的许多操作都是异步。 即，许多 MSMQ API 呼叫 (例如， **System.Messaging.MessageQueue.Send**) 返回给调用方请求的操作完全完成之前。 MSMQ 提供了一种在操作完成之后将反馈传送到应用程序的机制。 此机制涉及到使用"管理队列"。 MSMQ 管理队列中消息的形式返回的反馈。 MSMQ 将反馈返回到的管理队列进行原始 MSMQ API 调用时指定。 因此，举例来说，当发送消息使用**System.Messaging.MessageQueue.Send** API，应用程序可以指定管理队列的名称，通过使用**PROPID_M_ADMIN_QUEUE**消息属性对消息传递到调用中**System.Messaging.MessageQueue.Send**。 即使应用程序可能会获得成功返回代码**System.Messaging.MessageQueue.Send**调用时，如果消息的发送操作随后失败，MSMQ 消息写入该结果指定的管理队列。 如果应用程序未指定管理队列，发送失败会导致消息丢失并且捕获任何诊断 — 实际上，该消息消失但没有任何证据。 有了很多错误可能会导致这种情况发生，例如，执行非事务性 MSMQ 中的情况下将发送到事务性队列。  

 在本示例的上下文，非常重要的代码对的调用中指定的事务类型**System.Messaging.MessageQueue.Send**这就是与的队列的消息是指定的事务支持一致发送。 如果这不是，如果 （如在此示例中） 不指定任何管理队列，则 MSMQ 放弃时，它还执行该操作没有指示发送的消息 （即，没有错误代码返回给应用程序事件日志中写入任何诊断等等)。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<Samples Path\>\AdaptersUsage\SendMSMQMessage\  

 下表显示了本示例中的文件及其用途说明：  


|                                 文件                                 |                                                                      Description                                                                       |
|-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| App.ico、 AssemblyInfo.cs、 SendMSMQMessage.csproj、 SendMSMQMessage.sln |                           提供项目、 解决方案和相关的文件，此示例的简单图形应用程序。                           |
|                         Form1.cs, Form1.resx                          | 提供 Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].NET 源文件和表单文件，此示例的简单图形应用程序。 |

## <a name="how-to-use-this-sample"></a>如何使用此示例  
 可以在此示例随附作为示例，了解如何将发送到 MSMQ 消息的接收位置中的简单图形应用程序中使用代码[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从。NET 启用的应用程序如 Microsoft Office，从 ASP.NET 页中，依次类推。  

## <a name="building-and-initializing-the-sample"></a>生成并初始化示例  

#### <a name="to-build-the-sample-executable"></a>若要生成示例可执行文件  

1. 使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案文件 SendMSMQMessage.sln。  

2. 在“生成”  菜单上，单击“生成解决方案” 。  

## <a name="configuring-biztalk-server-and-creating-the-msmq-queue"></a>配置 BizTalk Server 和创建 MSMQ 队列  
 使用以下过程来配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并创建 MSMQ 队列以运行示例。  

#### <a name="to-create-the-msmq-queue-in-windows-server-2008-r2-or-windows-server-2008-sp2"></a>若要在 Windows Server 2008 R2 或 Windows Server 2008 SP2 中创建 MSMQ 队列  

1.  单击**启动**，右键单击**计算机**，然后单击**管理**。  

2.  展开**功能**节点。  如果**消息队列**是未安装，请右键单击**功能**，然后选择**添加功能**。  检查**消息队列**，单击**下一步**，然后单击**安装**该系统上安装 MSMQ。  

3.  展开**消息队列**节点。  

4.  右键单击**专用队列**节点中，单击**新建**，然后单击**专用队列**。  

5.  下**队列名称**，输入`test`。 絋粄**事务性**复选框处于选中状态。  

6.  单击“确定” 。  

#### <a name="to-create-the-msmq-queue-in-windows-7-or-windows-vista-sp2"></a>若要在 Windows 7 或 Windows Vista SP2 中创建 MSMQ 队列  

1.  单击**启动**，右键单击**计算机**，然后单击**管理**。  

2.  展开**服务和应用程序**，然后展开**消息队列**节点。  

    > [!NOTE]
    >  如果**消息队列**未安装在计算机中，转到**控制面板 > 程序 > 程序和功能**，然后选择**打开或关闭打开的 Windows 功能**。 检查下的所有功能**Microsoft 消息队列 (MSMQ) 服务器**，然后单击**确定**。  

3.  右键单击**专用队列**节点中，单击**新建**，然后单击**专用队列**。  

4.  下**队列名称**，输入**测试**。 絋粄**事务性**复选框处于选中状态。  

5.  单击“确定” 。  

#### <a name="to-configure-biztalk-server"></a>若要配置 BizTalk Server  

1. 选择用来接收消息的文件夹。 以下步骤假定选择了 C:\Demo\Report，但您可以调整为另一个文件夹所需的步骤。  

2. 打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

3. 创建新的应用程序名为**MSMQSample**。  

4. 右键单击**接收端口**，单击**新建**，然后单击**单向接收端口**。  

5. 在中**接收端口属性**对话框中**名称**框中输入**MyReceivePort**，然后单击**确定**。  

6. 右键单击**接收位置**，单击**新建**，然后单击**单向接收位置**。 在中**选择接收端口**对话框中，选择接收端口刚刚创建，并单击**确定**。  

7. 在中**接收位置属性**对话框中**名称**框中，键入接收端口的名称，如**MSMQReceiveLocation**。  

8. 在中**接收位置属性**对话框中的，为传输类型选择**MSMQ** 。  

9. 单击**配置**以打开**MSMQ 传输属性**对话框。 设置**队列**到`localhost\private$\test`，将**事务性**到`True`，然后单击**确定**。  

10. 展开的应用程序中，选择**发送端口**，选择**新建**，选择**静态单向发送端口**。  

11. 在中**发送端口属性**对话框中**名称**框中，键入发送端口的名称，如**MySendPort**。  

12. 设置**传输类型**属性设置为**文件**。  

13. 单击**配置**以打开**File 传输属性**对话框。  

14. 在中**FILE 传输属性**对话框中，将**目标文件夹**属性设置为**C:\Demo\Report**，保留其他属性的默认设置，然后单击**确定**。  

15. 选择**筛选器**，然后通过设置将添加一个新行**属性**到**BTS。ReceivePortName**。 将保留**运算符**列设置为**==**，将**值**列**MyReceivePort**，然后单击**确定**。  

16. 右键单击新发送端口，然后单击**登记**。  

17. 右键单击新发送端口，然后单击**启动**。  

18. 右键单击新接收位置，然后单击**启用**。  

    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 现在已准备好可使用本示例。  

## <a name="running-the-sample"></a>运行示例  
 使用以下过程运行 SendMSMQMessage 示例。  

#### <a name="to-run-the-sample"></a>若要运行示例  

1. 在命令窗口中，导航到以下文件夹：  

    \<Samples Path\>\AdaptersUsage\SendMSMQMessage\bin\Debug  

2. 运行文件 SendMSMQMessage.exe，这将启动此示例中提供的用户界面的图形应用程序。  

3. 在图形应用程序中**BizTalk 计算机名**框中，键入本地计算机的名称。  

4. 请尝试**Send Wrapped**选项：  

   1. （可选） 更改中的文本**消息正文**框。  

   2. 单击**发送已包装**。  

      如果操作成功，会看到以下：  

   - 单词**成功**立即按钮上方的框中以红色字体显示。  

   - 在你在目标文件夹 C:\Demo\Reports 中会出现一个文件。 此文件包含从文本**消息正文**包装在由.NET 消息队列库的简单 XML 标记的框。  

     如果操作失败，将看到立即按钮上方的框中的错误消息。  

5. 请尝试**Send Exact**选项：  

   1. （可选） 更改中的文本**消息正文**框。  

   2. 单击**发送确切**。  

      如果操作成功，会看到以下：  

   - 单词**成功**立即按钮上方的框中以红色字体显示。  

   - 在你在目标文件夹 C:\Demo\Reports 中会出现一个文件。 此文件包含从文本**消息正文**框在文本框中显示的样子。  

     如果操作失败，将看到立即按钮上方的框中的错误消息。  

## <a name="see-also"></a>请参阅  
 [适配器示例 - 用法](../core/adapter-samples-usage.md)