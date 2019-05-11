---
title: 部署和测试应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2c86d5f-1849-4b7d-8061-23f156245f5b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd6a2f7441611f6c223ac8932faaaa1b0f6f9c69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389647"
---
# <a name="deploy-and-test-the-application"></a>部署和测试应用程序
> [!NOTE]
>  本教程仅适用于 BizTalk Server。  
  
 在本主题中，我们构建、 部署、 配置和测试[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。  
  
## <a name="build-and-deploy-the-application"></a>生成和部署应用程序  
  
1.  在解决方案资源管理器，右键单击 BizTalk 项目名称，然后依次**属性**。  
  
2.  在属性页上，单击签名选项卡选择登录程序集复选框，并从下拉列表选择创建新的强名称密钥文件的选项。 按照提示操作以创建该文件。  
  
3.  将更改保存到项目。 在解决方案资源管理器，右键单击解决方案名称，然后单击**生成解决方案**。  
  
4.  成功生成项目后，在解决方案资源管理器，右键单击解决方案名称，然后依次**部署解决方案**。  
  
## <a name="configure-the-application"></a>配置应用程序  
 若要配置应用程序，在[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]创建发送和接收端口，然后将其绑定到业务流程和逻辑发送/接收端口的业务流程一部分创建。  
  
1. 创建接收端口接收 JSON 采购订单是通过其[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。  
  
   1. 在中[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk Application 1**，右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**.  
  
   2. 提供接收端口的名称，然后在左窗格中，单击**接收位置**。 在中**接收位置**选项卡上，单击**新建**。  
  
   3. 指定接收位置的名称，选择端口类型**文件**，然后单击**配置**。  
  
   4. 提供从接收位置将在其中选择传入 JSON 采购订单的文件夹位置。 指定`*.json`作为文件掩码，然后单击**确定**。  
  
   5. 从**接收管道**下拉列表中，选择**JSONToXml**。 创建此自定义接收管道中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。 右键单击省略号 **（...）** 接下来到管道中，然后在下的按钮**阶段 1 – 解码组件**，提供以下值：  
  
      - RootNode - `ROOT`  
  
      - RootNodeNamespace –`http://BTSJSON`。  
  
        这些值表示的目标命名空间和从 JSON 采购订单，使用 JSON 架构向导生成的 XML 采购订单架构的根节点名称。  
  
   6. 单击**确定**直到您退出所有打开的对话框。  
  
2. 创建用于发送 JSON 发票消息的发送端口。  
  
   1. 在中[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk Application 1**，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**.  
  
   2. 指定发送端口的名称，选择端口类型**文件**，然后单击**配置**。  
  
   3. 提供发送端口将传出 JSON 发票复制到其中的文件夹位置。 指定`%MessageID%.json`作为文件名称，然后单击**确定**。  
  
   4. 从**发送管道**下拉列表中，选择**XmlToJSON**，然后单击**确定**。  
  
   5. 单击**确定**直到您退出所有打开的对话框。  
  
3. 最后，将绑定到物理业务流程的一部分端口而创建的逻辑端口创建现在以配置应用程序。  
  
   1. 右键单击**BizTalk Application 1**，然后单击**配置**。  
  
   2. 在左窗格中，单击**ProcessPO**。 在右窗格中，将相关联[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]托管，将逻辑端口映射到物理端口，然后单击**确定**。  
  
   3. 右键单击**BizTalk Application 1**，然后单击**启动**。  
  
## <a name="test-the-application"></a>测试应用程序  
  
1.  导航到示例下载，并从**testmessage 库库**文件夹中，复制**JsonPurchaseOrder.json**，并将其粘贴在与接收位置关联的文件夹中。 该文件消失后等待。  
  
2.  导航到与你创建的发送端口关联的文件夹。 请注意，***\<GUID\>*.json**文件位于文件夹中。 打开文件并验证它将发票消息。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 处理 JSON 消息](../core/processing-json-messages-using-biztalk-server.md)