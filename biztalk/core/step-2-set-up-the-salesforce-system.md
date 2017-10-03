---
title: "步骤 2： 设置 Salesforce 系统 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a4b09fb-70a7-4eec-b1e3-f05de0e84df1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d65a1c741103b9c8f1e9493b7bd2aa56eef8cf18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-set-up-the-salesforce-system"></a>步骤 2： 设置 Salesforce 系统
在此步骤中，你要将 Salesforce 配置为在机会成功关闭时发送通知。 你需要先执行以下步骤，然后才能发送通知：  
  
-   在 Salesforce 中创建帐户。 帐户代表 Northwind 的客户。  
  
-   为帐户创建机会。 机会代表客户所带来的潜在销售机会。 在机会中，你还可以添加客户感兴趣的产品详细信息。  
  
-   在 Salesforce 中创建工作流。  
  
-   创建与 Salesforce 连接的应用程序定义。  
  
> [!NOTE]
>  本主题中的步骤假定你已拥有 Salesforce 开发人员帐户。 若要在 Salesforce 中创建新的开发人员帐户，请转到[http://go.microsoft.com/fwlink/?LinkId=296424](http://go.microsoft.com/fwlink/?LinkId=296424)。  
  
### <a name="to-create-an-account-in-salesforce"></a>在 Salesforce 中创建帐户  
  
1.  使用你的开发人员凭据登录到 Salesforce.com 门户。  
  
2.  在门户中，单击**帐户**选项卡上，并依次**新建**。  
  
3.  上**新帐户**页上，为各个字段提供值。 指定的值**帐户名称**是必需的。 对于本教程中，指定为帐户名`Customer1`。  
  
4.  单击 **“保存”**。  
  
### <a name="to-create-an-opportunity-for-the-customer"></a>为客户创建机会  
  
1.  在 Salesforce.com 门户中，单击**机会**选项卡。  
  
2.  在**最近的商机**部分中，单击**新建**。  
  
3.  在“新建机会”页中，指定以下值：  
  
    1.  指定**机会名称**，例如， `Opportunity with Customer 1`。  
  
    2.  指定**帐户名称**。 此项表示与该机会关联的帐户。 对于本教程中，将帐户设置为`Customer1`。 你已在上一步中创建了此帐户。  
  
    3.  指定**关闭日期**。 此项表示机会应截止的日期。  
  
    4.  指定**阶段**。 此项表示机会的当前阶段。 开始时，你可以将设置可以为任何内容，例如，**需要分析**。  
  
         ![在 Salesforce 中创建的商机](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")  
  
        > [!NOTE]
        >  请确保你未设置为阶段**关闭获胜**开始。 对于本教程中，每次阶段设置为中的方案**关闭获胜**将通知发送到中继终结点[!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)]。 我们尚未将设置为解决方案的该部分，不应设置阶段，为**关闭获胜**。  
  
    5.  指定为其他可选字段的值，然后单击**保存**。  
  
    6.  在有机会页上，为 Customer1 下,**产品**部分中，单击**添加产品**。  
  
    7.  从产品的列表中，选择客户有兴趣的产品，然后单击**选择**。  
  
    8.  对于每个所选的产品，指定客户想要数量，然后单击**保存**。  
  
         ![将产品添加到有机会](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")  
  
## <a name="create-a-salesforce-workflow"></a>创建 Salesforce 工作流  
 在此步骤中，我们将创建一个工作流，用于在每次机会成功关闭时发送通知。 通知的 SOAP 消息的格式并发送到中继终结点上承载[!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)]。  
  
#### <a name="to-create-a-workflow-for-opportunities"></a>为机会创建工作流  
  
1.  在 Salesforce 门户中，单击您在页上，右上角的登录名，然后单击**安装**。  
  
2.  在左窗格中，在**应用安装程序**，展开**创建**，展开**工作流和审批**，然后单击**工作流规则**。  
  
    > [!NOTE]
    >  如果你是首次打开“工作流规则”页，则系统会向你显示一些信息，让你了解工作流在 Salesforce 中是如何工作的。 阅读通过信息，然后单击**继续**。  
  
3.  上**所有工作流规则**页上，单击**新规则**。  
  
4.  从**选择对象**列表中，单击**机会**，然后单击**下一步**。  
  
5.  在下一页中，指定以下内容：  
  
    1.  设置**规则名称**作为`Closed Opportunity`。  
  
    2.  设置**评估条件**作为**创建，和其进行编辑以随后满足条件的任何时间**。  
  
    3.  有关**规则条件**，设置以运行规则时**满足条件**。  
  
    4.  设置**字段**到**机会： 阶段**，**运算符**到**等于**，和**值**到`Closed Won`.  
  
         ![创建工作流，Salesforce](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")  
  
    5.  单击**保存和下一步**。  
  
6.  为新规则定义工作流操作：  
  
    1.  上**指定工作流操作**页上，单击**添加工作流操作**按钮，然后单击**新的出站消息**。  
  
    2.  设置**名称**和**唯一名称**字段设置为`NewOp1`。  
  
    3.  例如，指定的描述， `Message sent when an opportunity is successfully closed`。  
  
    4.  指定**终结点 URL**作为`https://btssalesforce.servicebus.windows.net/notifications/opportunity`。  
  
         在这里， **btssalesforce**是你[!INCLUDE[sb](../includes/sb-md.md)]在之前的步骤中创建的命名空间。 **/notifications/机会/**表示我们将在本教程的后续步骤中创建的中继。  
  
        > [!NOTE]
        >  你必须指定你在前面创建的 [!INCLUDE[sb](../includes/sb-md.md)] 命名空间。  
  
    5.  请确保**保护组件**复选框已清除与**发送会话 ID**选中复选框。  
  
    6.  有关**机会字段发送**选择从的相关字段**可用字段**列表，然后单击**添加**按钮。  
  
    7.  单击**保存**，然后单击**完成**。  
  
    8.  在左窗格中，在**应用安装程序**，展开**创建**，展开**工作流和审批**，然后单击**工作流规则**。 验证**关闭机会**存在列出规则。 下**操作**列**关闭机会**规则，请单击**激活**以启用该规则。  
  
## <a name="create-a-salesforce-connected-application"></a>创建与 Salesforce 连接的应用程序  
 创建连接的应用程序定义时，将生成一组请求用于访问并连接到 Salesforce 的 OAuth 令牌所需的密钥。 在本教程中的后面阶段，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将成为使用连接的应用程序定义查询 Salesforce 的连接应用程序。  
  
#### <a name="to-create-a-connected-application-for-salesforce"></a>为 Salesforce 创建连接应用程序定义  
  
1.  在 Salesforce 门户中，单击您在页上，右上角的登录名，然后单击**安装**。  
  
2.  在左窗格中，在**应用安装程序**，展开**创建**，然后展开**应用**。 上**应用**页上，在**连接应用**部分中，单击**新建**。  
  
3.  在**新连接应用程序**页上，指定下列各项：  
  
    1.  有关**连接应用程序名称**，指定`BizTalk_Salesforce`。  
  
    2.  有关**开发人员姓名**，指定你的日志名称。  
  
    3.  有关**联系人电子邮件**，指定你的电子邮件。  
  
    4.  有关**回调 URL**，指定有效的 URL。  
  
        > [!NOTE]
        >  鉴于在此方案中我们向 Salesforce 进行身份验证的方式，不使用你在此处指定的值。  
  
    5.  下**可用的 OAuth 作用域**，选择**完全访问**，**随时替你执行请求**，和**访问和管理数据**，然后单击**添加**按钮以将它们移到**选择 OAuth 作用域**。  
  
    6.  单击 **“保存”**。 显示的页，包含有关的信息**使用者密钥**和**使用者机密**。 你必须记下这些值。 从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 连接到 Salesforce 时，将需要这些值。  
  
         ![为 Salesforce 访问密钥](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")  
  
4.  最后，生成从未知的网络位置连接到 Salesforce 时所需的安全令牌。  
  
    1.  在 Salesforce 门户的左窗格下**个人设置**，展开**个人信息**，然后单击**重置我的安全令牌**。  
  
    2.  阅读警告，然后单击**重置安全令牌**。  
  
    3.  你应该使用在创建你的 Salesforce 帐户时指定的电子邮件地址来接收安全令牌。  
  
## <a name="see-also"></a>另请参阅  
 [教程 6： 将与 Salesforce 集成 BizTalk Server 2013](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)