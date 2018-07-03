---
title: 步骤 2： 设置 Salesforce 系统 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a4b09fb-70a7-4eec-b1e3-f05de0e84df1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 772c18f87351d17b726ad498122715659dca79bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986526"
---
# <a name="step-2-set-up-the-salesforce-system"></a>步骤 2： 设置 Salesforce 系统
在此步骤中，你要将 Salesforce 配置为在机会成功关闭时发送通知。 你需要先执行以下步骤，然后才能发送通知：  
  
-   在 Salesforce 中创建帐户。 帐户代表 Northwind 的客户。  
  
-   为帐户创建机会。 机会代表客户所带来的潜在销售机会。 在机会中，你还可以添加客户感兴趣的产品详细信息。  
  
-   在 Salesforce 中创建工作流。  
  
-   创建与 Salesforce 连接的应用程序定义。  
  
> [!NOTE]
>  本主题中的步骤假定你已拥有 Salesforce 开发人员帐户。 若要在 Salesforce 中创建新的开发人员帐户，请转到[ http://go.microsoft.com/fwlink/?LinkId=296424 ](http://go.microsoft.com/fwlink/?LinkId=296424)。  
  
### <a name="to-create-an-account-in-salesforce"></a>在 Salesforce 中创建帐户  
  
1.  使用你的开发人员凭据登录到 Salesforce.com 门户。  
  
2.  在门户中，单击**帐户**选项卡，然后依次**新建**。  
  
3.  上**新的帐户**页上，为各字段提供值。 为指定值**帐户名**是必需的。 对于本教程中，帐户名称指定为`Customer1`。  
  
4.  单击 **“保存”**。  
  
### <a name="to-create-an-opportunity-for-the-customer"></a>为客户创建机会  
  
1. 在 Salesforce.com 门户中，单击**机会**选项卡。  
  
2. 在中**最近的机会**部分中，单击**新建**。  
  
3. 在“新建机会”页中，指定以下值：  
  
   1. 指定**机会名称**，例如， `Opportunity with Customer 1`。  
  
   2. 指定**帐户名**。 此项表示与该机会关联的帐户。 对于本教程中，设置该帐户为`Customer1`。 你已在上一步中创建了此帐户。  
  
   3. 指定**关闭日期**。 此项表示机会应截止的日期。  
  
   4. 指定**阶段**。 此项表示机会的当前阶段。 开始时，您可以将机会设置为任何内容，例如，**需要分析**。  
  
       ![在 Salesforce 中创建机会](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")  
  
      > [!NOTE]
      >  请确保未将阶段设置为**已结束-赢得**开始。 本教程中，每次将阶段设置中的方案**已结束-赢得**上将通知发送到中继终结点[!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)]。 我们尚未设置解决方案的该部分，因此不应将阶段设置为**已结束-赢得**。  
  
   5. 指定的其他可选字段的值，然后单击**保存**。  
  
   6. 在有机会页上为 Customer1 下,**产品**部分中，单击**添加产品**。  
  
   7. 从产品的列表中，选择客户感兴趣的产品，然后单击**选择**。  
  
   8. 对于每个所选的产品，指定以客户所需的数量，然后单击**保存**。  
  
       ![向机会添加产品](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")  
  
## <a name="create-a-salesforce-workflow"></a>创建 Salesforce 工作流  
 在此步骤中，我们将创建一个工作流，用于在每次机会成功关闭时发送通知。 通知采用 SOAP 消息的形式并发送到中继终结点上托管[!INCLUDE[winazure](../includes/winazure-md.md)] [!INCLUDE[sb](../includes/sb-md.md)]。  
  
#### <a name="to-create-a-workflow-for-opportunities"></a>为机会创建工作流  
  
1. 在 Salesforce 门户中，单击位于页面右上角的登录名，然后单击**安装程序**。  
  
2. 在左窗格中下,**应用安装程序**，展开**创建**，展开**工作流和审批**，然后单击**工作流规则**。  
  
   > [!NOTE]
   >  如果你是首次打开“工作流规则”页，则系统会向你显示一些信息，让你了解工作流在 Salesforce 中是如何工作的。 阅读的信息，然后单击**继续**。  
  
3. 上**所有工作流规则**页上，单击**新规则**。  
  
4. 从**选择对象**列表中，单击**机会**，然后单击**下一步**。  
  
5. 在下一页中，指定以下内容：  
  
   1.  设置**规则名称**作为`Closed Opportunity`。  
  
   2.  设置**评估条件**作为**创建，并随时对其进行编辑以以后满足条件**。  
  
   3.  有关**规则条件**，设置为运行规则时**满足条件**。  
  
   4.  设置**字段**到**机会： 阶段**，**运算符**到**等于**，并**值**到`Closed Won`.  
  
        ![创建 Salesforce 工作流](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")  
  
   5.  单击**保存并下一步**。  
  
6. 为新规则定义工作流操作：  
  
   1. 上**指定工作流操作**页上，单击**添加工作流操作**按钮，然后单击**新建出站消息**。  
  
   2. 设置**名称**并**唯一的名称**字段设置为`NewOp1`。  
  
   3. 指定描述，例如， `Message sent when an opportunity is successfully closed`。  
  
   4. 指定**终结点 URL**作为`https://btssalesforce.servicebus.windows.net/notifications/opportunity`。  
  
       在这里， **btssalesforce**是你[!INCLUDE[sb](../includes/sb-md.md)]之前的步骤中创建的命名空间。 **/notifications/opportunity/** 表示我们将在本教程的后续步骤中创建的中继。  
  
      > [!NOTE]
      >  你必须指定你在前面创建的 [!INCLUDE[sb](../includes/sb-md.md)] 命名空间。  
  
   5. 请确保**受保护的组件**复选框已清除并**发送会话 ID**选中复选框。  
  
   6. 有关**机会字段发送**中选择相关字段从**可用字段**列表，然后单击**添加**按钮。  
  
   7. 单击**保存**，然后单击**完成**。  
  
   8. 在左窗格中下,**应用安装程序**，展开**创建**，展开**工作流和审批**，然后单击**工作流规则**。 确认**关闭机会**列出规则。 下**操作**的列**关闭机会**规则中，单击**激活**以启用该规则。  
  
## <a name="create-a-salesforce-connected-application"></a>创建与 Salesforce 连接的应用程序  
 创建连接的应用程序定义时，将生成一组请求用于访问并连接到 Salesforce 的 OAuth 令牌所需的密钥。 在本教程中的后面阶段，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将成为使用连接的应用程序定义查询 Salesforce 的连接应用程序。  
  
#### <a name="to-create-a-connected-application-for-salesforce"></a>为 Salesforce 创建连接应用程序定义  
  
1. 在 Salesforce 门户中，单击位于页面右上角的登录名，然后单击**安装程序**。  
  
2. 在左窗格中下,**应用安装程序**，展开**创建**，然后展开**应用**。 上**应用程序**页面上，在**连接的应用**部分中，单击**新建**。  
  
3. 在中**新的连接应用**页上，指定以下内容：  
  
   1. 有关**连接应用名称**，指定`BizTalk_Salesforce`。  
  
   2. 有关**开发人员姓名**，指定你的登录名。  
  
   3. 有关**Contact Email**，指定你的电子邮件。  
  
   4. 有关**回叫 URL**，指定有效的 URL。  
  
      > [!NOTE]
      >  鉴于在此方案中我们向 Salesforce 进行身份验证的方式，不使用你在此处指定的值。  
  
   5. 下**可用 OAuth 作用域**，选择**的完全访问权限**，**随时代表你执行请求**，和**访问和管理你的数据**，然后单击**添加**按钮以将其移入**所选 OAuth 作用域**。  
  
   6. 单击 **“保存”**。 显示的页包含有关的信息**使用者密钥**并**使用者机密**。 你必须记下这些值。 从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 连接到 Salesforce 时，将需要这些值。  
  
       ![为 Salesforce 的访问密钥](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")  
  
4. 最后，生成从未知的网络位置连接到 Salesforce 时所需的安全令牌。  
  
   1.  在 Salesforce 门户的左窗格下**个人的安装程序**，展开**个人信息**，然后单击**重置我的安全令牌**。  
  
   2.  阅读该警告，然后单击**重置安全令牌**。  
  
   3.  你应该使用在创建你的 Salesforce 帐户时指定的电子邮件地址来接收安全令牌。  
  
## <a name="see-also"></a>请参阅  
 [教程 6： 将 BizTalk Server 2013 与 Salesforce 集成](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)