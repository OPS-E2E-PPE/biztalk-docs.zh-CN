---
title: 使用 Web Services 发布向导将架构发布为 Web 服务 |Microsoft Docs
description: 如何使用 BizTalk Web Services 发布向导将架构发布为 Web 服务
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Web Services Publishing Wizard, publishing
- BizTalk Web Services Publishing Wizard, schemas
ms.assetid: b22de720-1416-486a-988f-e52527ad9ab1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ada882149fc966d0b36062fb007c3b5722a9b2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398393"
---
# <a name="publish-schemas-as-a-web-service-in-biztalk"></a>将架构发布为 BizTalk 中的 Web 服务
使用 BizTalk Web Services 发布向导将架构发布为 Web 服务。  
  
## <a name="publish-schemas-as-a-web-service"></a>将架构发布为 web 服务  
  
1. 在中**程序**，选择**BizTalk Server**，然后选择**BizTalk Web Services 发布向导**。  
  
   > [!IMPORTANT]
   >  必须生成 BizTalk 项目在运行 BizTalk Web Services 发布向导之前。  
  
2. 上**欢迎**页上，单击**下一步**。  
  
3. 上**创建 Web 服务**页上，选择**架构发布为 web 服务**，然后单击**下一步**。  
  
4. 上**Web 服务**页上，选择要发布的 Web 服务。 使用中的树**Web 服务说明**对话框可以添加、 删除、 重命名和编辑 Web 服务说明节点。 **信息**对话框提供了有关所选节点的信息，并显示当前节点或任何子节点中的任何错误：  
  
   -   （Web 服务说明） 的树的根节点描述了 Web 服务项目的名称。 虚拟目录名称使用的根节点作为默认名称。 可以通过选择修改 Web 服务说明**重命名 web 服务说明**。  
  
   -   若要添加新的 Web 服务，请右键单击**Web 服务说明**节点，并单击**添加 web 服务**。 这将创建新的 Web 服务而无需任何 Web 方法。 若要修改 Web 服务的名称，请右键单击 Web 服务节点，然后选择**重命名 web 服务**，然后按 Enter 以接受新名称。  
  
   -   若要添加新的 Web 方法，请右键单击 Web 服务节点，指向**添加 Web 方法**，然后单击**单向**（对于请求 Web 方法） 或**请求-响应**(为请求-响应 Web 方法） 从快捷菜单。  
  
   -   若要设置的请求和响应架构类型，请右键单击**请求**或**响应**节点，，然后单击**选择架构类型**。 在中**请求消息类型**框中，键入包含文档架构中的程序集名称**BizTalk 程序集文件**文本框中或单击**浏览**搜索程序集。 **可用架构类型**列表视图中显示的架构的每个根元素。 选择要添加为请求或响应架构类型的根节点。  
  
       > [!NOTE]
       >  如果您已 BizTalk 程序集文件安装到全局程序集缓存 (GAC) 中，请确保已经使用将在中选择的程序集更新了 GAC 中的程序集**请求消息类型**对话框。 如果 GAC 具有相同的完全限定的名称，BizTalk Web Services 发布向导将使用 GAC 中的程序集文件而不是所选的一个。  
  
   -   您可以重命名**请求**并**响应**节点而不会影响生成的代码。 在之后定义了架构，您可以重命名部分元素中，这会修改 Web 方法参数名称。 通过查看生成的 Web 服务代码，可以看到所做的更改。  
  
   > [!NOTE]
   >  重命名任何 Web 服务说明节点时，不能使用空格。  
  
5. 单击**下一步**继续执行向导。  
  
6. 上**Web 服务属性**页上，在**web 服务的目标命名空间**对话框中，键入 Web 服务的目标命名空间，并选择相应的框以指定向导应如何处理 SOAP 标头和单一登录支持 Web 服务。 如果你想要进一步自定义 Web 服务实现，请单击**高级**按钮。 它会显示更多的可用选项：  
  
   |Option|ReplTest1|Description|  
   |------------|-----------|-----------------|  
   |SOAP 参数样式|默认|此选项指定的 SOAP 消息中如何格式化参数。 有关详细信息，请参阅 SoapParameterStyle 枚举[ http://go.microsoft.com/fwlink/?LinkId=62259 ](http://go.microsoft.com/fwlink/?LinkId=62259)。|  
   |SOAP 参数样式|裸机|此选项指定的 SOAP 消息中如何格式化参数。 有关详细信息，请参阅 SoapParameterStyle 枚举[ http://go.microsoft.com/fwlink/?LinkId=62259 ](http://go.microsoft.com/fwlink/?LinkId=62259)。|  
   |SOAP 参数样式|包装|此选项指定的 SOAP 消息中如何格式化参数。 有关详细信息，请参阅 SoapParameterStyle 枚举[ http://go.microsoft.com/fwlink/?LinkId=62259 ](http://go.microsoft.com/fwlink/?LinkId=62259)。|  
   |一致性声明|None|此选项指定绑定声明符合的 Web 服务互操作性 (WSI) 规范。 有关详细信息，请参阅在 WebServiceBindingAttribute.ConformsTo 属性[ http://go.microsoft.com/fwlink/?LinkId=193064 ](http://go.microsoft.com/fwlink/?LinkId=193064)。|  
   |一致性声明|WS-我基本配置文件 1.1|此选项指定绑定声明符合的 Web 服务互操作性 (WSI) 规范。 有关详细信息，请参阅在 WebServiceBindingAttribute.ConformsTo 属性[ http://go.microsoft.com/fwlink/?LinkId=193064 ](http://go.microsoft.com/fwlink/?LinkId=193064)。|  
   |强制请求响应|[默认]|此选项指定单向 BizTalk 操作是否应作为请求-响应 web 方法公开。 默认值不是强制单向标志。|  
  
   > [!NOTE]
   >  任何 SOAP 标头选项全局应用于所有 Web 服务和 Web 方法运行该向导的此实例时创建所选内容。  
  
7. 上**Web 服务属性**页上，单击**下一步**。  
  
8. 如果所选**添加附加 SOAP 标头**，则**请求 SOAP 标头**并**响应 SOAP 标头**页面以显示。 可以添加和删除使用的请求和响应 SOAP 标头**外**并**删除**下列对话框中的按钮：  
  
   -   若要添加的 SOAP 标头，请单击**添加**。 在中**BizTalk 程序集名称 (\*.dll)** 文本框中，键入程序集名称或浏览包含 SOAP 标头架构中的程序集**BizTalk 程序集文件**文本框。 **可用架构类型**列表视图中显示的架构的每个根元素。 选择要添加作为请求或响应 SOAP 标头的根节点。 若要选择多个项，按住 CTRL 键并单击**确定**。  
  
   -   要从列表中删除 SOAP 标头，从添加 SOAP 标头的列表中选择它，然后单击**删除**。  
  
   -   单击**下一步**在每个 SOAP 标头页上，继续执行向导。  
  
   > [!NOTE]
   >  目标命名空间和根元素名称定义 SOAP 标头。  
  
   > [!NOTE]
   >  如果同一目标命名空间/根元素名称组合添加为请求和响应 SOAP 标头，它将不被处理为输入/输出标头中。 您必须手动将传入标头复制到业务流程内部的传出标头。  
  
   > [!NOTE]
   >  同一目标命名空间/根元素名称组合只能添加作为请求 SOAP 标头的一次，一次为响应 SOAP 标头。  
  
9. 上**Web 服务项目**页上，在**项目位置**文本中，键入项目位置。 您可以接受默认位置 (`http://localhost/your_project_name`) 中，键入项目的位置或单击**浏览**并选择 Web 目录。 选择以下选项之一：  
  
    -   **覆盖现有项目。** 此选项才可用的项目位置已存在。 您才能够发布到相同的位置，如果选择此选项。 否则，必须输入不同的项目位置。  
  
    -   **允许匿名访问 web 服务。** 此选项将添加到创建的虚拟目录的匿名访问。 默认情况下，虚拟目录的访问权限从继承其父虚拟目录或 Web 站点 （如果它是顶级虚拟目录）。  
  
    -   **创建 BizTalk 接收位置。** 此选项会自动创建 SOAP 适配器接收端口和对应于每个生成的.asmx 文件的位置。 如果另一个接收位置已存在，则不会替换该接收位置。 使用格式解析 SOAP 适配器的接收位置"/\<*虚拟目录名称*\>/\<*业务流程 namespace_typename_portname* \>.asmx"。 选择此选项后，选择接收端口和位置将生成的应用程序。  
  
        > [!NOTE]
        >  项目位置可位于其他服务器上。 若要将 Web 服务发布到另一台服务器，键入项目名称设置为 **`http://<servername>/<project_name>`** 。  
  
        > [!NOTE]
        >  项目位置可位于非默认网站上。 发布到非默认网站时，在 URL 中包括该网站的端口号： `http://localhost:8080/<project_name>`。  
  
        > [!NOTE]
        >  当使用向导创建接收位置时，向导将创建接收位置使用许多默认值。 接收和发送管道的默认值是**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**并**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。 如果通过已发布的 Web 服务接收的消息需要任何特殊的管道处理 （例如，验证、 相关的更多信息或入站/出站映射），则应设置发送和接收管道， **Microsoft.BizTalk.DefaultPipelines.XMLReceive**， **Microsoft.BizTalk.DefaultPipelines.XMLSend**，或自定义管道。  
  
10. 单击**下一步**以查看 ASP.NET Web 服务项目设置。  
  
11. 单击**创建**创建 ASP.NET Web 服务。  
  
12. 单击**完成**完成 BizTalk Web Services 发布向导。  
  
## <a name="see-also"></a>请参阅  
 [将架构发布为 Web 服务](../core/publishing-schemas-as-a-web-service.md)
