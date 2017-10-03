---
title: "步骤 3： 创建 SharePoint 应用程序从 SAP 检索数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 879a4b48da7645471e53db357f7c0a6260117f99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-sap"></a>步骤 3： 创建 SharePoint 应用程序从 SAP 检索数据
![步骤 3 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **完成时间：** 15 分钟  
  
 **目标：**现在必须采用使用业务数据目录定义编辑器工具创建的应用程序定义文件，并将其导入 Microsoft Office SharePoint Server。  
  
## <a name="prerequisites"></a>先决条件  
  
-   您将会创建应用程序定义文件中所述[步骤 2： 为 SAP 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)。  
  
-   必须运行 Microsoft 单一登录服务。  
  
## <a name="how-to-create-a-sharepoint-application"></a>如何创建一个 SharePoint 应用程序  
 创建 SharePoint 应用程序涉及以下步骤：  
  
-   在 SharePoint 中创建的单一登录 (SSO) 应用程序  
  
-   创建共享服务提供程序  
  
-   导入应用程序定义文件  
  
-   创建 Web 部件页，并添加 Web 部件  
  
 本主题演示如何执行这些步骤。  
  
## <a name="creating-an-sso-application-in-sharepoint"></a>在 SharePoint 中创建 SSO 应用程序  
 若要访问 SAP 系统从 SharePoint 应用程序中的数据，必须设置的 SSO 应用程序将 SharePoint 用户映射到 SAP 用户。 在 SharePoint 中创建 SSO 应用程序涉及以下步骤：  
  
1.  **管理服务器上单一登录设置**。 在此步骤中，你可以指定可以管理和设置单一登录服务的用户帐户。 你可以在管理服务器设置页上执行操作。 此选项才可用从 SharePoint 管理中心控制台。 有关此步骤的详细信息，请参阅"配置单一登录的 Office SharePoint Server 2007"部分在[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)。  
  
2.  **管理企业应用程序定义的设置**。 在此步骤中，你配置的企业应用程序定义的设置。 你可以从企业应用程序定义页面的管理设置来实现。 此选项才可用从 SharePoint 管理中心控制台。  
  
    1.  在管理中心内，在顶部导航栏上，单击**操作**。  
  
    2.  在操作页面中**安全配置**部分中，单击**管理单一登录设置**。  
  
    3.  单一登录页的管理设置中**企业应用程序定义设置**部分中，单击**管理企业应用程序定义的设置**。  
  
    4.  在管理企业应用程序定义页上，提供的值**显示名称**，**应用程序名称**，和**联系人电子邮件地址**字段。  
  
        > [!IMPORTANT]
        >  有关**应用程序名称**字段中，请确保指定相同为指定的 SSO 应用程序名称**SecondarySsoApplicationId**时创建应用程序定义文件中，将其作为变量中所述[步骤 2： 为 SAP 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)。  
  
    5.  将其他字段保留为默认值，然后单击**确定**。  
  
3.  **管理企业应用程序定义的帐户信息**。 在此步骤中，你可以启用从 SharePoint 连接到企业应用程序的单个用户或组。 实质上，在此步骤中你映射单个用户或组的用户在 LOB 系统。 你还可以指定要连接到 LOB 系统的凭据。 你可以从企业应用程序定义页的管理帐户信息来实现。 此选项才可用从 SharePoint 管理中心控制台。 有关此步骤的详细信息，请参阅"管理企业应用程序定义的帐户信息"部分在[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)。  
  
## <a name="creating-a-shared-services-provider"></a>创建共享的服务提供程序  
 共享的服务提供程序是共享的服务和其支持的资源的逻辑分组。 可以通过使用 SharePoint 管理中心控制台来创建一个 SSP。  
  
 创建 SSP 时，必须定义网站 请记住端口号和你创建的站点地址。 将将的业务数据目录应用程序定义导入到此站点。  
  
 有关创建一个 SSP 的详细信息，请参阅"章概述： 创建和配置共享服务提供程序"在[http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)。  
  
## <a name="importing-the-application-definition-file"></a>导入的应用程序定义文件  
 现在，你必须将应用程序定义文件导入 SSP  
  
#### <a name="to-import-the-application-definition-file"></a>若要导入应用程序定义文件  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击你想要导入的应用程序定义的 SSP 的名称。  
  
3.  在**业务数据目录**部分中，单击**导入应用程序定义**。  
  
4.  在导入应用程序定义用于打开的页面，浏览到 Customer_Orders.xml，选择的文件，然后单击**打开**。  
  
5.  单击“导入” 。  
  
6.  单击 **“确定”**。  
  
     导入应用程序之后, 中，您可以查看你的应用程序通过转到**查看应用程序**链接。 单击以查看应用程序中的实体的应用程序名称。  
  
## <a name="creating-web-parts"></a>创建 Web 部件  
 你现在必须在 SharePoint 站点，以查看和管理将从 SAP 系统中提取的业务数据创建 Web 部件。 Web 部件是信息的可重用组件，可以包含任何类型的基于 Web，包括分析、 协作，和数据库信息。  
  
 在本教程中，创建在业务数据目录定义编辑器中的方法实例创建了 Web 部件。 Office SharePoint Server 提供了用于特定 Web 部件的不同类型。 此处使用以下 Web 部件：  
  
-   **业务数据列表**Web 部件**Finder**方法实例。 此 Web 部件，可指定要从 SAP 系统中检索一个客户列表的搜索表达式。 对于本教程中，这被称为搜索客户 Web 部件。  
  
-   **业务数据项**Web 部件**特定的 Finder**方法实例。 此 Web 部件显示特定客户从搜索客户 Web 部件中选择的详细信息。 此 Web 部件映射到搜索客户 Web 部件。  对于本教程中，这被称为客户详细信息 Web 部件。  
  
-   **业务数据相关列表**Web 部件**关联**方法实例。 此 Web 部件列出特定客户从搜索客户 Web 部件中选择的销售订单。 此 Web 部件将搜索客户 Web 部件与关联。  对于本教程中，这被称为销售订单详细信息 Web 部件。  
  
 本部分提供说明来创建这些 Web 部件并创建它们之间的关联。 有关创建 Web 部件的详细信息，请参阅"自定义业务数据列表、 Web 部件和站点"在[http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131)。  
  
 Web 部件将添加到单个 Web 部件页。 添加 Web 部件之前，必须创建的 Web 部件页。 对于本教程中，此 Web 部件页被称为 Customer_SalesOrders。  
  
### <a name="creating-a-web-part-page"></a>创建 Web 部件页  
 本部分提供说明创建的 Web 部件页。  
  
##### <a name="to-create-a-web-part-page"></a>若要创建的 Web 部件页  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**。  
  
2.  在左侧的导航窗格中，单击你想要导入的应用程序定义的 SSP 的名称。  
  
3.  在共享服务管理页上，在右上角，单击**站点操作**，然后单击**创建**。  
  
     ![若要创建 web 部件的菜单](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")  
  
4.  在创建页面上，在**网页**部分中，单击**Web 部件页**。  
  
5.  在新建 Web 部件页上，执行以下操作：  
  
    1.  在**名称**字段中，键入页面的名称。 对于本教程中，键入的名称作为**Customer_SalesOrders**。  
  
    2.  选择**文件已存在时覆盖**复选框，如果你想要使用与你创建的新页相同的名称覆盖旧的页。  
  
    3.  在**布局**部分中，从**选择布局模板**框中，选择 Web 部件页的布局。 对于本教程中，选择**标头，左侧列中，正文**。  
  
    4.  在**保存位置**部分中，在**文档库**列表中，单击**表单模板**。  
  
    5.  单击 **“创建”**。 只需创建后下, 图显示的 Web 部件页。  
  
         ![空 Web 部件页](../../adapters-and-accelerators/adapter-sap/media/6aa68c43-59df-47c4-95a6-453f7c668025.gif "6aa68c43-59df-47c4-95a6-453f7c668025")  
  
    6.  现在，你必须将不同的 Web 部件添加到此页。  
  
### <a name="adding-a-business-data-list-web-part"></a>添加业务数据列表 Web 部件  
 现在，你必须将业务数据列表 Web 部件添加到 Web 部件页。 使用此 Web 部件将从匹配的搜索表达式的 SAP 系统检索一个客户列表。 此 Web 部件对应于**Finder**方法实例 (*GetCustomerByName_Instance*) 创建在业务数据目录定义编辑器中。  
  
##### <a name="to-add-a-business-data-list-web-part"></a>若要添加业务数据列表 Web 部件  
  
1.  在 Customer_SalesOrders 页上，在**标头**部分中，单击**添加 Web 部件**。  
  
2.  在**添加 Web 部件**对话框中，在**业务数据**部分中，选择**业务数据列表**复选框，并依次**添加**。  
  
     ![创建业务数据 Web 部件的选项](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")  
  
3.  在新添加的业务数据列表 Web 部件，单击**打开工具窗格**链接。  
  
     ![为 Web 部件中打开工具窗格](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")  
  
4.  业务数据列表工具窗格中将在右窗格中打开。 在**业务数据列表**部分中，为**类型**字段中，单击**浏览**按钮。  
  
     ![业务数据列表工具窗格](../../adapters-and-accelerators/adapter-sap/media/580c58bf-bfc7-4d48-8c62-8ca4eee4ab48.gif "580c58bf-bfc7-4d48-8c62-8ca4eee4ab48")  
  
5.  在**业务数据类型选取器**对话框中，选择**Customer_Order_Instance**应用程序，，然后单击**确定**。  
  
     ![选择应用程序实例](../../adapters-and-accelerators/adapter-sap/media/79967c27-9c76-4394-89bc-38c63649bdda.gif "79967c27-9c76-4394-89bc-38c63649bdda")  
  
6.  展开**外观**节点，然后在**标题**框中，键入 Web 部件的标题。 有关此 Web 部件中，键入**客户列表**。  
  
7.  在业务数据列表工具窗格中，单击**应用**，然后单击**确定**。 业务数据列表 Web 部件现在如下所示：  
  
     ![业务数据列表 Web 部件](../../adapters-and-accelerators/adapter-sap/media/185fb3f3-98b0-4efe-960d-91312912ad7d.gif "185fb3f3-98b0-4efe-960d-91312912ad7d")  
  
8.  Web 部件列出通过执行 SD_RFC_CUSTOMER_GET RFC 返回的字段。 你可以删除不希望在 SharePoint 门户上显示的字段。 若要删除字段，请单击**编辑视图**Web 部件右上角中的链接。  
  
9. 在编辑视图页上的列部分中，清除针对你不想要显示的列的复选框。  
  
     ![查看 SharePoint 中的特定列](../../adapters-and-accelerators/adapter-sap/media/24213b67-aafe-4534-91a7-06bde7bcbf7c.gif "24213b67-aafe-4534-91a7-06bde7bcbf7c")  
  
10. 单击 **“确定”**。  
  
### <a name="adding-a-business-data-item-web-part"></a>添加业务数据项 Web 部件  
 现在，你必须将业务数据项 Web 部件添加到 Web 部件页。 你还将连接到你刚刚创建业务数据列表 Web 部件的此 Web 部件。 这样，你将能够看到在业务数据列表 Web 部件中选择的客户的详细信息。 此 Web 部件对应于**特定的 Finder**方法实例 (*GetCustomerByNumber_Instance*) 创建在业务数据目录定义编辑器中。  
  
##### <a name="to-add-a-business-data-item-web-part"></a>若要添加业务数据项 Web 部件  
  
1.  在 Customer_SalesOrders 页上，在右上角，单击**站点操作**，然后单击**编辑页**。  
  
2.  在 Customer_SalesOrders 页上，在**左列**部分中，单击**添加 Web 部件**。  
  
3.  在**添加 Web 部件**对话框中，在**业务数据**部分中，选择**业务数据项**复选框，并依次**添加**。  
  
4.  在新添加的业务数据项 Web 部件，单击**打开工具窗格**链接。  
  
5.  业务数据项工具窗格中打开在右窗格中。 在**业务数据项**部分中，为**类型**字段中，单击**浏览**按钮。  
  
     ![业务数据项工具窗格](../../adapters-and-accelerators/adapter-sap/media/29322df5-4ce3-4c1f-a658-39a355dfe2aa.gif "29322df5-4ce3-4c1f-a658-39a355dfe2aa")  
  
6.  在**业务数据类型选取器**对话框中，选择**Customer_Order_Instance**应用程序，，然后单击**确定**。  
  
7.  在**视图**列表中，选择**默认**。  
  
8.  保留**项**列表是空的。  
  
    > [!NOTE]
    >  有关**项**字段中，你必须指定客户名称或你想要查看的详细信息的客户编号。 以便提供作为输入参数为此 Web 部件。 因为你将通过连接到业务数据列表 Web 部件遇到输入的参数，你不需要显式指定一个项。  
  
9. 在**字段**部分中，单击**选择**以选择你想要显示在页面上的字段。  
  
10. 展开**外观**节点，然后在**标题**字段中，指定 Web 部件的标题。 对于此 Web 部件，指定**特定客户的详细信息**。  
  
11. 单击**应用**，然后单击**确定**。  
  
12. 连接到 Web 部件**客户列表**Web 部件。 为此：  
  
    1.  单击**编辑**Web 部件右上角。  
  
    2.  从上下文菜单中指向**连接**，指向**获取项从**，然后单击**客户列表**。  
  
         ![连接两个 Web 部件](../../adapters-and-accelerators/adapter-sap/media/505aead7-f498-448f-a7cb-55d0a121f91f.gif "505aead7-f498-448f-a7cb-55d0a121f91f")  
  
### <a name="adding-a-business-data-related-list-web-part"></a>添加业务数据相关列表 Web 部件  
 现在，你必须将业务数据相关列表 Web 部件添加到 Web 部件页。 你还将连接到之前创建业务数据列表 Web 部件的此 Web 部件。 这样，你将能够查看你在业务数据列表 Web 部件中选择的客户的销售订单。 此 Web 部件对应于**关联**方法实例 (*SalesOrderForCustomer_Instance*) 创建在业务数据目录定义编辑器中。  
  
##### <a name="to-add-a-business-data-related-list-web-part"></a>添加业务数据相关的列表 Web 部件  
  
1.  在 Customer_SalesOrders 页上，在**正文**部分中，单击**添加 Web 部件**。  
  
2.  在**添加 Web 部件**对话框中，在**业务数据**部分中，选择**业务数据相关列表**复选框，然后单击**添加**。  
  
3.  在新添加业务数据相关列表 Web 部件中，单击**打开工具窗格**链接。  
  
4.  业务数据相关列表工具窗格中将在右窗格中打开。 在**业务数据相关列表**部分中，为**类型**字段中，单击**浏览**按钮。  
  
     ![业务数据相关列表](../../adapters-and-accelerators/adapter-sap/media/1914e12d-27f0-4ecb-9605-3177183a2d44.gif "1914e12d-27f0-4ecb-9605-3177183a2d44")  
  
5.  在**业务数据类型选取器**对话框中，选择**Customer_Order_Instance**应用程序，，然后单击**确定**。 **关系**列表的名称，并用其填充**关联**方法实例 (*SalesOrderForCustomer_Instance*)。  
  
6.  展开**外观**节点，然后在**标题**框中，键入 Web 部件的标题。 有关此 Web 部件中，键入**特定客户的销售订单**。  
  
7.  单击**应用**，然后单击**确定**。  
  
8.  Web 部件列出通过执行 BAPI_SALESORDER_GETLIST RFC 返回的字段。 你可以删除不希望在 SharePoint 门户上显示的字段。 若要删除字段，请单击**编辑视图**Web 部件右上角中的链接。  
  
9. 在编辑视图页上，在**列**部分中，清除针对你不想要显示的列文本框。  
  
10. 单击 **“确定”**。  
  
11. 连接到 Web 部件**客户列表**Web 部件。 为此：  
  
    1.  单击**编辑**右上角**特定客户的销售订单**Web 部件。  
  
    2.  从上下文菜单中，指向**连接**，指向**获取相关项从**，然后单击**客户列表**。  
  
12. 单击**退出编辑模式**从页面的右上角。  
  
## <a name="next-steps"></a>后续步骤  
 通过从某个 SAP 系统检索数据来测试 SharePoint 应用程序。 请参阅[步骤 4： 测试 SharePoint 应用程序](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)。  
  
## <a name="see-also"></a>另请参阅  
 [教程 1： 从 SharePoint 站点上的 SAP 系统提供数据](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)