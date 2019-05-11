---
title: 教程：使用用于 PeopleSoft Enterprise 的 BizTalk 适配器将数据写入 PeopleSoft Enterprise |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 837dd4db-576d-41c1-9fe8-e1e46861270b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 152579975225efd803aa7f07613da8962048130a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396622"
---
# <a name="tutorial-using-the-biztalk-adapter-for-peoplesoft-enterprise-to-write-data-to-peoplesoft-enterprise"></a>教程：使用用于 PeopleSoft Enterprise 的 BizTalk 适配器将数据写入 PeopleSoft Enterprise
可以使用用于 PeopleSoft Enterprise 的 BizTalk 适配器将数据写入 PeopleSoft 系统接收来自贸易合作伙伴或内部应用程序的信息。 本演练描述说明了此功能的 SDK 示例。  

## <a name="prerequisites"></a>先决条件  

- Java 2 平台必须安装在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上运行用于 PeopleSoft Enterprise 的 BizTalk 适配器。  

- PeopleSoft Java Object Adapter JAR 文件中， **psjoa.jar**应复制到可以访问的文件夹[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上运行用于 PeopleSoft Enterprise 的 BizTalk 适配器。  

- [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 必须安装在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于 PeopleSoft Enterprise 的 BizTalk 适配器在运行，以便在生成和部署示例。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例选取一个文件夹中的 XML 文件、 将该文件发送到业务流程，，然后使用用于 PeopleSoft Enterprise 的 BizTalk 适配器以从 XML 文件中的数据在 PeopleSoft 系统中创建一条记录。  

## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 此示例设计中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和创建，用于说明适用于 PeopleSoft Enterprise 的 BizTalk 适配器使用 BizTalk 业务流程的基本功能。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 该示例位于以下文件夹：  

 \Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftOneWaySend  

 下表显示了本示例中的文件及其用途说明：  


|                               **Runtime 项目文件名**                                |                                                                                                                                                                           **运行时项目文件说明**                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                       OneWaySend.btproj，<br /><br /> OneWaySend.sln                       |                                                                                                                                                                      应用程序的项目和解决方案文件。                                                                                                                                                                      |
| LOCATIONService.xsd,<br /><br /> LOCATIONService_1.xsd,<br /><br /> LOCATIONService_2.xsd | 应用程序的架构文件。 **注意：** 在项目中的适配器架构文件最初创建使用**添加适配器元数据向导**。 添加适配器元数据向导的详细信息请参阅主题"如何添加适配器元数据向 BizTalk 项目"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档。 |
|                                 PeopleSoftOneWaySend.odx                                  |                                                                                                                                                                        使用应用程序的业务流程。                                                                                                                                                                         |
|                                 PeopleSoftOneWaySend.snk                                  |                                                                                                                                                                                强名称密钥文件。                                                                                                                                                                                |

## <a name="how-to-use-this-sample"></a>如何使用此示例  

#### <a name="create-a-new-instance-of-the-peoplesoft-enterprise-adapter"></a>创建 PeopleSoft Enterprise 适配器的新实例  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 单击**启动**，**所有程序**， [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]， **BizTalk Server 管理**。  

2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  

3. 右键单击**适配器**，然后指向**新建**，**适配器...** 若要显示**适配器属性**对话框。  

4. 输入一个值**名称**字段，例如**PeopleSoft**。  

5. 选择**PeopleSoft enterprise （)** 从列表中可用的适配器**适配器**下拉列表中单击**确定**。  

#### <a name="create-a-biztalk-send-port"></a>创建 BizTalk 发送端口  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**发送端口**。  

2. 右键单击**发送端口**，然后指向**新建**，**静态单向发送端口**以显示**发送端口属性**对话框。  

3. 输入一个值**名称**字段，例如**PeopleSoftOneWaySP**。  

4. 从中可用的适配器列表中选择 PeopleSoft 适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。  

   > [!NOTE]
   >  此值是在创建 PeopleSoft Enterprise 适配器时指定的名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

5. 输入以下值：**适配器必需属性**:  


   |       **属性**       |                                                                                                                                        **ReplTest1**                                                                                                                                         |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | 应用程序服务器路径  | PeopleSoft 服务器的计算机和端口位置，例如 / / PSServer:8888。 **注意：** 如果不指定端口号，则使用默认端口为 9000，以便在上例中您可以输入值 //PSServer 如果 PeopleSoft 服务器使用默认端口值 9000。 |
   |        JAVA_HOME         |                                                                                          与 Java 2 平台 SDK 文件，例如 C:\j2sdk1.4.2_08 相关联的主目录的路径                                                                                          |
   |         Password         |                                                                                                                 连接到 PeopleSoft 系统时使用的密码。                                                                                                                  |
   | PeopleSoft 8.x JAR 文件 |                                                                                          PeopleSoft Java Object Adapter JAR 文件的位置**psjoa.jar**，例如 C:\JARS\psjoa.jar。                                                                                          |
   |        “用户名”         |                                                                                                                    用于连接到 PeopleSoft 系统的用户名。                                                                                                                     |


6. 单击“确定” 。  

7. 选择**XML 传输**中的可用管道列表**发送管道**下拉列表中单击**确定**。  

8. 右键单击发送端口，然后单击**启动**以登记并启动发送端口。  

#### <a name="create-a-file-receive-port"></a>创建文件接收端口  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**接收端口**。  

2. 右键单击接收端口文件夹，然后单击**新建**，**单向接收端口**显示接收端口属性对话框。  

3. 输入一个值**名称**字段，例如**PeopleSoftOneWayFileRP**，然后单击**确定**。  

#### <a name="create-a-file-receive-location"></a>创建文件接收位置  

1.  创建一个文件夹以监视由文件接收位置，例如 C:\Filesource。  

2.  右键单击新接收端口，然后单击**新建**，**接收位置**以显示**接收位置属性**对话框。  

3.  输入一个值**名称**字段，例如**PeopleSoftOneWayFileRL**。  

4.  选择**文件**从列表中可用的适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。  

5.  输入您为前面创建的文件夹的位置**接收文件夹**属性，单击**确定**。  

6.  选择**XMLReceive**中的可用管道列表**接收管道**下拉列表框，然后单击**确定**。  

7.  右键单击接收位置，然后单击**启用**。  

#### <a name="modify-the-adapter-schema-target-namespace-property"></a>修改适配器架构目标命名空间属性  

1. 启动[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并打开 OneWaySend.sln。 单击**文件**，**打开**，**项目/解决方案...** 若要显示**打开项目**对话框。  

2. 浏览到 OneWaySend.sln 文件，单击以选择此文件，然后单击**打开**以打开包含示例项目的解决方案。  

3. 单击**视图**菜单，然后选择**解决方案资源管理器**以显示在解决方案资源管理器。  

4. 双击解决方案资源管理器以将其打开中的 LOCATIONService_1.xsd 文件。  

5. 右键单击**架构**节点的 LOCATIONService_1.xsd，然后选择**属性**菜单选项以显示架构的属性。  

6. 编辑**目标 Namespace**属性以使用适当的值的适配器名称，例如**Target Namespace**属性应按如下所示：  

   ```  
   http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]  
   ```  

    其中*PeopleSoft*是 PeopleSoft 适配器的名称，因为在 BizTalk 管理控制台中查看。  

   > [!IMPORTANT]
   >  如果已配置的值**目标 Namespace**与输入的文档实例中指定，则由处理输入的文档实例时，将发生路由失败的命名空间不匹配[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

#### <a name="generate-a-document-instance-from-the-adapter-schema"></a>从适配器架构生成文档实例  

1.  双击**LOCATIONService_1.xsd**在解决方案资源管理器在架构编辑器中打开该文件。  

2.  右键单击**\<架构\>** 节点在架构编辑器中，单击**属性**以显示该节点的属性。  

3.  选择**CreateEx**从列表中的可用节点**根引用**下拉框中。 这应这样做为了生成示例文档实例时它将生成从**CreateEx**架构节点。  

4.  右键单击解决方案资源管理器中的 LOCATIONService_1.xsd，然后单击**属性**。  

5.  在属性窗口中，单击以选中**输出实例文件名**下**常规**部分。  

6.  单击省略号按钮 （...） 以显示**选择输出文件**对话框。  

7.  指定的文件夹和输出文件实例名称，例如**C:\instance.xml**然后单击**保存**。  

    > [!NOTE]
    >  未指定为 file 接收位置在此处指定的文件夹的位置。  

8.  右键单击解决方案资源管理器中的 LOCATIONService_1.xsd，然后单击**生成实例**以在指定位置生成文档实例。  

9. 右键单击**\<架构\>** 节点在架构编辑器中，单击**属性**以显示该节点的属性。  

10. 选择 (**默认值)** 从列表中的可用节点**根引用**下拉框中。  

#### <a name="modify-the-generated-document-instance"></a>修改生成的文档实例  

1.  在诸如记事本之类的文本编辑器中打开生成的文档实例，并编辑文档实例，以确保这些字段中的数据将在 PeopleSoft 系统中生成唯一的记录，如下面的 XML 文件介绍了中的字段的内容定义位置的记录：  

    ```  
    <ns0:CreateEx xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
      <ns0:SETID>SHARE</ns0:SETID>  
      <ns0:LOCATION>9991</ns0:LOCATION>  
      <ns0:interactiveMode>true</ns0:interactiveMode>  
       <ns0:properties>  
        <ns0:LOCATION_TBL_sequence>  
          <ns0:LOCATION_TBL>  
            <ns0:COUNTRY>USA</ns0:COUNTRY>  
            <ns0:DESCR>Adapter Test</ns0:DESCR>  
            <ns0:EFFDT>2006-05-31</ns0:EFFDT>  
            <ns0:EFF_STATUS>A</ns0:EFF_STATUS>  
            <ns0:SETID>SHARE</ns0:SETID>  
          </ns0:LOCATION_TBL>  
        </ns0:LOCATION_TBL_sequence>  
      </ns0:properties>  
    </ns0:CreateEx>  
    ```  

    > [!NOTE]
    >  在上述示例中， *PeopleSoft*是 BizTalk 管理控制台中的适配器实际名称的占位符。  

2.  保存修改后的文档实例。  

#### <a name="build-and-deploy-the-project"></a>生成并部署项目  

1. 右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**属性**启动项目设计器。  

2. 单击**部署**选项卡。  

3. 输入适当的值**服务器**属性和**配置数据库**下的属性**BizTalk 组**。  

4. 右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**部署**以生成项目，并部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。  

#### <a name="bind-and-enlist-the-orchestration"></a>绑定并登记业务流程  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**业务流程**。  

2. 单击**刷新**按钮在 MMC 工具栏或按**F5**若要刷新在键盘上键[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。  

3. 双击业务流程以显示**业务流程属性**对话框。  

4. 单击**绑定**以显示业务流程的绑定选项对话框的左窗格中。  

5. 指定适当的值的绑定选项，例如：  


   |      **参数**       |        **ReplTest1**         |
   |--------------------------|--------------------------|
   |           主机           | BizTalkServerApplication |
   |     FileReceivePort      |  PeopleSoftOneWayFileRP  |
   | PeopleSoftOneWaySendPort |    PeopleSoftOneWaySP    |


6. 单击“确定”。  

#### <a name="start-the-orchestration"></a>启动业务流程  

- 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击该业务流程，然后单击**启动**以登记并启动业务流程。  

#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a>拖放到该文件所监视的文件夹的文档实例接收位置  

-   将文件接收位置的文件夹到先前创建的文档实例复制配置为监视。  

#### <a name="verify-that-the-peoplesoft-system-is-updated"></a>验证 PeopleSoft 系统已更新  

- 使用 PeopleSoft web 界面验证记录已创建从 XML 文件中的数据。  

  如果成功处理的文档实例，会发生以下事件序列：  

1.  文件适配器从文件夹中检索该文件，并将其发布到 MessageBox 作为 BizTalk 消息。  

2.  业务流程订阅此发布的消息，以便 BizTalk 消息引擎将激活业务流程的实例并将消息发送到业务流程实例。  

3.  业务流程实例处理使用业务流程中指定的逻辑消息，并将消息发布回 MessageBox。  

4.  PeopleSoft 发送端口订阅此发布消息，因此 BizTalk 消息引擎将消息发送到 PeopleSoft 发送端口。  

5.  发送端口将消息传递给 BizTalk 适配器，用于 PeopleSoft Enterprise。  

6.  用于 PeopleSoft Enterprise 的 BizTalk 适配器调用 CreateEx 方法来创建 XML 文件中使用的数据的记录。  

## <a name="see-also"></a>请参阅  
 [教程：使用用于 PeopleSoft Enterprise 的 BizTalk 适配器](../core/tutorials-using-biztalk-adapter-for-peoplesoft-enterprise.md)