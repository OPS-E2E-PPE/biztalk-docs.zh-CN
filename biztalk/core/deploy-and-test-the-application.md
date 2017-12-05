---
title: "部署和测试应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2c86d5f-1849-4b7d-8061-23f156245f5b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d93284823c2ce5d0c00a1601a5b9ae0aac4643c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="deploy-and-test-the-application"></a>部署并测试应用程序
> [!NOTE]
>  本教程仅适用于 BizTalk Server。  
  
 在本主题中，我们将生成、部署、配置并测试 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序。  
  
## <a name="build-and-deploy-the-application"></a>生成并部署应用程序  
  
1.  在解决方案资源管理器，右键单击 BizTalk 项目名称，，然后单击**属性**。  
  
2.  在“属性”页上，单击“签名”选项卡，选中“为程序集签名”复选框，然后从下拉菜单中选择新建一个强名称密钥文件的选项。 按照提示创建此文件。  
  
3.  保存对项目所做的更改。 在解决方案资源管理器，右键单击解决方案名称，然后单击**生成解决方案**。  
  
4.  成功生成项目后，在解决方案资源管理器，右键单击解决方案名称，然后单击**部署解决方案**。  
  
## <a name="configure-the-application"></a>配置应用程序  
 若要配置该应用程序，请在 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]中创建发送和接收端口，然后将这些端口绑定到业务流程以及作为业务流程的一部分而创建的逻辑发送/接收端口。  
  
1.  创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序用来接收 JSON 采购订单的接收端口。  
  
    1.  在[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 应用程序 1**，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**.  
  
    2.  提供接收端口的名称，然后从左侧的平移中，单击**接收位置**。 在**接收位置**选项卡上，单击**新建**。  
  
    3.  指定接收位置的名称，请选择与具有端口类型**文件**，然后单击**配置**。  
  
    4.  提供接收位置将从中选取传入 JSON 采购订单的文件夹位置。 指定`*.json`作为文件掩码，然后单击**确定**。  
  
    5.  从**接收管道**下拉列表中，选择**JSONToXml**。 此时，你已在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序中创建此自定义接收管道。 右键单击省略号**（...）**按钮旁边向管道，然后在下**阶段 1 – Deocde 组件**，提供以下值：  
  
        -   RootNode-`ROOT`  
  
        -   RootNodeNamespace –`http://BTSJSON`。  
  
         这些值代表使用 JSON 架构向导从 JSON 采购订单生成的 XML 采购订单架构的目标命名空间和根节点名。  
  
    6.  单击**确定**直到退出所有打开的对话框。  
  
2.  创建用于向外发送 JSON 发票消息的发送端口。  
  
    1.  在[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 应用程序 1**，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**.  
  
    2.  指定发送端口的名称，请选择与具有端口类型**文件**，然后单击**配置**。  
  
    3.  提供发送端口将传出 JSON 发票复制到的文件夹位置。 指定`%MessageID%.json`作为文件名称，然后单击**确定**。  
  
    4.  从**发送管道**下拉列表中，选择**XmlToJSON**，然后单击**确定**。  
  
    5.  单击**确定**直到退出所有打开的对话框。  
  
3.  最后，将作为业务流程一部分创建的逻辑端口绑定到你当前已创建的物理端口，以对应用程序进行配置。  
  
    1.  右键单击**BizTalk 应用程序 1**，然后单击**配置**。  
  
    2.  从左窗格中，单击**ProcessPO**。 从右窗格中，将相关联[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机，将逻辑端口映射到的物理端口，然后单击**确定**。  
  
    3.  右键单击**BizTalk 应用程序 1**，然后单击**启动**。  
  
## <a name="test-the-application"></a>测试应用程序  
  
1.  导航到你下载的示例和从**testmessage 存储库库**文件夹中，复制**JsonPurchaseOrder.json**，并将其粘贴在与接收位置关联的文件夹中。 等待此文件消失。  
  
2.  导航到与你所创建的发送端口关联的文件夹。 请注意，   ***\<GUID\>*.json**文件位于文件夹中可用。 打开此文件并验证它是否是发票消息。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 处理 JSON 消息](../core/processing-json-messages-using-biztalk-server.md)