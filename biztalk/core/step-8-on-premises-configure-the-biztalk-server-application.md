---
title: 步骤 8 （本地）：配置 BizTalk Server 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 2015-12-08
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5109fb54-8453-444f-bc9c-070a65053397
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccff5ca7f7f101eb5b203196449ce1cbb1834b49
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258636"
---
# <a name="step-8-on-premises-configure-the-biztalk-server-application"></a>步骤 8 （本地）：配置 BizTalk Server 应用程序
上一步中创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程。 在此步骤中，将生成、 部署和配置应用程序。  

## <a name="build-and-deploy-the-application"></a>生成和部署应用程序  

1.  在 Visual Studio 中，右键单击解决方案名称，在解决方案资源管理器，然后单击**生成**。  

2.  部署过程要求程序集强签名。  必须将项目与一个强名称程序集密钥文件相关联来签名你的程序集。  

    1.  在解决方案资源管理器中右键单击**OrderProcessingDemo**项目，并单击**属性**。  

    2.  单击**签名**选项卡，然后选择**程序集签名**复选框。  

    3.  从下拉列表中**选择强名称密钥文件**框中，选择**\<新建...\>**.  

    4.  在中**创建强名称密钥**对话框框中，输入密钥文件的名称，例如`OrderProcessingDemo.snk`。 清除用于保护包含密码的密钥文件复选框，然后单击**确定**。  

3.  单击**部署**选项卡上，在右侧的框中**应用程序名称**，类型`OrderProcessingDemo`。  

4.  从下拉列表右侧的框中**重新部署**，选择**True**。  

5.  在解决方案资源管理器中右键单击**OrderProcessingDemo**，然后单击**部署**。  输出窗口应显示：  

    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  

    ```  

## <a name="configure-the-application"></a>配置应用程序  

1. 单击**启动**，依次指向**所有程序**，指向**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。  

2. 在控制台树中的左窗格上，依次展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**刷新**。  

3. 展开**BizTalk 组**，展开**应用程序**，展开**OrderProcessingDemo**，然后单击**业务流程**。 你将看到**OrderProcessingDemo.OrderProcessing**部署业务流程。  

4. 在业务流程，创建一个逻辑端口 (**ReceiveSO**) 从服务总线队列接收消息。 在此步骤中，创建物理接收端口映射到逻辑端口。  

   1. 从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在**OrderProcessingDemo**节点，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  

   2. 在 **“常规”** 选项卡上，请执行下列操作：  


      |                使用此选项                |     执行的操作      |
      |----------------------------------------|---------------------|
      |                **名称**                | 类型**ReceiveSO**。 |
      | **为失败消息启用路由功能** |       （清除）       |


   3. 单击**接收位置**，然后单击**新建**。  

   4. 从接收位置 1 – 接收位置属性对话框中，执行以下步骤：  


      |       使用此选项       |              执行的操作              |
      |----------------------|--------------------------------------|
      |       **名称**       |      类型**ReceiveOrders_SO**。      |
      |       **类型**       |       选择**SB 消息**。       |
      | **接收处理程序**  | 选择“BizTalkServerApplication” 。 |
      | **接收管道** |        选择**XMLReceive**。        |


   5. 单击**配置**。  

   6. SB 消息传输属性对话框中，从上**常规**选项卡上，对于**队列或订阅 URL**，输入**sb://mynamespace.servicebus.appfabriclabs.com/queueordersedi**. 在这里， *mynamespace*是服务总线命名空间和*queueordersedi*是你在中创建的服务总线队列[步骤 3 (Azure):创建服务总线队列](../core/step-3-for-azure-create-a-service-bus-queue.md)。  

   7. SB 消息传输属性对话框中，从上**身份验证**选项卡上，指定以下值：  

      |使用此选项|执行的操作|  
      |--------------|----------------|  
      |**访问控制服务 STS Uri**|类型 `https://mynamespace-sb.accesscontrol.appfabriclabs.com/`|  
      |**颁发者名称**|指定颁发者名称。 通常此值设置为`owner`。|  
      |**颁发者密钥**|指定的颁发者密钥。|  

      > [!NOTE]
      >  你可以获取的值的队列 URL、 ACS URL、 颁发者名称和密钥[Windows Azure CTP 管理门户](http://go.microsoft.com/fwlink/p/?LinkId=202886)。  

   8. 单击**确定**直到您退出所有对话框。  

5. 在业务流程，创建一个逻辑端口 (**SendToSQL**) 将消息发送到**SalesOrder**数据库表。 在此步骤中，您将创建一个物理发送端口映射到逻辑端口。  

   1. 从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在**OrderProcessingDemo**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  

   2. 在常规选项卡上，执行以下步骤：  


      |     使用此选项      |              执行的操作              |
      |-------------------|--------------------------------------|
      |     **名称**      |         类型**SendToSQL**。          |
      |     **类型**      |         选择**WCF SQL**。          |
      | **发送处理程序**  | 选择**BizTAlkServerApplication**。 |
      | **发送管道** |     选择**PassThruTransmit**。     |


   3. 单击**配置**。  

   4. 从 WCF SQL 传输属性上**常规**选项卡上，执行以下操作：  


      |     使用此选项      |                                                                                                                                                                                    执行的操作                                                                                                                                                                                    |
      |-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      | **地址 (URI)** | 类型**mssql://computername/database_instance_name/databasename**。 例如，若要连接到**DemoDB**默认数据库实例下运行的本地计算机上的数据库中，输入 `mssql://.//DemoDB`<br /><br /> 有关详细信息，请参阅[创建 SQL Server 连接 URI](../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。 |
      |    **操作**     |                                                                                                                                                                     类型**TableOp/Insert/dbo/SalesOrder**。                                                                                                                                                                      |


   5. 从 WCF SQL 传输属性上**凭据**选项卡上，选择**不使用单一登录**，并指定凭据 （区分大小写） 以连接到 SQL Server 数据库中指定连接字符串。 如果你想要使用 Windows 身份验证进行连接，将凭据留空。  

   6. 单击**确定**直到您退出所有对话框。  

6. 在业务流程，创建一个逻辑端口 (**SendToFile**) 将消息发送到共享的文件位置。 在此步骤中，您将创建一个物理发送端口映射到逻辑端口。  

   1. 从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在**OrderProcessingDemo**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  

   2. 在常规选项卡上，执行以下步骤：  


      |     使用此选项      |              执行的操作              |
      |-------------------|--------------------------------------|
      |     **名称**      |         类型**SendToFile**。         |
      |     **类型**      |           选择**文件**。           |
      | **发送处理程序**  | 选择**BizTAlkServerApplication**。 |
      | **发送管道** |       选择**XML 传输**。       |


   3. 单击**配置**。  

   4. 从文件传输属性中，执行以下步骤：  


      |      使用此选项      |                        执行的操作                        |
      |--------------------|----------------------------------------------------------|
      | **接收文件夹** | 指定你想要发送消息的位置。 |
      |   **文件名**    |               保留 **%MessageID%.xml**。                |


   5. 单击**确定**直到您退出所有对话框。  

7. 现在必须将绑定在一起以配置应用程序的物理和逻辑端口。  

   1. 从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**OrderProcessingDemo**，然后单击**配置**。  

   2. 配置应用程序，在左窗格中，单击**OrderProcessing**。  

   3. 使用下表中的值配置该应用程序。  


      |            使用此选项             |             执行的操作              |
      |---------------------------------|-------------------------------------|
      |          有关**主机**           | Select **BizTalkServerApplication** |
      | 对于逻辑端口**ReceiveSO**  | 选择物理端口**ReceiveSO**  |
      | 对于逻辑端口**SendToSQL**  | 选择物理端口**SendToSQL**  |
      | 对于逻辑端口**SendToFile** | 选择物理端口**SendToFile** |


   4. 单击**确定**保存配置。  

## <a name="start-the-application"></a>启动应用程序  

1. 从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**OrderProcessingDemo**，然后单击**启动**。  

2. 从对话框中，单击**启动**。  

## <a name="see-also"></a>请参阅  
 [教程 4：创建混合应用程序使用 BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)