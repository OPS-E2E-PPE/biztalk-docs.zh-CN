---
title: 自定义 Web 部件使用 Siebel 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3a6c04-6523-483c-bdf4-ce0ac47cda87
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ad29a3ad28fcea81b00b6b2e2dabf51f0962e79
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963955"
---
# <a name="use-a-custom-web-part-with-the-siebel-adapter"></a>用于 Siebel 适配器的自定义 Web 部件
本部分提供有关使用 Microsoft Office SharePoint Server 的自定义 Web 部件的信息。 若要使用自定义 Web 部件，您必须执行以下操作：  
  
1.  创建自定义 Web 部件  
  
2.  将自定义 Web 部件部署到 SharePoint 门户网站  
  
3.  配置 SharePoint 门户以使用自定义 Web 部件  
  
## <a name="before-you-begin"></a>开始之前  
 创建自定义 Web 部件之前：  
  
-   作为 WCF 服务发布 Siebel 项目。 有关详细信息，请参阅[步骤 1： 发布 Siebel 业务组件操作作为 WCF 服务](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)中[教程 1： 演示数据从 Siebel 系统 SharePoint 站点上](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)。  
  
-   创建在 Microsoft Office SharePoint Server 中使用业务数据目录的 Siebel 项目的应用程序定义文件。 有关详细信息，请参阅[步骤 2： 为 Siebel 业务组件操作创建应用程序定义文件](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)中[教程 1： 演示数据从 Siebel 系统 SharePoint 站点上](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)。  
  
##  <a name="Create_a_Custom_Web_Part"></a>步骤 1： 创建自定义 Web 部件  
 若要创建自定义 Web 部件使用 Visual Studio，请执行以下操作：  
  
1.  启动 Visual Studio，然后创建一个项目。  
  
2.  在**新项目**对话框中，从**项目类型**窗格中，选择**Visual C#**。 从**模板**窗格中，选择**类库**。  
  
3.  指定的名称和解决方案的位置。 对于本主题中，指定`CustomWebPart`中**名称**和**解决方案名称**框。 指定一个位置，，然后单击**确定**。  
  
4.  将对 System.Web 组件的引用添加到项目。 右键单击中的项目名称**解决方案资源管理器**，然后单击**添加引用**。 在**添加引用**对话框中，选择**System.Web**中 **.NET**选项卡上，并依次**确定**。 System.Web 组件包含 System.Web.UI.WebControls.WebParts 的所需命名空间。  
  
5.  添加所需的代码，根据你在项目中的问题。 与某些问题相关的代码示例，请参阅"问题涉及自定义 Web 部件"中[注意事项与 SharePoint 使用 Siebel 适配器时](../../adapters-and-accelerators/adapter-siebel/considerations-when-using-the-siebel-adapter-with-sharepoint.md)。  
  
6.  生成此项目。 上的项目的成功生成，.dll 文件，CustomWebPart.dll，将生成在\<*项目文件夹* \> /bin/Debug 文件夹。  
  
## <a name="step-2-deploy-the-custom-web-part-to-a-sharepoint-portal"></a>步骤 2： 将自定义 Web 部件部署到 SharePoint 门户网站  
 你必须执行以下操作来使 CustomWebPart.dll 文件 （自定义 Web 部件） 中创建"步骤 1： 创建自定义 Web 部件"的 SharePoint 门户网站上使用本主题：  
  
-   **将 CustomWebPart.dll 文件复制到 SharePoint 门户网站的 bin 文件夹**: Microsoft Office SharePoint Server 创建门户下的\<*根驱动器*\>: \Inetpub\wwwroot\wss\VirtualDirectories 文件夹。 文件夹为每个门户中，创建，并且可以使用的端口号来标识。 必须将复制中创建的 CustomWebPart.dll 文件"步骤 1： 创建自定义 Web 部件"到本主题的\<*根驱动器*\>: \Inetpub\wwwroot\wss\VirtualDirectories\\ <*Port_Number*\>\bin 文件夹。 例如，如果你的 SharePoint 门户的端口号是 13614，你必须 CustomWebPart.dll 将文件复制到\<*根驱动器*\>: \Inetpub\wwwroot\wss\VirtualDirectories\13614\bin 文件夹。  
  
    > [!TIP]
    >  另一种方法来查找 SharePoint 门户网站的文件夹位置是使用**Internet Information Services (IIS) Manager**窗口 (**启动** > **运行** >  **inetmgr**)。 找到你在中的 SharePoint 门户**Internet Information Services (IIS) Manager**窗口 ([*computer_name*] > 网站 > [*门户名称*])，右键单击，并然后单击**属性**的快捷菜单中。 在 SharePoint 门户的属性对话框中，单击**主目录**选项卡上，然后选择**本地路径**框。  
  
-   **在 web.config 文件中添加安全控制项**： 因为不同的计算机上以及由多个用户，则会使用 CustomWebPart.dll 文件，您必须声明为"安全"。 文件 为此，请打开 web.config 文件位于 SharePoint 门户文件夹在\<*根驱动器*\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number\>。 下`<SafeControls>`部分的 web.config 文件中，添加以下安全控件项：  
  
    ```  
    <SafeControl Assembly="CustomWebPart" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
    ```  
  
     保存 web.config 文件中，并将其关闭。  
  
## <a name="step-3-configure-the-sharepoint-portal-to-use-the-custom-web-part"></a>步骤 3： 配置 SharePoint 门户以使用自定义 Web 部件  
 你需要将自定义 Web 部件添加到 Microsoft Office SharePoint Server Web 部件库，以便 SharePoint 门户网站上使用它。 为此：  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击名称的共享服务提供程序 (SSP) 你想要添加自定义 Web 部件。  
  
3.  上**共享服务管理**页上，在右上角，单击**站点操作**，然后单击**创建**。  
  
4.  上**站点设置**页上，单击**Web 部件**下**库**列。  
  
5.  上**Web 部件库**页上，若要将自定义 Web 部件添加到库中，单击**新建**。 在此点自定义 Web 部件在中不可用**Web 部件库**页。  
  
6.  上**新的 Web 部件**页上，找到**CustomWebPart** （自定义 Web 部件的名称） 在列表中，选择左侧上的复选框，然后单击**导入库**的顶部页。 这将添加**CustomWebPart**中的条目**Web 部件库**页。  
  
 现在，你可以使用自定义 Web 部件 (**CustomWebPart**) 在你的 SharePoint 门户中创建 Web 部件。 自定义 Web 部件 (**CustomWebPart**) 将出现在**杂项**主题中**添加 Web 部件**页。  
  
## <a name="see-also"></a>另请参阅  
 [使用 Siebel 适配器和 SharePoint](../../adapters-and-accelerators/adapter-siebel/use-the-siebel-adapter-with-sharepoint.md)