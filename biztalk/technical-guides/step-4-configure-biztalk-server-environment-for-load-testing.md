---
title: 步骤 4： 配置用于负载测试的 BizTalk Server 环境 |Microsoft 文档
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
ms.openlocfilehash: cf2e8b2b3751f31401ef0353944be0bdad3cbb2b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976803"
---
# <a name="step-4-configure-biztalk-server-environment-for-load-testing"></a>步骤 4： 配置用于负载测试的 BizTalk Server 环境
本主题提供有关创建 BizTalk Server 接收位置，接收端口的信息和运行主题所述的示例代码所需的发送端口[步骤 1： 创建单元测试以提交给 BizTalk Server 的文档进行](~/technical-guides/step-1-create-a-unit-test-to-submit-documents-to-biztalk-server.md)和[步骤 3： 创建负载测试，以同时执行多个单元测试](~/technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)。  
  
## <a name="configure-biztalk-server-environment-for-load-tests"></a>为负载测试配置 BizTalk Server 环境  
 本主题中所述[步骤 3： 创建负载测试对执行多个单元测试同时](~/technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)，负载测试**BTS_Messaging_Step**配置为执行单元测试**BTSMessaging**和**BTSMessaging2**。 反过来，这些单元测试加载消息 C:\Projects\LoadTest\BTSLoad\TestMessages\TestXmlDocument.xml 的副本，并将其发送到终结点**BTSMessagingEP**和**BTSMessagingEP2**中定义项目的应用程序配置 (app.config) 文件的以下部分：  
  
 \<\!-BTSMessagingEP-\>\<终结点 address="net.tcp://*BizTalk 服务器计算机*: 8123/btsloadtest"绑定 ="netTcpBinding"bindingConfiguration ="netTcpBinding"协定 ="System.ServiceModel.Channels.IRequestChannel"名称 ="BTSMessagingEP"/\>\<终结点 address="net.tcp://*BizTalk 服务器计算机*: 8123/btsloadtest"绑定 ="netTcpBinding"bindingConfiguration ="netTcpBinding"contract="System.ServiceModel.Channels.IRequestChannel"名称 ="BTSMessagingEP2"/                  \>  
  
> [!NOTE]
>  如前文所述， *BizTalk 服务器计算机*是一个占位符的实际的 BizTalk Server 计算机名，或在情况下，将 BizTalk Server 计算机配置为网络负载平衡 (NLB) 群集; 的成员*BizTalk 服务器计算机*是的名称或地址的相应的 NLB 虚拟服务器的占位符。  
  
 此示例的目的，使用两台 BizTalk Server 计算机和 BizTalk Server 消息框数据库在远程 SQL Server 计算机上已被。  
  
### <a name="create-biztalk-server-send-and-receive-hosts"></a>创建 BizTalk Server 发送和接收主机  
 请按照 BizTalk Server 文档主题中的步骤[如何创建新的主机](http://go.microsoft.com/fwlink/?LinkId=208595)(http://go.microsoft.com/fwlink/?LinkId=208595) 创建 BizTalk Server"发送"主机发送端口和发送适配器处理程序。 配置主机具有以下属性：  
  
|属性|值|  
|--------------|-----------|  
|Name|TxHost|  
|类型|进程内|  
|允许主机跟踪|确保未选中此框。|  
|受信任验证|确保未选中此框。|  
|仅限 32 位|确保未选中此框。|  
|将其用作组中的默认主机|确保未选中此框。|  
|Windows 组|用于控制对此主机与关联的主机实例的访问的 Windows 组。 为默认进程内主机为创建的窗口组*\<计算机名称\>* \BizTalk 应用程序用户 （适用于单个服务器 BizTalk Server 安装） 或 *\<域名\>* \BizTalk 应用程序用户 （适用于多个服务器需要域组使用的 BizTalk Server 安装）。 **注意：***\<计算机名称\>* 和*\<域名\>* 占位符的实际计算机名或域名创建组时使用。   <br /><br /> 如果为该主机中创建新组，则它必须具有本主题所述的特权[主机组](http://go.microsoft.com/fwlink/?LinkId=208803)(http://go.microsoft.com/fwlink/?LinkId=208803) BizTalk Server 文档中。|  
  
 重复执行您遵循创建用来创建"接收"宿主"发送"主机时的步骤。 使用以下属性值配置"接收"主机：  
  
|属性|值|  
|--------------|-----------|  
|Name|RxHost|  
|类型|进程内|  
|允许主机跟踪|确保未选中此框。|  
|受信任验证|确保未选中此框。|  
|仅限 32 位|确保未选中此框。|  
|将其用作组中的默认主机|确保未选中此框。|  
|Windows 组|用于控制对此主机与关联的主机实例的访问的 Windows 组。 为默认进程内主机为创建的窗口组*\<计算机名称\>* \BizTalk 应用程序用户 （适用于单个服务器 BizTalk Server 安装） 或 *\<域名\>* \BizTalk 应用程序用户 （适用于多个服务器需要域组使用的 BizTalk Server 安装）。 **注意：***\<计算机名称\>* 和*\<域名\>* 占位符的实际计算机名或域名创建组时使用。   <br /><br /> 如果为该主机中创建新组，则它必须具有本主题所述的特权[主机组](http://go.microsoft.com/fwlink/?LinkId=208803)(http://go.microsoft.com/fwlink/?LinkId=208803) BizTalk Server 文档中。|  
  
### <a name="create-instances-of-the-biztalk-server-send-and-receive-hosts"></a>创建 BizTalk Server 发送的实例，并接收主机  
 请按照 BizTalk Server 文档主题中的步骤[如何添加一个主机实例](http://go.microsoft.com/fwlink/?LinkId=208596)(http://go.microsoft.com/fwlink/?LinkId=208596) 创建并启动 BizTalk Server"发送"主机的实例。 配置要在 BizTalk Server 组中每个 BizTalk 服务器上运行并将每个主机实例配置为带有以下属性值的"发送"主机的实例：  
  
|属性|值|  
|--------------|-----------|  
|**主机名**|选择**TxHost**下拉列表中下一步**主机名**。|  
|**Server**|选择将运行此主机实例中的下拉列表旁边的 BizTalk 服务器**服务器**。|  
|**登录**|1.单击**配置**按钮以显示**登录凭据**对话框。<br />2.在**登录凭据**对话框中指定的属性中输入以下值：<br />     **属性**<br />     **登录**： 是与此 BizTalk Server 主机关联的 Windows 组的成员的用户帐户名称。<br />     **密码**： 中指定的用户帐户的密码**登录**文本框。<br />3.单击**确定**关闭**登录凭据**对话框。|  
|**禁用主机启动的实例。**|确保未选中此框。|  
  
 创建主机实例之后, 的主机实例上右键单击并选择**启动**从上下文菜单。  
  
 重复执行在创建要创建"接收"主机实例的"发送"主机实例时遵循的步骤。 配置"接收"主机在 BizTalk Server 组中每个 BizTalk Server 上运行并将每个主机实例配置为带有以下属性值的实例：  
  
|属性|值|  
|--------------|-----------|  
|主机名|选择**RxHost**下拉列表中下一步**主机名**。|  
|Server|选择将运行此主机实例中的下拉列表旁边的 BizTalk 服务器**服务器**。|  
|登录|1.单击**配置**按钮以显示**登录凭据**对话框。<br />2.在**登录凭据**对话框中指定的属性中输入以下值：<br />     **属性**<br />     **登录**： 是与此 BizTalk Server 主机关联的 Windows 组的成员的用户帐户名称。<br />     **密码**： 中指定的用户帐户的密码**登录**文本框。<br />3.单击**确定**以关闭登录凭据对话框。|  
|禁止主机实例启动|确保未选中此框。|  
  
 创建主机实例之后, 的主机实例上右键单击并选择**启动**从上下文菜单。  
  
### <a name="create-a-biztalk-server-receive-port"></a>创建 BizTalk Server 接收端口  
 按照本主题中的步骤[如何创建接收端口](http://go.microsoft.com/fwlink/?LinkID=154843)(http://go.microsoft.com/fwlink/?LinkID=154843) BizTalk Server 文档，以创建单向接收端口中。 在创建时接收端口，将保留为默认值除外的所有属性下, 表中所述：  
  
|属性|值|  
|--------------|-----------|  
|General\Name|BTSLoadTestMessaging.OneWay.ReceivePort|  
|General\Port 类型|单向|  
|General\Authentication|不进行身份验证|  
|General\Enable 路由失败消息|确保未选中此框。|  
|General\Description|将保留为空|  
|入站映射|无|  
|跟踪|请确保所有框未选中。|  
|接收位置|单击**新建**，这将显示**接收位置属性**对话框中下一节中所述，应将其配置**创建 BizTalk 服务器接收位置**.|  
  
### <a name="create-a-biztalk-server-receive-location"></a>创建 BizTalk Server 接收位置  
 在**接收位置属性**对话框中显示创建 BizTalk Server 接收端口时，应用的指定的属性值：  
  
|属性|值|  
|--------------|-----------|  
|名称：|BTSLoadTest.Messaging.OneWay.WCF Customer.ReceiveLocation|  
|接收处理程序：|RxHost|  
|接收管道：|PassThruReceive|  
|说明:|将其留空|  
|类型：|选择**WCF 自定义**从下拉列表，然后单击**配置**按钮，这将显示**WCF 自定义传输属性**对话框中，它应该是配置中下一节所述**配置 WCF 自定义接收传输**。|  
  
### <a name="configure-the-wcf-custom-receive-transport"></a>配置 WCF 自定义接收传输  
 在**WCF 自定义传输属性**对话框中显示创建 BizTalk Server 接收位置时，将所有属性都保留为默认值除外下, 表中所述：  
  
|属性|值|  
|--------------|-----------|  
|General\Address (URI)|net.tcp: //localhost: 8123/btsloadtest|  
|Binding\Binding 类型|netTcpbinding|  
|Binding\NetTcpBindingElement\listenBacklog|400|  
|Binding\NetTcpBindingElement\maxConnections|400|  
|Binding\Security\NetTcpSecurityElement\mode|无|  
|Behavior\ServiceBehavior\serviceThrottling\ServiceThrottlingElement**注意：** 将 serviceThrottling 行为添加到的行为，右键单击 ServiceBehavior 列表单击**添加扩展**，选择**serviceThrottling**从列表中的行为扩展，然后单击**确定**。|设置**ServiceThrottlingElement**为以下值的属性：<br /><br /> -   **maxConcurrentCalls** 400<br />-   **maxConcurrentInstances** 400<br />-   **maxConcurrentSessions** 400|  
|Behavior\ServiceBehavior\serviceDebug\ServiceDebugElement**注意：** 将 serviceDebug 行为添加到的行为，右键单击 ServiceBehavior 列表单击**添加扩展**，选择**serviceDebug**从列表中的行为扩展，然后单击**确定**。|保留的列表**ServiceDebugElement**其默认值 （空） 除外的以下属性，其中应更改为 True 的值的属性：<br /><br /> -   **httpHelpPageEnabled** True<br />-   **httpsHelpPageEnabled** True<br />-   **includeExceptionDetailInFaults** True|  
  
 单击**确定**若要关闭 WCF 自定义传输属性对话框中，然后单击**确定**以关闭接收位置属性对话框。  
  
### <a name="create-a-biztalk-server-send-port"></a>创建 BizTalk Server 发送端口  
 按照本主题中的步骤[如何创建发送端口](http://go.microsoft.com/fwlink/?LinkID=154845)(http://go.microsoft.com/fwlink/?LinkID=154845) 在 BizTalk Server 文档中用于创建**静态单向**发送端口。 在创建时发送端口，将保留为默认值除外的所有属性下, 表中所述：  
  
|属性|值|  
|--------------|-----------|  
|General\Name|BTSLoadTest.Messaging.Send.WCF 自定义|  
|General\Send 处理程序|TxHost|  
|General\Send 管道|PassThruTransmit|  
|Filters\Name|BTS.ReceivePortName|  
|Filters\Operator|==|  
|Filters\Value|BTSLoadTest.Messaging.OneWay.ReceivePort|  
|通过 Filters\Group|和**注意：** 这些属性配置为包含正确的值，如果筛选器应显示为`BTS.ReceivePortName == BTSLoadTest.Messaging.OneWay.ReceivePort`b 中的发送端口属性对话框的筛选器页的底部所示ox。 由于应用此筛选器，此发送端口订阅接收 BizTalk Server 通过名为 BTSLoadTest.Messaging.OneWay.ReceivePort 的接收端口的任何消息。|  
|跟踪|请确保所有框未选中。|  
|General\Type|选择**WCF 自定义**从下拉列表，然后单击**配置**按钮，这将显示**WCF 自定义传输属性**对话框中，它应该是配置中下一节所述**配置 WCF 自定义发送传输**。|  
  
### <a name="configure-the-wcf-custom-send-transport"></a>配置 WCF 自定义发送传输  
 在**WCF 自定义传输属性**对话框中显示创建 BizTalk Server 发送端口时，将所有属性都保留为默认值除外下, 表中所述：  
  
|属性|值|  
|--------------|-----------|  
|General\Address (URI)|net.tcp://*\<计算机名称\>*: 2001年/TCP1**重要说明：***\<计算机名称\>* 是一个占位符对于用于承载 IndigoService.exe 的实际计算机名称，该方法旨在使用通过 WCF 发送的消息。   由于 IndigoService.exe 需要很少的资源，它通常是完全可以接受用于 BizTalk Server 组数据库的 SQL Server 计算机上运行 IndigoService.exe。 IndigoService.exe 属于 BizTalk 基准向导中，位于[BizTalk 基准向导](http://go.microsoft.com/fwlink/?LinkID=186347)(http://go.microsoft.com/fwlink/?LinkID=186347)。|  
|Binding\Binding 类型|**customBinding**|  
  
 与大多数 WCF 自定义绑定类型**customBinding**绑定类型公开多个属性，应设置为以下值：  
  
1.  下**绑定**部分没有**CustomBindingElement**具有一个关联属性**配置**部分。 保留的所有值的配置部分中**CustomBindingElement**其默认值的属性。  
  
2.  然后在**CustomBindingElement**右键单击**textMessageEncoding**和选择**删除扩展 (Del)**。 同样，右键单击**httpTransport**和选择**删除扩展 (Del)**。  
  
3.  现在，右键单击**CustomBindingElement**和选择**添加扩展单元**以显示**选择绑定元素扩展**对话框。  
  
4.  选择**binaryMessageEncoding**单击**确定**添加**binaryMessageEncoding**元素扩展。 重复步骤，以显示**选择绑定元素扩展**对话框框和滚动下级可用元素扩展的列表，直到你看到**tcpTransport**元素扩展，请选择**tcpTransport**单击**确定**。  
  
5.  下**CustomBindingElement**选择**tcpTransport**元素和中的配置节**tcpTransport**，将所有属性都保留为默认值为除外下表所示：  
  
    |属性|值|  
    |--------------|-----------|  
    |connectionBufferSize|2097152|  
    |maxBufferSize|2097152|  
    |maxPendingAccepts|400|  
    |maxPendingConnections|400|  
    |listenBacklog|400|  
    |maxBufferPoolSize|2097152|  
    |maxReceivedMessageSize|2097152|  
  
6.  下**tcpTransport**元素选择**ConnectionPoolSettings**元素，并保留在默认的所有属性都值除外**maxOutboundConnectionsPerEndpoint**属性，应更改为 400 的值。  
  
7.  单击**确定**若要关闭 WCF 自定义传输属性对话框中，然后单击**确定**以关闭 BTSLoadTest.Messaging.Send.WCF Custom-发送端口属性对话框。  
  
### <a name="configure-a-computer-to-consume-messages-sent-by-the-biztalk-server-send-port"></a>将计算机配置为使用由 BizTalk Server 发送端口发送消息  
 如前面所述，IndigoService.exe 旨在使用通过 WCF 发送的消息。 IndigoService.exe 属于 BizTalk 基准向导中，位于[BizTalk 基准向导](http://go.microsoft.com/fwlink/?LinkID=186347)(http://go.microsoft.com/fwlink/?LinkID=186347)。 设置和运行此示例的目的 IndigoService.exe 的最简单方法是只需下载中的 BizTalk 基准向导 zip 文件[BizTalk 基准向导下载页](http://go.microsoft.com/fwlink/?LinkID=209100)(http://go.microsoft.com/fwlink/?LinkID = 209100) 和提取到你想要运行 IndigoService.exe 的计算机上以下 4 个文件：  
  
1.  \IndigoService\bin\Release\IndigoService.exe  
  
2.  \IndigoService\bin\Release\IndigoService.exe.config  
  
3.  \IndigoService\bin\Release\Response.xml  
  
4.  \IndigoService\bin\Release\StartIndigoService.bat  
  
 然后，通过双击 StartIndigoService.bat 启动 IndigoService.exe。 IndigoService.exe 使用消息发送到 IndigoService.exe.config 文件中指定的终结点：  
  
 \<终结点地址 ="net.tcp: //localhost: 2001年/TCP1"绑定 ="netTcpBinding"bindingConfiguration ="Binding1"名称 ="endpoint1"contract="IndigoService.IServiceTwoWaysVoidNonTransactional"/\>  
  
 这就是为什么发送端口地址配置与地址 (URI) 的 net.tcp://*\<计算机名称\>*: 2001年/TCP1  
  
 由于 IndigoService.exe 需要很少的资源，它通常是完全可以接受用于 BizTalk Server 数据库的 SQL Server 计算机上运行 IndigoService.exe。  
  
### <a name="disable-tracking-and-throttling-for-the-biztalk-server-group"></a>禁用跟踪和限制用于 BizTalk Server 组  
 若要确定系统，这两个消息的绝对最大可持续吞吐量跟踪和带宽限制之前，应禁用开始负载测试。 这可以通过执行以下步骤中使用 BizTalk Server 管理控制台：  
  
1.  启动 BizTalk Server 管理控制台。 单击**启动**，指向**所有程序**，指向**BizTalk Server 2010** ，然后单击**BizTalk Server 管理**。  
  
2.  下**BizTalk Server 管理**、 选择你的 BizTalk 组，如果它列出或如果未列出，请右键单击**BizTalk Server 管理**，选择**连接到现有组**，输入旁边保存 BizTalk 组的 BizTalk Server 管理数据库的 SQL Server 名称**SQL Server 名称：**，输入的 BizTalk 组的管理数据库名称旁边**数据库名称：** ，然后单击**确定**。  
  
3.  右键单击 BizTalk 组节点并选择**设置**以显示**BizTalk 设置仪表板**。  
  
4.  单击以选择**主机**BizTalk 设置仪表板的左侧窗格中。  
  
5.  单击下拉列表中下一步**主机**选择其中一种将性能测试期间使用的主机。  
  
6.  将属性保留为其默认值除外下, 表中所述：  
  
    |属性|值|  
    |--------------|-----------|  
    |**General\Move 到 DTA DB 跟踪数据**|如果对其进行检查，取消选中此框。|  
    |**仅 General\32 位**|如果对其进行检查，取消选中此框。|  
    |**General\Polling Intervals\Messaging**|设置为 20000000 的值|  
    |**General\Polling Intervals\Orchestrations**|设置为 20000000 的值|  
    |**基于资源的 Throttling\In 处理消息**|设置为 10000 的值|  
    |**基于资源的 Throttling\Internal 消息队列大小**|设置为 10000 的值|  
    |**在数据库中的基于资源的 Throttling\Message 计数**|设置为 0 的值|  
    |**虚拟的基于资源的 Throttling\Memory Usage\Process**|设置为 0 的值|  
    |**速率基于 Throttling\Publishing\Throttling 替代**|设置为不限制|  
    |**速率基于 Throttling\Delivery\Throttling 替代**|设置为不限制|  
  
7.  重复步骤 6 中所述过程的性能测试过程中将使用每个主机的过程。  
  
8.  单击以选择**主机实例**BizTalk 设置仪表板的左侧窗格中。  
  
9. 单击下拉列表中下一步**主机实例：** 若要选择将用于性能测试的主机实例之一。  
  
10. 将属性值保留为其默认设置，除了更改 **.NET CLR 最大工作线程**为值**100**和更改 **.NET CLR 最小工作线程**到值**25**。  
  
11. 重复此过程的性能测试过程中将使用每个主机实例的步骤 10 中所述的过程。  
  
 即使禁用跟踪和带宽限制确实不以任何方式表示应如何在生产方案中，因为这些操作可从性能角度最好先禁用它们以找出 true 最大可持续如此昂贵BizTalk Server 环境的吞吐量 (MST)。 这允许测试人员清楚地看出调整的任何性能的影响已应用到环境。 当然，不应禁用跟踪，如果你从一开始就知道你的 BizTalk Server 应用程序将需要跟踪然后应启用跟踪，则无法进行自变量。 话虽如此，**应尽量将以禁用限制为进行性能测试**。 限制将阻止 BizTalk Server 发生从"故障"因负载过大，在生产环境中非常有用。 但是，你不希望限制启用性能测试，因为它将占用大量资源从性能角度来看，并且如果负载测试期间限制中的启动，则必须确定何种级别的性能很难时间期间你BizTalk Server 应用程序真的能实现。 下一步的主题介绍如何执行步骤负载测试，以便推送你的 BizTalk Server 环境超出 MST，然后规模缩减至实际 MST 使用常量负载测试。 如果启用限制然后它将变得几乎不可能推送超出 MST BizTalk 环境，以便你可能会反过来发现哪些 MST 是 true。