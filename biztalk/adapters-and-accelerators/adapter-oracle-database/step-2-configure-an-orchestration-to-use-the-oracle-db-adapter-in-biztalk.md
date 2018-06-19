---
title: 步骤 2： 在 BizTalk Server 管理控制台，以使用 Oracle 数据库适配器中配置业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 598b4ab0-ff22-4dfa-aa9c-774c60c90227
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b348a21a54ece0e5db736e18f60c9bed2b8d047d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215549"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-to-use-the-oracle-database-adapter"></a>步骤 2： 在 BizTalk Server 管理控制台，以使用 Oracle 数据库适配器中配置业务流程
![步骤 2 / 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **完成时间：** 10 分钟  
  
 **目标：** 在此步骤中，你将要执行以下任务：  
  
-   创建 WCF 自定义发送接收要发送和接收消息从 Oracle 数据库使用端口[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 配置此端口，以使用你在上一步中创建的映射。  
  
-   配置业务流程部署中使用 WCF 自定义端口的最后一步。  
  
## <a name="prerequisite"></a>前提条件  
  
-   你必须部署 BizTalk 业务流程你想要配置的 WCF 自定义端口。  
  
### <a name="to-create-a-wcf-custom-port"></a>若要创建的 WCF 自定义端口  
  
1.  生成对 Oracle 数据库使用的操作的架构时[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，绑定文件还添加到 BizTalk 项目。 你可以导入此绑定文件到你的 BizTalk 应用程序来创建 WCF 自定义发送-接收端口。 有关导入绑定文件的说明，请参阅[导入绑定](http://msdn.microsoft.com/library/4cac9267-8bd8-453b-96b4-5c038912463f)。  
  
2.  导入的绑定文件后下, 创建发送端口**发送端口**BizTalk Server 管理控制台中的文件夹。  
  
3.  右键单击 WCF 自定义端口，然后单击**属性**。  
  
4.  从发送端口属性对话框的左窗格中，单击**常规**选项卡。在右窗格中，单击**配置**。  
  
5.  在**WCF 自定义传输属性**对话框中，单击**凭据**选项卡，然后指定要连接到 Oracle 数据库的凭据。  
  
6.  单击 **“确定”**。  
  
7.  从发送端口属性对话框的左窗格中，单击**入站映射**。 从右窗格中，单击下的字段**映射**列中，从下拉列表中选择**ResponseMap**。  
  
     ![配置入站的映射](../../adapters-and-accelerators/adapter-oracle-database/media/a5e49da1-fe34-46fe-80ca-9316d217171a.gif "a5e49da1-fe34-46fe-80ca-9316d217171a")  
  
8.  从发送端口属性对话框的左窗格中，单击**出站映射**。 从右窗格中，单击下的字段**映射**列中，从下拉列表中选择**RequestMap**。  
  
     ![配置出站映射](../../adapters-and-accelerators/adapter-oracle-database/media/697b23d8-4231-4718-8a52-8013fac35e3e.gif "697b23d8-4231-4718-8a52-8013fac35e3e")  
  
9. 单击 **“确定”**。  
  
### <a name="to-configure-the-biztalk-application"></a>若要配置 BizTalk 应用程序  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，展开其中部署业务流程的 BizTalk 应用程序。  
  
2.  右键单击 BizTalk 应用程序，然后再选择**配置**。  
  
3.  从左窗格中，单击要配置业务流程。 从右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。  
  
4.  下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到 BizTalk Server 管理控制台中的物理端口。  
  
    1.  选择将放置请求消息的位置的文件端口。 BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。  
  
    2.  选择 BizTalk 业务流程放置包含从 Oracle 数据库响应的响应消息的位置的文件端口。  
  
    3.  选择你在本主题前面创建的 WCF 自定义发送端口。  
  
    4.  单击 **“确定”**。  
  
     有关配置应用程序的详细信息，请参阅"如何为配置应用程序"在[http://go.microsoft.com/fwlink/?LinkID=196961](http://go.microsoft.com/fwlink/?LinkID=196961)。  
  
## <a name="next-steps"></a>后续步骤  
 你现在已经完成迁移到将消息发送到使用基于 WCF 的 Oracle 数据库的 BizTalk 项目 vPrev BizTalk 项目[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 你现在必须通过以下方式测试迁移的 BizTalk 应用程序通过发送请求消息来执行对 Oracle 数据库中，插入操作中所述[步骤 3： 测试到 Oracle 数据库适配器已迁移的应用程序](../../adapters-and-accelerators/adapter-oracle-database/step-3-test-the-migrated-application-to-oracle-database-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
 [教程： 迁移 BizTalk 项目](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)