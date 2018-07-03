---
title: 步骤 4： 创建 Sharepoint 应用程序以访问适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2d8c398-370a-4c62-961d-0eab6066ad5a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15da47a4171d6bdf4f3b53e2208851bd15ecb0d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986638"
---
# <a name="step-4-create-a-sharepoint-application-to-access-the-adapter"></a>步骤 4： 创建 Sharepoint 应用程序以访问适配器
![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **完成时间：** 15 分钟  
  
 在此步骤需要使用 Business Data Catalog Definition Editor 工具中，创建应用程序定义文件并将其导入 Microsoft Office SharePoint Server。  
  
## <a name="prerequisites"></a>必要條件  
  
-   您应创建了一个应用程序文件中所述[第 3 步： 创建应用程序定义文件](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)。  
  
-   必须运行 Microsoft 单一登录服务。  
  
## <a name="how-to-create-a-sharepoint-application"></a>如何创建 SharePoint 应用程序  
 创建 SharePoint 应用程序涉及以下步骤：  
  
- 在 SharePoint 中创建的单一登录 (SSO) 应用程序。  
  
- 创建共享服务提供程序，并导入应用程序定义文件。  
  
- 创建 Web 部件页，并添加 Web 部件。  
  
  本主题演示如何执行这些步骤。  
  
## <a name="creating-an-sso-application-in-sharepoint"></a>在 SharePoint 中创建的 SSO 应用程序  
 若要将用户凭据传递给 Echo 适配器中，从 SharePoint 应用程序，必须设置 SSO 应用程序映射到用户帐户或组。  
  
#### <a name="manage-server-settings-for-single-sign-on"></a>管理服务器设置单一登录  
  
1.  启动 SharePoint 3.0 管理中心。 上**启动**菜单，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在顶部导航栏上，单击**操作**。  
  
3.  在操作页中**的安全配置**部分中，单击**管理的单一登录设置**。  
  
4.  在单一登录页上，管理设置中**服务器设置**部分中，单击**管理服务器设置**。  
  
5.  请确保此页上的信息是为实现单一登录安装正确。 有关这些操作的详细信息，请参阅"配置单一登录 (Office SharePoint Server)"网址[ http://go.microsoft.com/fwlink/?LinkId=105291 ](http://go.microsoft.com/fwlink/?LinkId=105291)。  
  
#### <a name="manage-settings-for-enterprise-application-definitions"></a>管理企业应用程序定义的设置  
  
1.  在 SharePoint 管理中心内，在顶部导航栏上，单击**操作**。  
  
2.  在操作页中**的安全配置**部分中，单击**管理的单一登录设置**。  
  
3.  在单一登录页上，管理设置中**企业应用程序定义设置**部分中，单击**管理企业应用程序定义的设置**。  
  
4.  在管理企业应用程序定义页上，单击**新项**。  
  
5.  在创建企业应用程序定义页，将**显示名称**字段**EchoSSO**，然后设置**应用程序名称**字段**EchoSSO**。 此值应匹配中指定的 SecondarySsoApplicationId[第 3 步： 创建应用程序定义文件](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)。  
  
6.  在中**联系人电子邮件地址**字段中输入你的电子邮件地址，然后单击**确定**。  
  
#### <a name="manage-account-information-for-enterprise-application-definitions"></a>管理企业应用程序定义的帐户信息  
  
1.  在 SharePoint 管理中心内，在顶部导航栏上，单击**操作**。  
  
2.  在操作页面上中**安全配置部分**，单击**管理的单一登录设置**。  
  
3.  在单一登录页上，管理设置中**企业应用程序定义设置**部分中，单击**管理帐户信息的企业应用程序定义**。  
  
4.  企业应用程序定义的管理帐户信息，选择**EchoSSO**从**企业应用程序定义**列表。  
  
5.  在中**组帐户名称**字段中，键入将用于保护此应用程序定义的 Windows 组。 例如， **\ 用户**。  
  
6.  单击 **“设置”**。  
  
7.  在提供 EchoSSO 帐户信息页上，在**用户名**字段中，键入**testuser**，然后在**密码**字段中，键入**testpassword**.  
  
8.  单击**确定**，然后单击**完成**。  
  
## <a name="creating-a-shared-services-provider-and-importing-the-application-definition-file"></a>创建共享服务提供程序和导入应用程序定义文件  
 共享服务提供程序 (SSP) 是共享的服务和及其支持资源的逻辑分组。 可以使用 SharePoint 中心管理控制台来创建 SSP。 此示例适用于任何 ssp。 有关创建 SSP 的详细信息，请参阅"一章概述： 创建和配置共享服务提供程序"处[ http://go.microsoft.com/fwlink/?LinkId=105119 ](http://go.microsoft.com/fwlink/?LinkId=105119)。  
  
### <a name="to-import-the-application-definition-file"></a>若要导入应用程序定义文件  
  
1.  启动 SharePoint 3.0 管理中心。 上**启动**菜单，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击你想要导入应用程序定义的 SSP 的名称。  
  
3.  在中**业务数据目录**部分中，单击**导入应用程序定义**。  
  
4.  在导入应用程序定义页上单击**浏览**，然后选择 EchoWS.xml 文件。  
  
5.  单击**导入**，然后单击**确定**。  
  
## <a name="creating-web-parts"></a>创建 Web 部件  
 现在必须在 SharePoint 网站中使用方法实例创建在 Business Data Catalog Definition Editor 创建 Web 部件。 Web 部件是信息的可重用的组件，可包含任何类型的基于 Web，包括分析、 协作式和和数据库信息。  
  
#### <a name="to-create-a-web-part-page"></a>若要创建的 Web 部件页  
  
1.  启动 SharePoint 3.0 管理中心。 上**启动**菜单，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击导入应用程序定义文件的 SSP 的名称。  
  
3.  在共享服务管理页上，在右上角，单击**站点操作**，然后单击**创建**。  
  
     ![创建站点操作](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")  
  
4.  上**创建**页上，在**网页**部分中，单击**Web 部件页**。  
  
5.  在新的 Web 部件页上，在**名称**字段中，键入**EchoPart**，然后选择**整页、 垂直**从**选择布局模板**列表。  
  
6.  单击 **“创建”**。  
  
#### <a name="to-add-a-business-data-web-part"></a>若要添加业务数据 Web 部件  
  
1.  单击 **“添加 Web 部件”**。  
  
2.  在中**添加 Web 部件**对话框中，选择**业务数据列表**，然后单击**添加**。  
  
     ![业务数据列表](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")  
  
3.  单击**打开工具窗格**。  
  
4.  业务数据列表工具窗格将在右窗格中打开。 在中**业务数据列表**部分中，对于**类型**字段中，单击**浏览**按钮。  
  
     ![选择的类型](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")  
  
5.  在中**业务数据类型选取器**对话框中，选择**EchoWSLob_Instance**应用程序，，然后单击**确定**。  
  
6.  在业务数据列表工具窗格中，单击**确定**。  
  
7.  您会看到允许您输入要传递给 EchoGreetings 方法的问候语值的字段。 问候语字段中输入数据，然后单击**检索数据**。 这将调用 Echo 适配器在 IIS 中承载的 EchoGreetings 方法并返回响应。  
  
     ![EchoGreetings 列表](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")  
  
    > [!NOTE]
    >  名称列不包含用户信息，但只显示 BDC。名称。 这是因为 BDC 需要仅简单记录结构，并且不会显示名称字段所表示的复杂结构。  
  
8.  单击**退出编辑模式**从页面右上角。  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 您使用 SharePoint 3.0 中心管理导入应用程序定义，并创建使用此定义调用 Echo 适配器的 EchoGreetings 操作的 Web 部件。  
  
## <a name="next-steps"></a>后续步骤  
 本教程中已完成。 有关详细信息使用业务数据目录，请参阅"业务数据目录"网址[ http://go.microsoft.com/fwlink/?LinkId=119921 ](http://go.microsoft.com/fwlink/?LinkId=119921)。  
  
## <a name="see-also"></a>请参阅  
 [教程 3：在 IIS 中托管 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)