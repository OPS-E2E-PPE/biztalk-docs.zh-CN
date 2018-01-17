---
title: "如何使用 BizTalk Web Services 发布向导发布作为 Web 服务的架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Web Services Publishing Wizard, publishing
- BizTalk Web Services Publishing Wizard, schemas
ms.assetid: b22de720-1416-486a-988f-e52527ad9ab1
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba7f93eae8866212546f5daa3b9ed1a5b653c983
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-use-the-biztalk-web-services-publishing-wizard-to-publish-schemas-as-a-web-service"></a>如何使用发布向导的 BizTalk Web 服务以将架构作为 Web 服务发布
使用 BizTalk Web Services 发布向导可将架构发布为 Web Services。  
  
### <a name="to-publish-schemas-as-a-web-service"></a>将架构发布为 Web Services  
  
1.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Web 服务发布向导**。  
  
    > [!IMPORTANT]
    >  在运行 BizTalk Web Services 发布向导之前，必须生成 BizTalk 项目。  
  
2.  上 **欢迎** 页上，单击 **下一步**。  
  
3.  上 **创建 Web 服务** 页上，选择 **发布作为 web 服务的架构** ，然后单击 **下一步**。  
  
4.  上 **Web 服务** 页上，定义要发布的 Web 服务。 你使用的树中 **Web 服务描述** 对话框中，添加、 删除、 重命名，以及编辑 Web 服务描述节点。 **信息** 对话框中提供有关所选节点的信息，并在当前节点或任何子节点中显示任何错误︰  
  
    -   树的根节点（Web Services 说明）描述了 Web Services 项目名称。 虚拟目录名称使用该根节点作为默认名称。 你可以通过选择修改 Web 服务描述 **重命名 web 服务描述**。  
  
    -   要添加一个新的 Web 服务，请右键单击 **Web 服务描述** 节点，，然后单击 **添加 web 服务**。 这将在不使用任何 Web 方法的情况下创建新的 Web Services。 若要修改 Web 服务的名称，右键单击 Web 服务节点中，然后选择 **重命名 web 服务**,，然后按 Enter 以接受新的名称。  
  
    -   若要添加新的 Web 方法，右击 Web 服务节点，指向 **添加 Web 方法**, ，然后单击 **单向** （对于 Web 方法的请求） 或 **请求-响应** （对于请求-响应 Web 方法） 从快捷菜单。  
  
    -   若要设置的请求和响应架构类型，右键单击 **请求** 或 **响应** 节点，，然后单击 **选择架构类型**。 在 **请求消息类型** 对话框框中，键入包含文档架构中的程序集名称 **BizTalk 程序集文件** 文本框中或单击 **浏览** 搜索程序集。 **可用架构类型** 列表视图显示每个根元素的架构。 选择要作为请求或响应架构类型添加的根节点。  
  
        > [!NOTE]
        >  如果你安装 BizTalk 程序集文件到全局程序集缓存 (GAC) 中，请确保在 GAC 的程序集，已更新与程序集将在中选择 **请求消息类型** 对话框。 如果 GAC 具有相同的完全限定名，则 BizTalk Web Services 发布向导将使用 GAC 中的程序集文件而不是你选择的程序集文件。  
  
    -   你可以重命名 **请求** 和 **响应** 节点而不会影响生成的代码。 在定义了架构之后，可以重命名 part 元素，这会修改 Web 方法的参数名称。 通过查看所生成的 Web Services 代码，可以看到发生的更改。  
  
    > [!NOTE]
    >  在重命名任何 Web Services 说明节点时，不能使用空格。  
  
5.  单击 **下一步** 继续执行向导。  
  
6.  上 **Web 服务属性** 页上，在 **的 web 服务的目标命名空间** 对话框中，键入 Web 服务的目标命名空间，然后选择相应的框以指定向导应如何处理 SOAP 标头和单一登录支持 Web 服务。 如果你想要进一步自定义的 Web 服务实现，请单击 **高级** 按钮。 这将显示更多可用选项：  
  
    |选项|值|Description|  
    |------------|-----------|-----------------|  
    |SOAP 参数样式|Default|该选项指定在 SOAP 消息中如何设置参数格式。 有关详细信息，请参阅在 SoapParameterStyle 枚举 [http://go.microsoft.com/fwlink/?LinkId=62259](http://go.microsoft.com/fwlink/?LinkId=62259)。|  
    |SOAP 参数样式|Bare|该选项指定在 SOAP 消息中如何设置参数格式。 有关详细信息，请参阅在 SoapParameterStyle 枚举 [http://go.microsoft.com/fwlink/?LinkId=62259](http://go.microsoft.com/fwlink/?LinkId=62259)。|  
    |SOAP 参数样式|Wrapped|该选项指定在 SOAP 消息中如何设置参数格式。 有关详细信息，请参阅在 SoapParameterStyle 枚举 [http://go.microsoft.com/fwlink/?LinkId=62259](http://go.microsoft.com/fwlink/?LinkId=62259)。|  
    |一致性声明|无|该选项指定绑定声明所符合的 Web Services 互操作性 (WSI) 规范。 有关详细信息，请参阅在 WebServiceBindingAttribute.ConformsTo 属性 [http://go.microsoft.com/fwlink/?LinkId=193064](http://go.microsoft.com/fwlink/?LinkId=193064)。|  
    |一致性声明|WS-I 基本配置文件 1.1|该选项指定绑定声明所符合的 Web Services 互操作性 (WSI) 规范。 有关详细信息，请参阅在 WebServiceBindingAttribute.ConformsTo 属性 [http://go.microsoft.com/fwlink/?LinkId=193064](http://go.microsoft.com/fwlink/?LinkId=193064)。|  
    |强制请求响应|[默认值]|该选项指定单向 BizTalk 操作是否应作为请求-响应 Web 方法公开。 默认值不强制单向标志。|  
  
    > [!NOTE]
    >  所选的任何 SOAP 标头选项将全局应用于在运行该向导实例时创建的所有 Web Services 和 Web 方法。  
  
7.  上 **Web 服务属性** 页上，单击 **下一步**。  
  
8.  如果你选择 **添加其他的 SOAP 标头**, 、 **请求 SOAP 标头** 和 **响应 SOAP 标头** 显示页。 你可以添加和删除请求和响应使用的 SOAP 标头 **添加** 和 **删除** 在以下对话框中的按钮︰  
  
    -   若要添加的 SOAP 标头，单击 **添加**。 在 **BizTalk 程序集名称 (\*.dll)** 文本框中，键入程序集名称或包含的 SOAP 标头架构中的程序集浏览 **BizTalk 程序集文件** 文本框。 **可用架构类型** 列表视图显示每个根元素的架构。 选择要作为请求或响应 SOAP 标头添加的根节点。 若要选择多个项，请按住 CTRL 键并单击 **确定**。  
  
    -   要从列表中删除的 SOAP 标头，从添加 SOAP 标头的列表中选择它，然后单击 **删除**。  
  
    -   单击 **下一步** 上每个 SOAP 标头页后，可以继续执行向导。  
  
    > [!NOTE]
    >  目标命名空间和根元素名称用于定义 SOAP 标头。  
  
    > [!NOTE]
    >  如果同一目标命名空间/根元素名称组合是作为请求和响应 SOAP 标头添加的，则不会将该标头视为传入/传出标头。 必须在业务流程内部手动将传入标头复制到传出标头。  
  
    > [!NOTE]
    >  同一目标命名空间/根元素名称组合只能作为请求 SOAP 标头和响应 SOAP 标头各添加一次。  
  
9. 上 **Web 服务项目** 页上，在 **项目位置** 文本框中，键入项目位置。 你可以接受默认位置 (http://localhost/ <*文件的内容*>)，键入项目的位置或单击 **浏览** 并选择 Web 目录。 选择以下任何选项：  
  
    -   **覆盖现有项目。** 仅当项目位置已存在时，此选项才可用。 仅当选择了此选项时，你才能够发布到同一位置。 否则，必须输入不同的项目位置。  
  
    -   **允许匿名访问 web 服务。** 此选项会为已创建的虚拟目录添加匿名访问权限。 默认情况下，虚拟目录继承其父虚拟目录或网站（如果该目录是顶级虚拟目录）的访问权限。  
  
    -   **创建 BizTalk 接收位置。** 此选项自动创建与每个生成的 .asmx 文件对应的 SOAP 适配器接收端口和位置。 如果已存在其他接收位置，则不会替换此接收位置。 使用格式解析 SOAP 适配器接收位置"/\<*虚拟目录名称*\>/\<*orchestration namespace_typename_portname* \>.asmx"。 选择此选项后，选择将在其中生成接收端口和位置的应用程序。  
  
        > [!NOTE]
        >  项目位置可位于其他服务器上。 若要将 Web 服务发布到不同的服务器，键入项目名称作为**http://&lt*servername*>/<*文件的内容*>**。  
  
        > [!NOTE]
        >  项目位置可位于非默认网站上。 在发布到非默认网站时，在 URL 中包括的网站的端口号︰ http://localhost:8080/ / <*文件的内容*>。  
  
        > [!NOTE]
        >  在使用向导创建接收位置时，向导会使用多个默认值创建接收位置。 默认值为接收和发送管道 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive** 和 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。 如果通过已发布的 Web 服务接收的消息需要任何特殊的管道处理 （例如，验证、 关联或入站/出站映射），则应设置发送和接收到的管道 **Microsoft.BizTalk.DefaultPipelines.XMLReceive**, ，**Microsoft.BizTalk.DefaultPipelines.XMLSend**, ，或自定义管道。  
  
10. 单击 **下一步** 若要查看你的 ASP.NET Web 服务项目的设置。  
  
11. 单击 **创建** 创建 ASP.NET Web 服务。  
  
12. 单击 **完成** 完成 BizTalk Web 服务发布向导。  
  
## <a name="see-also"></a>另请参阅  
 [将架构发布为 Web 服务](../core/publishing-schemas-as-a-web-service.md)