---
title: SAP 适配器一起使用自定义 Web 部件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b7fecd2-a385-4b2d-a01b-3bfd65ecff3a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94a521caa483c258fd2bacb8b02a47d15ce666ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372267"
---
# <a name="use-a-custom-web-part-with-the-sap-adapter"></a>SAP 适配器一起使用自定义 Web 部件
本部分提供有关 Microsoft Office SharePoint Server 中使用自定义 Web 部件的信息。 若要使用自定义 Web 部件，必须执行以下操作：  
  
1.  创建自定义 Web 部件  
  
2.  将自定义 Web 部件部署到 SharePoint 门户网站  
  
3.  配置 SharePoint 门户以使用自定义 Web 部件  
  
## <a name="before-you-begin"></a>开始之前  
 创建自定义 Web 部件之前：  
  
-   将 SAP 项目作为 WCF 服务发布。 有关详细信息，请参阅[步骤 1:将 SAP 项目作为 WCF 服务发布](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)在[教程 1:从 SharePoint 站点上的 SAP 系统提供数据](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)。  
  
-   创建 SAP 项目使用 Microsoft Office SharePoint Server 中的业务数据目录应用程序定义文件。 有关详细信息，请参阅[步骤 2:为 SAP 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)在[教程 1:从 SharePoint 站点上的 SAP 系统提供数据](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)。  
  
##  <a name="Create_a_Custom_Web_Part"></a> 步骤 1：创建自定义 Web 部件  
 若要创建自定义 Web 部件使用 Visual Studio，请执行以下操作：  
  
1.  启动 Visual Studio 中，并创建一个项目。  
  
2.  在中**新的项目**对话框中，从**项目类型**窗格中，选择**Visual C#**。 从**模板**窗格中，选择**类库**。  
  
3.  指定的名称和位置的解决方案。 对于本主题中，指定`CustomWebPart`中**名称**并**解决方案名称**框。 指定一个位置，然后单击**确定**。  
  
4.  将对 System.Web 组件的引用添加到项目。 右键单击项目名称在**解决方案资源管理器**，然后单击**添加引用**。 在中**添加引用**对话框中，选择**System.Web**中 **.NET**选项卡，然后依次**确定**。 System.Web 组件包含所需的 System.Web.UI.WebControls.WebParts 命名空间。  
  
5.  添加基于你在项目中的问题所需的代码。 与某些问题相关的代码示例，请参阅"问题涉及自定义 Web 部件"中[与 SharePoint 结合使用 SAP 适配器时的注意事项](../../adapters-and-accelerators/adapter-sap/considerations-when-using-the-sap-adapter-with-sharepoint.md)。  
  
6.  生成项目。 在项目的成功生成，.dll 文件，CustomWebPart.dll，将在其中生成\<项目文件夹 \> /bin/Debug 文件夹。  
  
7.  **只为 64 位计算机**:使用强名称对 CustomWebPart.dll 文件签名然后再执行以下步骤。 否则，你将无法导入，并因此在 SharePoint 门户中使用 CustomWebPart.dll"步骤 3:配置 SharePoint 门户以使用自定义 Web 部件。" 请参阅[如何：为程序集具有强名称签名](https://msdn.microsoft.com/library/xc31ft41.aspx)。
  
## <a name="step-2-deploy-the-custom-web-part-to-a-sharepoint-portal"></a>第 2 步：将自定义 Web 部件部署到 SharePoint 门户网站  
 必须执行以下操作来使 CustomWebPart.dll 文件 （自定义 Web 部件） 中创建的"步骤 1:创建自定义 Web 部件"本主题的 SharePoint 门户上可用：  
  
- **将 CustomWebPart.dll 文件复制到 bin 文件夹中的 SharePoint Portal**:Microsoft Office SharePoint Server 创建下的门户网站\<根驱动器\>: \Inetpub\wwwroot\wss\VirtualDirectories 文件夹。 文件夹创建每个门户中，并可以使用的端口号标识。 必须将 CustomWebPart.dll 文件中创建"步骤 1:创建自定义 Web 部件"到本主题的\<根驱动器\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number\>\bin 文件夹。 例如，如果你的 SharePoint 门户的端口号是 13614，您必须 CustomWebPart.dll 文件复制到\<根驱动器\>: \Inetpub\wwwroot\wss\VirtualDirectories\13614\bin 文件夹。  
  
  > [!TIP]
  >  若要查找你的 SharePoint 门户的文件夹位置的另一种方法是使用**Internet 信息服务 (IIS) 管理器**窗口 (**启动** > **运行** >  **inetmgr**)。 找到你的 SharePoint 门户中**Internet 信息服务 (IIS) 管理器**窗口 ([computer_name] > 网站 > [门户名称])，右键单击，然后单击**属性**中快捷菜单。 在 SharePoint 门户的属性对话框中，单击**主目录**选项卡，然后选择**本地路径**框。  
  
- **在 web.config 文件中添加安全控件项**:因为 CustomWebPart.dll 文件用于不同的计算机上，并由多个用户，必须声明为"安全"。 文件 为此，请打开 web.config 文件位于 SharePoint 门户文件夹在\<根驱动器\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number\>。 下`<SafeControls>`部分中的 web.config 文件中，添加以下安全控件项：  
  
  - **在 32 位计算机：**  
  
    ```  
    <SafeControl Assembly="CustomWebPart" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
    ```  
  
  - **在 64 位计算机：**  
  
    ```  
    <SafeControl Assembly="CustomWebPart, Version=1.0.0.0, Culture=neutral, PublicKeyToken=<PUBLICKKEYTOKEN_OF_CustomWebPart.dll>" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
    ```  
  
    保存 web.config 文件中，并将其关闭。  
  
## <a name="step-3-configure-the-sharepoint-portal-to-use-the-custom-web-part"></a>步骤 3：配置 SharePoint 门户以使用自定义 Web 部件  
 需要将自定义 Web 部件添加到 Microsoft Office SharePoint Server Web 部件库，以便 SharePoint 门户网站上使用它。 为此，请执行以下操作：  
  
1. 启动 SharePoint 3.0 管理中心。 单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2. 在左侧的导航窗格中，单击名称的共享服务提供程序 (SSP) 你想要添加自定义 Web 部件。  
  
3. 在共享服务管理页上，在右上角，单击**站点操作**，然后单击**创建**。  
  
4. 在站点设置页上单击**Web 部件**下**库**列。  
  
5. 在 Web 部件库页上，若要将自定义 Web 部件添加到库，请单击**新建**。 此时不可用的 Web 部件库页中自定义 Web 部件。  
  
6. 在新的 Web 部件页上，找到**CustomWebPart** （自定义 Web 部件的名称） 在列表中，选择左侧上的复选框，然后单击**导入库**页面顶部。 这将添加**CustomWebPart** Web 部件库页面中的条目。  
  
   现在，可以使用自定义 Web 部件 (**CustomWebPart**) 以在你的 SharePoint 门户中创建 Web 部件。 自定义 Web 部件 (**CustomWebPart**) 将显示在下面**杂项**添加 Web 部件页部分中的。  
  
## <a name="see-also"></a>请参阅  
[使用包含 SharePoint 的 SAP 适配器](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)