---
title: 执行 JD Edwards OneWorld 示例查询 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b060d383-a2df-472f-90cc-e79078b0bcfd
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e017be5c36766c6be0997c5dbcf1f1aef7d2384
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346039"
---
# <a name="execute-a-jd-edwards-oneworld-sample-query"></a>执行 JD Edwards OneWorld 示例查询
JD Edwards OneWorld (JDEOW) 系统是从可访问[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统通过使用 JD Edwards OneWorld 适配器。 此适配器随[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。
  
 这是 JD Edwards OneWorld 实验室工作的第二部分。 在第一部分 (实验室 1) 中，手动访问 JD Edwards OneWorld 系统不需要的协助上的数据[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或其他 Microsoft 技术。 在本部分（实验室 2）中，你将创建一个 BizTalk 业务流程作为 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk 项目的一部分。 在此业务流程，以使用 JD Edwards OneWorld 适配器从 JD Edwards OneWorld 系统中获取数据，您将配置端口。  
  
## <a name="prerequisites"></a>先决条件  
  
- Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]
  
- Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 
  
- JD Edwards OneWorld 客户端软件  
  
- 网络连接到另一台服务器上的 JD Edwards OneWorld 系统  
  
- Microsoft BizTalk Adapters for Enterprise Applications  
  
> [!NOTE]
>  请参阅[安装和配置企业应用程序的适配器](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)用于 JD Edwards、 PeopleSoft 和 TIBCO 适配器的重要配置信息。  
  
## <a name="lab-2---executing-a-jd-edwards-oneworld-sample-query"></a>实验室 2-执行 JD Edwards OneWorld 示例查询  
 在此实验中，将执行**获取**针对 JD Edwards OneWorld 系统的操作。 具体将执行以下任务：  
  
- 验证 JD Edwards OneWorld 先决条件  
  
- 设置在 JD Edwards OneWorld 发送端口 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- 创建一个 BizTalk 业务流程项目  
  
- 生成并部署项目  
  
- 测试应用程序并查看 XML 输出  
  
  您将使用 JD Edwards OneWorld 适配器从 JD Edwards OneWorld 系统上访问数据[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
  此适配器支持使用请求和响应执行的业务流程来处理 JD Edwards OneWorld 对象。 许多方法都可用于架构对象。 此实验演示了如何使用**Address Book MBF**方法。  
  
  在运行之前服务请求，必须创建特定的 JD Edwards OneWorld 对象的服务请求和响应架构。 添加生成的项 / 添加适配器向导创建这些架构通过直接询问 JD Edwards OneWorld 中支持的元数据对象。 本实验室阐释了创建的架构所需的步骤**Address Book MBF**方法并处理查询。  
  
## <a name="step-1-verify-the-jd-edwards-oneworld-prerequisites"></a>第 1 步：验证 JD Edwards OneWorld 先决条件  
 在开始创建 BizTalk 项目，以便使用与 JD Edwards OneWorld 适配器之前，您需要确保文件和适配器正确设置了访问 JD Edwards OneWorld 系统。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机，JD Edwards OneWorld 适配器与 JD Edwards OneWorld 系统进行通信使用 Java 接口。    

1. 四个文件是对使用 JD Edwards OneWorld 适配器的 JD Edwards OneWorld 系统所需的适当的接口访问：Connector.jar、 Kernel.jar、 BTSLIBinterop.jar 和 JDEJAccess.jar。  
  
    -   Connector.jar 和 Kernel.jar 文件随附 JD Edwards OneWorld 系统，并从 JD Edwards OneWorld 管理员获取。 这些文件位于在 C:\JDEOWJars 文件夹中。  
  
    -   JD Edwards OneWorld 系统生成 BTSLIBinterop.jar 文件包括适配器安装指南中的说明。 此文件位于在 C:\JDEOWJars 文件夹中。  
  
    -   JDEJAccess.jar 文件是 JDEOW 适配器的一部分，包含与安装的适配器。 默认情况下，它位于 C:\Program Files\Microsoft BizTalk Adapters Enterprise applications\j.d.的。 Edwards OneWorld® \Classes 文件夹。  
  
2. 确认 Connector.jar、 Kernel.jar 和 BTSLIBinterop.jar 文件存在于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机的 C:\JDEOWJars 文件夹中。  
  
3. 确认 JDEJAccess.jar 文件上是否存在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]C:\Program Files\Microsoft BizTalk Adapters for Enterprise applications\j.d.中的计算机。 Edwards OneWorld\Classes 文件夹。  
  
## <a name="step-2-configure-biztalk-send-ports"></a>第 2 步：配置 BizTalk 发送端口  
接下来，验证 JD Edwards OneWorld 适配器已安装，并且创建发送端口。  

1. 打开**BizTalk Server 管理**，展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  
  
   确认**JDE_OneWorld**列出适配器。 如果未安装 JD Edwards OneWorld 适配器，用于企业应用程序 （请参阅前面的"先决条件"部分） 安装的 BizTalk 适配器。 安装适配器后，右键单击**适配器**，然后单击**新建-适配器**安装 JD Edwards OneWorld 适配器。 重新启动主机实例这才会生效。  
  
2. 展开**应用程序**，然后展开**BizTalk Application 1**。  
  
3. 右键单击**发送端口**，单击**新建**，然后单击**静态要求响应发送端口**。为这些字段中输入以下值：  
  
   1.  **名称：**  `JDE_OneWorldPort`  
  
   2.  **类型：**  `JDE_OneWorld`  
  
   3.  **发送处理程序：**  `BizTalkServerApplication`  
  
   4.  **发送管道：**  `XMLTransmit`  
  
   5.  **接收管道：**  `XMLReceive`  
  
4. 单击“配置” ，然后输入以下属性值：  
  
   1. **主机：** \<输入你的 JDEOW 主机名\>  
  
   2. **JAVA_HOME:** `C:\j2sdk1.4.2_08`  
  
   3. **JDEdwards 环境：** \<输入您的 JDEOW 环境\>  
  
   4. **JDEdwards JAR 文件：** \<输入的 JAR 文件的完整路径\>  
  
       `C:\JDEOWJars\BTSLIBInterop.jar; C:\JDEOWJars\Connector.jar; C:\JDEOWJars\Kernel.jar;C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards OneWorld®\Classes\JDEJAccess.jar`  
  
   5. **密码：** 使用下拉列表，然后输入您的 JD Edwards OneWorld 密码。  
  
   6. **端口：**  `6009`  
  
   7. **用户名：** \<输入 JD Edwards 用户名\>  
  
      ![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")  
  
5. 选择**确定**以关闭**发送端口属性**。  
  
## <a name="step-3-create-a-biztalk-orchestration-project"></a>步骤 3：创建 BizTalk 业务流程项目  
接下来，创建的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，并要处理之间的通信的项目中配置业务流程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 JD Edwards OneWorld 系统。 你将添加发送端口和接收端口，生成项目，然后部署项目。  

  
1. 打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，并在 C:\LABS 文件夹中创建新的 BizTalk 项目。 在“文件”  菜单上，单击“新建” 。 此时将显示“新建项目”  对话框。 在“发送端口属性”  选择“空的 BizTalk Server 项目”。  输入`JDE_OW_Test`作为唯一项目名称，然后单击**确定**。  
  
2. 在解决方案资源管理器中，右键单击该项目，单击“添加” ，然后单击“添加生成的项” 。 在类别窗格中，选择**添加适配器元数据**，在模板窗格中选择**添加适配器元数据**，然后单击**添加**。  
  
3. 在添加适配器向导中，选择**JD Edwards OneWorld**适配器，选择**JDE_OneWorldPort**发送端口，在前面的过程中创建，然后单击**下一步**.  
  
    ![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")  
  
4. 上**选择导入的服务**页上，打开**JD Edwards OneWorld**。 JDEOW 系统使用 BrowsingAgent 程序通过适配器联系。 BrowsingAgent 返回以下服务。  
  
    ![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")  
  
5. 展开**CALLBSFN**向下滚动到**N0100041-Address Book MBF**。 选择 N0100041，然后单击**完成**。  
  
6. 在解决方案资源管理器，没有新的 BizTalk 业务流程包含两个新关联的架构文件。 这些文件由添加适配器向导创建。 双击“BizTalk Orchestration.odx”文件以打开业务流程。   
  
    ![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")  
  
   此业务流程接受作为输入文件适配器用于 JD Edwards OneWorld 系统设置格式的 XML 文件中。 业务流程使用 JD Edwards OneWorld 适配器将 XML 文件发送到 JD Edwards OneWorld 系统。 JD Edwards OneWorld 处理查询并生成一个包含结果的输出 XML 文件。 此 XML 文件返回到业务流程通过 JD Edwards OneWorld 适配器，文件适配器在磁盘上将 XML 文件写入到输出位置。  
  
   要完成业务流程，你需要创建并配置用于接收和发送 XML 文件的端口。 首先，配置接收端口，以将文件适配器用于将输入到业务流程从磁盘中包含的查询的 XML。  
  
#### <a name="configure-a-receive-port-to-accept-the-input-xml-file"></a>配置接收端口，以接受 XML 输入的文件  
  
1. 双击“BizTalk Orchestration.odx”文件以打开业务流程。   
  
2. 在 BizTalk Orchestration.odx 文件中，右键单击左侧的端口图面，然后单击**新建配置的端口**。 这将启动端口配置向导。 在“欢迎使用端口配置向导”  页上，单击“下一步” 。  
  
3. 上**端口属性**页上，输入`JDE_File_In`有关**名称**，然后单击**下一步**。  
  
4. 在“选择端口类型”  页中，选择“新建端口类型” ，然后输入或选择以下属性值：  
  
    **端口类型名称**: `JDE_FileIn_Port`  
  
    **通信模式**:**One Way**  
  
    **访问限制**:**内部-仅限于此项目**  
  
5. 单击“下一步”转至“端口绑定”页  ，然后选择以下属性值：    
  
    **端口通信方向**:**我将始终接收此端口上的消息**  
  
    **端口绑定**:**以后指定**  
  
6. 单击“下一步” ，然后单击“完成” 。  
  
   接下来，创建用于发送包含对 JD Edwards OneWorld 系统的查询的初始 XML 输入的文件的发送/接收端口。 此端口还将接收包含到 JD Edwards OneWorld 系统调用的查询结果的输出 XML 文件。  
  
#### <a name="configure-a-sendreceive-port-to-interface-with-jd-edwards-oneworld"></a>使用 JD Edwards OneWorld 配置到接口发送/接收端口  
  
1. 在 BizTalk Orchestration.odx 文件中，右键单击右侧端口图面，然后单击**新建配置的端口**。 这将启动端口配置向导。 在“欢迎使用端口配置向导”  页上，单击“下一步” 。  
  
2. 在“选择端口类型”  页上，选择“使用现有端口类型” 。 下**可用端口类型**，选择**JD_OW_Test.N0100041**，然后单击**下一步**。  
  
    ![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")  
  
3. 选择以下属性值：  
  
    **端口通信方向**:**我将发送请求并接收响应**  
  
    **端口绑定**:**以后指定**  
  
4. 单击“下一步” ，然后单击“完成” 。 端口图面上将看到端口和可用的方法。  
  
   最后，配置发送端口以通过文件适配器用于输出包含到磁盘的查询结果的 XML。  
  
#### <a name="configure-a-send-port-to-output-the-xml-file-to-disk"></a>配置发送端口输出到磁盘的 XML 文件  
  
1. 在 BizTalk Orchestration.odx 文件中，右键单击左侧的端口图面，然后单击**新建配置的端口**。 这将启动端口配置向导。 在“欢迎使用端口配置向导”  页上，单击“下一步” 。  
  
2. 上**端口属性**页上，输入`JDE_FileOut`有关**名称**，然后单击**下一步**。  
  
3. 在“选择端口类型”  页中，选择“新建端口类型” ，然后输入或选择以下属性值：  
  
    **端口类型名称**: `JDE_FileOut_Port`  
  
    **通信模式**:**One Way**  
  
    **访问限制**:**内部-仅限于此项目**  
  
4. 单击“下一步”转至“端口绑定”页  ，然后选择以下属性值：    
  
    **端口通信方向**:**我始终在发送消息此端口上**  
  
    **端口绑定**:**以后指定**  
  
5. 单击“下一步” ，然后单击“完成” 。  
  
   端口图面上显示的是新的端口与用于 JD Edwards OneWorld 服务的可用方法。 随后将指定 JD Edwards OneWorld 适配器发送和接收来自 JD Edwards OneWorld 系统的文件。  
  
   **JDE_File_In**并**JDE_File_Out**您刚才创建需要端口关联的消息类型。  
  
#### <a name="assign-message-types-to-the-ports"></a>分配到的端口的消息类型  
  
1. 在左侧的端口图面上, **JDE_File_In**端口上，单击**请求**。 在属性窗口中，展开**消息类型**，展开**多部分消息**，然后单击**JDE_OW_TestAddressBookMasterMBF**。  
  
2. 在左侧的端口图面上, **JDE_File_Out**端口上，单击**请求**。 在属性窗口中，展开**消息类型**，展开**多部分消息**，然后单击**JDE_OW_TestAddressBookMasterMBFResponse**。  
  
   将两个**发送**形状和两个**接收**形状插入业务流程，以链接到的端口。  
  
#### <a name="add-send-and-receive-shapes"></a>添加发送和接收形状  
  
1.  将工具箱中的“接收”  组件拖放到业务流程的起点（绿色圆圈）下。 单击**接收**形状，然后在属性窗口中输入`Get_File`有关**名称**，并设置**激活**到`true`。 执行此操作后，此接收端口上收到传入文档时将激活业务流程。  
  
2.  拖动**发送**组件从工具箱拖放立即**GetFileReceive**形状。 单击新建**发送**形状，然后在属性窗口中输入`SendToJDEOW`有关**名称**。  
  
3.  拖动**接收**组件从工具箱拖放立即**SendToJDEOWSend**形状。 单击**接收**形状，然后在属性窗口中输入`JDEOW_Resp`有关**名称**。  
  
4.  拖动**发送**组件从工具箱拖放立即**JDEOW_RespReceive**形状。 单击新建**发送**形状，然后在属性窗口中输入`FileToDisk`有关**名称**。  
  
     ![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")  
  
5.  连接**JDE_FileIn**到端口**GetFileReceive**组件。  
  
6.  连接**JDE_FileOut**到端口**FileToDiskReceive**组件。  
  
7.  转到**业务流程视图**展开**消息**。 更改的标识符**Message_1**到`MsgToJDEOW`，并为**Message_2**到 `JDEOW_Resp.`  
  
8.  突出显示**SendToJDEOWSend**组件并将其**消息**属性设置为**MsgToJDEOW**。  
  
9. 突出显示**JDEOW_RespReceive**组件并将其**消息**属性设置为**JDEOW_Resp**。  
  
10. 连接**SendToJDEOW**到**请求**一部分**JDE_OW_Port**端口。  
  
11. 连接**JDEOW_Resp**到**响应**一部分**JDE_OW_Port**端口。  
  
     ![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")  
  
## <a name="step-4-build-and-deploy-the-project"></a>步骤 4：生成并部署项目  
 现在，BizTalk 项目已完成，你可以生成项目并将其部署在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]中。  
  
1.  启动**Visual Studio 命令提示符**。  
  
2.  若要生成项目时，需要一个强名称密钥文件。 在命令提示符处，输入以下命令以创建强名称密钥文件：  
  
     **sn -k labs.snk**  
  
3.  在解决方案资源管理器中右键单击**JD_OW_Test**项目，并单击**属性**以启动项目的项目设计器。  
  
4.  单击“签名”  选项卡。  
  
5.  选择“为程序集签名”  选项，单击下拉列表中的“选择强名称密钥文件”  选项，然后单击“浏览” 。  
  
6.  浏览以选择密钥文件“labs.snk” ，然后单击“打开” 。  
  
7.  单击项目设计器中的“部署”  选项卡。  
  
8.  设置**应用程序名称**到`JDE_OW_Test`。  
  
9. 在解决方案资源管理器中右键单击**JDE_OW_Test**项目，并单击**生成。**  
  
     ![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")  
  
10. 生成成功完成后，右键单击**XX_JD Edwards OneWorldQuery**项目，并单击**部署**。 在输出窗口中将显示以下输出：  
  
     ![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")  
  
## <a name="step-5-test-the-application-and-viewing-the-xml-output"></a>步骤 5：测试应用程序和查看 XML 输出  
 现在，你将测试你所创建和部署的应用程序。 你将创建用于启动业务流程进程的 XML 文件，然后将文件夹配置为接收和发送应用程序中的 XML 文件。 配置应用程序之后，将运行该应用程序并查看业务流程返回的 XML 文件。  
  
#### <a name="generate-the-xml-file-for-the-query"></a>生成查询的 XML 文件  
  
1.  在解决方案资源管理器中双击**N0100041Service_N0100041.xsd**以打开该文件。  
  
2.  右键单击**N0100041Service_N0100041.xsd** ，然后单击**属性**。 为“输出实例文件名”输入示例 XML 的  以下路径和文件名：  
  
     `C:\LABS\JDE_OW_TEST\SAMPLE.XML`  
  
3.  单击“确定” **。** 在属性窗口中，选择**\<架构\>** 并设置**根引用：** 到`AddressBookMasterMBF`。 这将导致生成的 XML 只包括**查询**xml。  
  
     ![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")  
  
4.  右键单击**N0100041Service_N0100041.xsd** ，然后单击**生成实例**。 这将生成**Sample.xml**文件。 此文件将放入接收位置，作为适配器启动业务流程进程的输入。  
  
#### <a name="configure-and-start-the-biztalk-application"></a>配置并启动 BizTalk 应用程序  
  
1. 配置用于接收传入文件和发送传出文件的文件夹。 转到**C:\LABS\JDE_OW_Test**并创建两个新的子文件夹名为`FileIn`和`FileOut`。  
  
2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。  
  
3. 右键单击**JDE_OW_Test**，然后单击**配置**。  
  
    ![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")  
  
4. 选择“Orchestration_1”  ，然后单击“主机”  下拉框。 选择“BizTalkServerApplication” 。  
  
5. 下**接收端口**，单击 **\<None\>**。 在下拉列表中，选择“新建接收端口” 。  
  
6. 有关**名称**，类型`JDE_FileIn_Port`，然后单击**确定**。 将出现一个消息框，表明你需要指定接收位置。 单击“确定”，然后单击“新建”。    
  
    ![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")  
  
7. 键入或选择以下属性值：  
  
    **名称**：JDE_`FileInLoc`  
  
    **类型**：**File**  
  
    **接收处理程序**:**BizTalkServerApplication**  
  
    **接收管道**:**XMLReceive**  
  
    ![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")  
  
8. 单击**配置**，类型`C:\LABS\JDE_OW_Test\FileIn`有关**接收文件夹**，然后单击**确定**三次。  
  
    ![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")  
  
9. 单击**\<无\>** 有关**JDE_OW_Port**下拉列表中。  
  
10. 选择**新发送端口**，然后选择或键入属性的以下值：  
  
     **名称**：`JDE_OW_Port`  
  
     **类型**：**JDE_OneWorld**  
  
     **发送处理程序**:**BizTalkServerApplication**  
  
     **管道**:**XMLTransmit**和**XMLReceive**  
  
11. 单击“配置” ，然后输入以下属性值：  
  
     **主机：** \<输入你的 JDEOW 主机名\>  
  
     **JAVA_HOME:** `C:\j2sdk1.4.2_08`  
  
     **JDEdwards 环境：** \<输入您的 JDEOW 环境\>  
  
     **JDEdwards JAR 文件：** <enter full path of JAR files>  
  
     `C:JDEOWJarsBTSLIBInterop.jar; C:JDEOWJarsConnector.jar; C:JDEOWJarsKernel.jar;C:Program FilesMicrosoft BizTalk Adapters for Enterprise ApplicationsJ.D. Edwards OneWorld®ClassesJDEJAccess.jar`  
  
     **密码：** 使用下拉列表，然后输入您的 JD Edwards OneWorld 密码。  
  
     **端口：**  `6009`  
  
     **用户名：** <enter your JD Edwards User Name>  
  
     ![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")  
  
12. 单击“确定”  两次以关闭对话框。  
  
13. 在配置 Applicationwindow 中，单击**\<无\>** 有关**JDE_FileOut**下拉列表中。  
  
14. 选择“新建发送端口”  ，然后键入或选择以下属性值：  
  
     **名称**：`FileOutPort`  
  
     **类型**：**File**  
  
     **发送处理程序**:**BizTalkServerApplication**  
  
     **发送管道**:**XMLTransmit**  
  
15. 单击“配置”  ，为“接收文件夹”键入`C:\Labs\JDE_OW_Test\FileOut` ， **C:\Labs\PS_Test\FileOut** 。为“文件名”保留“”，因为这会为每个消息生成唯一的文件。  ，  because this results in a unique file ， each message.  
  
     ![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")  
  
16. 单击“确定”三次  以关闭对话框。  
  
17. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右击**JDE_OW_Test**应用程序，，然后单击**启动**。  
  
#### <a name="test-the-orchestration"></a>测试业务流程  
  
1.  在中**C:\Labs\JDE_OW_Test**目录**Sample.xml**文件将显示为：  
  
     ![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")  
  
2.  编辑**Sample.xml**文件以删除以外的所有内容**cActionCode**并**mnAddressBookNumber**元素。  
  
     ![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")  
  
3.  有关**cActionCode**元素插入字母`i`。  
  
4.  有关**mnAddressBookNumber**插入数字`500`。  
  
5.  保存所做的更改并将文件复制到**C:\Labs\JDE_OW_Test\FileIn**文件夹。 这是启动业务流程的接收位置。  
  
6.  几秒钟后，应出现一个 XML 文件中**C:\Labs\JDE_OW_Test\FileOut**文件夹。 这应包含的所有记录的地址为 500。  
  
     ![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")  
  
     此返回的记录数据应与针对实验室 1 中的 JD Edwards OneWorld 系统的查询返回的数据匹配。 通过比较在实验室 1 中获取的记录，你可以验证**获取**方法正常工作。  
  
## <a name="summary"></a>总结  
 在此实验中，您首先验证，系统必备组件已正确设置了访问 JD Edwards OneWorld 系统。 然后，你使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 创建了包含业务流程的新 BizTalk 项目。 配置 BizTalk 业务流程，以使用 JD Edwards OneWorld 适配器从 JD Edwards OneWorld 系统中获取数据。 为配置业务流程，你创建了发送端口、接收端口和发送/接收端口。 您将这些端口绑定到 JD Edwards OneWorld 适配器，并将消息分配给相应的端口。  
  
 完成 BizTalk 项目后，你使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 来生成和部署该项目。 然后，你将配置新的应用程序并运行它来从 JD Edwards OneWorld 系统中获取数据。 若要验证在应用程序正常运行，与比较其输出 XML 文件从 JD Edwards OneWorld 系统在实验室 1 中收到的文件。