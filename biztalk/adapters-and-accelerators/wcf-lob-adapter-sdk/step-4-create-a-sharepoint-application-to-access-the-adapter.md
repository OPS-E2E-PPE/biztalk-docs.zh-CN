---
title: "步骤 4： 创建 Sharepoint 应用程序访问适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2d8c398-370a-4c62-961d-0eab6066ad5a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3360bbdf5ae5a6a8dde9851c544342ea6a6bc1cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-create-a-sharepoint-application-to-access-the-adapter"></a>步骤 4： 创建 Sharepoint 应用程序访问适配器
![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **完成时间：** 15 分钟  
  
 在此步骤中，你需要使用业务数据目录定义编辑器工具中，创建的应用程序定义文件并将其导入 Microsoft Office SharePoint Server。  
  
## <a name="prerequisites"></a>先决条件  
  
-   您将会创建应用程序文件中所述[步骤 3： 创建应用程序定义文件](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)。  
  
-   必须运行 Microsoft 单一登录服务。  
  
## <a name="how-to-create-a-sharepoint-application"></a>如何创建一个 SharePoint 应用程序  
 创建 SharePoint 应用程序涉及以下步骤：  
  
-   在 SharePoint 中创建的单一登录 (SSO) 应用程序。  
  
-   创建共享服务提供程序，并导入应用程序定义文件。  
  
-   创建 Web 部件页，并添加 Web 部件。  
  
 本主题演示如何执行这些步骤。  
  
## <a name="creating-an-sso-application-in-sharepoint"></a>在 SharePoint 中创建 SSO 应用程序  
 若要将用户凭据传递给 Echo 适配器中，从 SharePoint 应用程序，必须设置的 SSO 应用程序映射到用户帐户或组。  
  
#### <a name="manage-server-settings-for-single-sign-on"></a>管理服务器设置单一登录  
  
1.  启动 SharePoint 3.0 管理中心。 上**启动**菜单上，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在顶部导航栏上，单击**操作**。  
  
3.  在操作页面中**安全配置**部分中，单击**管理单一登录设置**。  
  
4.  单一登录页的管理设置中**服务器设置**部分中，单击**管理服务器设置**。  
  
5.  确保此页上的信息用于上单一登录安装正确。 有关这些操作的详细信息，请参阅"配置单一登录 (Office SharePoint Server)"在[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)。  
  
#### <a name="manage-settings-for-enterprise-application-definitions"></a>管理企业应用程序定义的设置  
  
1.  在 SharePoint 管理中心内，在顶部导航栏上，单击**操作**。  
  
2.  在操作页面中**安全配置**部分中，单击**管理的单一登录设置**。  
  
3.  单一登录页的管理设置中**企业应用程序定义设置**部分中，单击**企业应用程序定义的管理设置**。  
  
4.  在管理企业应用程序定义页上，单击**新项**。  
  
5.  在创建企业应用程序定义页，设置**显示名称**字段**EchoSSO**，然后设置**应用程序名称**字段**EchoSSO**。 此值应与匹配中指定 SecondarySsoApplicationId[步骤 3： 创建应用程序定义文件](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)。  
  
6.  在**联系人电子邮件地址**字段，输入你的电子邮件地址，然后单击**确定**。  
  
#### <a name="manage-account-information-for-enterprise-application-definitions"></a>管理企业应用程序定义的帐户信息  
  
1.  在 SharePoint 管理中心内，在顶部导航栏上，单击**操作**。  
  
2.  在操作页面中**的安全配置部分**，单击**管理单一登录设置**。  
  
3.  单一登录页的管理设置中**企业应用程序定义设置**部分中，单击**管理帐户信息为企业应用程序定义**。  
  
4.  有关企业应用程序定义的管理帐户信息，请选择**EchoSSO**从**企业应用程序定义**列表。  
  
5.  在**组帐户名**字段中，键入将用于保护此应用程序定义的 Windows 组。 例如， **\ 用户**。  
  
6.  单击 **“设置”**。  
  
7.  在提供 EchoSSO 帐户信息页上，在**用户名**字段中键入**testuser**，然后在**密码**字段中键入**testpassword**.  
  
8.  单击**确定**，然后单击**完成**。  
  
## <a name="creating-a-shared-services-provider-and-importing-the-application-definition-file"></a>创建共享服务提供程序和导入的应用程序定义文件  
 共享服务提供程序 (SSP) 是共享的服务和其支持的资源的逻辑分组。 可以通过使用 SharePoint 中心管理控制台来创建一个 SSP。 此示例将工作中任何 ssp。 有关创建一个 SSP 的详细信息，请参阅"章概述： 创建和配置共享服务提供程序"在[http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)。  
  
### <a name="to-import-the-application-definition-file"></a>若要导入应用程序定义文件  
  
1.  启动 SharePoint 3.0 管理中心。 上**启动**菜单上，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击你想要导入的应用程序定义的 SSP 的名称。  
  
3.  在**业务数据目录**部分中，单击**导入应用程序定义**。  
  
4.  在导入应用程序定义页上，单击**浏览**，然后选择 EchoWS.xml 文件。  
  
5.  单击**导入**，然后单击**确定**。  
  
## <a name="creating-web-parts"></a>创建 Web 部件  
 你现在必须在 SharePoint 站点，以使用创建在业务数据目录定义编辑器中的方法实例中创建 Web 部件。 Web 部件是信息的可重用组件，可以包含任何类型的基于 Web，包括分析、 协作，和数据库信息。  
  
#### <a name="to-create-a-web-part-page"></a>若要创建的 Web 部件页  
  
1.  启动 SharePoint 3.0 管理中心。 上**启动**菜单上，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击导入的应用程序定义文件的 SSP 的名称。  
  
3.  在共享服务管理页上，在右上角，单击**站点操作**，然后单击**创建**。  
  
     ![创建站点操作](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")  
  
4.  上**创建**页上，在**网页**部分中，单击**Web 部件页**。  
  
5.  在新建 Web 部件页上，在**名称**字段中，键入**EchoPart**，然后选择**完整的页面、 垂直**从**选择布局模板**列表。  
  
6.  单击 **“创建”**。  
  
#### <a name="to-add-a-business-data-web-part"></a>若要添加业务数据 Web 部件  
  
1.  单击 **“添加 Web 部件”**。  
  
2.  在**添加 Web 部件**对话框中，选择**业务数据列表**，然后单击**添加**。  
  
     ![业务数据列表](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")  
  
3.  单击**打开工具窗格**。  
  
4.  业务数据列表工具窗格中将在右窗格中打开。 在**业务数据列表**部分中，为**类型**字段中，单击**浏览**按钮。  
  
     ![选择的类型](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")  
  
5.  在**业务数据类型选取器**对话框中，选择**EchoWSLob_Instance**应用程序，，然后单击**确定**。  
  
6.  业务数据列表工具窗格中，单击**确定**。  
  
7.  系统会显示允许您输入要传递给 EchoGreetings 方法的问候语值的字段。 问候语字段中输入数据，然后单击**检索数据**。 这将调用承载于 IIS 中的 Echo 适配器 EchoGreetings 方法，并返回的响应。  
  
     ![EchoGreetings 列表](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")  
  
    > [!NOTE]
    >  名称列不包含用户信息，但只显示 BDC。名称。 发生这种情况是因为 BDC 本来期望仅简单记录结构，但不会显示名称字段所表示的复杂结构。  
  
8.  单击**退出编辑模式**从页左上角。  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 你使用 SharePoint 3.0 管理中心导入应用程序定义，并创建使用此定义来调用 Echo 适配器 EchoGreetings 操作的 Web 部件。  
  
## <a name="next-steps"></a>后续步骤  
 本教程已完成。 有关详细信息使用业务数据目录，请参阅"业务数据目录"在[http://go.microsoft.com/fwlink/?LinkId=119921](http://go.microsoft.com/fwlink/?LinkId=119921)。  
  
## <a name="see-also"></a>另请参阅  
 [教程 3： 承载在 IIS 中的 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)