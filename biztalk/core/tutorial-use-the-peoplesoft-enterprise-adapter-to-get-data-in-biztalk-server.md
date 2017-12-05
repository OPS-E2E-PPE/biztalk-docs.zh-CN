---
title: "教程： 使用 PeopleSoft 企业的 BizTalk 适配器从 PeopleSoft Enterprise 检索数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c173fa4c-911e-4fa3-813f-e8f36b0049a5
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 510ee984688d218e2c83b4e70dcdf737cd5566e2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-peoplesoft-enterprise-to-retrieve-data-from-peoplesoft-enterprise"></a>教程：使用 PeopleSoft Enterprise 的 BizTalk 适配器以从 PeopleSoft Enterprise 中检索数据
PeopleSoft Enterprise 的 BizTalk 适配器可以用于执行针对 PeopleSoft 系统的查询，并返回查询的结果。 本演练介绍了可演示此功能的 SDK 示例。  
  
## <a name="prerequisites"></a>先决条件  
  
-   Java 2 平台必须安装在 PeopleSoft Enterprise Geis 的 BizTalk 适配器正在运行的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上。  
  
-   PeopleSoft Java 对象适配器 JAR 文件中， **psjoa.jar**应复制到可以访问的文件夹[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]PeopleSoft 企业 BizTalk 适配器上运行。  
  
-   为了构建和部署示例，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 必须安装在运行有 PeopleSoft Enterprise 的 BizTalk 适配器的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例从文件夹中选取 XML 文件，将文件发送到业务流程中，然后使用 PeopleSoft Enterprise 的 BizTalk 适配器来执行针对 PeopleSoft 系统的查询。 查询的结果将写入到 XML 文件中。  
  
## <a name="how-this-sample-is-designed-and-why"></a>本示例旨在如何以及为何  
 此示例使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 设计和创建，用于说明将 PeopleSoft Enterprise 的 BizTalk 适配器用于 BizTalk 业务流程的基本功能。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例位于以下文件夹中：  
  
 \Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftTwoWaySend  
  
 下表显示了本示例中的文件及其用途说明：  
  
|**运行时项目文件名**|**运行时项目文件说明**|  
|----------------------------------|------------------------------------------|  
|TwoWaySend.btproj,<br /><br /> TwoWaySend.sln|应用程序的项目和解决方案文件。|  
|LOCATIONService.xsd，<br /><br /> LOCATIONService_1.xsd，<br /><br /> LOCATIONService_2.xsd|应用程序的架构文件。 **注意：**项目中的适配器架构文件最初创建使用**添加适配器元数据向导**。 有关“添加适配器元数据向导”的详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的“如何向 BizTalk 项目添加适配器元数据”主题。|  
|PeopleSoftTwoWaySend.odx|应用程序使用的业务流程。|  
|PeopleSoftTwoWaySend.snk|强命名密钥文件。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
  
#### <a name="create-a-new-instance-of-the-peoplesoft-enterprise-adapter"></a>创建 PeopleSoft Enterprise 适配器的新实例  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 单击**启动**，**程序**， **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]， **BizTalk Server 管理**。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  
  
3.  右键单击**适配器**和指向**新建**，**适配器**以显示**适配器属性**对话框。  
  
4.  输入一个值**名称**字段，例如**PeopleSoft**。  
  
5.  选择**PeopleSoft Enterprise(r)**从列表中可用的适配器**适配器**下拉列表中单击**确定**。  
  
#### <a name="create-a-solicit-response-biztalk-send-port"></a>创建要求响应 BizTalk 发送端口  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**发送端口**。  
  
2.  右键单击**发送端口**和指向**新建**，**静态请求-响应发送端口**以显示**发送端口属性**对话框。  
  
3.  输入一个值**名称**字段，例如**PeopleSoftTwoWaySP**。  
  
4.  从中的可用适配器的列表中选择 PeopleSoft 适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。  
  
    > [!NOTE]
    >  此值是在管理控制台创建 PeopleSoft Enterprise 适配器时指定的名称。  
  
5.  输入以下值**适配器所需属性**:  
  
    |**属性**|**值**|  
    |------------------|---------------|  
    |应用程序服务器路径|PeopleSoft Server 的计算机和端口位置，例如 //PSServer:8888。 **注意：**如果未指定端口号，使用 9000 的默认端口，因此在上面的示例可能输入值 //PSServer 如果 PeopleSoft 服务器使用 9000 的默认端口值。|  
    |JAVA_HOME|与 Java 2 平台 SDK 文件相关联的主目录路径，例如 C:\j2sdk1.4.2_08|  
    |密码|连接到 PeopleSoft 系统时使用的密码。|  
    |PeopleSoft 8.x JAR 文件|文件的位置 PeopleSoft Java 对象适配器 JAR， **psjoa.jar**，例如 C:\JARS\psjoa.jar。|  
    |用户名|用于 连接到 PeopleSoft 系统的用户名 。|  
  
6.  单击 **“确定”**。  
  
7.  选择**XMLTransmit**从管道中提供的列表的管道**发送管道**下拉列表。  
  
8.  选择**XMLReceive**从管道中提供的列表的管道**接收管道**下拉列表中单击**确定**。  
  
9. 右键单击发送端口，然后单击**启动**登记和启动发送端口。  
  
#### <a name="create-a-one-way-biztalk-send-port"></a>创建单向 BizTalk 发送端口  
  
1.  创建发送端口使用的目标文件夹，例如 C:\Files\Out。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**发送端口**。  
  
3.  右键单击**发送端口**和指向**新建**，**静态单向发送端口**以显示**发送端口属性**对话框。  
  
4.  输入一个值**名称**字段，例如**PeopleSoftTwoWayFileSP**。  
  
5.  选择**文件**从列表中的可用适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。  
  
6.  输入以前为创建的文件夹的位置**目标文件夹**属性，然后单击**确定**。  
  
7.  选择**XMLTransmit**从管道中提供的列表的管道**发送管道**下拉列表中单击**确定**。  
  
8.  右键单击发送端口，然后单击**启动**登记和启动发送端口。  
  
#### <a name="create-a-file-receive-port"></a>创建文件接收端口  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**接收端口**。  
  
2.  右键单击接收端口文件夹，然后单击**新建**，**单向接收端口**以显示接收端口属性对话框。  
  
3.  输入一个值**名称**字段，例如**PeopleSoftTwoWayFileRP**，然后单击**确定**。  
  
#### <a name="create-a-file-receive-location"></a>创建文件接收位置  
  
1.  创建由文件接收位置监视的文件夹，例如 C:\Files\In。  
  
2.  右键单击新的接收端口，然后单击**新建**，**接收位置**以显示**接收位置属性**对话框。  
  
3.  输入一个值**名称**字段，例如**PeopleSoftTwoWayFileRL**。  
  
4.  选择**文件**从列表中的可用适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。  
  
5.  输入以前为创建的文件夹的位置**接收文件夹**属性，然后单击**确定**。  
  
6.  选择**XMLReceive**从列表中的可用管道**接收管道**下拉列表框中，单击**确定**。  
  
7.  右键单击接收位置，然后单击**启用**。  
  
#### <a name="modify-the-adapter-schema-target-namespace-property"></a>修改适配器架构目标命名空间属性  
  
1.  启动[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并打开 TwoWaySend.sln。 单击**文件**，**打开**，**项目/解决方案**以显示**打开项目**对话框。  
  
2.  浏览到 TwoWaySend.sln 文件，单击以选择此文件，然后单击**打开**以打开包含示例项目的解决方案。  
  
3.  单击**视图**菜单，然后选择**解决方案资源管理器**以显示解决方案资源管理器。  
  
4.  双击“解决方案资源管理器”中的 LOCATIONService_1.xsd 文件以将其打开。  
  
5.  右键单击**架构**LOCATIONService_1.xsd 和选择节点**属性**菜单选项，以显示适用于架构的属性。  
  
6.  编辑**目标 Namespace**属性用于适当的值的适配器名称，例如**目标 Namespace**属性应阅读，如下所示：  
  
    ```  
    http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]  
    ```  
  
     其中*PeopleSoft*是 PeopleSoft 适配器的名称，因为在中查看[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
    > [!IMPORTANT]
    >  如果的配置的值**目标 Namespace**与指定的输入的文档实例中，然后处理的输入的文档实例时，将发生路由故障的命名空间不匹配[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
#### <a name="generate-a-document-instance-from-the-adapter-schema"></a>从适配器架构生成文档实例  
  
1.  双击**LOCATIONService_1.xsd**在解决方案资源管理器，以在架构编辑器中打开该文件。  
  
2.  右键单击**\<架构\>**节点在架构编辑器中和单击**属性**以显示节点的属性。  
  
3.  选择**获取**从列表中的可用节点**根引用**下拉框。 这应这样做为了在你生成的示例文档实例时它将从生成**获取**节点的架构。  
  
4.  右键单击**LOCATIONService_1.xsd**在解决方案资源管理器，然后单击**属性**以在属性窗口中显示属性。  
  
5.  在属性窗口中，单击以选中**输出实例文件名**选项。  
  
6.  单击省略号按钮 （…） 以显示**选择输出文件**对话框。  
  
7.  指定的文件夹和输出文件实例的名称，例如**C:\instance.xml**单击**保存**。  
  
    > [!NOTE]
    >  请勿指定为此处的文件接收位置指定的文件夹位置。  
  
8.  右击 LOCATIONService_1.xsd 在解决方案资源管理器中的，单击**生成实例**在指定的位置生成文档实例。  
  
9. 右键单击**\<架构\>**节点在架构编辑器中和单击**属性**以显示节点的属性。  
  
10. 选择 (**默认)**从列表中的可用节点**根引用**下拉框。  
  
#### <a name="modify-the-generated-document-instance"></a>修改生成的文档实例  
  
1.  在文本编辑器（如记事本）中打开生成的文档实例，并编辑文档实例的内容，以确保这些字段中的数据将返回现有记录：  
  
    ```  
    <ns0:Get xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
    <ns0:SETID>SHARE</ns0:SETID>  
    <ns0:LOCATION>WFKLOC</ns0:LOCATION>  
    <ns0:getHistory>true</ns0:getHistory>  
    </ns0:Get>  
    ```  
  
    > [!NOTE]
    >  在上例中， *PeopleSoft*是适配器的实际名称的占位符，如在 BizTalk 管理控制台中查看。 *共享*和*WFKLOC*是用于标识特定记录 PeopleSoft 系统中的值的占位符。  
  
2.  保存修改后的文档实例。  
  
#### <a name="build-and-deploy-the-project"></a>生成并部署项目  
  
1.  右键单击解决方案资源管理器中的 TwoWaySend 项目，然后单击**属性**以显示项目设计器中为该项目。  
  
2.  单击**部署**项目设计器中的选项卡。  
  
3.  输入适当的值为**服务器**属性和**配置数据库**下的属性**BizTalk 组**。  
  
4.  右键单击解决方案资源管理器中的 TwoWaySend 项目，然后单击**部署**以生成项目并将其部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。  
  
#### <a name="bind-and-enlist-the-orchestration"></a>绑定并登记业务流程  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**业务流程**。  
  
2.  单击**刷新**按钮[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台工具栏或按**F5**密钥刷新你键盘上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。  
  
3.  双击要显示的业务流程**业务流程属性**对话框。  
  
4.  单击**绑定**显示业务流程的绑定选项对话框的左窗格中。  
  
5.  指定绑定选项的适当值，例如：  
  
    |**参数**|**值**|  
    |-------------------|---------------|  
    |主机|BizTalkServerApplication|  
    |FileReceivePort|PeopleSoftTwoWayFileRP|  
    |PeopleSoftTwoWaySend678|PeopleSoftTwoWaySP|  
    |ResponsePort|PeopleSoftTwoWayFileSP|  
  
6.  单击“确定”。  
  
#### <a name="start-the-orchestration"></a>启动业务流程  
  
-   在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击业务流程，然后单击**启动**登记和启动业务流程。  
  
#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a>将文档实例拖到由文件接收位置监视的文件夹  
  
-   将以前创建的文档实例复制到文件接收位置配置为监视的文件夹中。  
  
#### <a name="verify-that-the-document-instance-was-processed-by-the-biztalk-adapter-for-peoplesoft-enterprise"></a>验证文档实例是否由 PeopleSoft Enterprise 的 BizTalk 适配器处理。  
  
-   打开将文件发送端口配置为发送到的目标文件夹，并验证是否已生成输出文档。 此文件应包含 PeopleSoft Enterprise 的 BizTalk 适配器处理的查询结果。  
  
 成功处理文档实例后，会发生以下事件序列：  
  
1.  文件适配器从文件夹中检索文件，并作为 BizTalk 消息将其发布到 MessageBox。  
  
2.  业务流程会订阅此发布的消息，以便 BizTalk 消息引擎能够激活业务流程的实例，并将该消息发送到业务流程实例。  
  
3.  业务流程实例将此消息发布回 MessageBox。  
  
4.  要求响应发送端口会订阅此发布的消息，因此 BizTalk 消息引擎会将消息发送到 PeopleSoft 发送端口中。  
  
5.  发送端口会将消息交给适用于 PeopleSoft Enterprise 的 BizTalk 适配器。  
  
6.  PeopleSoft Enterprise 的 BizTalk 适配器会使用定义在输入文件中的参数针对 PeopleSoft 系统执行 Get 语句。  
  
7.  PeopleSoft Enterprise 的 BizTalk 适配器会为业务流程中的要求响应端口以响应消息形式返回 Get 语句的结果。  
  
8.  业务流程将结果集发布到 MessageBox。  
  
9. 文件发送端口会订阅此消息，以便 BizTalk 能够将消息发送到文件适配器。  
  
10. 文件适配器将包含结果集的消息写入到指定的输出文件夹。  
  
## <a name="see-also"></a>另请参阅  
 [教程：使用用于 PeopleSoft Enterprise 的 BizTalk 适配器](../core/tutorials-using-biztalk-adapter-for-peoplesoft-enterprise.md)