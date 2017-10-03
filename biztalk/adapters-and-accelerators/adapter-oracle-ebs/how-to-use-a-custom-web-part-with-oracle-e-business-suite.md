---
title: "如何自定义 web 部件使用 Oracle E-business Suite |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf420061-41d1-4d97-9be1-403cd101e41c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c0cc9a3cbae11fd18cbe9a91249cf5d3cf42925
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-a-custom-web-part-with-oracle-e-business-suite"></a>如何通过 Oracle E-business Suite 中使用自定义 web 部件
本部分提供有关使用 Microsoft Office SharePoint Server 的自定义 Web 部件的信息。 若要使用自定义 Web 部件，您必须执行以下操作：  
  
1.  创建自定义 Web 部件  
  
2.  将自定义 Web 部件部署到 SharePoint 门户网站  
  
3.  配置 SharePoint 门户以使用自定义 Web 部件  
  
## <a name="before-you-begin"></a>开始之前  
 创建自定义 Web 部件之前：  
  
-   作为 WCF 服务发布 Oracle E-business Suite 项目。 有关详细信息，请参阅[步骤 1： 使用 Oracle E-business 适配器来创建和发布 WCF 服务](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)中[教程： 呈现数据的 SharePoint 站点上的 Oracle E-business Suite](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)。  
  
-   创建在 Microsoft Office SharePoint Server 中使用业务数据目录的 Oracle E-business Suite 项目的应用程序定义文件。 有关详细信息，请参阅[步骤 2： 创建应用程序定义文件的 Oracle E-business Suite 项目](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)中[教程： 呈现数据的 SharePoint 站点上的 Oracle E-business Suite](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)。  
  
##  <a name="Create_a_Custom_Web_Part"></a>步骤 1： 创建自定义 Web 部件  
 若要创建自定义 Web 部件使用 Visual Studio，请执行以下操作：  
  
1.  启动[!INCLUDE[vs2010](../../includes/vs2010-md.md)]，然后创建一个项目。  
  
2.  在**新项目**对话框中，从**项目类型**窗格中，选择**Visual C#**。 从**模板**窗格中，选择**类库**。  
  
3.  指定的名称和解决方案的位置。 对于本主题中，指定`CustomWebPart`中**名称**和**解决方案名称**框。 指定一个位置，，然后单击**确定**。  
  
4.  将对 System.Web 组件的引用添加到项目。 右键单击中的项目名称**解决方案资源管理器**，然后单击**添加引用**。 在**添加引用**对话框中，选择**System.Web**中**.NET**选项卡上，并依次**确定**。 System.Web 组件包含 System.Web.UI.WebControls.WebParts 的所需命名空间。  
  
5.  添加所需的代码，根据你在项目中的问题。 与某些问题相关的代码示例，请参阅"问题涉及自定义 Web 部件"中[注意事项与 SharePoint 使用 Oracle Business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/considerations-using-the-oracle-business-suite-adapter-with-sharepoint.md)。  
  
6.  生成此项目。 上的项目的成功生成，.dll 文件，CustomWebPart.dll，将生成在\<项目文件夹 >/bin/Debug 文件夹。  
  
7.  **仅对 64 位计算机**： 在执行以下步骤之前签署 CustomWebPart.dll 文件所用强名称。 否则，你将无法导入，并因此在 SharePoint 门户中使用 CustomWebPart.dll"步骤 3： 配置 SharePoint 门户以使用自定义 Web 部件。" 有关如何使用强名称程序集进行签名的信息，请参阅[如何： 使用强名称为程序集签名](https://msdn.microsoft.com/library/xc31ft41.aspx)。
  
## <a name="step-2-deploy-the-custom-web-part-to-a-sharepoint-portal"></a>步骤 2： 将自定义 Web 部件部署到 SharePoint 门户网站  
 你必须执行以下操作来使 CustomWebPart.dll 文件 （自定义 Web 部件） 中创建"步骤 1： 创建自定义 Web 部件"的 SharePoint 门户网站上使用本主题：  
  
-   **将 CustomWebPart.dll 文件复制到 SharePoint 门户网站的 bin 文件夹**: Microsoft Office SharePoint Server 创建门户下的\<根驱动器 >: \Inetpub\wwwroot\wss\VirtualDirectories 文件夹。 文件夹为每个门户中，创建，并且可以使用的端口号来标识。 必须将复制中创建的 CustomWebPart.dll 文件"步骤 1： 创建自定义 Web 部件"到本主题的\<根驱动器 >: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number > \bin 文件夹。 例如，如果你的 SharePoint 门户的端口号是 13614，你必须 CustomWebPart.dll 将文件复制到\<根驱动器 >: \Inetpub\wwwroot\wss\VirtualDirectories\13614\bin 文件夹。  
  
    > [!TIP]
    >  另一种方法来查找 SharePoint 门户网站的文件夹位置是使用**Internet Information Services (IIS) Manager**窗口 (**启动** > **运行** >  **inetmgr**)。 找到你在中的 SharePoint 门户**Internet Information Services (IIS) Manager**窗口 ([computer_name] > 网站 > [门户名称])，右键单击，然后再单击**属性**中快捷菜单。 在 SharePoint 门户的属性对话框中，单击**主目录**选项卡上，然后选择**本地路径**框。  
  
-   **在 web.config 文件中添加安全控制项**： 因为不同的计算机上以及由多个用户，则会使用 CustomWebPart.dll 文件，您必须声明为"安全"。 文件 为此，请打开 web.config 文件位于 SharePoint 门户文件夹在\<根驱动器 >: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number >。 下`<SafeControls>`部分的 web.config 文件中，添加以下安全控件项：  
  
    -   **在 32 位计算机：**  
  
        ```  
        <SafeControl Assembly="CustomWebPart" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
        ```  
  
    -   **在 64 位计算机：**  
  
        ```  
        <SafeControl Assembly="CustomWebPart, Version=1.0.0.0, Culture=neutral, PublicKeyToken=<PUBLICKKEYTOKEN_OF_CustomWebPart.dll>" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
        ```  
  
     保存 web.config 文件中，并将其关闭。  
  
## <a name="step-3-configure-the-sharepoint-portal-to-use-the-custom-web-part"></a>步骤 3： 配置 SharePoint 门户以使用自定义 Web 部件  
 你需要将自定义 Web 部件添加到 Microsoft Office SharePoint Server Web 部件库，以便 SharePoint 门户网站上使用它。 为此：  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击名称的共享服务提供程序 (SSP) 你想要添加自定义 Web 部件。  
  
3.  在共享服务管理页上，在右上角，单击**站点操作**，然后单击**创建**。  
  
4.  在站点设置页上，单击**Web 部件**下**库**列。  
  
5.  在 Web 部件库页上，若要将自定义 Web 部件添加到库，请单击**新建**。 此时没有 Web 部件库页上可用的自定义 Web 部件。  
  
6.  在新的 Web 部件页上，找到**CustomWebPart** （自定义 Web 部件的名称） 在列表中，选择左侧上的复选框，然后单击**导入库**页面顶部。 这将添加**CustomWebPart** Web 部件库页中的条目。  
  
 现在，你可以使用自定义 Web 部件 (**CustomWebPart**) 在你的 SharePoint 门户中创建 Web 部件。 自定义 Web 部件 (**CustomWebPart**) 将出现在**杂项**中添加 Web 部件页的部分。  
  
## <a name="see-also"></a>另请参阅  
[使用带有 SharePoint Oracle E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/use-the-oracle-e-business-suite-adapter-with-sharepoint.md)