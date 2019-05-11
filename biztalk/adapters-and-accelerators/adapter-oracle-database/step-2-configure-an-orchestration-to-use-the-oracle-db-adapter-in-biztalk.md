---
title: 第 2 步：若要使用 Oracle 数据库适配器的 BizTalk Server 管理控制台中配置业务流程 |Microsoft Docs
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
ms.openlocfilehash: 113d1b90f02961fd8ecdf5fd7ecc894e664b3796
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376000"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-to-use-the-oracle-database-adapter"></a>第 2 步：若要使用 Oracle 数据库适配器的 BizTalk Server 管理控制台中配置业务流程
![步骤 2 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")  
  
 **若要完成的时间：** 10 分钟。  
  
 **目标：** 在此步骤中，您可以执行以下任务：  
  
- 创建 WCF 自定义发送接收端口以发送和接收消息从 Oracle 数据库使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 配置此端口以使用在上一步中创建的映射。  
  
- 配置业务流程中使用 WCF 自定义端口的最后一步部署。  
  
## <a name="prerequisite"></a>先决条件  
  
-   你必须部署你想要配置 WCF 自定义端口的 BizTalk 业务流程。  
  
### <a name="to-create-a-wcf-custom-port"></a>若要创建的 WCF 自定义端口  
  
1. 生成对 Oracle 数据库使用的操作的架构时[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，绑定文件也添加到 BizTalk 项目。 您可以对此绑定文件导入到 BizTalk 应用程序来创建 WCF 自定义发送-接收端口。 有关导入绑定文件的说明，请参阅[导入绑定](http://msdn.microsoft.com/library/4cac9267-8bd8-453b-96b4-5c038912463f)。  
  
2. 导入绑定文件后下, 创建的发送端口**发送端口**BizTalk Server 管理控制台中的文件夹。  
  
3. 右键单击 WCF 自定义端口，然后单击**属性**。  
  
4. 从发送端口属性对话框的左窗格中，单击**常规**选项卡。在右窗格中，单击**配置**。  
  
5. 在中**Wcf-custom 传输属性**对话框中，单击**凭据**选项卡，然后指定用于连接到 Oracle 数据库的凭据。  
  
6. 单击“确定” 。  
  
7. 从发送端口属性对话框的左窗格中，单击**入站映射**。 在右窗格中，单击下的字段**地图**列中，从下拉列表中选择**ResponseMap**。  
  
    ![配置入站的映射](../../adapters-and-accelerators/adapter-oracle-database/media/a5e49da1-fe34-46fe-80ca-9316d217171a.gif "a5e49da1-fe34-46fe-80ca-9316d217171a")  
  
8. 从发送端口属性对话框的左窗格中，单击**出站映射**。 在右窗格中，单击下的字段**地图**列中，从下拉列表中选择**RequestMap**。  
  
    ![配置出站映射](../../adapters-and-accelerators/adapter-oracle-database/media/697b23d8-4231-4718-8a52-8013fac35e3e.gif "697b23d8-4231-4718-8a52-8013fac35e3e")  
  
9. 单击“确定” 。  
  
### <a name="to-configure-the-biztalk-application"></a>若要配置的 BizTalk 应用程序  
  
1. 在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，以及其中部署该业务流程的 BizTalk 应用程序。  
  
2. 右键单击 BizTalk 应用程序，然后选择**配置**。  
  
3. 从左窗格中，单击业务流程配置。 在右窗格中，从**主机**下拉列表中，选择 BizTalk 主机实例。  
  
4. 下**绑定**框中，将 BizTalk 业务流程的逻辑端口映射到 BizTalk Server 管理控制台中的物理端口。  
  
   1. 选择将存放请求消息的文件端口。 BizTalk 业务流程将使用请求消息并将其发送到 Oracle 数据库。  
  
   2. 选择 BizTalk 业务流程放置包含从 Oracle 数据库响应的响应消息的位置的文件端口。  
  
   3. 选择本主题中前面创建的 WCF 自定义发送端口。  
  
   4. 单击“确定” 。  
  
      有关配置应用程序的详细信息，请参阅"如何配置应用程序的"网址[ http://go.microsoft.com/fwlink/?LinkID=196961 ](http://go.microsoft.com/fwlink/?LinkID=196961)。  
  
## <a name="next-steps"></a>后续步骤  
 你现在已经完成迁移到 BizTalk 项目，将消息发送到使用基于 WCF 的 Oracle 数据库 vPrev BizTalk 项目的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 您现在必须测试已迁移的 BizTalk 应用程序通过发送请求消息以执行插入操作上，对 Oracle 数据库中所述[步骤 3:测试已迁移应用程序到 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/step-3-test-the-migrated-application-to-oracle-database-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程：迁移 BizTalk 项目](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)