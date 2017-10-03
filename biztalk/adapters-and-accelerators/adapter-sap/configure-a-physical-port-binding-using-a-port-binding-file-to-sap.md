---
title: "配置物理端口绑定使用的端口绑定文件，以便 SAP |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port binding file
- physical port binding, configuring using a port binding file
ms.assetid: c637971c-3ecd-4026-8f74-bd5173774438
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0383ad738140467f17e4ff56ba60f2cc5b9698f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-physical-port-binding-using-a-port-binding-file-to-sap"></a>配置使用的端口绑定文件，以便 SAP 的物理端口绑定
当你使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]生成一个 SAP 项目，以外的架构文件，元数据[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会生成端口绑定文件。 你可以将此绑定文件导入你的 BizTalk 应用程序创建物理发送或接收端口。 [重复使用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)包括步骤导入绑定文件。 如果你导入此绑定文件，你无需手动创建物理发送或接收端口。  
  
> [!IMPORTANT]
>  在使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，如果未指定的字符串类型的绑定属性的值，并且其默认值为 null，然后，绑定属性将不可用的绑定中。 你必须手动添加绑定属性，并且其值在绑定文件中，如果需要。  
  
 创建始终使用端口绑定文件的端口创建双向发送或接收端口。 如果你想要创建单向端口，则可以创建它手动使用在步骤[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。 或者，你可以按照本主题，以修改要创建单向端口的端口绑定文件中所述的解决方法。  
  
> [!IMPORTANT]
>  使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]不会创建使用该可以创建一个 WCF SAP 端口的端口绑定文件。 但是，您无法对生成的端口绑定文件进行一些更改[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]并用它来创建 WCF SAP 端口。 有关详细信息，请参阅[配置端口绑定文件生成使用使用适配器服务外接程序使用 WCF SAP 端口](#BKMK_add_wcf_sap)。  
  
 以下是你必须了解与生成的绑定文件有关的一些要点[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]:  
  
-   使用特定的命名约定创建这些文件。 如果生成是将消息发送到 SAP 系统，对于出站操作，元数据文件的名称是 WcfSendPort_SAPBinding_Custom.bindinginfo.xml。  
  
     如果生成是从 SAP 系统接收消息，对于入站操作，元数据文件的名称是 WcfReceivePort_SAPBinding_Custom.bindinginfo.xml。  
  
-   该文件包含有关绑定配置、 绑定类型、 终结点 URI，和基于为其生成元数据的操作的端口操作的信息。 当你导入此绑定文件以创建一个端口时，在端口上自动设置所有所需配置的物理端口的相关信息。  
  
    > [!IMPORTANT]
    >  默认情况下，发送端口上的操作映射到为其生成元数据的操作名称。 例如，如果您为 RFC_CUSTOMER_GET 生成元数据，则端口上的操作设置为`<Operation Name="RFC_CUSTOMER_GET" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />`。 但是，创建 BizTalk 业务流程中的逻辑发送端口上的操作名称可能不能相同。 你必须确保 （中 BizTalk 业务流程） 的逻辑端口和物理发送端口 （在 BizTalk Server 管理控制台） 中的操作名称相同。 如果没有，你会将消息发送到通过发送端口的 SAP 系统时收到错误。  
  
-   只需提供要连接到 SAP 系统的端口的凭据。 虽然绑定文件未保留与要连接的用户名，出于安全原因绑定文件不包含密码。  
  
## <a name="key-considerations-for-using-the-port-binding-file"></a>使用的端口绑定文件的重要注意事项  
  
-   当你导入绑定文件时，你可能会收到对话框消息，通知绑定文件中的 BizTalk 应用程序名称不到导入的绑定文件的应用程序名称不匹配。 你可以安全地忽略此消息并继续。  
  
-   绑定文件还包含端口的名称和接收位置。 如果 BizTalk 应用程序向其导入的绑定文件创建一个端口或接收位置与在相同的 BizTalk 应用程序中的现有端口具有相同的名称，将出现错误。 你必须手动编辑要指定端口的唯一名称，或接收位置的绑定文件。  
  
-   绑定文件还包含有关连接 URI 的信息。 如果绑定文件创建为接收位置相同的 BizTalk 应用程序中已存在具有相同接收 URI 的接收位置，则将出现错误。 你必须手动编辑该绑定文件以指定一个唯一的 URI。  
  
-   默认情况下，端口绑定文件始终包含了双向端口的定义 （发送或接收）。 当你导入此文件在 BizTalk 应用程序时，它将创建双向发送或接收端口。 但是，你可能具有一个业务流程具有单向发送或接收端口。 因此，当你配置此类业务流程，并使用通过导入绑定文件创建的端口，端口不可用在列表中。 这是因为业务流程的一部分创建的逻辑端口是单向的端口，而在业务流程中创建的物理端口是双向端口。 在这种情况下，你可以编辑绑定文件以进行以下更改：  
  
    |若要了解|操作|  
    |--------------|-------------|  
    |若要编辑要配置的端口绑定文件单向发送端口|1.在以下摘录内容中，将的值更改**IsTwoWay**属性**false**。 最初，此值设置为**true**。<br />     `<SendPort Name="port_name" IsStatic="true" IsTwoWay="false" BindingOption="0">`<br />2.注释掉下面的摘录：<br />     `<ReceivePipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLReceive"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLReceive,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="1" TrackingOption="None" Description=""/>`<br />     `<ReceivePipelineData xsi:nil="true" />`|  
    |若要编辑要配置的端口绑定文件单向接收端口|1.在以下摘录内容中，将的值更改**IsTwoWay**属性**false**。 最初，此值设置为**true**。<br />     `<ReceivePort Name="port_name" IsTwoWay="false" BindingOption="1">`<br />2.注释掉下面的摘录：<br />     `<SendPipeline Name="Microsoft.BizTalk.DefaultPipelines.XMLTransmit"    FullyQualifiedName="Microsoft.BizTalk.DefaultPipelines.XMLTransmit,    Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral,    PublicKeyToken=token" Type="2" TrackingOption="None" Description="" />`<br />     `<SendPipelineData xsi:nil="true" />`<br />     `<SendPipelineData xsi:nil="true" />`|  
  
##  <a name="BKMK_add_wcf_sap"></a>配置 WCF SAP 端口使用生成使用的端口绑定文件使用适配器服务外接程序  
 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]还会创建，您可以导入的端口绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 你可以使用相同的端口绑定文件也可用来创建中的 BizTalk WCF SAP 端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 但是，在创建 WCF SAP 端口之前必须执行以下任务来修改端口绑定文件。  
  
1.  在文本编辑器中打开端口绑定文件。  
  
2.  搜索和替换与其添加中的 WCF SAP 适配器的名称替换"WCF 自定义"[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 例如，如果你添加为"SAPAdapter"WCF SAP 适配器，将"WCF 自定义"与"SAPAdapter"。  
  
3.  搜索"ConfigurationClsid"属性，并将该特性的现有值替换为"A5F15999-8879-472d-8C62-3B5EA9406504"。  
  
4.  保存并关闭绑定文件。  
  
5.  导入中的绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 [重复使用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)列出的步骤。
  
## <a name="see-also"></a>另请参阅  
[若要创建的 SAP 应用程序的构建基块](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)