---
title: 配置物理端口绑定使用的 Oracle 数据库的端口绑定文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- physical port binding, configuring by using a port binding file
ms.assetid: 154d219e-c6f3-4f70-9ac5-d9345f5260e9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 846c77040527694822381cfd55c805f78d96e69d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001486"
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database"></a>配置使用的 Oracle 数据库的端口绑定文件的物理端口绑定
当你使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]若要为 Oracle 数据库项目，以外的架构文件，生成元数据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会生成端口绑定文件。 您可以将此绑定文件导入 BizTalk 应用程序，以创建物理发送端口或接收端口。 有关导入绑定文件的说明，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。 如果此绑定文件导入，您无需手动创建物理发送或接收端口。  
  
> [!IMPORTANT]
>  同时使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，如果未指定字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不能在绑定文件中。 您必须手动添加的绑定属性和其值在绑定文件中，如果所需。  
  
 创建端口始终使用端口绑定文件创建双向发送或接收端口。 如果你想要创建单向发送或接收端口，您可以创建它手动中所述的过程[手动配置到 Oracle 数据库适配器的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)。 或者，可以按照本主题，以修改要创建单向发送或接收端口的端口绑定文件中所述的解决方法。  
  
 以下是一些您必须了解与生成的绑定文件相关的关键点[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]:  
  
-   创建文件时特定的命名约定。 如果生成是将消息发送到 Oracle 数据库，对于出站操作，元数据文件的名称是 WcfSendPort_OracleDBBinding_Custom.bindinginfo.xml。  
  
     如果生成的元数据的入站操作，从 Oracle 数据库接收消息，该文件的名称是 WcfReceivePort_OracleDBBinding_Custom.bindinginfo.xml。  
  
-   该文件包含有关绑定配置、 绑定类型、 终结点 URI，和基于为其生成元数据的操作的端口操作的信息。 导入该绑定文件来创建端口时，将自动在端口上设置配置物理端口所需的所有相关信息。  
  
    > [!IMPORTANT]
    >  默认情况下，发送端口上的操作映射到为其生成元数据的操作名称。 例如，如果您生成 ACCOUNTACTIVITY 表选择操作的元数据，则在端口上的操作设置为`<Operation Name="Select" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />`。 但是，在 BizTalk 业务流程中创建的逻辑发送端口上的操作名称可能不能相同。 您必须确保 （在 BizTalk 业务流程） 的逻辑端口 （在 BizTalk Server 管理控制台） 的物理发送端口中的操作名称都相同。 否则，会将消息发送到发送端口通过 Oracle 数据库时收到错误。  
  
-   只需提供要连接到 Oracle 数据库的端口的凭据。 虽然该绑定文件确实保留与要连接的用户名，出于安全原因该绑定文件不包含密码。  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>使用端口绑定文件的重要注意事项  
  
-   导入绑定文件时，可能会收到通知绑定文件中的 BizTalk 应用程序名称与要向其导入绑定文件的应用程序名称不匹配对话框消息。 可以安全地忽略此消息并继续。  
  
-   绑定文件还包含端口的名称和接收位置。 如果要向其导入绑定文件的 BizTalk 应用程序创建一个端口或与同一个 BizTalk 应用程序中的现有端口具有相同名称的接收位置，将会出错。 您必须手动编辑绑定文件指定唯一名称的端口或接收位置。  
  
-   绑定文件还包含有关连接 URI 的信息。 如果绑定文件将创建具有相同的接收 URI 与同一个 BizTalk 应用程序中的现有接收位置的接收位置，将会出错。 您必须手动编辑绑定文件以指定一个唯一的 URI。 可以通过包括轮询 id。 指定一个唯一的 URI  
  
-   默认情况下，端口绑定文件将始终包含定义双向端口 （发送或接收）。 导入 BizTalk 应用程序中的此文件时，它创建双向发送或接收端口。 但是，你可能具有一个业务流程具有单向发送或接收端口。 因此，当您配置此类业务流程，并使用通过导入绑定文件创建的端口，端口不可用在列表中。 发生这种情况是因为业务流程的一部分创建的逻辑端口是单向端口，而在业务流程中创建的物理端口为双向端口。 在这种情况下，可以编辑绑定文件以进行以下更改：  
  
    |若要了解|操作|  
    |--------------|-------------|  
    |若要编辑该端口的绑定文件，以配置一个单向发送端口|-在以下摘录中，更改的值**IsTwoWay**属性设置为 false。 最初，此值设置为 true。<br /><br /> `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br /><br /> -注释掉下面的摘录：<br /><br /> `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br /><br /> `<ReceivePipelineData xsi:nil="true" />`|  
    |若要编辑该端口的绑定文件，以配置一个单向接收端口|-在以下摘录中，更改的值**IsTwoWay**属性设置为 false。 最初，此值设置为 true。<br /><br /> `<ReceivePort Name="port_name" IsTwoWay="false" BindingOption="1">`<br /><br /> -注释掉下面的摘录：<br /><br /> `<SendPipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLTransmit"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLTransmit,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="2" TrackingOption="None" Description="" />`<br /><br /> `<SendPipelineData xsi:nil="true" />`<br /><br /> `<SendPipelineData xsi:nil="true" />`|  
  
## <a name="configuring-a-wcf-oracledb-port-using-the-port-binding-file-generated-using-consume-adapter-service-add-in"></a>配置使用生成使用的端口绑定文件的 Wcf-oracledb 端口使用适配器服务外接程序  
 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk Server 管理控制台中创建一个端口绑定文件，可以导入。 可以使用相同的端口绑定文件还在 BizTalk Server 管理控制台中创建 BizTalk Wcf-oracledb 端口。 但是，在创建 Wcf-oracledb 端口之前必须执行以下任务来修改端口绑定文件。  
  
1. 在文本编辑器中打开端口绑定文件。  
  
2. 搜索和替换"WCF 自定义"中的将 Wcf-oracledb 适配器添加与其同名[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 例如，如果你添加为"OracleDBAdapter"Wcf-oracledb 适配器，将为"Wcf-custom"与"OracleDBAdapter"。  
  
3. "ConfigurationClsid"属性中，搜索并替换"D7127586-E851-412e-8A8A-2428AEDDC219"现有属性的值。  
  
4. 保存并关闭绑定文件。  
  
5. 导入绑定文件中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关如何导入绑定文件的说明，请参阅[重复使用 Oracle 数据库适配器绑定](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)。  
  
## <a name="see-also"></a>请参阅  
[若要开发与 Oracle 数据库的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)