---
title: 配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95b54357-b23d-4ed7-8e31-bd60ed3e625f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 631914f72287b9fbd48a6695a4edf79e88d28182
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014198"
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-use-the-sql-adapter"></a>配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定
当你使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]若要为 SQL Server 项目，以外的架构文件，生成元数据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会生成端口绑定文件。 您可以将此绑定文件导入 BizTalk 应用程序，以创建物理发送端口或接收端口。 有关导入绑定文件的说明，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。 如果此绑定文件导入，您无需手动创建物理发送或接收端口。  
  
> [!IMPORTANT]
>  同时使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，如果未指定字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不能在绑定文件中。 您必须手动添加的绑定属性和其值在绑定文件中，如果所需。  
  
 创建始终使用端口绑定文件的端口创建一个双向发送端口或一个单向接收端口。 如果你想要创建单向发送端口，您可以创建它使用的步骤手动[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。 或者，可以按照本主题，以修改要创建单向发送端口的端口绑定文件中所述的解决方法。  
  
> [!NOTE]
>  绑定文件的端口的入站的操作将始终创建一个单向接收端口。 这是因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]仅支持单向接收端口的入站操作。  
> 
> [!IMPORTANT]
>  使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]不会创建使用可创建 WCF SQL 端口的端口绑定文件。 但是，无法对生成的端口绑定文件进行一些更改[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]并用它来创建 WCF SQL 端口。 有关详细信息，请参阅[配置端口绑定文件生成使用使用适配器服务外接程序使用 WCF SQL 端口](#BKMK_Create_WCF_SQL)。  
  
 以下是一些要点必须了解相对于绑定文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成：  
  
- 创建文件时特定的命名约定。 如果生成出站操作的元数据，也就是说，将消息发送到 SQL Server 的名称是文件的 WcfSendPort_SqlAdapterBinding_Custom.bindinginfo.xml。  
  
   如果生成的入站操作的元数据，也就是说，从 SQL Server 接收消息的名称是文件的 WcfReceivePort_SqlAdapterBinding_Custom.bindinginfo.xml。  
  
- 该文件包含有关绑定配置、 绑定类型、 终结点 URI，和基于为其生成元数据的操作的端口操作的信息。 此绑定文件导入到 BizTalk 应用程序创建的端口的端口上自动设置所有所需配置物理端口的相关信息。  
  
  > [!IMPORTANT]
  >  默认情况下，发送端口上的操作映射到为其生成元数据的操作名称。 例如，如果您生成有关客户表上的插入操作的元数据，则在端口上的操作设置为`<Operation Name="Insert" Action="TableOp/Insert/dbo/CustomerTable" />`。 但是，在 BizTalk 业务流程中创建的逻辑发送端口上的操作名称可能不能相同。 您必须确保发送端口 （在 BizTalk 业务流程） 中的逻辑操作名称和物理发送端口 (在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台) 相同。 否则，将通过发送端口将消息发送到 SQL Server 时收到错误。  
  
- 只需提供要连接到 SQL Server 的端口的凭据。 尽管该绑定文件确实保留与要连接的用户名，但出于安全原因该绑定文件不包含密码。  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>使用端口绑定文件的重要注意事项  
  
- 导入绑定文件时，可能会收到通知绑定文件中的 BizTalk 应用程序名称与要向其导入绑定文件的应用程序名称不匹配对话框消息。 可以安全地忽略此消息并继续。  
  
- 绑定文件还包含端口的名称和接收位置。 如果要向其导入绑定文件的 BizTalk 应用程序创建一个端口或与同一个 BizTalk 应用程序中的现有端口具有相同名称的接收位置，将会出错。 您必须手动编辑绑定文件指定唯一名称的端口或接收位置。  
  
- 绑定文件还包含有关连接 URI 的信息。 如果绑定文件将创建具有相同的接收 URI 与同一个 BizTalk 应用程序中的现有接收位置的接收位置，将会出错。 您必须手动编辑绑定文件以指定一个唯一的 URI。  
  
- 默认情况下，出站操作的端口绑定文件始终包含定义为双向发送端口。 导入 BizTalk 应用程序中的此文件时，它会创建一个双向发送端口。 但是，您可能有一个单向发送端口业务流程。 因此，当您配置此类业务流程，并使用通过导入绑定文件创建的端口，端口不可用在列表中。 发生这种情况是因为业务流程的一部分创建的逻辑端口是单向端口，而在业务流程中创建的物理端口为双向端口。 在这种情况下，可以编辑绑定文件以进行以下更改：  
  
  |若要了解|操作|  
  |--------------|-------------|  
  |若要编辑该端口绑定文件，以配置一个单向发送端口|1.在以下摘录中，更改的值**IsTwoWay**属性设置为**false**。 最初，此值设置为 **，则返回 true**。<br />     `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br />2.注释掉下面的摘录：<br />     `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br />     `<ReceivePipelineData xsi:nil="true" />`|  
  
  > [!IMPORTANT]
  >  绑定文件的端口的入站的操作将始终创建一个单向接收端口。 这是因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]仅支持单向接收端口的入站操作。  
  
##  <a name="BKMK_Create_WCF_SQL"></a> 配置 WCF SQL 端口使用的端口绑定文件，生成使用使用适配器服务外接程序  
 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会创建一个端口绑定文件，您可以在导入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 可以使用相同的端口绑定文件，也创建中的 BizTalk WCF SQL 端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 但是，在创建 WCF SQL 端口之前必须执行以下任务来修改端口绑定文件。  
  
1. 在文本编辑器中打开端口绑定文件。  
  
2. 搜索并替换与添加中的 WCF SQL 适配器的名称为"WCF 自定义"[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 例如，如果你添加为"SQLAdapter"WCF-SQL 适配器，将为"Wcf-custom"与"SQLAdapter"。  
  
3. "ConfigurationClsid"属性中，搜索并替换"59B35D03-6A06-4734-A249-EF561254ECF7"现有属性的值。  
  
4. 保存并关闭绑定文件。  
  
5. 导入绑定文件中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关如何导入绑定文件的说明，请参阅[重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)。
  
## <a name="see-also"></a>请参阅  
[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)