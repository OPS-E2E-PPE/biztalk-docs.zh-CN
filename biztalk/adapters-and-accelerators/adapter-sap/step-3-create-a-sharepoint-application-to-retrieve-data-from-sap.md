---
title: 步骤 3：创建 SharePoint 应用程序将数据从 SAP 检索 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO application, creating an
- Business Data Catalog Definition Editor
- application definition file, importing
- Web Part
- SSP
- Web Part page, creating a
- Shared Services Provider, creating a
ms.assetid: 7158caec-9dc0-477c-9db3-179e634e5196
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db5b9a6278de98cbd3105d921806454f51e32a69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372818"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-sap"></a>步骤 3：创建 SharePoint 应用程序以从 SAP 检索数据
![步骤 3，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **若要完成的时间：** 15 分钟  
  
 **目标：** 现在必须通过使用 Business Data Catalog Definition Editor 工具创建应用程序定义文件并将其导入 Microsoft Office SharePoint Server。  
  
## <a name="prerequisites"></a>先决条件  
  
-   您将会创建应用程序定义文件中所述[步骤 2:为 SAP 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)。  
  
-   必须运行 Microsoft 单一登录服务。  
  
## <a name="how-to-create-a-sharepoint-application"></a>如何创建 SharePoint 应用程序  
 创建 SharePoint 应用程序涉及以下步骤：  
  
- 在 SharePoint 中创建的单一登录 (SSO) 应用程序  
  
- 创建共享服务提供程序  
  
- 导入应用程序定义文件  
  
- 创建 Web 部件页，并添加 Web 部件  
  
  本主题演示如何执行这些步骤。  
  
## <a name="creating-an-sso-application-in-sharepoint"></a>在 SharePoint 中创建的 SSO 应用程序  
 若要在 SAP 系统从 SharePoint 应用程序中访问数据，必须设置映射到 SAP 用户的 SharePoint 用户的 SSO 应用程序。 在 SharePoint 中创建的 SSO 应用程序涉及以下步骤：  
  
1.  **管理服务器上单一登录设置**。 在此步骤中，你指定的用户帐户，可以管理和设置单一登录服务。 可以在管理服务器设置页上执行操作。 此选项可从 SharePoint 中心管理控制台。 有关此步骤的详细信息，请参阅"配置单一登录适用于 Office SharePoint Server 2007"部分在[ http://go.microsoft.com/fwlink/?LinkId=105291 ](http://go.microsoft.com/fwlink/?LinkId=105291)。  
  
2.  **管理企业应用程序定义的设置**。 在此步骤中，您配置企业应用程序定义的设置。 您可以从企业应用程序定义页的管理设置执行操作。 此选项可从 SharePoint 中心管理控制台。  
  
    1.  在管理中心内，在顶部导航栏上，单击**操作**。  
  
    2.  在操作页中**的安全配置**部分中，单击**管理的单一登录设置**。  
  
    3.  在单一登录页上，管理设置中**企业应用程序定义设置**部分中，单击**管理企业应用程序定义的设置**。  
  
    4.  在管理企业应用程序定义页上，提供的值**显示名称**，**应用程序名称**，并**联系人电子邮件地址**字段。  
  
        > [!IMPORTANT]
        >  有关**应用程序名称**字段中，请确保指定相同的 SSO 应用程序名称为指定**SecondarySsoApplicationId**时创建应用程序定义文件中，为变量中所述[步骤 2:为 SAP 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)。  
  
    5.  将其他字段保留为默认值，然后单击**确定**。  
  
3.  **管理企业应用程序定义的帐户信息**。 在此步骤中，启用单个用户或组从 SharePoint 连接到企业应用程序。 从根本上来说，在此步骤中您映射单个用户或组到用户在 LOB 系统。 您还指定用于连接到 LOB 系统的凭据。 您可以从企业应用程序定义页的管理帐户信息执行操作。 此选项可从 SharePoint 中心管理控制台。 有关此步骤的详细信息，请参阅"管理企业应用程序定义的帐户信息"部分在[ http://go.microsoft.com/fwlink/?LinkId=105291 ](http://go.microsoft.com/fwlink/?LinkId=105291)。  
  
## <a name="creating-a-shared-services-provider"></a>创建共享的服务提供程序  
 共享服务提供程序是共享的服务和及其支持资源的逻辑分组。 可以使用 SharePoint 中心管理控制台来创建 SSP。  
  
 必须定义网站时创建 ssp。 请记住的端口号和你创建的站点地址。 你将导出到此站点的业务数据目录应用程序定义。  
  
 有关创建 SSP 的详细信息，请参阅"一章概述：创建和配置共享服务提供程序"处[ http://go.microsoft.com/fwlink/?LinkId=105119 ](http://go.microsoft.com/fwlink/?LinkId=105119)。  
  
## <a name="importing-the-application-definition-file"></a>导入应用程序定义文件  
 现在必须将应用程序定义文件导入 ssp。  
  
#### <a name="to-import-the-application-definition-file"></a>若要导入应用程序定义文件  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击你想要导入应用程序定义的 SSP 的名称。  
  
3.  在中**业务数据目录**部分中，单击**导入应用程序定义**。  
  
4.  在导入应用程序定义页，此时会打开，浏览到 Customer_Orders.xml，选择该文件，并单击**打开**。  
  
5.  单击“导入” 。  
  
6.  单击“确定” 。  
  
     导入后应用程序，可以查看你的应用程序通过转到**查看应用程序**链接。 单击以查看应用程序中的实体的应用程序名称。  
  
## <a name="creating-web-parts"></a>创建 Web 部件  
 现在必须在您的 SharePoint 站点查看和管理将从 SAP 系统中提取的业务数据中创建 Web 部件。 Web 部件是信息的可重用的组件，可包含任何类型的基于 Web，包括分析、 协作式和和数据库信息。  
  
 在本教程中，在 Business Data Catalog Definition Editor 创建方法实例创建 Web 部件。 Office SharePoint Server 提供了特定使用 Web 部件的不同种类。 此处使用了以下 Web 部件：  
  
- **业务数据列表**适用于 Web 部件**Finder**方法实例。 此 Web 部件，可指定要从 SAP 系统中检索客户列表的搜索表达式。 对于本教程中，这被称为搜索客户 Web 部件。  
  
- **业务数据项**适用于 Web 部件**特定的 Finder**方法实例。 此 Web 部件显示您从搜索客户 Web 部件中选择特定客户的详细信息。 此 Web 部件映射到搜索客户 Web 部件。  对于本教程中，这被称为客户详细信息 Web 部件。  
  
- **业务数据相关列表**适用于 Web 部件**关联**方法实例。 此 Web 部件列出了从搜索客户 Web 部件中选择的特定客户的销售订单。 此 Web 部件是与搜索客户 Web 部件相关联。  对于本教程中，这被称为销售订单详细信息 Web 部件。  
  
  本部分提供的说明来创建这些 Web 部件，并创建它们之间的关联。 有关创建 Web 部件的详细信息，请参阅"自定义业务数据列表、 Web 部件和站点"网址[ http://go.microsoft.com/fwlink/?LinkId=104131 ](http://go.microsoft.com/fwlink/?LinkId=104131)。  
  
  Web 部件将添加到单个 Web 部件页。 必须添加 Web 部件之前创建的 Web 部件页。 对于本教程中，此 Web 部件页称为 Customer_SalesOrders。  
  
### <a name="creating-a-web-part-page"></a>创建 Web 部件页  
 本部分介绍如何创建 Web 部件页。  
  
##### <a name="to-create-a-web-part-page"></a>若要创建的 Web 部件页  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**。  
  
2.  在左侧的导航窗格中，单击你想要导入应用程序定义的 SSP 的名称。  
  
3.  在共享服务管理页上，在右上角，单击**站点操作**，然后单击**创建**。  
  
     ![若要创建 web 部件的菜单](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")  
  
4.  在创建页上，在**网页**部分中，单击**Web 部件页**。  
  
5.  在新的 Web 部件页上，执行以下步骤：  
  
    1.  在中**名称**字段中，键入页面的名称。 对于本教程中，键入作为名称**Customer_SalesOrders**。  
  
    2.  选择**如果文件已存在，则覆盖**复选框，如果你想要使用相同的名称创建新的页覆盖旧页面。  
  
    3.  在中**布局**部分中，从**选择一个布局模板**框中，选择适用于 Web 部件页的布局。 对于本教程中，选择**标头，左侧列中，正文**。  
  
    4.  在中**保存位置**部分中，在**文档库**列表中，单击**窗体模板**。  
  
    5.  单击 **“创建”**。 只需创建后下, 图显示的 Web 部件页。  
  
         ![空 Web 部件页](../../adapters-and-accelerators/adapter-sap/media/6aa68c43-59df-47c4-95a6-453f7c668025.gif "6aa68c43-59df-47c4-95a6-453f7c668025")  
  
    6.  您现在必须将不同的 Web 部件添加到此页。  
  
### <a name="adding-a-business-data-list-web-part"></a>添加业务数据列表 Web 部件  
 现在，你必须将业务数据列表 Web 部件添加到 Web 部件页。 使用此 Web 部件将从 SAP 系统相匹配的搜索表达式检索客户列表。 此 Web 部件对应于**Finder**方法实例 (*GetCustomerByName_Instance*) 创建在 Business Data Catalog Definition Editor。  
  
##### <a name="to-add-a-business-data-list-web-part"></a>若要添加业务数据列表 Web 部件  
  
1.  在 Customer_SalesOrders 页上，在**标头**部分中，单击**添加 Web 部件**。  
  
2.  在中**添加 Web 部件**对话框中**业务数据**部分中，选择**业务数据列表**复选框，然后依次**添加**。  
  
     ![创建业务数据 Web 部件的选项](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")  
  
3.  在新添加的业务数据列表 Web 部件，单击**打开工具窗格**链接。  
  
     ![Web 部件中打开工具窗格](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")  
  
4.  业务数据列表工具窗格将在右窗格中打开。 在中**业务数据列表**部分中，对于**类型**字段中，单击**浏览**按钮。  
  
     ![业务数据列表工具窗格](../../adapters-and-accelerators/adapter-sap/media/580c58bf-bfc7-4d48-8c62-8ca4eee4ab48.gif "580c58bf-bfc7-4d48-8c62-8ca4eee4ab48")  
  
5.  在中**业务数据类型选取器**对话框中，选择**Customer_Order_Instance**应用程序，，然后单击**确定**。  
  
     ![选择应用程序实例](../../adapters-and-accelerators/adapter-sap/media/79967c27-9c76-4394-89bc-38c63649bdda.gif "79967c27-9c76-4394-89bc-38c63649bdda")  
  
6.  展开**外观**节点，然后在**标题**框中，键入 Web 部件的标题。 为此 Web 部件中，键入**客户列表**。  
  
7.  在业务数据列表工具窗格中，单击**Apply**，然后单击**确定**。 业务数据列表 Web 部件现在看起来如下所示：  
  
     ![业务数据列表 Web 部件](../../adapters-and-accelerators/adapter-sap/media/185fb3f3-98b0-4efe-960d-91312912ad7d.gif "185fb3f3-98b0-4efe-960d-91312912ad7d")  
  
8.  Web 部件列出了通过执行 SD_RFC_CUSTOMER_GET RFC 返回的字段。 可以删除不想要在 SharePoint 门户上显示的字段。 若要删除字段，请单击**编辑视图**Web 部件右上角中的链接。  
  
9. 在编辑视图页上的列部分中，清除针对不想要显示的列的复选框。  
  
     ![在 SharePoint 中查看特定的列](../../adapters-and-accelerators/adapter-sap/media/24213b67-aafe-4534-91a7-06bde7bcbf7c.gif "24213b67-aafe-4534-91a7-06bde7bcbf7c")  
  
10. 单击“确定” 。  
  
### <a name="adding-a-business-data-item-web-part"></a>添加业务数据项 Web 部件  
 您现在必须将业务数据项 Web 部件添加到 Web 部件页。 您还将此 Web 部件连接到刚创建的业务数据列表 Web 部件中。 这样，您将能够查看业务数据列表 Web 部件中选择的客户的详细信息。 此 Web 部件对应于**特定的 Finder**方法实例 (*GetCustomerByNumber_Instance*) 创建在 Business Data Catalog Definition Editor。  
  
##### <a name="to-add-a-business-data-item-web-part"></a>若要添加业务数据项 Web 部件  
  
1.  在 Customer_SalesOrders 页上，在右上角，单击**站点操作**，然后单击**编辑页面**。  
  
2.  在 Customer_SalesOrders 页上，在**左侧列**部分中，单击**添加 Web 部件**。  
  
3.  在中**添加 Web 部件**对话框中**业务数据**部分中，选择**业务数据项**复选框，然后依次**添加**。  
  
4.  在新添加的业务数据项 Web 部件，单击**打开工具窗格**链接。  
  
5.  在右窗格中打开业务数据项工具窗格。 在中**业务数据项**部分中，对于**类型**字段中，单击**浏览**按钮。  
  
     ![业务数据项工具窗格](../../adapters-and-accelerators/adapter-sap/media/29322df5-4ce3-4c1f-a658-39a355dfe2aa.gif "29322df5-4ce3-4c1f-a658-39a355dfe2aa")  
  
6.  在中**业务数据类型选取器**对话框中，选择**Customer_Order_Instance**应用程序，，然后单击**确定**。  
  
7.  在中**视图**列表中，选择**默认**。  
  
8.  将保留**项**列表为空。  
  
    > [!NOTE]
    >  有关**项**字段中，必须指定一个客户名称或你想要查看的详细信息的客户编号。 为此 Web 部件可用作输入参数。 您将通过连接到业务数据列表 Web 部件来获得的输入的参数，因为您无需显式指定项。  
  
9. 在中**字段**部分中，单击**选择**以选择想要在页面上显示的字段。  
  
10. 展开**外观**节点，然后在**标题**字段中，指定 Web 部件的标题。 对于此 Web 部件，指定**特定客户的详细信息**。  
  
11. 单击**Apply**，然后单击**确定**。  
  
12. 连接到 Web 部件**客户列表**Web 部件。 为此，请执行以下操作：  
  
    1.  单击**编辑**向 Web 部件右上角。  
  
    2.  从上下文菜单上指向**连接**，依次指向**获取项从**，然后单击**客户列表**。  
  
         ![连接两个 Web 部件](../../adapters-and-accelerators/adapter-sap/media/505aead7-f498-448f-a7cb-55d0a121f91f.gif "505aead7-f498-448f-a7cb-55d0a121f91f")  
  
### <a name="adding-a-business-data-related-list-web-part"></a>添加业务数据相关列表 Web 部件  
 现在，您必须将业务数据相关列表 Web 部件添加到 Web 部件页。 此外会将此 Web 部件连接到前面创建的业务数据列表 Web 部件。 这样，您将能够查看业务数据列表 Web 部件中选择的客户的销售订单。 此 Web 部件对应于**关联**方法实例 (*SalesOrderForCustomer_Instance*) 创建在 Business Data Catalog Definition Editor。  
  
##### <a name="to-add-a-business-data-related-list-web-part"></a>添加业务数据相关列表 Web 部件  
  
1.  在 Customer_SalesOrders 页上，在**正文**部分中，单击**添加 Web 部件**。  
  
2.  在中**添加 Web 部件**对话框中**业务数据**部分中，选择**业务数据相关列表**复选框，然后单击**添加**。  
  
3.  在新添加的业务数据相关列表 Web 部件中，单击**打开工具窗格**链接。  
  
4.  业务数据相关列表工具窗格将在右窗格中打开。 在中**业务数据相关列表**部分中，对于**类型**字段中，单击**浏览**按钮。  
  
     ![业务数据相关列表](../../adapters-and-accelerators/adapter-sap/media/1914e12d-27f0-4ecb-9605-3177183a2d44.gif "1914e12d-27f0-4ecb-9605-3177183a2d44")  
  
5.  在中**业务数据类型选取器**对话框中，选择**Customer_Order_Instance**应用程序，，然后单击**确定**。 **关系**列表的名称填充**关联**方法实例 (*SalesOrderForCustomer_Instance*)。  
  
6.  展开**外观**节点，然后在**标题**框中，键入 Web 部件的标题。 为此 Web 部件中，键入**特定客户的销售订单**。  
  
7.  单击**Apply**，然后单击**确定**。  
  
8.  Web 部件列出了通过执行 BAPI_SALESORDER_GETLIST RFC 返回的字段。 可以删除不想要在 SharePoint 门户上显示的字段。 若要删除字段，请单击**编辑视图**Web 部件右上角中的链接。  
  
9. 在编辑视图页上，在**列**部分中，清除针对不想要显示的列文本框。  
  
10. 单击“确定” 。  
  
11. 连接到 Web 部件**客户列表**Web 部件。 为此，请执行以下操作：  
  
    1.  单击**编辑**针对的右上角**特定客户的销售订单**Web 部件。  
  
    2.  从上下文菜单中，指向**连接**，依次指向**获取相关项从**，然后单击**客户列表**。  
  
12. 单击**退出编辑模式**从页面的右上角。  
  
## <a name="next-steps"></a>后续步骤  
 通过从 SAP 系统中检索数据来测试 SharePoint 应用程序。 请参阅[步骤 4:测试 SharePoint 应用程序](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程 1:在 SharePoint 站点上提供来自 SAP 系统的数据](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)