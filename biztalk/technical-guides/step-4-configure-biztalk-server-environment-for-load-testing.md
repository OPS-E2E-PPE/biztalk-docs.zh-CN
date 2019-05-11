---
title: 步骤 4：配置 BizTalk Server 环境以进行负载测试 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f336c5f-5a18-493d-8fc0-a8a475ab47b3
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 046c79e5528accea92081415542c5b1aea1b1455
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400674"
---
# <a name="step-4-configure-biztalk-server-environment-for-load-testing"></a>步骤 4：配置 BizTalk Server 环境以进行负载测试
本主题提供有关创建 BizTalk Server 接收位置，接收端口的信息和运行在主题中所述的示例代码所需的发送端口[步骤 1:创建单元测试，以提交到 BizTalk Server 文档](~/technical-guides/step-1-create-a-unit-test-to-submit-documents-to-biztalk-server.md)和[步骤 3:创建负载测试，以同时执行多个单元测试](~/technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)。  

## <a name="configure-biztalk-server-environment-for-load-tests"></a>为负载测试配置 BizTalk Server 环境  
 本主题中所述[步骤 3:创建负载测试对执行多个单元测试同时](~/technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)，在负载测试**BTS_Messaging_Step**配置为执行单元测试**BTSMessaging**和**BTSMessaging2**。 反过来，这些单元测试加载消息 C:\Projects\LoadTest\BTSLoad\TestMessages\TestXmlDocument.xml 的副本并将其发送到终结点**BTSMessagingEP**并**BTSMessagingEP2**中定义项目的应用程序配置 (app.config) 文件的以下部分：  

 \<\!-BTSMessagingEP-\>\<终结点 address="net.tcp://*BizTalk Server 计算机*: 8123/btsloadtest"绑定 ="netTcpBinding"bindingConfiguration ="netTcpBinding"协定 ="System.ServiceModel.Channels.IRequestChannel"名称 ="BTSMessagingEP"/\>\<终结点 address="net.tcp://*BizTalk Server 计算机*: 8123/btsloadtest"绑定 ="netTcpBinding"bindingConfiguration ="netTcpBinding"contract="System.ServiceModel.Channels.IRequestChannel"名称 ="BTSMessagingEP2"/                  \>  

> [!NOTE]
>  如前文所述， *BizTalk Server 计算机*是一个占位符的实际的 BizTalk Server 计算机名，或在情况下，BizTalk Server 计算机都配置为网络负载平衡 (NLB) 群集; 的成员*BizTalk Server 计算机*是占位符的名称或相应的 NLB 虚拟服务器的地址。  

 对于此示例中，使用两台 BizTalk Server 计算机和 BizTalk Server Messagebox 数据库是远程的 SQL Server 计算机上。  

### <a name="create-biztalk-server-send-and-receive-hosts"></a>创建 BizTalk Server 发送和接收主机  
 按照 BizTalk Server 文档主题中的步骤[如何创建新的主机](http://go.microsoft.com/fwlink/?LinkId=208595)(http://go.microsoft.com/fwlink/?LinkId=208595)若要创建的 BizTalk Server"发送"主机的发送端口和发送适配器处理程序。 配置主机具有以下属性：  

|属性|ReplTest1|  
|--------------|-----------|  
|“属性”|TxHost|  
|类型|进程内|  
|允许主机跟踪|确保未选中此框。|  
|受信任的身份验证|确保未选中此框。|  
|仅限 32 位|确保未选中此框。|  
|将此组中的默认主机|确保未选中此框。|  
|Windows 组|用于控制对此主机与关联的主机实例的访问的 Windows 组。 为默认进程内主机为创建的窗口组*\<计算机名\>* \BizTalk 应用程序用户 （适用于单个服务器 BizTalk Server 安装） 或 *\<域名\>* \BizTalk 应用程序用户 （适用于多个服务器需要使用域组的 BizTalk Server 安装）。 **注意：** *\<计算机名\>* 并*\<域名\>* 都是实际的计算机名称或创建组时使用的域名的占位符。 <br /><br /> 如果为此主机创建新的组，则它必须具有本主题中所述的权限[主机组](http://go.microsoft.com/fwlink/?LinkId=208803)(http://go.microsoft.com/fwlink/?LinkId=208803) BizTalk Server 文档中。|  

 重复执行时创建"发送"主机来创建"接收"主机遵循的步骤。 使用以下属性值配置"接收"主机：  

|属性|ReplTest1|  
|--------------|-----------|  
|“属性”|RxHost|  
|类型|进程内|  
|允许主机跟踪|确保未选中此框。|  
|受信任的身份验证|确保未选中此框。|  
|仅限 32 位|确保未选中此框。|  
|将此组中的默认主机|确保未选中此框。|  
|Windows 组|用于控制对此主机与关联的主机实例的访问的 Windows 组。 为默认进程内主机为创建的窗口组*\<计算机名\>* \BizTalk 应用程序用户 （适用于单个服务器 BizTalk Server 安装） 或 *\<域名\>* \BizTalk 应用程序用户 （适用于多个服务器需要使用域组的 BizTalk Server 安装）。 **注意：** *\<计算机名\>* 并*\<域名\>* 都是实际的计算机名称或创建组时使用的域名的占位符。 <br /><br /> 如果为此主机创建新的组，则它必须具有本主题中所述的权限[主机组](http://go.microsoft.com/fwlink/?LinkId=208803)(http://go.microsoft.com/fwlink/?LinkId=208803) BizTalk Server 文档中。|  

### <a name="create-instances-of-the-biztalk-server-send-and-receive-hosts"></a>创建实例的 BizTalk Server 发送和接收主机  
 按照 BizTalk Server 文档主题中的步骤[如何将主机实例添加](http://go.microsoft.com/fwlink/?LinkId=208596)(http://go.microsoft.com/fwlink/?LinkId=208596)创建并启动 BizTalk Server"发送"主机的实例。 配置要在 BizTalk Server 组中每个 BizTalk Server 上运行并配置每个主机实例使用以下属性值的"发送"主机实例：  

|属性|ReplTest1|  
|--------------|-----------|  
|**主机名**|选择**TxHost**下拉列表中下一步**主机名**。|  
|**Server**|选择 BizTalk Server 将运行此主机实例从下拉列表旁边**Server**。|  
|**登录**|1.单击**配置**按钮以显示**登录凭据**对话框。<br />2.在中**登录凭据**对话框中的指定属性中输入以下值：<br />     **属性**<br />     **登录**:是与此 BizTalk Server 主机关联的 Windows 组的成员的用户帐户的名称。<br />     **密码**:中指定的用户帐户的密码**登录**文本框中。<br />3.单击**确定**以关闭**登录凭据**对话框。|  
|**禁用主机实例启动。**|确保未选中此框。|  

 在创建主机实例，右键单击主机实例，然后选择**启动**从上下文菜单。  

 重复创建"发送"主机实例创建"接收"主机实例时所遵循的步骤。 配置要在 BizTalk Server 组中每个 BizTalk Server 上运行并配置每个主机实例使用以下属性值的"接收"主机实例：  

|属性|ReplTest1|  
|--------------|-----------|  
|主机名|选择**RxHost**下拉列表中下一步**主机名**。|  
|“服务器”|选择 BizTalk Server 将运行此主机实例从下拉列表旁边**Server**。|  
|登录|1.单击**配置**按钮以显示**登录凭据**对话框。<br />2.在中**登录凭据**对话框中的指定属性中输入以下值：<br />     **属性**<br />     **登录**:是与此 BizTalk Server 主机关联的 Windows 组的成员的用户帐户的名称。<br />     **密码**:中指定的用户帐户的密码**登录**文本框中。<br />3.单击**确定**以关闭登录凭据对话框。|  
|禁止主机实例启动|确保未选中此框。|  

 在创建主机实例，右键单击主机实例，然后选择**启动**从上下文菜单。  

### <a name="create-a-biztalk-server-receive-port"></a>创建 BizTalk Server 接收端口  
 按照本主题中的步骤[如何创建接收端口](http://go.microsoft.com/fwlink/?LinkID=154843)(http://go.microsoft.com/fwlink/?LinkID=154843)中创建一个单向接收端口的 BizTalk Server 文档。 创建接收端口时，将保留默认值，除非所有属性下, 表中所述：  

|属性|ReplTest1|  
|--------------|-----------|  
|General\Name|BTSLoadTestMessaging.OneWay.ReceivePort|  
|General\Port Type|单向|  
|General\Authentication|无身份验证|  
|失败消息 General\Enable 路由功能|确保未选中此框。|  
|General\Description|将保留为空|  
|入站映射|None|  
|跟踪|确保取消选中所有框。|  
|接收位置|单击**新建**，这将显示**接收位置属性**对话框中，应进行配置，如下面部分中所述**创建 BizTalk Server 接收位置**.|  

### <a name="create-a-biztalk-server-receive-location"></a>创建 BizTalk Server 接收位置  
 在中**接收位置属性**对话框显示创建 BizTalk Server 接收端口时，将应用指定的属性值：  

|属性|ReplTest1|  
|--------------|-----------|  
|名称：|BTSLoadTest.Messaging.OneWay.WCF-Customer.ReceiveLocation|  
|接收处理程序：|RxHost|  
|接收管道：|PassThruReceive|  
|说明:|将此留空|  
|键入：|选择**WCF 自定义**从下拉列表，再单击**配置**按钮，这将显示**Wcf-custom 传输属性**应为对话框下面部分中所述配置**配置 WCF 自定义接收传输**。|  

### <a name="configure-the-wcf-custom-receive-transport"></a>配置 WCF 自定义接收传输  
 在中**Wcf-custom 传输属性**对话框显示创建 BizTalk Server 接收位置时，将所有属性保留为默认值除外下, 表中所述：  

|属性|ReplTest1|  
|--------------|-----------|  
|General\Address (URI)|net.tcp://localhost:8123/btsloadtest|  
|Binding\Binding 类型|netTcpbinding|  
|Binding\NetTcpBindingElement\listenBacklog|400|  
|Binding\NetTcpBindingElement\maxConnections|400|  
|Binding\Security\NetTcpSecurityElement\mode|None|  
|Behavior\ServiceBehavior\serviceThrottling\ServiceThrottlingElement**注意：** 若要将 serviceThrottling 行为添加到的行为，右键单击 ServiceBehavior 列表单击**添加扩展**，选择**serviceThrottling**从列表中的行为扩展，然后单击**确定**。|设置**ServiceThrottlingElement**属性设置为以下值：<br /><br /> -   **maxConcurrentCalls** 400<br />-   **maxConcurrentInstances** 400<br />-   **maxConcurrentSessions** 400|  
|Behavior\ServiceBehavior\serviceDebug\ServiceDebugElement**注意：** 若要将 serviceDebug 行为添加到的行为，右键单击 ServiceBehavior 列表单击**添加扩展**，选择**serviceDebug**从列表中的行为扩展，然后单击**确定**。|保留的列表**ServiceDebugElement**属性的默认值 （空） 的以下属性除外的应更改为值为 True:<br /><br /> -   **httpHelpPageEnabled** True<br />-   **httpsHelpPageEnabled** True<br />-   **includeExceptionDetailInFaults** True|  

 单击**确定**以关闭 Wcf-custom 传输属性对话框中，然后单击**确定**以关闭接收位置属性对话框。  

### <a name="create-a-biztalk-server-send-port"></a>创建 BizTalk Server 发送端口  
 按照本主题中的步骤[如何创建发送端口](http://go.microsoft.com/fwlink/?LinkID=154845)(http://go.microsoft.com/fwlink/?LinkID=154845)中创建的 BizTalk Server 文档**静态单向**发送端口。 创建发送端口时，将保留默认值，除非所有属性下, 表中所述：  

|属性|ReplTest1|  
|--------------|-----------|  
|General\Name|BTSLoadTest.Messaging.Send.WCF-Custom|  
|General\Send 处理程序|TxHost|  
|General\Send 管道|PassThruTransmit|  
|Filters\Name|BTS.ReceivePortName|  
|Filters\Operator|==|  
|Filters\Value|BTSLoadTest.Messaging.OneWay.ReceivePort|  
|通过 Filters\Group|和**注意：** 如果这些属性配置了正确的值，该筛选器应显示为`BTS.ReceivePortName == BTSLoadTest.Messaging.OneWay.ReceivePort`发送端口属性对话框中的筛选器页底部所示。 由于应用此筛选器，此发送端口订阅通过名为 BTSLoadTest.Messaging.OneWay.ReceivePort 的接收端口的 BizTalk Server 接收的任何消息。|  
|跟踪|确保取消选中所有框。|  
|General\Type|选择**WCF 自定义**从下拉列表，再单击**配置**按钮，这将显示**Wcf-custom 传输属性**应为对话框下面部分中所述配置**配置 WCF 自定义发送传输**。|  

### <a name="configure-the-wcf-custom-send-transport"></a>配置 Wcf-custom 发送传输  
 在中**Wcf-custom 传输属性**对话框显示创建 BizTalk Server 发送端口时，将所有属性保留为默认值除外下, 表中所述：  

|属性|ReplTest1|  
|--------------|-----------|  
|General\Address (URI)|net.tcp://*\<计算机名\>*: 2001年/TCP1**重要：***\<计算机名\>* 是用于托管 IndigoService.exe，旨在使用通过 WCF 发送的消息的实际计算机名称的占位符。 由于 IndigoService.exe 需要很少的资源，它通常是完全可以接受的 BizTalk Server 组数据库使用 SQL Server 计算机上运行 IndigoService.exe。 属于 BizTalk 基准向导，可在 IndigoService.exe [BizTalk 基准向导](http://go.microsoft.com/fwlink/?LinkID=186347)(http://go.microsoft.com/fwlink/?LinkID=186347)。|  
|Binding\Binding 类型|**customBinding**|  

 与大多数 WCF 自定义绑定类型一样**customBinding**绑定类型公开多个属性，应设置为以下值：  

1.  下**绑定**部分中没有**CustomBindingElement**带有关联属性**配置**部分。 保留的配置部分中的所有值**CustomBindingElement**属性的默认值。  

2.  然后在**CustomBindingElement**右键单击**textMessageEncoding** ，然后选择**删除扩展 (Del)**。 同样，用鼠标右键单击**httpTransport** ，然后选择**删除扩展 (Del)**。  

3.  现在，右键单击**CustomBindingElement** ，然后选择**添加扩展项**以显示**选择绑定元素扩展**对话框。  

4.  选择**binaryMessageEncoding**然后单击**确定**若要添加**binaryMessageEncoding**元素扩展。 重复步骤以显示**选择绑定元素扩展**对话框并滚动下可用的元素扩展的列表，直到看到**tcpTransport**元素扩展，选择**tcpTransport**然后单击**确定**。  

5.  下**CustomBindingElement**选择**tcpTransport**元素和中的配置节**tcpTransport**，将所有属性保留为默认值为除外下表中所述：  

    |属性|ReplTest1|  
    |--------------|-----------|  
    |connectionBufferSize|2097152|  
    |maxBufferSize|2097152|  
    |maxPendingAccepts|400|  
    |maxPendingConnections|400|  
    |listenBacklog|400|  
    |maxBufferPoolSize|2097152|  
    |maxReceivedMessageSize|2097152|  

6.  下**tcpTransport**元素选择**ConnectionPoolSettings**元素，并保留默认值的所有属性都值除**maxOutboundConnectionsPerEndpoint**应为 400 的值已更改的属性。  

7.  单击**确定**以关闭 Wcf-custom 传输属性对话框中，然后单击**确定**以关闭 BTSLoadTest.Messaging.Send.WCF Custom-发送端口属性对话框。  

### <a name="configure-a-computer-to-consume-messages-sent-by-the-biztalk-server-send-port"></a>将计算机配置为使用由 BizTalk Server 发送端口发送的消息  
 如前文所述，IndigoService.exe 旨在使用通过 WCF 发送的消息。 属于 BizTalk 基准向导，可在 IndigoService.exe [BizTalk 基准向导](http://go.microsoft.com/fwlink/?LinkID=186347)(http://go.microsoft.com/fwlink/?LinkID=186347)。 设置和 IndigoService.exe 运行此示例的最简单方法是只需下载中的 BizTalk 基准向导 zip 文件[BizTalk 基准向导下载页](http://go.microsoft.com/fwlink/?LinkID=209100)(http://go.microsoft.com/fwlink/?LinkID=209100)并提取以下 4到你想要运行 IndigoService.exe 的计算机上的文件：  

1. \IndigoService\bin\Release\IndigoService.exe  

2. \IndigoService\bin\Release\IndigoService.exe.config  

3. \IndigoService\bin\Release\Response.xml  

4. \IndigoService\bin\Release\StartIndigoService.bat  

   然后，通过双击 StartIndigoService.bat 启动 IndigoService.exe。 IndigoService.exe 使用的消息发送到 IndigoService.exe.config 文件中指定的终结点：  

   \<终结点地址 ="net.tcp: //localhost: 2001年/TCP1"绑定 ="netTcpBinding"bindingConfiguration ="Binding1"名称 ="endpoint1"contract="IndigoService.IServiceTwoWaysVoidNonTransactional"/\>  

   这就是原因发送端口地址配置与一个地址 (URI) 的 net.tcp://*\<计算机名\>*: 2001年/TCP1  

   由于 IndigoService.exe 需要很少的资源，它通常是完全可以接受的 BizTalk Server 数据库使用 SQL Server 计算机上运行 IndigoService.exe。  

### <a name="disable-tracking-and-throttling-for-the-biztalk-server-group"></a>禁用跟踪和 BizTalk Server 组的限制  
 若要确定系统，这两个消息的绝对最大可承受吞吐量跟踪和阻止功能之前，应该禁用从负载测试。 这可以通过执行以下步骤使用在 BizTalk Server 管理控制台：  

1. 启动 BizTalk Server 管理控制台。 单击**启动**，依次指向**所有程序**，指向**BizTalk Server 2010** ，然后单击**BizTalk Server 管理**。  

2. 下**BizTalk Server 管理**中，选择你的 BizTalk 组，如果它列出或如果未列出，请右键单击**BizTalk Server 管理**，选择**连接到现有组**，输入旁边存储 BizTalk 组的 BizTalk Server 管理数据库的 SQL Server 名称**SQL Server 名称：**，输入名称为 BizTalk 组的管理数据库名称旁边**数据库名称：** ，然后单击**确定**。  

3. 右键单击 BizTalk 组节点并选择**设置**以显示**BizTalk 设置仪表板**。  

4. 单击此项可选择**主机**BizTalk 设置仪表板的左侧窗格中。  

5. 单击下拉列表旁边**主机**选择一个将性能测试期间使用的主机。  

6. 保留属性的默认值除下表中所述：  


   |                          属性                          |               ReplTest1                |
   |------------------------------------------------------------|------------------------------------|
   |          **General\Move 到 DTA 数据库跟踪数据**          | 如果对其进行检查，请取消选中此框。 |
   |                  **仅限 General\32 位**                   | 如果对其进行检查，请取消选中此框。 |
   |          **General\Polling Intervals\Messaging**           |     设置为 20000000 值     |
   |        **General\Polling Intervals\Orchestrations**        |     设置为 20000000 值     |
   |     **基于资源的 Throttling\In 处理消息**      |      设置为值为 10000       |
   | **基于资源的 Throttling\Internal 消息队列大小**  |      设置为值为 10000       |
   |     **在 DB 中的基于资源的 Throttling\Message 计数**      |        设置为 0 的值         |
   | **虚拟的基于资源的 Throttling\Memory Usage\Process** |        设置为 0 的值         |
   |  **基于速率的 Throttling\Publishing\Throttling 重写**  |       设置为不阻止       |
   |   **基于速率的 Throttling\Delivery\Throttling 重写**   |       设置为不阻止       |


7. 重复步骤 6 中所述过程的性能测试过程中将使用每个主机的过程。  

8. 单击此项可选择**主机实例**BizTalk 设置仪表板的左侧窗格中。  

9. 单击下拉列表旁边**主机实例：** 来选择一种用于性能测试的主机实例。  

10. 将属性值保留为其默认设置，除了更改 **.NET CLR 最大工作线程**为值**100**并更改 **.NET CLR 最小工作线程**到值**25**。  

11. 重复步骤 10 的每个主机实例将使用的性能测试过程中所述的过程。  

    即使禁用跟踪和带宽限制确实不以任何方式表示应如何处理在生产方案中，因为这些操作是从性能角度看，最好禁用它们以找出 true 最大可承受如此昂贵BizTalk Server 环境的吞吐量 (MST)。 这样，测试人员能够清楚地看到的调整的任何性能影响应用到环境。 当然不应禁用跟踪，如果你从一开始就知道在 BizTalk Server 应用程序将需要跟踪然后应启用跟踪，则无法进行自变量。 话虽如此，**应将每项工作可以禁用阻止功能的性能测试**。 限制会阻止 BizTalk Server"侵扰"因负载过大，在生产环境中非常有用。 但是，您不希望限制在性能测试，因为它将极大地影响系统性能，因为如果负载测试期间限制中的时，将启动然后将具有很难确定何种级别的性能的过程中启用你BizTalk Server 应用程序可以实际实现。 下一步的主题介绍如何执行负载测试来推送你的 BizTalk Server 环境超出 MST 并缩放回实际 MST 常量负载测试步骤。 如果启用限制然后它将成为几乎无法推送，以便您又无法发现的真正所 MST 是 BizTalk 环境超出 MST。