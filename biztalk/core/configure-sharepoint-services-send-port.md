---
title: 配置 SharePoint Services 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36aadbc2-316f-4e1c-a5a8-b162470acf9e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76ab3a3dc1f7eaf92a3c132305865a8351c9b891
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391429"
---
# <a name="configure-sharepoint-services-send-port"></a>配置 SharePoint Services 发送端口
本主题比较静态发送端口与动态发送端口，并还列出了步骤来创建[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]发送端口。 具体来说：  

 [静态发送端口与动态发送端口](../core/configure-sharepoint-services-send-port.md#BKMK_StaticvsDynamic)  

 [创建静态发送端口](../core/configure-sharepoint-services-send-port.md#BKMK_StaticSend)  

 [创建动态发送端口](../core/configure-sharepoint-services-send-port.md#BKMK_DynamicSend)  

##  <a name="BKMK_StaticvsDynamic"></a> 静态发送端口与动态发送端口  

||静态发送端口|动态发送端口|  
|-|----------------------|-----------------------|  
|用于不同适配器使用单个发送端口。|否<br /><br /> 创建静态发送端口时，传输类型是必需的。|是<br /><br /> 动态发送端口通常添加到业务流程。 传输类型配置业务流程逻辑中。|  
|使用不同的发送端口属性，如 URL 中使用单个发送端口。|否<br /><br /> 创建静态发送端口时，某些适配器属性必须配置，如 URL。|是<br /><br /> 动态发送端口通常添加到业务流程。 业务流程逻辑中配置的属性。|  
|必须使用默认发送处理程序。|否<br /><br /> 创建发送端口时，发送处理程序进行配置。|否<br /><br /> 创建发送端口时，发送处理程序进行配置。|  
|当您不知道该消息应发送到何处时使用。|否<br /><br /> 创建静态发送端口时，你指定的传输类型和结束位置。|是<br /><br /> 可以在业务流程和基于内容的路由方案中配置的结束位置。 规则还可向筛选器发送消息。|  
|使用单个发送端口将消息发送到多个合作伙伴。|否<br /><br /> 创建静态发送端口时，你指定的传输类型和结束位置。|是<br /><br /> 动态发送端口通常添加到业务流程。 属性是在业务流程逻辑中配置，基于你指定的规则，可以将消息发送到多个合作伙伴。|  

##  <a name="BKMK_StaticSend"></a> 创建静态发送端口  
 创建静态发送端口时，发送端口将使用默认值与传输类型关联的发送处理程序。 使用时[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]适配器，发送处理程序的默认**BizTalkServerApplication**。 对于要添加新的发送处理程序的步骤，请转到[如何创建适配器处理程序](http://go.microsoft.com/fwlink/p/?LinkId=263646)。  

 创建静态发送端口：  

1. 在中**BizTalk Server 管理**控制台中，展开**BizTalk 组 [*GroupName*]**，展开**应用程序**，然后展开要包含发送端口的应用程序。  

2. 右键单击**发送端口**，单击**新建**，然后单击**静态单向发送端口**。  

   > [!IMPORTANT]
   >  一个**静态要求响应发送端口**不是可配置为[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]适配器。  

3. 在中**属性**，单击**Windows SharePoint Services**中**类型**下拉列表。 输入**名称**，**发送处理程序**，并**发送管道**属性。  

4. 单击**配置**。 在中**属性**，配置以下各项：  


   |                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   |-------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      适配器 Web 服务端口       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           **所需**。 承载的 IIS web 站点上配置的端口[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]适配器 web 服务。<br /><br /> 默认端口为端口**80**，这是标准 HTTP 端口。 如果使用非 80 的端口，请更新此值。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
   |               超时               |                                                                                                                                                                                                                                                                                                                                                                                                                     **所需**。 以毫秒为单位，此值确定适配器从 web 服务收到响应的时间。<br /><br /> 默认值是**100000 毫秒**（100 秒）。<br /><br /> 如果消息或批大小高于预期，请增大此值。<br /><br /> 以毫秒为单位，用于对 Windows SharePoint Services 适配器 Web services 的适配器运行时 Web 服务调用的超时。 您可能需要增加此值，如果消息或批大小超过适配器预期的平均值。                                                                                                                                                                                                                                                                                                                                                                                                                     |
   |            使用客户端 OM            |                                                                                                                                                                                                         **所需**。 确定是否使用 SharePoint 客户端对象模型 (CSOM) 或服务端对象模型 (SSOM)。<br /><br /> 默认值是**是**。 设置为**是**上使用 SharePoint CSOM [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在没有任何要求[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]计算机。<br /><br /> 设置为**否**若要使用 SharePoint SSOM，包括 web 服务上安装[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]计算机。<br /><br /> [附录 b:安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)上使用的 SSOM 和 CSOM 组件提供的特定信息[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]适配器。                                                                                                                                                                                                         |
   |       目标文件夹 URL        |                                                                                                                                                                                                                                                                                                                                                               **所需**。 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]文件夹 URL，以存储文档。 输入 SharePoint 站点的相对路径。 例如， **Shared Documents**或**Shared Documents/Purchase Orders /**。 列表还可以用作目标。 例如， **Lists/Tasks**。 如果指定列表时，消息正文不会保存与列表项。 从消息中提取的值将提升到 SharePoint 列中。 **注意：** SharePoint 文档库或文件夹 URL 可以与其名称不同。 获取正确的 URL 检查 web 浏览器中的地址。                                                                                                                                                                                                                                                                                                                                                                |
   |              Filename               |                                                                                                                                                                                                                                            **可选**。 输入的名称[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]文件名。<br /><br /> 输入文件名称，如**PurchaseOrder0001.xml**或表达式。 表达式包括文本、 宏和 XPATH 查询的任意组合。 例如，输入**PurchOrd-%XPATH=//po:PurchaseOrderId%-%MessageID%.xml**。 如果不提供任何文件名称，则使用原始文件提供的业务流程或 Msg-%MessageID%.xml 的值的文件名。 请参阅[Windows SharePoint Services 适配器表达式](../core/windows-sharepoint-services-adapter-expressions.md)有关详细信息。 **注意：** 时向列表发送消息，此文件名值被忽略，并且不会保存在 SharePoint 列。 相反，更新标题列使用其中一个可用的 16 列。 SharePoint 列表中没有文件名列。                                                                                                                                                                                                                                             |
   |         命名空间别名          |                                                                                                                                                                                                                                                                                                                                                                                                           **可选**。 以逗号或分号分隔的命名空间别名定义列表。<br /><br /> 使用此字段来定义等文件名或栏值字段中引入的 XPATH 查询所使用的命名空间别名。 例如，输入**po ='<http://OrderProcess/POrder>'，conf ='<http://OrderProcess/Confirmation>' xmlns =""; ipsol = {D8217CF1-4EF7-4bb5-A30D-765ECB09E0D9}**。 **注意：** 此属性不会覆盖 WSS。业务流程定义 ConfigNamespacesAliases 消息上下文属性。 相反，将合并两个值。                                                                                                                                                                                                                                                                                                                                                                                                           |
   |              Overwrite              |                                                                                                                                                                                                                                                                                                                                    **所需**。 如果文件存在，则确定会覆盖此文件。<br /><br /> 默认值是**否**。 选项包括：<br /><br /> -   **不**:引发错误并挂起该消息，如果存在具有相同名称的文件。<br />-   **业务流程**:使用业务流程中定义，如果存在具有相同名称的文件的值。<br />-   **重命名**:如果存在具有相同名称的文件重命名新文件。<br />-   **是**:如果它具有相同的名称，将覆盖现有文件。<br />     如果设置为**是**，发送大量同名消息可能会导致 SharePoint 事件查看器错误。 这些错误不会影响适配器和重试失败的所有消息。                                                                                                                                                                                                                                                                                                                                     |
   |         SharePoint 站点 URL         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     **所需**。 完整 URL [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] web 站点。 例如， http://<em>SharePointServer</em>/sites/testsite。 **注意：** 一个发送端口或接收位置的 URI 不能超过 256 个字符。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |    Microsoft Office 集成     |                                       **所需**。 对于二进制消息，必须使用**否**或**可选**。<br /><br /> 默认值是**可选**。 选项包括：<br /><br /> <ul><li>**否**：将文档保存**为-是**。 对于二进制消息，可以使用此选项。</li><li>**可选**:修改文档，使其自动在 InfoPath 等 Office 应用程序中打开。 如果找不到处理指令，处理文档**为-是**。 对于二进制消息，可以使用此选项。</li><li>**业务流程**:使用业务流程中定义的值。</li><li>**是**:修改文档，使其自动在 InfoPath 等 Office 应用程序中打开。 如果找不到处理指令，则挂起消息。<br /><br />     如果设置为**是**，则需要至少以下属性对之一：<br /><br /> <ul><li>*模板文档库*和*模板 Namespace 列*</li><li>*模板后备文档库*和*模板回退 Namespace 列*</li></ul></li><li>**是 （InfoPath 表单库）**:如果 InfoPath 解决方案位于表单库，则修改文档，使它在 InfoPath 等 Office 应用程序中自动打开。 如果表单库不具有一种解决方案，则挂起消息。</li></ul>                                       |
   |     模板文档库      |                                                                                                                                                                                                                                                **所需*仅*时*模板 Namespace 列*填充**。 存储 InfoPath 解决方案的 SharePoint 文档库。 例如， **My Solutions**。 适配器会*模板文档库*匹配的 InfoPath 解决方案。 如果找不到一种解决方案，适配器会*模板后备文档库*。 **注意：** *模板文档库*要求至少一个 Single line of text SharePoint 栏的填充以下： <ul><li>命名空间和用 InfoPath 解决方案打开的 XML 文档的根节点</li><li>或者，XML 文档的根节点</li></ul> 有关详细信息，请参阅[演练：模块 2-将集成 Office 与 Windows SharePoint Services 适配器](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)。                                                                                                                                                                                                                                                 |
   | 模板后备文档库 | **所需*仅*时*模板后备 Namespace 栏*填充**。 存储 InfoPath 解决方案的 SharePoint 文档库。 例如，**模板**。<br /><br /> 如果在找不到一种解决方案*模板文档库*，适配器会*模板后备文档库*匹配的 InfoPath 解决方案。 *模板后备文档库*并*模板文档库*字段可用于两组 InfoPath 解决方案。 有适用于所有通用目的的通用 InfoPath 解决方案和仅用于特定合作伙伴的专用的 InfoPath 解决方案。 *模板后备文档库*字段应指向通用解决方案，并*模板文档库*应指向该特定合作伙伴的专用解决方案。 **注意：** *模板后备文档库*要求至少一个 Single line of text SharePoint 栏的填充以下： <ul><li>命名空间和用 InfoPath 解决方案打开的 XML 文档的根节点</li><li>或者，XML 文档的根节点</li></ul> 有关详细信息，请参阅[演练：模块 2-将集成 Office 与 Windows SharePoint Services 适配器](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)。 |
   | 模板后备 Namespace 栏 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         **所需*仅*时*模板后备文档库*填充**。 存储 InfoPath 解决方案命名空间的 SharePoint 文档库。 例如， **myNamespace**。 **注意：** 此字段是区分大小写。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
   |     模板 Namespace 列      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    **所需*仅*时*模板文档库*填充**。 SharePoint*模板文档库*存储 InfoPath 解决方案命名空间的列。 例如， **myNamespace**。 **注意：** 此字段是区分大小写。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
   |     SharePoint Online 密码      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              **可选**。 SharePoint online 帐户的密码。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
   |     SharePoint Online 用户名      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              **可选**。 SharePoint online 帐户的用户名。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
   |             列 `n`              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        **可选**。 中存在的 SharePoint 栏*目标文档库*。 使用从消息中提取或中指定的值更新该列*列值*字段。 **注意：** 可以指定最多 16 列。 此字段是区分大小写。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
   |          列`n`值           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        **可选**。 输入要为此消息设置的栏值。 您可以键入如 Purchase Order 或表达式的文本值。 表达式可以包括文本、 宏和 XPATH 查询的任意组合。 例如，输入 **"%xpath=//po:poamount%"、"%sendingorchestrationid%"**。 **注意：** 可以指定最多 16 列。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |


5. 单击**确定**保存设置。  

6. 其他发送端口配置选项包括：  

   1.  [如何配置传输高级选项的发送端口](../core/how-to-configure-transport-advanced-options-for-a-send-port.md)  

   2.  [如何为发送端口配置备份传输选项](../core/how-to-configure-backup-transport-options-for-a-send-port.md)  

   3.  [如何配置发送端口的出站映射](../core/how-to-configure-outbound-maps-for-a-send-port.md)  

   4.  [如何为发送端口配置筛选器](../core/how-to-configure-filters-for-a-send-port.md)  

   5.  [如何为发送端口分配证书](../core/how-to-assign-a-certificate-to-a-send-port.md)  

   6.  [如何为发送端口配置跟踪](../core/how-to-configure-tracking-for-a-send-port.md)  

##  <a name="BKMK_DynamicSend"></a> 创建动态发送端口  
 创建动态发送端口时，是可以为每个适配器配置发送处理程序。 可以由多个适配器使用单一的动态发送端口。 请参阅[动态发送端口处理程序是可配置](../core/dynamic-send-port-handler-is-configurable.md)有关配置动态发送端口处理程序的步骤。  

1. 在中**BizTalk Server 管理**控制台中，展开**BizTalk 组 [*GroupName*]**，展开**应用程序**，然后展开要包含发送端口的应用程序。  

2. 右键单击**发送端口**，单击**新建**，然后选择**动态单向发送端口**或**动态要求响应发送端口**  

3. 在中**属性**，输入**名称**并**管道**属性  

    单击**配置**。  

4. 在中**配置发送处理程序**窗口中，选择**发送处理程序**适用于单个适配器。 默认发送处理程序是**BizTalkServerApplication**。 对于要添加新的发送处理程序的步骤，请转到[如何创建适配器处理程序](http://go.microsoft.com/fwlink/p/?LinkId=263646)。  

    有很多原因要使用单独的主机，包括：  

   - **32 位要求**:某些适配器需要 32 位主机，如 FTP 和 POP3 适配器。 可以将所有组合或各个 32 位适配器到它们自己的主机。  

      [BizTalk Server 64 位支持](../core/biztalk-server-64-bit-support2.md)  

   - **按用途划分主机**:创建一个主机用于发送，用于接收，处理业务流程，用于跟踪的主机的主机的主机。  

   - **不同的主机设置**:在主机级别实施了许多设置。 因此，不同的阻止设置进行配置的每个主机。 例如，可以禁用在 HostA 上的阻止功能。 跟踪 HostB 中的每个事件。 修改 HostC 的.NET CLR 设置。 增加 hostd 的内存使用量。  

   - **安全**:安全性在主机级别来实现。 每个主机在其自身 Windows 帐户下运行。 例如，HostA 使用 FILE 适配器来访问文件共享。 向 HostA 用户帐户授予权限的文件共享。 HostB 使用 IIS 服务器上承载的 web 服务。 为提供 HostB 用户帐户授权对 web 服务。 这还会阻止其他主机帐户访问它不需要访问的实体。  

   - **单独的适配器**:例如，你有多个项目 （接收位置和发送端口） 使用 HTTP 适配器。 你想使用自己的主机中的 HTTP 适配器关联的所有内容。  

   - **单独的业务流程**:个体业务流程可以在它们自己的主机。 例如，如果业务流程使用较高的内存或 cpu 使用率较高，然后将该业务流程置于自己的主机。  

     [BizTalk Server 性能优化指南](http://msdn.microsoft.com/library/dn775063\(v=bts.10\).aspx)并[如何维护和故障排除 BizTalk Server 数据库](http://support.microsoft.com/kb/952555)提供了性能建议。  

5. 单击**确定**保存设置。  

6. 其他发送端口配置选项包括：  

   1.  [如何配置传输高级选项的发送端口](../core/how-to-configure-transport-advanced-options-for-a-send-port.md)  

   2.  [如何配置发送端口的出站映射](../core/how-to-configure-outbound-maps-for-a-send-port.md)  

   3.  [如何为发送端口配置筛选器](../core/how-to-configure-filters-for-a-send-port.md)  

   4.  [如何为发送端口分配证书](../core/how-to-assign-a-certificate-to-a-send-port.md)  

   5.  [如何为发送端口配置跟踪](../core/how-to-configure-tracking-for-a-send-port.md)  

7. 单击**确定**保存设置。  

   其他发送端口主题：  

   [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)  

   [创建和配置发送端口组](../core/creating-and-configuring-send-port-groups.md)  

## <a name="see-also"></a>请参阅  
 [SharePoint Services 适配器故障排除](../core/troubleshooting-sharepoint-services-adapter.md)   
 [配置 SharePoint Services 接收位置](../core/configure-sharepoint-services-receive-location.md)   
 [CSOM:SharePoint Services Adapter](../core/csom-sharepoint-services-adapter.md)