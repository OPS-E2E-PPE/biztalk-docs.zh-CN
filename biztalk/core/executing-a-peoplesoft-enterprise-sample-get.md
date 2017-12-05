---
title: "执行 PeopleSoft 企业示例 Get |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb54f14c-3fce-44d6-91bb-cb1ca38a20da
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29cf6bba03e6a43bb3fdedf0742741e48ac22dd6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="execute-a-peoplesoft-enterprise-sample-get"></a>执行 PeopleSoft 企业示例 Get
使用 PeopleSoft 适配器可以从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统访问 PeopleSoft 系统。 此适配器是附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。
  
 这是 PeopleSoft 实验室工作的第二部分。 在第一部分（实验室 1）中，您在未使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 协助或其他 Microsoft 技术的情况下，手动访问并修改了 PeopleSoft 系统上的数据。 在本部分（实验室 2）中，你将创建一个 BizTalk 业务流程作为 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk 项目的一部分。 您需要针对此业务流程配置端口，以便使用 PeopleSoft 适配器获取 PeopleSoft 系统中的数据。  
  
## <a name="prerequisites"></a>先决条件  
  
-   Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]
  
-   Microsoft BizTalk Adapters for Enterprise Applications  
  
-   Microsoft Visual Studio  
  
-   Sun Systems Java Development Kit (JDK) 版本 1.4 或更高版本  
  
> [!NOTE]
>  请参阅[安装和配置企业应用程序的适配器](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)博士 Edwards、 PeopleSoft 和 TIBCO 适配器的密钥配置信息。  
  
## <a name="lab-2---executing-a-peoplesoft-sample-get"></a>实验室 2 - 执行 PeopleSoft Get 示例  
 在此实验室中，您将针对 PeopleSoft 系统执行 **Get** 操作。 具体将执行以下任务：  
  
-   验证 PeopleSoft 必备组件  
  
-   在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中设置一个 PeopleSoft 发送端口  
  
-   创建一个 BizTalk 业务流程项目  
  
-   生成并部署项目  
  
-   测试应用程序并查看 XML 输出  
  
## <a name="procedures-for-lab-2--executing-a-peoplesoft-sample-get"></a>实验室 2 的过程 - 执行 PeopleSoft Get 示例  
 必须使用以下两个文件，才能对 PeopleSoft 系统的接口进行正确访问：PSJOA.JAR 和 GET_CI_INFO.PC。 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上，PeopleSoft 适配器通过使用 PeopleSoft Java 接口与 PeopleSoft 系统进行通信。 此接口由 PSJOA.JAR 文件提供。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上存放的此文件的副本通常来自正在访问的 PeopleSoft 服务器系统的管理员。 在此实验室中，PSJOA.JAR 的副本位于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上的 C:\PSJars\Ver841\ 文件夹中。 PeopleSoft 适配器配置属性中指定了此文件的位置。  
  
 PeopleSoft 系统本身必须安装自定义组件接口 (CI)。 这将允许适配器在适配器配置过程中浏览 PeopleSoft 对象。 将（从“添加生成的项”步骤）调用自定义组件接口，以获取可访问的 PeopleSoft 对象的列表。 这些对象确定可用于客户端系统的公开的 PeopleSoft 功能。  
  
 特别是在初始安装过程中，PeopleSoft 系统上必须安装自定义组件 GET_CI_INFO。 可对此文件进行修改，以限制 GET_CI_INFO 公开的内容（默认情况下，公开 PeopleSoft 系统中的所有组件接口）。 此文件源位于以下默认位置的 GET_CI_INFO.PC 文本文件中：  
  
 **C:\Program Files\Microsoft BizTalk 适配器 Enterprise Applications\PeopleSoft Enterprise(r) \Config**  
  
 中提供了有关安装到 PeopleSoft GET_CI_INFO 组件接口的一般说明[安装和配置企业应用程序的适配器](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)。 这些说明面向经验丰富的 PeopleSoft 管理员。  
  
## <a name="step-1-confirm-the-peoplesoft-rerequisites"></a>步骤 1： 确认 PeopleSoft rerequisites  
 开始创建与 PeopleSoft 适配器配合使用的 BizTalk 项目之前，需要确保为访问 PeopleSoft 正确安装了所有必备组件。  
  
1.  确认 PSJOA。JAR 文件位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]C:\psjars\ver841 文件夹中的计算机。 （此文件可能位于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上的其他位置。 在以下给定的配置中，假设该文件位于此位置。）  
  
2.  确认 get_ci_info.pc 文件位于 Enterprise Applications\PeopleSoft Enterprise(r) \Config 文件夹 C:\Program Files\Microsoft BizTalk 适配器。  
  
3.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**控制台根节点**，展开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。 确保安装了 PeopleSoft 适配器，且该适配器位于列表中。  
  
     如果未安装 PeopleSoft 适配器，请安装企业应用程序的 BizTalk 适配器（请参阅前面的“必备组件”部分）。 安装适配器之后，右键单击“适配器”  ，然后单击“新建 - 适配器”  以安装 PeopleSoft 适配器。 重新启动主机实例，这才会生效。  
  
## <a name="step-2-create-a-send-port-for-peoplesoft"></a>步骤 2： 为 PeopleSoft 创建发送端口  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 需要具有发送端口以便用于与 PeopleSoft 系统通信。 此发送端口将最终绑定到业务流程的逻辑端口。  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk.EnterpriseApplication。**  
  
2.  右键单击“发送端口” ，单击“新建” ，然后选择“静态要求响应发送端口” 。 在“发送端口属性”  对话框中，输入以下属性值：  
  
    1.  **名称：**  `PeopleSoftSamplePort`  
  
    2.  **类型：**  `PeopleSoft`  
  
    3.  **发送处理程序：**  `BizTalkServerApplication`  
  
    4.  **发送管道：**  `XMLTransmit`  
  
    5.  **接收管道：**  `XMLReceive`  
  
3.  单击“配置” ，然后输入以下属性值：  
  
    1.  **应用程序服务器路径**： **//Servername:9000**  
  
         Servername 是您的应用程序服务器。 这是特定服务器名称或 IP 地址以及此 PeopleSoft 系统的端口号。  
  
    2.  **JAVA_HOME**： **C:\J2SDK1.4.2_08**  
  
         此路径特定于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上的 Java SDK 安装。  
  
    3.  **密码**:\<输入 PeopleSoft 密码\>  
  
    4.  **PeopleSoft 8.x JAR 文件**： **C:\PSJARS\VER841\PSJOA.JAR**  
  
    5.  **用户名：** \<输入 PeopleSoft 用户 Id\>  
  
     ![](../core/media/7bf30707-c7c6-409f-af18-9c9dfeb0de58.gif "7bf30707-c7c6-409f-af18-9c9dfeb0de58")  
  
4.  单击“确定”  两次以关闭对话框。  
  
## <a name="step-3-create-a-biztalk-orchestration-project"></a>步骤 3： 创建 BizTalk 业务流程项目  
 现在，您将在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中创建 BizTalk 项目，并配置该项目中的业务流程，以处理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与 PeopleSoft 系统之间的通信。 你将添加发送端口和接收端口，生成项目，然后部署项目。  
  
1.  打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在 C:\LABS 文件夹中创建新的 BizTalk 项目。 在“文件”  菜单上，单击“新建” 。 此时将显示“新建项目”  对话框。 在“发送端口属性”  选择“空的 BizTalk Server 项目”。  输入`PS_Test`作为唯一项目名称，然后单击**确定**。  
  
2.  在解决方案资源管理器中，右键单击该项目，单击“添加” ，然后单击“添加生成的项” 。 在“类别”  窗格中选择“添加适配器元数据”  ，在“模板”  侧选择“添加适配器元数据”  ，然后单击“添加” 。  
  
3.  在添加适配器向导中，选择“PeopleSoft Enterprise”适配器  ，选择在前面的过程中创建的“PeopleSoftSamplePort”  发送端口，然后单击“下一步” 。  
  
     ![](../core/media/ed0dedc5-a8fb-444c-b884-e310cf56462c.gif "ed0dedc5-a8fb-444c-b884-e310cf56462c")  
  
4.  在“选择要导入的服务”页上，  展开“PeopleSoft” ，然后展开“CI” 。  
  
     适配器使用浏览代理对 PeopleSoft 系统进行询问。 展开“CI” 时，BrowsingAgent.exe 进程启动（进程运行时，您可以在任务管理器中查看），并返回下图中显示的服务。  
  
     ![](../core/media/6988104c-6483-4df2-a637-3301628ea665.gif "6988104c-6483-4df2-a637-3301628ea665")  
  
    > [!NOTE]
    >  从您的 PeopleSoft 系统获得和显示的 PeopleSoft 服务可能与此处显示的服务稍有不同。  
  
5.  向下滚动，选择“LOCATION” ，然后单击“完成” 。  
  
     ![](../core/media/0506affd-3caa-47cb-9c25-f49c8a0ad614.gif "0506affd-3caa-47cb-9c25-f49c8a0ad614")  
  
6.  在解决方案资源管理器中，出现一个新的 BizTalk 业务流程和两个新的相关架构文件。 这些文件由添加适配器向导创建。 双击“BizTalk Orchestration.odx”文件以打开业务流程。   
  
     ![](../core/media/825c5690-78eb-4048-9a47-cd3fc7310b7b.gif "825c5690-78eb-4048-9a47-cd3fc7310b7b")  
  
 此业务流程接受已为 PeopleSoft **Get** 方法设置格式的 XML 文件作为输入，并将该 XML 文件发送到 PeopleSoft 系统。 **Get** 方法从 PeopleSoft 系统检索位置信息并将其返回到 BizTalk 业务流程。 业务流程使用端口帮助与适配器和 PeopleSoft 系统进行此类通信。 您将在此处配置的端口用于接收和发送 XML 文件。 传出 XML 文件告知 PeopleSoft 系统这是 **Get** 操作。 传入 XML 文件将位置信息返回到业务流程。  
  
 要完成业务流程，你需要创建并配置用于接收和发送 XML 文件的端口。 首先，设置一个新的接收端口，以便接受包含 **Get** 方法的初始 XML 输入文件以启动业务流程。  
  
#### <a name="configure-a-receive-port"></a>配置接收端口  
  
1.  在上一步中打开的 BizTalk Orchestration.odx 文件中，右键单击左侧的端口图面，然后单击“新建配置的端口” 。 这将启动端口配置向导。 在“欢迎使用端口配置向导”  页上，单击“下一步” 。  
  
2.  上**端口属性**页上，输入`FileIn`为**名称**，然后单击**下一步**。  
  
3.  在“选择端口类型”  页中，选择“新建端口类型” ，然后输入或选择以下属性值：  
  
     **端口类型名称**:`FileInPort`  
  
     **通信模式**： **单向**  
  
     **访问限制**： **内部 - 仅限于此项目**  
  
4.  单击“下一步”转至“端口绑定”页  ，然后选择以下属性值：    
  
     **端口通信方向**： **始终在此端口上接收消息**  
  
     **端口绑定**： **以后指定**  
  
5.  单击“下一步” ，然后单击“完成” 。 您将使用文件适配器接受此文件作为来自磁盘的输入。  
  
 接下来，创建一个发送端口，以接受包含位置结果（从调用 PeopleSoft **Get** 方法获得）的 XML 文件。 业务流程使用文件适配器通过此发送端口将该 XML 文件写入磁盘。  
  
#### <a name="configure-a-send-port"></a>配置发送端口  
  
1.  在 BizTalk Orchestration.odx 文件中，右键单击右侧的端口图面，然后单击“新建配置的端口” 。 这将启动端口配置向导。 在“欢迎使用端口配置向导”页上，单击“下一步”。    
  
2.  上**端口属性**页上，输入`FileOut`为**名称**，然后单击**下一步**。  
  
3.  在“选择端口类型”  页中，选择“新建端口类型” ，然后输入或选择以下属性值：  
  
     **端口类型名称**:`FileOutPort`  
  
     **通信模式**： **单向**  
  
     **访问限制**： **内部 - 仅限于此项目**  
  
4.  单击“下一步”转至“端口绑定”页  ，然后选择以下属性值：    
  
     **端口通信方向**： **始终在此端口上发送消息**  
  
     **端口绑定**： **以后指定**  
  
5.  单击“下一步” ，然后单击“完成” 。  
  
 最后，创建一个发送/接收端口，以将包含 **Get** 方法的初始 XML 输入文件发送到 PeopleSoft 系统。 此端口还将接收 XML 文件，该文件包含从 PeopleSoft 系统上调用 **Get** 方法获得的位置信息。  
  
#### <a name="configure-a-sendreceive-port"></a>配置发送/接收端口  
  
1.  在 BizTalk Orchestration.odx 文件中，右键单击右侧的端口图面，然后单击“新建配置的端口” 。 这将启动端口配置向导。 在“欢迎使用端口配置向导”  页上，单击“下一步” 。  
  
2.  上**端口属性**页上，输入`PeopleSoft_Port`为**名称**，然后单击**下一步**。  
  
3.  在“选择端口类型”  页上，选择“使用现有端口类型” 。 为“可用端口类型” 选择“PS_Test.LOCATION” ，然后单击“下一步” 。  
  
     ![](../core/media/d8b443ec-294d-4124-a29d-aeb42bbb107e.gif "d8b443ec-294d-4124-a29d-aeb42bbb107e")  
  
4.  单击“下一步”转至“端口绑定”页  ，然后选择以下属性值：    
  
     **端口通信方向**： **我将始终发送请求并接收响应**  
  
     **端口绑定**： **以后指定**  
  
5.  单击“下一步” ，然后单击“完成” 。  
  
 端口图面上显示的是 PeopleSoft 定位服务的新端口和可用方法。 随后您将指定 PeopleSoft 适配器，以发送和接收来自 PeopleSoft 系统的文件。  
  
 现在，将两个“发送”  形状和两个“接收”  形状插入业务流程，以链接到您刚才创建的端口。  
  
#### <a name="add-send-and-receive-shapes"></a>添加发送和接收形状  
  
1.  将工具箱中的“接收”  组件拖放到业务流程的起点（绿色圆圈）下。 单击**接收**形状，然后在属性窗口中，输入`FromDisk`为**名称**，并设置**激活**到`true`。 执行此操作后，此接收端口上收到传入文档时将激活业务流程。  
  
2.  拖动**发送**组件从工具箱拖放正下方**FromDiskReceive**形状。 单击新建**发送**形状，然后在属性窗口中，输入`ToPS`为**名称**。  
  
3.  拖动**接收**组件从工具箱拖放正下方**To_PS * * * 发送**形状。 单击**接收**形状，然后在属性窗口中，输入`FromPS`为**名称**。  
  
4.  拖动**发送**组件从工具箱拖放正下方**From_PSReceive**形状。 单击新建**发送**形状，然后在属性窗口中，输入`ToDisk`为**名称**。  
  
 您需要先定义要处理的消息类型，然后才能将这些形状连接到逻辑端口。 适配器需要传入（**Request** 方法）消息和传出（**Response** 方法）消息。 每种方法的消息不同。  
  
 在此业务流程中，您仅使用 **Get-Request** 和 **Get-Response** 消息。 如果业务流程正在更新数据（假设使用 **UpdateEx** 方法），则需要其他请求/响应消息。  
  
#### <a name="define-and-assign-messages-to-ports"></a>定义并将消息分配到端口  
  
1.  在左侧的端口图面上，  单击 **“FileIn”** 端口上的“请求”。 在“属性”窗口中，依次展开“消息类型” 和“多部分消息” ，然后单击“PS_Test.Get” 。  
  
2.  在左侧的端口图面上，单击“FileOut”端口上的“请求”。   在“属性”窗口中，依次展开“消息类型” 和“多部分消息” ，然后单击“PS_Test.GetResponse” 。  
  
     ![](../core/media/6b844ca3-322a-47b3-8cfd-68652c950752.gif "6b844ca3-322a-47b3-8cfd-68652c950752")  
  
3.  选择“FileIn”  端口，并将其传出发送箭头拖到“FromDisk”形状上的传入反向接收箭头。   
  
4.  选择“FileOut”  端口，并将其传入反向接收箭头拖到“ToDisk”形状上的传出发送箭头。   
  
5.  将现有的一般消息名称重命名为更具描述性的名称，以遵循正确的应用程序设计原则。 在解决方案资源管理器中，单击“业务流程视图”选项卡  。下**消息**，更改的标识符**Message_1**到**PS_Msg**。 将 **“Message_2”** 的标识符更改为 **“PS_Resp”**。  
  
     ![](../core/media/5ec92b81-4a55-4d44-a360-78a6aaa64255.gif "5ec92b81-4a55-4d44-a360-78a6aaa64255")  
  
     ![](../core/media/04b31c26-73a6-40a6-8d50-39c7c929d6a1.gif "04b31c26-73a6-40a6-8d50-39c7c929d6a1")  
  
6.  突出显示“To_PS”  发送形状，并将其“消息”  属性设置为“PS_Msg” 。  
  
7.  突出显示“From_PS”  接收形状，并将其“消息”  属性设置为“PS_Resp” 。  
  
8.  将 **“To_PS”** 发送形状连接到 **“PeopleSoft_Port”** 端口上“Get”方法的“请求”部分。    
  
9. 将 **“From_PS”** 发送形状连接到 **“PeopleSoft_Port”** 端口上“Get”方法的“响应”部分。    
  
     ![](../core/media/d16e02bc-954c-4aa2-99d6-3fee1222c730.gif "d16e02bc-954c-4aa2-99d6-3fee1222c730")  
  
## <a name="step-4-build-and-deploy-the-project"></a>步骤 4： 生成并部署项目  
 现在，BizTalk 项目已完成，你可以生成项目并将其部署在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中。  
  
1.  在 Visual Studio 中，依次指向**Visual Studio Tools**，然后选择 Visual Studio 命令提示符 * *。  
  
2.  要生成项目，您需要强名称密钥文件。在命令提示符下，输入以下内容以创建强名称密钥文件：  
  
     **sn-k labs.snk**  
  
3.  在“解决方案资源管理器”中，右键单击“PS_Test”  项目，然后单击“属性”  以启动项目的项目设计器。  
  
4.  单击“签名”  选项卡。  
  
5.  选择“为程序集签名”  选项，单击下拉列表中的“选择强名称密钥文件”  选项，然后单击“浏览” 。  
  
6.  浏览以选择密钥文件“labs.snk” ，然后单击“打开” 。  
  
7.  单击项目设计器中的“部署”  选项卡。  
  
8.  设置**应用程序名称**到`PS_Test`。  
  
9. 在解决方案资源管理器中，右键单击“”  项目，然后单击“生成”   
  
10. 成功生成该项目后，右键单击“PS_Test”  项目，然后单击“部署” 。  
  
## <a name="step-5-test-the-application-and-viewing-the-xml-output"></a>步骤 5： 测试应用程序和查看 XML 输出  
 现在，你将测试你所创建和部署的应用程序。 你将创建用于启动业务流程进程的 XML 文件，然后将文件夹配置为接收和发送应用程序中的 XML 文件。 配置应用程序之后，将运行该应用程序并查看业务流程返回的 XML 文件。  
  
#### <a name="generate-the-xml-file-for-the-query"></a>生成查询的 XML 文件  
  
1.  在解决方案资源管理器中，双击“LOCATIONService_LOCATION_x5d.xsd”  以打开该文件。  
  
2.  右键单击“LOCATIONService_LOCATION_x5d.xsd”  ，然后单击“属性” 。 为“输出实例文件名”输入示例 XML 的  以下路径和文件名：  
  
     `C:\LABS\PS_TEST\SAMPLEQUERY.XML`  
  
3.  单击“确定” **。** 在属性窗口中，选择**\<架构\>**并设置**根引用： 获取**。  
  
4.  右键单击“LOCATIONService_LOCATION_x5d.xsd”  ，然后单击“生成实例” 。 这将生成 **SampleQuery.xml** 文件。 此文件将放入接收位置，作为适配器启动业务流程进程的输入。  
  
     ![](../core/media/ef65a96c-2daa-44db-ab95-d18b1fda934e.gif "ef65a96c-2daa-44db-ab95-d18b1fda934e")  
  
#### <a name="configure-and-start-the-biztalk-application"></a>配置和启动 BizTalk 应用程序  
  
1.  配置用于接收传入文件和发送传出文件的文件夹。 转到**C:\LABS\PS_TEST**并创建两个新的子文件夹名为`FileIn`和`FileOut`。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**控制台根节点**，展开**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**，展开**BizTalk 组**，展开**应用程序**，右键单击**PS_Test** ，然后单击**配置**。  
  
     ![](../core/media/e45f4c8b-fc8a-492a-9824-5232eb728d95.gif "e45f4c8b-fc8a-492a-9824-5232eb728d95")  
  
3.  选择“Orchestration_1”  ，然后单击“主机”  下拉框。 选择“BizTalkServerApplication” 。  
  
4.  下**接收端口**，单击**\<无\>**。 在下拉列表中，选择“新建接收端口” 。  
  
5.  有关**名称**，类型`FileInPort`，然后单击**确定**。 将出现一个消息框，表明你需要指定接收位置。 单击“确定”，然后单击“新建”。    
  
     ![](../core/media/298638b6-0eb8-49c4-8a2e-485571d070cf.gif "298638b6-0eb8-49c4-8a2e-485571d070cf")  
  
6.  键入或选择以下属性值：  
  
     **名称**:`FileInLoc`  
  
     **类型**： **文件**  
  
     **接收处理程序**： **BizTalkServerApplication**  
  
     **接收管道**： **XMLReceive**  
  
     ![](../core/media/613a5dbc-effe-4827-a72b-d16eef8d0e8a.gif "613a5dbc-effe-4827-a72b-d16eef8d0e8a")  
  
7.  单击“配置”  ，为“接收文件夹”键入 `C:\LABS\PS_TEST\FILEIN` ， ，然后单击“添加生成的项”    
  
     ![](../core/media/513eebb0-58ca-4aaa-a33b-31700f9cf7a8.gif "513eebb0-58ca-4aaa-a33b-31700f9cf7a8")  
  
8.  单击**\<无\>**为**PeopleSoft_Port**下拉列表中。  
  
9. 选择“新建发送端口”  ，然后选择或键入以下属性值。  
  
     **名称**:`PS_Test_Port`  
  
     **类型**： **PeopleSoft**  
  
     **发送处理程序**： **BizTalkServerApplication**  
  
     **管道**：“XMLTransmit”  和“XMLReceive”   
  
10. 单击“配置” ，然后输入以下属性值：  
  
    1.  **应用程序服务器路径**： **//Servername:9000**  
  
         Servername 是您的应用程序服务器。 这是特定服务器名称或 IP 地址以及此 PeopleSoft 系统的端口号。  
  
    2.  **JAVA_HOME**： **C:\J2SDK1.4.2_08**  
  
         此路径特定于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上的 Java SDK 安装。  
  
    3.  **密码**:\<输入 PeopleSoft 密码\>  
  
    4.  **PeopleSoft 8.x JAR 文件**： **C:\PSJARS\VER841\PSJOA.JAR**  
  
     **用户名：** \<输入 PeopleSoft 用户 Id\>  
  
11. 单击“确定”  两次以关闭对话框。  
  
12. 在配置 Applicationwindow 中，单击**\<无\>**为**FileOut**下拉列表中。  
  
13. 选择“新建发送端口”  ，然后键入或选择以下属性值：  
  
     **名称**:`FileOutPort`  
  
     **类型**： **文件**  
  
     **发送处理程序**： **BizTalkServerApplication**  
  
     **发送管道**： **XMLTransmit**  
  
14. 单击“配置”  ，为“接收文件夹”键入`C:\Labs\PS_Test\FileOut` ， **C:\Labs\PS_Test\FileOut** 。为“文件名”保留“”，因为这会为每个消息生成唯一的文件。  ，  because this results in a unique file ， each message.  
  
15. 单击“确定”三次  以关闭对话框。  
  
16. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**PS_Test**应用程序，然后单击**启动**。  
  
     ![](../core/media/7bf30707-c7c6-409f-af18-9c9dfeb0de58.gif "7bf30707-c7c6-409f-af18-9c9dfeb0de58")  
  
#### <a name="test-the-orchestration"></a>测试业务流程  
  
1.  在 **“C:\Labs\PS_Test”** 目录中，将 **Samplequery.xml** 文件更改为以下内容：  
  
    ```  
    <ns0:Get xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
      <ns0:SETID>SHARE</ns0:SETID>  
      <ns0:LOCATION>AUS01</ns0:LOCATION>  
      <ns0:getHistory>true</ns0:getHistory>  
    </ns0:Get>  
    ```  
  
    > [!NOTE]
    >  所有系统上都将使用 **SHARE** 数据值。 但您的系统上必须存在要用于此 XML 文件中的 **Location** 的值。 您会在实验室 1 中发现这一点。  
  
2.  保存更改并将文件复制到 **C:\Labs\PS_Test\FileIn** 文件夹。 这是用于启动业务流程进程的 FileIn 的接收位置。  
  
3.  几秒钟之后， **C:\Labs\PS_Test\FileOut** 文件夹中应出现一个 XML 文件。 此文件应包含的记录（记录了位置为 AUS01）中的数据。  
  
     ![](../core/media/1320ea3c-b2bc-4717-b200-c3c550079ccb.gif "1320ea3c-b2bc-4717-b200-c3c550079ccb")  
  
     这些返回的记录数据应与在 PeopleSoft 练习 1 中针对 PeopleSoft 系统的查询所返回的结果相匹配。 通过比较的值在中获取实验室 1 专门**地址 1**和**Address2**对中所示此处线**\<位置： 地址 1\>**和**\<位置： ADDRESS2\>** 字段，你可以验证**获取**方法正常运行。  
  
## <a name="summary"></a>摘要  
 在本实验室中，您首先验证了必备组件的设置对于访问 PeopleSoft 系统是否正确。 然后，你使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 创建了包含业务流程的新 BizTalk 项目。 对 BizTalk 业务流程进行了配置，以使用 PeopleSoft 适配器获取来自 PeopleSoft 系统的数据。 为配置业务流程，你创建了发送端口、接收端口和发送/接收端口。 将这些端口绑定到 PeopleSoft 适配器，并将消息分配给相应的端口。  
  
 完成 BizTalk 项目后，你使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 来生成和部署该项目。 随后，配置了新应用程序，并运行该应用程序，以获取来自 PeopleSoft 系统的数据。 为了验证应用程序是否正常运行，您将其输出 XML 文件与在实验室 1 中从 PeopleSoft 系统接收到的文件进行了比较。