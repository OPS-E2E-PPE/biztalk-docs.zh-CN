---
title: 如何使用 BizTalk Web Services 发布向导业务流程发布为 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- BizTalk Web Services Publishing Wizard, publishing
- BizTalk Web Services Publishing Wizard
- Web services, orchestrations
- BizTalk Web Services Publishing Wizard, orchestrations
- BizTalk Web Services Publishing Wizard, about BizTalk Web Services Publishing Wizard
- orchestrations, publishing
ms.assetid: d990f8e4-88ce-4718-8a94-63796b8d92dc
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 204c574494c2dfb82a8722675a6f64fb694d5ae4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398411"
---
# <a name="how-to-use-the-biztalk-web-services-publishing-wizard-to-publish-an-orchestration-as-a-web-service"></a>如何使用 BizTalk Web Services 发布向导业务流程发布为 Web 服务
BizTalk Web Services 发布向导用于业务流程发布为 Web 服务。  
  
> [!NOTE]
>  必须生成 BizTalk 项目在运行 BizTalk Web Services 发布向导之前。  
  
> [!NOTE]
>  可以使用命令行工具 BTSWebSvcPub.exe 将业务流程作为 Web 服务发布。 有关详细信息，请参阅[BTSWebSvcPub 命令行参考](../core/btswebsvcpub-command-line-reference.md)。  
  
### <a name="to-publish-an-orchestration-as-a-web-service"></a>若要在业务流程发布为 Web 服务  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Web Services 发布向导**.  
  
2.  上**欢迎使用 BizTalk Web Services 发布向导**页上，单击**下一步**。  
  
3.  上**创建 Web 服务**页上，选择**BizTalk 业务流程发布为 web services**，然后单击**下一步**。  
  
4.  上**BizTalk 程序集**页上，在 BizTalk 程序集文件 (\*.dll) 文本框中，键入 BizTalk 程序集文件的名称，或单击**浏览**以浏览到包含的程序集业务流程以发布，然后单击**下一步**。  
  
    > [!NOTE]
    >  之前选择 BizTalk 程序集文件，将所有依赖程序集复制到同一文件夹中，与 BizTalk 程序集或安装到全局程序集缓存 (GAC) 中的依赖程序集。  
  
    > [!NOTE]
    >  如果 BizTalk 程序集文件安装到 GAC 中时，请确保已经使用将在中选择的程序集更新了 GAC 中的程序集**BizTalk 程序集**对话框。 如果 GAC 具有相同的完全限定的名称，BizTalk Web Services 发布向导将使用 GAC 中的程序集文件而不是所选的一个。  
  
    > [!NOTE]
    >  如果包含业务流程在 Visual Studio 中打开 BizTalk Web Services 发布向导，BizTalk 程序集文件将填充包含业务流程的程序集。  
  
    > [!NOTE]
    >  路径长度超过 260 个字符可能会收到一条错误消息的路径太长。  
  
5.  上**业务流程和端口**页上，单击加号展开每个程序集和业务流程的树节点。 选择业务流程和端口发布通过选中相应树节点复选框。 如果你想要创建一个 Web 服务 (.asmx) 的所有选定的接收端口，而不是一个 Web 服务为每个接收端口，请选择**所有选定的端口合并为单个 web 服务**选项，并单击**下一步**.  
  
    > [!NOTE]
    >  所有选定的端口合并到单个 web 服务时，所有选定的端口都具有相同的端口类型，并且端口中的操作名称都是唯一。  
  
6.  上**Web 服务属性**页上，在**web 服务的目标命名空间**框中，键入 Web 服务的目标命名空间，选择相应的框以指定向导应如何处理 SOAP标头和 SharePoint Portal Server 2007 单一登录 (SSO) 支持的 Web 服务。 如果你想要进一步自定义 Web 服务实现，请单击**高级**按钮。 它会显示更多的可用选项：  
  
    |Option|ReplTest1|Description|  
    |------------|-----------|-----------------|  
    |SOAP 参数样式|默认|此选项指定的 SOAP 消息中如何格式化参数。 有关详细信息，请参阅 SoapParameterStyle 枚举[ http://go.microsoft.com/fwlink/?LinkId=62259 ](http://go.microsoft.com/fwlink/?LinkId=62259)。|  
    |SOAP 参数样式|裸机|此选项指定的 SOAP 消息中如何格式化参数。 有关详细信息，请参阅 SoapParameterStyle 枚举[ http://go.microsoft.com/fwlink/?LinkId=62259 ](http://go.microsoft.com/fwlink/?LinkId=62259)。|  
    |SOAP 参数样式|包装|此选项指定的 SOAP 消息中如何格式化参数。 有关详细信息，请参阅 SoapParameterStyle 枚举[ http://go.microsoft.com/fwlink/?LinkId=62259 ](http://go.microsoft.com/fwlink/?LinkId=62259)。|  
    |一致性声明|None|此选项指定绑定声明符合的 Web 服务互操作性 (WSI) 规范。 有关详细信息，请参阅在 WebServiceBindingAttribute.ConformsTo 属性[ http://go.microsoft.com/fwlink/?LinkId=193064 ](http://go.microsoft.com/fwlink/?LinkId=193064)。|  
    |一致性声明|WS-我基本配置文件 1.1|此选项指定绑定声明符合的 Web 服务互操作性 (WSI) 规范。 有关详细信息，请参阅在 WebServiceBindingAttribute.ConformsTo 属性[ http://go.microsoft.com/fwlink/?LinkId=193064 ](http://go.microsoft.com/fwlink/?LinkId=193064)。|  
    |强制请求响应|[默认]|此选项指定单向 BizTalk 操作是否应作为请求-响应 web 方法公开。 默认值不是强制单向标志。|  
    |强制请求响应|否|此选项指定单向 BizTalk 操作是否应作为请求-响应 web 方法公开。 默认值不是强制单向标志。|  
    |强制请求响应|是|此选项指定单向 BizTalk 操作是否应作为请求-响应 web 方法公开。 默认值不是强制单向标志。|  
  
7.  上**Web 服务属性**页上，单击**下一步**。  
  
    > [!NOTE]
    >  选择任何 SOAP 标头选项全局应用于所有 Web 服务和运行该向导的此实例时创建的 Web 方法。  
  
8.  如果所选**添加附加 SOAP 标头**选项，**请求 SOAP 标头**并**响应 SOAP 标头**页面以显示。 可以添加和删除使用的请求和响应 SOAP 标头**外**并**删除**下列对话框中的按钮：  
  
    -   若要添加的 SOAP 标头，请单击**添加**。 在中**BizTalk 程序集文件 (\*.dll)** 文本框中，键入或浏览包含 SOAP 标头架构的程序集。 **可用架构类型**列表视图中显示的架构的每个根元素。 选择要添加作为请求或响应 SOAP 标头的根节点。 若要选择多个项，按住 CTRL 键并单击**确定**。  
  
    -   要从列表中删除 SOAP 标头，从添加 SOAP 标头的列表中选择它，然后单击**删除**。  
  
    -   单击**下一步**每个**SOAP 标头**页后，可以继续执行向导。  
  
    > [!NOTE]
    >  目标命名空间和根元素名称定义 SOAP 标头。  
  
    > [!NOTE]
    >  如果同一目标命名空间/根元素名称组合添加为请求和响应 SOAP 标头，它将不被处理为输入/输出标头中。 您必须手动将传入标头复制到业务流程内部的传出标头。  
  
    > [!NOTE]
    >  同一目标命名空间/根元素名称组合只能添加作为请求 SOAP 标头的一次，一次为响应 SOAP 标头。  
  
9. 上**Web 服务项目**页上，在**项目名称**文本中，键入项目名称。 您可以接受默认位置 (`http://localhost/<project_name>`)，键入在项目的位置**项目位置**文本框中或单击**浏览**并选择 Web 目录。 选择以下选项之一：  
  
    -   **覆盖现有项目。** 此选项才可用的项目位置已存在。 您才能够发布到相同的位置，如果选择此选项。 否则，必须输入不同的项目位置。  
  
    -   **允许匿名访问 web 服务。** 此选项将添加到创建的虚拟目录的匿名访问。 默认情况下，虚拟目录的访问权限从继承其父虚拟目录或 Web 站点 （如果它是顶级虚拟目录）。  
  
    -   **创建 BizTalk 接收位置。** 此选项会自动创建 SOAP 适配器接收端口和对应于每个生成的.asmx 文件的位置。 如果接收位置已存在，则不会替换它。 使用格式解析 SOAP 适配器的接收位置 /\<*虚拟目录名称*\>/\<*业务流程 namespace_typename_portname* \>.asmx。 选择此选项后，选择接收端口和位置将生成的应用程序。  
  
        > [!NOTE]
        >  项目位置可位于其他服务器上。 若要将 Web 服务发布到另一台服务器，键入项目名称设置为`http://<servername>/<project_name>`。  
  
        > [!NOTE]
        >  项目位置可位于非默认网站上。 发布到非默认网站时，请在该 URL 中包括网站的端口号。 例如，`http://localhost:8080/<project_name>`。  
  
        > [!NOTE]
        >  在使用向导创建接收位置时，向导会使用默认值创建接收位置。 接收管道的默认值是**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**管道。 如果通过已发布的 Web 服务接收的消息需要任何特殊的管道处理 (例如，验证、 关联 / 属性升级或者入站/出站映射)，然后应将接收管道为**Microsoft.BizTalk.DefaultPipelines.XMLReceive**，或自定义管道。  
  
        > [!NOTE]
        >  当您使用从业务流程 （调用） Web 服务时，则 SOAP 适配器仅支持直通样式的发送管道。 可以使用自定义发送管道，但它不能包含修改消息的正文部分的组件。 这些组件包括 XML 组装器和任何编码组件。  
  
        > [!NOTE]
        >  在到达此页并选择从选择回退**架构发布为 web 服务**选项，在**Web Services**页上，你可能会看到**Web 服务说明**显示从 BizTalk 程序集以前之前你选择的服务和方法名称从回**BizTalk 业务流程发布为 web services**选项。 这是因为更改发布方法时不会清除内存中的 web 服务说明。  
  
10. 单击**下一步**以查看 ASP.NET Web 服务项目设置。  
  
11. 单击**创建**创建 ASP.NET Web 服务。  
  
12. 单击**完成**完成 BizTalk Web Services 发布向导。  
  
> [!NOTE]
>  如果发布的业务流程作为 Windows Vista 上的 web 服务，则必须更新托管服务的虚拟目录。 为此，请发出以下命令从命令提示符下，替换\<vdir\>的虚拟目录名称： **%systemroot%\system32\inetsrv\appcmd。EXE 迁移配置"Default Web Site /\<vdir 名称\>"**。  
  
## <a name="see-also"></a>请参阅  
 [业务流程发布为 Web 服务](../core/publishing-an-orchestration-as-a-web-service.md)   
 [如何将业务流程映射到 Web 服务](../core/how-to-map-orchestrations-to-web-services.md)