---
title: "于 MSMQ 的大消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, examples
- examples, MSMQ adapters
ms.assetid: 1fb87b46-5656-42c0-be99-8ab66e51bb4d
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e6a3fda3082260338bd387dfe84fe48c7aed565
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="large-message-to-msmq"></a>于 MSMQ 的大型消息
大型消息到 MSMQ 示例演示如何.xml 文档大于 4 兆字节 (MB) 将从发送消息队列 (也称为 MSMQ) 到 BizTalk MSMQ 适配器使用**MQSendLargeMessage** API 实现通过MQRTLarge.dll。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例的工作原理如下所示：  
  
1.  用户使用 SendLargeMessage.exe 将大型 .xml 文件发送到本地计算机中的队列。  
  
2.  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 从该队列接收大型 .xml 文件，并将其复制到本地目录。  
  
 消息队列中的许多操作都是异步进行的。 也就是说，许多 MSMQ API 调用 (例如， **MQSendLargeMessage**) 返回到调用方完全完成请求的操作之前。  
  
 MSMQ 提供了一种在操作完成之后将反馈传送到应用程序的机制。 此机制涉及“管理队列”的使用。 MSMQ 将反馈以管理队列中的消息的形式返回。 MSMQ 将向其返回反馈的管理队列是在进行原始 MSMQ API 调用时指定的。 因此，举例来说，当发送消息使用**MQSendLargeMessage** API，应用程序可以指定管理队列的名称，通过使用**PROPID_M_ADMIN_QUEUE**消息对消息的属性对的调用中传递**MQSendLargeMessage**。 即使应用程序可能会成功的返回代码在**MQSendLargeMessage**调用时，如果该消息的发送操作随后失败，MSMQ 将消息针对此效果写入指定的管理队列。  
  
 如果应用程序未指定管理队列，则发送失败会导致消息丢失并且捕获不到任何诊断信息，实际上，就是消息会不留任何痕迹地消失。 MSMQ 中的许多错误情形都可以导致这种情况发生，例如，向事务性队列执行非事务性发送。  
  
 在此示例的上下文，很重要这段代码的调用中指定的事务类型**MQSendLargeMessage**是为队列消息发送到指定的事务支持使用一致。 如果未完成此和未管理员指定队列 （就是在此示例中这种情况），如果 MSMQ 放弃时，它还执行该操作没有指示发送的消息 （即，没有错误代码返回给应用程序事件日志中写入任何诊断依此类推)。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<示例路径 > \AdaptersUsage\MSMQLarge  
  
> [!NOTE]
>  如果使用 Windows 的 64 位版本和[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，该示例将安装在**C:\Program Files (x86) \Microsoft BizTalk Server\<版本 > \SDK\Samples\AdaptersUsage\MSMQLarge**文件夹。  请注意有关在此文档中使用的任何其他说明此更改**C:\Program Files**文件夹。  
  
 下表显示了本示例中的文件及其用途说明：  
  
|**文件**|**Description**|  
|--------------|---------------------|  
|**MQRTLarge.dll**|为本地消息队列提供加载项。 公开**MQSendLargeMessage**和**MQReceiveLargeMessage** Api。<br /><br /> 必须将 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 安装到 64 位版本的 Windows 上才能访问 64 位版本的 Mqrtlarge.dll。<br /><br /> 对于 MSMQ 解决方案，即使没有 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，MQRTLarge.dll 仍能正常工作。 但是，Microsoft 不推荐使用这种配置，如果在 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 环境外使用，可能会发生意外结果。|  
|||  
|**LargeMessages.sln**|提供 [!INCLUDE[vs2010](../includes/vs2010-md.md)] 解决方案，以创建在本示例中使用的 SendLargeMessage 可执行文件。|  
|**XMLCreator.sln**|提供 [!INCLUDE[vs2010](../includes/vs2010-md.md)] 解决方案，以创建为 SDK 示例生成 .xml 测试文件的 XMLCreator 可执行文件。|  
  
## <a name="configuring-biztalk-server-and-creating-the-msmq-queue"></a>配置 BizTalk Server 和创建 MSMQ 队列  
 请确保你已安装 [!INCLUDE[vs2010](../includes/vs2010-md.md)]、Microsoft 消息队列和 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。  
  
#### <a name="to-configure-biztalk-server"></a>若要配置 BizTalk Server  
  
1.  在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开**C:\Program Files\Microsoft BizTalk Server\<版本 > \SDK\Samples\AdaptersUsage\MSMQLarge\LargeMessages.sln**解决方案文件。  生成示例。  
  
2.  创建**C:\Demo**目录其中[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]将放置在 MSMQ 的消息。  
  
3.  打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
4.  为本示例创建发送端口，以写入消息。  
  
    -   展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，右键单击**发送端口**，单击**新建**，然后单击**静态单向发送端口**。  
  
5.  在**静态单向发送端口属性**对话框框中，设置到端口的名称的**MySendPort**。  
  
6.  将传输类型设置为**文件**。  
  
7.  单击**配置**按钮以打开**文件传输属性**窗体。 输入**C:\Demo**中**目标文件夹**。 确保主机实例标识具有对 C:\Demo 文件夹的访问权限。  
  
8.  确保**文件名**设置为**%MessageID%.xml**。 单击 **“确定”**。  
  
9. 单击 **“筛选器”**。  
  
    1.  设置**属性**到**BTS。ReceivePortName**。  
  
    2.  设置**运算符**到 **=** 。  
  
    3.  设置**值**到**MyReceivePort**。  
  
    4.  单击 **“确定”**。  
  
10. 创建接收端口，以接受来自 MSMQ 的消息。  
  
    1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**。  
  
    2.  单击**新建**，然后单击**单向接收端口**。  
  
11. 在**接收端口属性**对话框框中，设置到端口的名称的**MyReceivePort**，然后单击**确定**。  
  
12. 为本示例创建接收端口后，必须创建接收位置。  
  
    1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收位置**。  
  
    2.  单击**新建**，然后单击**单向接收位置**。  
  
    3.  设置到的接收位置的名称**MSMQReceiveLocation**。  
  
    4.  在**选择接收端口**对话框中，选择**MyReceivePort**。  
  
    5.  在**接收位置属性**对话框中，设置**传输类型**到**MSMQ**。  
  
    6.  在**地址 (URI)**部分中，单击**配置**以打开**MSMQ 传输属性**窗体。 设置**队列**到**localhost\private$ \test**。  
  
    7.  设置**事务**到`True`，然后单击**确定**。  
  
13. 你必须通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台使端口和接收位置可用。  
  
    1.  右键单击**MySendPort**，然后单击**Enlist**。  
  
    2.  右键单击**MySendPort**，然后单击**启动**。  
  
    3.  右键单击**MSMQReceiveLocation**，然后单击**启用**。  
  
#### <a name="to-create-the-msmq-queue-in-windows-server-2008-r2-or-windows-server-2008-sp2"></a>在 Windows Server 2008 R2 或 Windows Server 2008 SP2 中创建 MSMQ 队列的步骤  
  
1.  单击**启动**，右键单击**计算机**，然后单击**管理**。  
  
2.  展开**功能**节点。  
  
3.  展开**消息队列**节点。  
  
4.  右键单击**专用队列**节点，单击**新建**，然后单击**专用队列**。  
  
5.  下**队列名称**，输入**测试**。 确保**事务**复选框处于选中状态。  
  
6.  单击 **“确定”**。  
  
#### <a name="to-create-the-msmq-queue-in-windows-7-or-windows-vista-sp2"></a>在 Windows 7 或 Windows Vista SP2 中创建 MSMQ 队列的步骤  
  
1.  单击**启动**，右键单击**计算机**，然后单击**管理**。  
  
2.  展开**服务和应用程序**，然后展开**消息队列**节点。  
  
    > [!NOTE]
    >  如果**消息队列**未安装在计算机上，转到**控制面板 > 程序 > 程序和功能**，然后选择**打开或关闭 Windows 功能**。 检查下的所有功能**Microsoft Message Queue (MSMQ) 服务器**，然后单击**确定**。  
  
3.  右键单击**专用队列**节点，单击**新建**，然后单击**专用队列**。  
  
4.  下**队列名称**，输入**测试**。 确保**事务**复选框处于选中状态。  
  
5.  单击 **“确定”**。  
  
## <a name="creating-a-test-file-and-running-the-sample"></a>创建测试文件并运行该示例  
  
#### <a name="to-create-a-large-test-file"></a>创建大型测试文件  
  
1.  在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开解决方案**C:\Program Files\Microsoft BizTalk Server\<版本 > \SDK\Samples\AdaptersUsage\MSMQLarge\XMLCreator\XMLCreator.sln**。  
  
2.  生成并运行该项目。  
  
3.  下**XML 正文**，类型**这是测试消息**。  
  
4.  下**数次以复制 XML 正文**，类型`250000`。  
  
5.  下**XML 文件位置**，类型`C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml`。  
  
6.  单击**创建 XML**，然后单击**确定**。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  打开命令提示符，并将目录更改为**C:\Program Files\Microsoft BizTalk Server\<版本 > \SDK\Samples\AdaptersUsage\MSMQLarge\SendLargeMessage\bin\debug**。  
  
2.  在命令提示符处，运行**SendLargeMessage.exe**。 SendLargeMessage 可执行文件接受两个变量，第一个是 MSMQ 队列的位置，第二个是要发送的 .xml 文件的位置：  
  
    ```  
    DIRECT=OS:localhost\private$\Test  "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml"  
    ```  
  
3.  验证是否相同大小的文件已在创建[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]中的计算机**C:\Demo**目录。 此目录即为在 MySendPort 发送端口中标识的目录。  
  
## <a name="comments"></a>注释  
 SendLargeMessage.exe 引用**LargeMessages** API，后者反过来又引用 BizTalk 消息队列大型消息扩展 (MQRTLarge.dll) API。 消息队列大消息扩展 API 是本地消息队列的加载项，利用它便能处理大于本地消息队列 4 MB 限制的消息。  
  
 此示例使用**MQSendLargeMessage** API 并公开 API 的.NET framework 通过**LargeMessages** API。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk 消息队列大型消息扩展](../core/biztalk-message-queuing-large-message-extension.md)   
 [适配器示例-使用情况](../core/adapter-samples-usage.md)