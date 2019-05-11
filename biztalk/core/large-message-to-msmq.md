---
title: 大消息到 MSMQ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fb87b46-5656-42c0-be99-8ab66e51bb4d
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d92428426b7032de36ab63cfd2be286ce3c67569
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329823"
---
# <a name="large-message-to-msmq"></a>大到 MSMQ 消息
大消息示例演示如何将发送的.xml 文档超过 4 兆字节 (MB) 从消息队列 (也称为 MSMQ) 到 BizTalk MSMQ 适配器通过使用**MQSendLargeMessage**由 API 实现MQRTLarge.dll。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 该示例的工作方式如下：  
  
1. 用户使用 SendLargeMessage.exe 将大型.xml 文件发送到本地计算机上的队列。  
  
2. BizTalk Server 从队列接收大型.xml 文件，并将其复制到本地目录。  
  
   消息队列中的许多操作都是异步的。 即，许多 MSMQ API 呼叫 (例如， **MQSendLargeMessage**) 返回给调用方请求的操作完全完成之前。  
  
   MSMQ 提供了一种在操作完成之后将反馈传送到应用程序的机制。 此机制涉及到使用"管理队列"。 MSMQ 管理队列中消息的形式返回的反馈。 MSMQ 将反馈返回到的管理队列进行原始 MSMQ API 调用时指定。 因此，举例来说，当发送消息使用**MQSendLargeMessage** API，应用程序可以指定管理队列的名称，通过使用**PROPID_M_ADMIN_QUEUE**消息在消息上的属性对的调用中传递**MQSendLargeMessage**。 即使应用程序可能会获得成功返回代码**MQSendLargeMessage**调用时，如果消息的发送操作随后失败，MSMQ 消息写入该结果指定的管理队列。  
  
   如果应用程序未指定管理队列，发送失败会导致消息丢失并且捕获任何诊断 — 实际上，该消息消失但没有任何证据。 很多 MSMQ 中的错误情况可能会导致这种情况发生，例如，非事务性发送到事务性队列。  
  
   在本示例的上下文，非常重要的代码对的调用中指定的事务类型**MQSendLargeMessage**这就是与为向其发送消息的队列指定的事务支持一致。 如果这不是，如果 （如在此示例中） 不指定任何管理队列，则 MSMQ 放弃时，它还执行该操作没有指示发送的消息 （即，没有错误代码返回给应用程序事件日志中写入任何诊断等等)。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<Samples Path\>\AdaptersUsage\MSMQLarge  
  
> [!NOTE]
>  如果使用 Windows 和 BizTalk Server 的 64 位版本，该示例将安装在**C:\Program Files (x86) \Microsoft BizTalk Server\<版本\>\SDK\Samples\AdaptersUsage\MSMQLarge**文件夹。  请注意在该文档中使用的任何其他说明此更改**C:\Program Files**文件夹。  
  
 下表显示了本示例中的文件及其用途说明：  
  
|**File**|**说明**|  
|--------------|---------------------|  
|**MQRTLarge.dll**|提供外接程序的本地消息队列。 公开**MQSendLargeMessage**并**MQReceiveLargeMessage** Api。<br /><br /> 必须在 64 位版本的 Windows 上安装 BizTalk Server，才能访问 64 位版本的 MQRTLarge.dll。<br /><br /> 对于 MSMQ 解决方案未使用 BizTalk Server，MQRTLarge.dll 仍可正常运行。 但是，这不的建议的配置，Microsoft 支持，并且如果在 BizTalk Server 环境外部使用，可能会发生意外的结果。|  
|||  
|**LargeMessages.sln**|提供 Visual Studio 解决方案，以创建示例中使用的 SendLargeMessage 可执行文件。|  
|**XMLCreator.sln**|提供 Visual Studio 解决方案，以创建 XMLCreator 可执行文件生成为 SDK 示例.xml 测试文件。|  
  
## <a name="configure-biztalk-and-create-the-msmq-queue"></a>配置 BizTalk 和创建 MSMQ 队列  
 请确保 Visual Studio、 Microsoft 消息队列和 BizTalk Server 安装。  
  
#### <a name="to-configure-biztalk-server"></a>若要配置 BizTalk Server  
  
1. 在 Visual Studio 中打开**C:\Program Files\Microsoft BizTalk Server\<版本\>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeMessages.sln**解决方案文件。  生成该示例。  
  
2. 创建**C:\Demo** BizTalk Server 将放置来自 MSMQ 的消息目录。  
  
3. 打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
4. 创建示例以写入消息的发送端口。  
  
   -   展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，右键单击**发送端口**，单击**新建**，然后单击**静态单向发送端口**。  
  
5. 在中**静态单向发送端口属性**对话框框中，设置到的端口的名称**MySendPort**。  
  
6. 将传输类型设置为**文件**。  
  
7. 单击**配置**按钮以打开**File 传输属性**窗体。 输入**C:\Demo**中**目标文件夹**。 确保主机实例标识具有对 C:\Demo 文件夹的访问。  
  
8. 絋粄**文件名**设置为 **%MessageID%.xml**。 单击“确定” 。  
  
9. 单击 **“筛选器”**。  
  
    1.  设置**属性**到**BTS。ReceivePortName**。  
  
    2.  设置**运算符**到**=**。  
  
    3.  设置**值**到**MyReceivePort**。  
  
    4.  单击“确定” 。  
  
10. 创建用于接受来自 MSMQ 的消息的接收端口。  
  
    1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收端口**。  
  
    2. 单击**新建**，然后单击**单向接收端口**。  
  
11. 在中**接收端口属性**对话框框中，设置到的端口的名称**MyReceivePort**，然后单击**确定**。  
  
12. 创建示例接收端口后，必须创建接收位置。  
  
    1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**接收位置**。  
  
    2. 单击**新建**，然后单击**单向接收位置**。  
  
    3. 设置为接收位置的名称**MSMQReceiveLocation**。  
  
    4. 在中**选择接收端口**对话框中，选择**MyReceivePort**。  
  
    5. 在中**接收位置属性**对话框中，将**传输类型**到**MSMQ**。  
  
    6. 在中**地址 (URI)** 部分中，单击**配置**以打开**MSMQ 传输属性**窗体。 设置**队列**到**localhost\private$ \test**。  
  
    7. 设置**事务性**到`True`，然后单击**确定**。  
  
13. 您必须使端口和接收位置可用于通过使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
    1.  右键单击**MySendPort**，然后单击**登记**。  
  
    2.  右键单击**MySendPort**，然后单击**启动**。  
  
    3.  右键单击**MSMQReceiveLocation**，然后单击**启用**。  
  
#### <a name="to-create-the-msmq-queue-in-windows-server"></a>若要在 Windows Server 中创建 MSMQ 队列
  
1.  单击**启动**，右键单击**计算机**，然后单击**管理**。  
  
2.  展开**功能**节点。  
  
3.  展开**消息队列**节点。  
  
4.  右键单击**专用队列**节点中，单击**新建**，然后单击**专用队列**。  
  
5.  下**队列名称**，输入**测试**。 絋粄**事务性**复选框处于选中状态。  
  
6.  单击“确定” 。  
  
#### <a name="to-create-the-msmq-queue-in-windows"></a>若要在 Windows 中创建 MSMQ 队列 
  
1.  单击**启动**，右键单击**计算机**，然后单击**管理**。  
  
2.  展开**服务和应用程序**，然后展开**消息队列**节点。  
  
    > [!NOTE]
    >  如果**消息队列**未安装在计算机中，转到**控制面板 > 程序 > 程序和功能**，然后选择**打开或关闭打开的 Windows 功能**。 检查下的所有功能**Microsoft 消息队列 (MSMQ) 服务器**，然后单击**确定**。  
  
3.  右键单击**专用队列**节点中，单击**新建**，然后单击**专用队列**。  
  
4.  下**队列名称**，输入**测试**。 絋粄**事务性**复选框处于选中状态。  
  
5.  单击“确定” 。  
  
## <a name="creating-a-test-file-and-running-the-sample"></a>创建测试文件和运行示例  
  
#### <a name="to-create-a-large-test-file"></a>若要创建一个大型测试文件  
  
1.  在 Visual Studio 中，打开解决方案**C:\Program Files\Microsoft BizTalk Server\<版本\>\SDK\Samples\AdaptersUsage\MSMQLarge\XMLCreator\XMLCreator.sln**。  
  
2.  生成并运行该项目。  
  
3.  下**XML 正文**，类型**这是测试消息**。  
  
4.  下**数次以复制 XML 正文**，类型`250000`。  
  
5.  下**XML 文件位置**，类型`C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml`。  
  
6.  单击**创建 XML**，然后单击**确定**。  
  
#### <a name="to-run-the-sample"></a>若要运行示例  
  
1.  打开命令提示符，并将目录更改为**C:\Program Files\Microsoft BizTalk Server\<版本\>\SDK\Samples\AdaptersUsage\MSMQLarge\SendLargeMessage\bin\debug**。  
  
2.  在命令提示符处，运行**SendLargeMessage.exe**。 SendLargeMessage 可执行文件接受两个变量，第一个是 MSMQ 队列的位置，第二个是要发送的.xml 文件的位置：  
  
    ```  
    DIRECT=OS:localhost\private$\Test  "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml"  
    ```  
  
3.  验证是否已在 BizTalk Server 计算机上创建大小相同的文件**C:\Demo**目录。 这是在 MySendPort 发送端口中标识的目录中。  
  
## <a name="comments"></a>注释  
 SendLargeMessage.exe 引用**LargeMessages** API，后者又引用 BizTalk 消息队列大消息扩展 (MQRTLarge.dll) API。 消息队列大消息扩展 API 是本地消息队列的外接程序允许处理大于 4 MB 的限制的本机消息队列的消息。  
  
 此示例使用**MQSendLargeMessage** API 并公开 API 到.NET Framework 通过使用**LargeMessages** API。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk 消息队列大消息扩展](../core/biztalk-message-queuing-large-message-extension.md)   
 [适配器示例 - 用法](../core/adapter-samples-usage.md)