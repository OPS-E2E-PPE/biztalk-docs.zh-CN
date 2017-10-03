---
title: "执行博士 Edwards OneWorld 示例查询 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b060d383-a2df-472f-90cc-e79078b0bcfd
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35d05dfe719a9b199d7422f99ef80e888126f01f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="executing-a-jd-edwards-oneworld-sample-query"></a>执行 JD Edwards OneWorld 示例查询
可以使用 JD Edwards OneWorld 适配器从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统访问 JD Edwards OneWorld (JDEOW) 系统。 此适配器是 Microsoft 提供的与 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 配合使用的一组八个业务线 (LOB) 适配器之一。  
  
 这是 JD Edwards OneWorld 实验室工作的第二部分。 第一部分（实验室 1）中，你在没有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 协助或其他 Microsoft 技术的情况下，手动访问 JD Edwards OneWorld 系统上的数据。 在本部分（实验室 2）中，你将创建一个 BizTalk 业务流程作为 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk 项目的一部分。 你将在此业务流程中配置端口，以使用 JD Edwards OneWorld 适配器从 JD Edwards OneWorld 系统中获取数据。  
  
## <a name="prerequisites"></a>先决条件  
  
-   Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]  
  
-   Microsoft [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   JD Edwards OneWorld 客户端软件  
  
-   与另一台服务器上的 JD Edwards OneWorld 系统的网络连接  
  
-   Microsoft BizTalk Adapters for Enterprise Applications  
  
> [!NOTE]
>  有关安装和配置 Microsoft BizTalk 适配器为企业应用程序的信息，请参阅[超链接"http://go.microsoft.com/fwlink/?LinkId=196039"\t"_blank"http://go.microsoft.com/fwlink/?LinkId=196039](http://go.microsoft.com/fwlink/?LinkId=196039)。 本文档包含 JD Edwards、PeopleSoft、JD Edwards OneWorld、TIBCO 和 Siebel LOB 适配器的重要配置信息。  
  
## <a name="lab-2---executing-a-jd-edwards-oneworld-sample-query"></a>实验室 2 - 执行 JD Edwards OneWorld 示例查询  
 在本实验中，将执行**获取**针对博士 Edwards OneWorld 系统操作。 具体将执行以下任务：  
  
-   验证博士 Edwards OneWorld 先决条件  
  
-   在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中设置 JD Edwards OneWorld 发送端口  
  
-   创建一个 BizTalk 业务流程项目  
  
-   生成并部署项目  
  
-   测试应用程序并查看 XML 输出  
  
 你将使用 JD Edwards OneWorld 适配器从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中访问 JD Edwards OneWorld 系统上的数据。  
  
 此适配器允许由业务流程执行的请求和响应来处理 JD Edwards OneWorld 对象。 许多方法可用于架构对象。 此实验室将演示如何使用**地址簿图： MBF**方法。  
  
 在运行服务请求之前，必须为特定的 JD Edwards OneWorld 对象创建服务请求和响应架构。 通过直接询问 JD Edwards OneWorld 中支持的元数据对象，添加生成的项/添加适配器向导可以创建这些架构。 此实验室说明创建架构所需的步骤**地址簿图： MBF**方法并处理查询。  
  
## <a name="procedures-for-lab-2--executing-a-jd-edwards-oneworld-sample-query"></a>实验室 2 的过程 - 执行 JD Edwards OneWorld 示例查询  
  
### <a name="verifying-the-jd-edwards-oneworld-prerequisites"></a>验证 JD Edwards OneWorld 先决条件  
 在开始创建 BizTalk 项目以便使用 JD Edwards OneWorld 适配器之前，你需要确保访问 JD Edwards OneWorld 系统所需的文件和适配器设置正确。 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上，JD Edwards OneWorld 适配器通过 Java 接口与 JD Edwards OneWorld 系统进行通信。  
  
 四个文件所需的适当的接口访问使用博士 Edwards OneWorld 适配器博士 Edwards OneWorld 系统： Connector.jar、 Kernel.jar、 BTSLIBinterop.jar 和 JDEJAccess.jar。  
  
-   Connector.jar 和 Kernel.jar 文件随附了 JD Edwards OneWorld 系统，可以从 JD Edwards OneWorld 管理员获取。 这些文件在 C:\JDEOWJars 文件夹中。  
  
-   遵循适配器安装指南中附带的这些说明，BTSLIBinterop.jar 文件可由 JD Edwards OneWorld 系统生成。 此文件在 C:\JDEOWJars 文件夹中。  
  
-   JDEJAccess.jar 文件是 JDEOW 适配器的一部分，包含在该适配器的安装中。 默认情况下，它位于 C:\Program Files\Microsoft BizTalk 适配器对于企业 Applications\J.D。 Edwards OneWorld® \Classes 文件夹。  
  
##### <a name="to-verify-the-jd-edwards-oneworld-prerequisites"></a>验证 JD Edwards OneWorld 先决条件的步骤  
  
1.  请确保 Connector.jar、Kernel.jar 和 BTSLIBinterop.jar 文件在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机的 C:\JDEOWJars 文件夹中。  
  
2.  请确保 JDEJAccess.jar 文件上存在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]企业 Applications\J.D 的 C:\Program Files\Microsoft BizTalk 适配器中的计算机。 Edwards OneWorld® \Classes 文件夹。  
  
3.  单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
### <a name="configuring-biztalk-send-ports"></a>配置 BizTalk 发送端口  
 现在，你将验证是否安装了 JD Edwards OneWorld 适配器并创建 JD Edwards OneWorld 发送端口。  
  
##### <a name="to-verify-that-the-jd-edwards-oneworld-adapter-is-installed-in-includepragueincludesprague-mdmd"></a>验证 JD Edwards OneWorld 适配器是否安装在 [!INCLUDE[prague](../includes/prague-md.md)] 中的步骤  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  
  
     确保**JDE_OneWorld**安装适配器和列表。 如果没有安装 JD Edwards OneWorld 适配器，请安装企业应用程序的 BizTalk 适配器（请参阅前面的“先决条件”部分）。 安装适配器后，右键单击**适配器**，然后单击**新建-适配器**安装博士 Edwards OneWorld 适配器。 你必须重新启动主机实例才能使此操作生效。  
  
##### <a name="to-create-the-jd-edwards-oneworld-send-port"></a>创建 JD Edwards OneWorld 发送端口的步骤  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。  
  
2.  右键单击**发送端口**，单击**新建**，然后单击**静态请求-响应发送端口**。为这些字段中输入以下值：  
  
    1.  **名称：**  `JDE_OneWorldPort`  
  
    2.  **类型：**  `JDE_OneWorld`  
  
    3.  **发送处理程序：**  `BizTalkServerApplication`  
  
    4.  **发送管道：**  `XMLTransmit`  
  
    5.  **接收管道：**  `XMLReceive`  
  
3.  单击“配置” ，然后输入以下属性值：  
  
    1.  **主机：** \<输入你 JDEOW 的主机名 >  
  
    2.  **JAVA_HOME:**`C:\j2sdk1.4.2_08`  
  
    3.  **JDEdwards 环境：** \<进入 JDEOW 环境 >  
  
    4.  **JDEdwards JAR 文件：** \<输入的 JAR 文件的完整路径 >  
  
         `C:\JDEOWJars\BTSLIBInterop.jar; C:\JDEOWJars\Connector.jar; C:\JDEOWJars\Kernel.jar;C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards OneWorld®\Classes\JDEJAccess.jar`  
  
    5.  **密码：**使用下拉列表，然后输入你博士 Edwards OneWorld 密码。  
  
    6.  **端口：**  `6009`  
  
    7.  **用户名：** \<输入博士 Edwards 用户名 >  
  
     ![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")  
  
4.  单击**确定**两次以关闭**发送端口属性**对话框。  
  
### <a name="creating-a-biztalk-orchestration-project"></a>创建 BizTalk 业务流程项目  
 现在，你将在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中创建 BizTalk 项目，并配置该项目中的业务流程，以处理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与 JD Edwards OneWorld 系统之间的通信。 你将添加发送端口和接收端口，生成项目，然后部署项目。  
  
##### <a name="to-create-the-biztalk-orchestration-project-in-visual-studio"></a>在 Visual Studio 中创建 BizTalk 业务流程项目  
  
1.  打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在 C:\LABS 文件夹中创建新的 BizTalk 项目。 在“文件”  菜单上，单击“新建” 。 此时将显示“新建项目”  对话框。 在“发送端口属性”  选择“空的 BizTalk Server 项目”。  输入`JDE_OW_Test`作为唯一项目名称，然后单击**确定**。  
  
2.  在解决方案资源管理器中，右键单击该项目，单击“添加” ，然后单击“添加生成的项” 。 在类别窗格中，选择**添加适配器元数据**，在模板窗格中，选择**添加适配器元数据**，然后单击**添加**。  
  
3.  在添加适配器向导中，选择**博士 Edwards OneWorld**适配器，选择**JDE_OneWorldPort**发送在前面的过程中，创建的端口，然后单击**下一步**.  
  
     ![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")  
  
4.  上**选择服务添加到导入**页上，打开**博士 Edwards OneWorld**。 JDEOW 系统使用 BrowsingAgent 程序通过适配器进行连接。 BrowsingAgent 返回以下服务。  
  
     ![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")  
  
5.  展开**CALLBSFN**和向下滚动到**N0100041-地址簿图： MBF**。 选择 N0100041，然后单击**完成**。  
  
6.  在解决方案资源管理器中，会有一个新的 BizTalk 业务流程，包含两个新的相关架构文件。 这些文件由添加适配器向导创建。 双击“BizTalk Orchestration.odx”文件以打开业务流程。   
  
     ![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")  
  
 此业务流程接受已为 JD Edwards OneWorld 系统设置格式的 XML 文件作为文件适配器中的输入。 此业务流程使用 JD Edwards OneWorld 适配器将 XML 文件发送到 JD Edwards OneWorld 系统。 JD Edwards OneWorld 处理查询并生成包含结果的输出 XML 文件。 此 XML 文件通过 JD Edwards OneWorld 适配器返回到业务流程，并且文件适配器将 XML 文件写入磁盘上的输出位置。  
  
 要完成业务流程，你需要创建并配置用于接收和发送 XML 文件的端口。 首先，配置文件适配器所用的接收端口，以便从磁盘将包含查询的 XML 输入到业务流程。  
  
##### <a name="to-configure-a-receive-port-to-accept-the-input-xml-file"></a>配置接收端口以接受 XML 输入文件的步骤  
  
1.  双击“BizTalk Orchestration.odx”文件以打开业务流程。   
  
2.  在 BizTalk Orchestration.odx 文件中，右键单击左的端口图面，然后单击**新配置端口**。 这将启动端口配置向导。 在“欢迎使用端口配置向导”  页上，单击“下一步” 。  
  
3.  上**端口属性**页上，输入`JDE_File_In`为**名称**，然后单击**下一步**。  
  
4.  在“选择端口类型”  页中，选择“新建端口类型” ，然后输入或选择以下属性值：  
  
     **端口类型名称**:`JDE_FileIn_Port`  
  
     **通信模式**： **单向**  
  
     **访问限制**： **内部 - 仅限于此项目**  
  
5.  单击“下一步”转至“端口绑定”页  ，然后选择以下属性值：    
  
     **端口通信方向**： **始终在此端口上接收消息**  
  
     **端口绑定**： **以后指定**  
  
6.  单击“下一步” ，然后单击“完成” 。  
  
 接下来，创建一个发送/接收端口，将包含查询的初始 XML 输入文件发送到 JD Edwards OneWorld 系统。 此端口还接收 XML 输出文件，该文件包含来自对 JD Edwards OneWorld 系统调用的查询结果。  
  
##### <a name="to-configure-a-sendreceive-port-to-interface-with-jd-edwards-oneworld"></a>配置发送/接收端口以连接 JD Edwards OneWorld 的步骤  
  
1.  在 BizTalk Orchestration.odx 文件中，右键单击右侧端口图面，然后单击**新配置端口**。 这将启动端口配置向导。 在“欢迎使用端口配置向导”  页上，单击“下一步” 。  
  
2.  在“选择端口类型”  页上，选择“使用现有端口类型” 。 下**可用端口类型**，选择**JD_OW_Test.N0100041**，然后单击**下一步**。  
  
     ![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")  
  
3.  选择以下属性值：  
  
     **端口的通信的方向**:**我将发送请求并接收响应**  
  
     **端口绑定**： **以后指定**  
  
4.  单击“下一步” ，然后单击“完成” 。 在端口图面上，你将看到端口和可用的方法。  
  
 最后，配置文件适配器要使用的发送端口，从而将包含查询结果的 XML 输出到磁盘。  
  
##### <a name="to-configure-a-send-port-to-output-the-xml-file-to-disk"></a>配置发送端口将 XML 文件输出到磁盘的步骤  
  
1.  在 BizTalk Orchestration.odx 文件中，右键单击左的端口图面，然后单击**新配置端口**。 这将启动端口配置向导。 在“欢迎使用端口配置向导”  页上，单击“下一步” 。  
  
2.  上**端口属性**页上，输入`JDE_FileOut`为**名称**，然后单击**下一步**。  
  
3.  在“选择端口类型”  页中，选择“新建端口类型” ，然后输入或选择以下属性值：  
  
     **端口类型名称**:`JDE_FileOut_Port`  
  
     **通信模式**： **单向**  
  
     **访问限制**： **内部 - 仅限于此项目**  
  
4.  单击“下一步”转至“端口绑定”页  ，然后选择以下属性值：    
  
     **端口通信方向**： **始终在此端口上发送消息**  
  
     **端口绑定**： **以后指定**  
  
5.  单击“下一步” ，然后单击“完成” 。  
  
 端口图面上显示的是 JD Edwards OneWorld 服务的新端口和可用方法。 随后，你将指定 JD Edwards OneWorld 适配器，以发送和接收来自 JD Edwards OneWorld 系统的文件。  
  
 **JDE_File_In**和**JDE_File_Out**你刚刚创建需要的端口相关联的消息类型。  
  
##### <a name="to-assign-message-types-to-the-ports"></a>为端口分配消息类型  
  
1.  在左的端口面上**JDE_File_In**端口，请单击**请求**。 在属性窗口中，展开**消息类型**，展开**多部分消息**，然后单击**JDE_OW_TestAddressBookMasterMBF**。  
  
2.  在左的端口面上**JDE_File_Out**端口，请单击**请求**。 在属性窗口中，展开**消息类型**，展开**多部分消息**，然后单击**JDE_OW_TestAddressBookMasterMBFResponse**。  
  
 插入两个**发送**形状和第二个**接收**用于链接到的端口到业务流程形状。  
  
##### <a name="to-add-send-and-receive-shapes"></a>添加“发送”和“接收”形状  
  
1.  将工具箱中的“接收”  组件拖放到业务流程的起点（绿色圆圈）下。 单击**接收**形状，然后在属性窗口中，输入`Get_File`为**名称**，并设置**激活**到`true`。 执行此操作后，此接收端口上收到传入文档时将激活业务流程。  
  
2.  拖动**发送**组件从工具箱拖放正下方**GetFileReceive**形状。 单击新建**发送**形状，然后在属性窗口中，输入`SendToJDEOW`为**名称**。  
  
3.  拖动**接收**组件从工具箱拖放正下方**SendToJDEOWSend**形状。 单击**接收**形状，然后在属性窗口中，输入`JDEOW_Resp`为**名称**。  
  
4.  拖动**发送**组件从工具箱拖放正下方**JDEOW_RespReceive**形状。 单击新建**发送**形状，然后在属性窗口中，输入`FileToDisk`为**名称**。  
  
     ![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")  
  
5.  连接**JDE_FileIn**端口到**GetFileReceive**组件。  
  
6.  连接**JDE_FileOut**端口到**FileToDiskReceive**组件。  
  
7.  转到**业务流程视图**展开**消息**。 更改的标识符**Message_1**到`MsgToJDEOW`，和**Message_2**到`JDEOW_Resp.`  
  
8.  突出显示**SendToJDEOWSend**组件，并且已设置其**消息**属性**MsgToJDEOW**。  
  
9. 突出显示**JDEOW_RespReceive**组件，并且已设置其**消息**属性**JDEOW_Resp**。  
  
10. 连接**SendToJDEOW**到**请求**部分**JDE_OW_Port**端口。  
  
11. 连接**JDEOW_Resp**到**响应**部分**JDE_OW_Port**端口。  
  
     ![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")  
  
### <a name="building-and-deploying-the-project"></a>生成并部署项目  
 现在，BizTalk 项目已完成，你可以生成项目并将其部署在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中。  
  
##### <a name="to-build-and-deploy-the-project"></a>生成并部署项目  
  
1.  启动**Visual Studio 命令提示**。  
  
2.  要生成项目，你需要强名称密钥文件。 在命令提示符下，输入以下内容以创建强名称密钥文件：  
  
     **sn-k labs.snk**  
  
3.  在解决方案资源管理器，右键单击**JD_OW_Test**项目，，然后单击**属性**以启动项目设计器中为该项目。  
  
4.  单击“签名”  选项卡。  
  
5.  选择“为程序集签名”  选项，单击下拉列表中的“选择强名称密钥文件”  选项，然后单击“浏览” 。  
  
6.  浏览以选择密钥文件“labs.snk” ，然后单击“打开” 。  
  
7.  单击项目设计器中的“部署”  选项卡。  
  
8.  设置**应用程序名称**到`JDE_OW_Test`。  
  
9. 在解决方案资源管理器，右键单击**JDE_OW_Test**项目，，然后单击**生成。**  
  
     ![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")  
  
10. 生成成功完成后，右键单击**XX_JD Edwards OneWorldQuery**项目，，然后单击**部署**。 在输出窗口中将显示以下输出：  
  
     ![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")  
  
### <a name="testing-the-application-and-viewing-the-xml-output"></a>测试应用程序并查看 XML 输出  
 现在，你将测试你所创建和部署的应用程序。 你将创建用于启动业务流程进程的 XML 文件，然后将文件夹配置为接收和发送应用程序中的 XML 文件。 配置应用程序之后，将运行该应用程序并查看业务流程返回的 XML 文件。  
  
##### <a name="to-generate-the-xml-file-for-the-query"></a>生成 XML 文件以便查询  
  
1.  在解决方案资源管理器中，双击**N0100041Service_N0100041.xsd**打开文件。  
  
2.  右键单击**N0100041Service_N0100041.xsd** ，然后单击**属性**。 为“输出实例文件名”输入示例 XML 的  以下路径和文件名：  
  
     `C:\LABS\JDE_OW_TEST\SAMPLE.XML`  
  
3.  单击“确定” **。** 在属性窗口中，选择**\<架构 >**并设置**根引用：**到`AddressBookMasterMBF`。 这将导致生成的 XML，仅包含**查询**xml。  
  
     ![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")  
  
4.  右键单击**N0100041Service_N0100041.xsd** ，然后单击**生成实例**。 这将生成**Sample.xml**文件。 此文件将放入接收位置，作为适配器启动业务流程进程的输入。  
  
##### <a name="to-configure-and-start-the-biztalk-application"></a>配置和启动 BizTalk 应用程序  
  
1.  配置用于接收传入文件和发送传出文件的文件夹。 转到**C:\LABS\JDE_OW_Test**并创建两个新的子文件夹名为`FileIn`和`FileOut`。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  右键单击**JDE_OW_Test**，然后单击**配置**。  
  
     ![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")  
  
4.  选择“Orchestration_1”  ，然后单击“主机”  下拉框。 选择“BizTalkServerApplication” 。  
  
5.  下**接收端口**，单击**\<无 >**。 在下拉列表中，选择“新建接收端口” 。  
  
6.  有关**名称**，类型`JDE_FileIn_Port`，然后单击**确定**。 将出现一个消息框，表明你需要指定接收位置。 单击“确定”，然后单击“新建”。    
  
     ![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")  
  
7.  键入或选择以下属性值：  
  
     **名称**: JDE_`FileInLoc`  
  
     **类型**： **文件**  
  
     **接收处理程序**： **BizTalkServerApplication**  
  
     **接收管道**： **XMLReceive**  
  
     ![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")  
  
8.  单击**配置**，类型`C:\LABS\JDE_OW_Test\FileIn`为**接收文件夹**，然后单击**确定**三次。  
  
     ![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")  
  
9. 单击**\<无 >**为**JDE_OW_Port**下拉列表中。  
  
10. 选择**新建发送端口**，然后选择或键入属性的以下值：  
  
     **名称**:`JDE_OW_Port`  
  
     **类型**: **JDE_OneWorld**  
  
     **发送处理程序**： **BizTalkServerApplication**  
  
     **管道**：“XMLTransmit”  和“XMLReceive”   
  
11. 单击“配置” ，然后输入以下属性值：  
  
     **主机：** \<输入你 JDEOW 的主机名 >  
  
     **JAVA_HOME:**`C:\j2sdk1.4.2_08`  
  
     **JDEdwards 环境：** \<进入 JDEOW 环境 >  
  
     **JDEdwards JAR 文件：**<enter full path of JAR files>  
  
     `C:JDEOWJarsBTSLIBInterop.jar; C:JDEOWJarsConnector.jar; C:JDEOWJarsKernel.jar;C:Program FilesMicrosoft BizTalk Adapters for Enterprise ApplicationsJ.D. Edwards OneWorld®ClassesJDEJAccess.jar`  
  
     **密码：**使用下拉列表，然后输入你博士 Edwards OneWorld 密码。  
  
     **端口：**  `6009`  
  
     **用户名：**<enter your JD Edwards User Name>  
  
     ![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")  
  
12. 单击“确定”  两次以关闭对话框。  
  
13. 在配置 Applicationwindow 中，单击**\<无 >**为**JDE_FileOut**下拉列表中。  
  
14. 选择“新建发送端口”  ，然后键入或选择以下属性值：  
  
     **名称**:`FileOutPort`  
  
     **类型**： **文件**  
  
     **发送处理程序**： **BizTalkServerApplication**  
  
     **发送管道**： **XMLTransmit**  
  
15. 单击**配置**和类型`C:\Labs\JDE_OW_Test\FileOut`为**目标文件夹。** 。为“文件名”保留“”，因为这会为每个消息生成唯一的文件。  ，  because this results in a unique file ， each message.  
  
     ![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")  
  
16. 单击“确定”三次  以关闭对话框。  
  
17. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**JDE_OW_Test**应用程序，，然后单击**启动**。  
  
##### <a name="to-test-the-orchestration"></a>测试业务流程  
  
1.  在**C:\Labs\JDE_OW_Test**目录**Sample.xml**文件将显示为：  
  
     ![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")  
  
2.  编辑**Sample.xml**文件，以删除以外的所有内容**cActionCode**和**mnAddressBookNumber**元素。  
  
     ![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")  
  
3.  有关**cActionCode**元素插入的字母`i`。  
  
4.  有关**mnAddressBookNumber**插入数`500`。  
  
5.  保存更改并将文件复制到**C:\Labs\JDE_OW_Test\FileIn**文件夹。 这是启动业务流程进程的接收位置。  
  
6.  在几秒钟，XML 文件应出现在**C:\Labs\JDE_OW_Test\FileOut**文件夹。 此文件应包含地址为 500 的所有记录。  
  
     ![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")  
  
     此返回的记录数据应与匹配实验室 1 中为博士 Edwards OneWorld 系统的查询返回的数据。 通过比较实验室 1 中获得的记录，你可以验证**获取**方法正常运行。  
  
## <a name="summary"></a>摘要  
 在本实验室中，你首先验证了访问 JD Edwards OneWorld 系统所需的先决条件是否正确设置。 然后，你使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 创建了包含业务流程的新 BizTalk 项目。 你将配置 BizTalk 业务流程，以使用 JD Edwards OneWorld 适配器从 JD Edwards OneWorld 系统中获取数据。 为配置业务流程，你创建了发送端口、接收端口和发送/接收端口。 将这些端口绑定到 JD Edwards OneWorld 适配器，并将消息分配给相应的端口。  
  
 完成 BizTalk 项目后，你使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 来生成和部署该项目。 随后，配置了新应用程序，运行该应用程序，并从 JD Edwards OneWorld 系统中获取数据。 要验证应用程序是否正常运行，你将其输出 XML 文件与实验室 1 中从 JD Edwards OneWorld 系统接收到的文件进行了比较。