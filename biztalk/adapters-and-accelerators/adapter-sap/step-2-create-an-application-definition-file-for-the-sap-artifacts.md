---
title: 第 2 步：为 SAP 项目创建应用程序定义文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- application definition file, creating a
- Business Data Catalog Definition Editor
- Business Data Catalog
ms.assetid: d254b00e-dbeb-4167-ad57-6f0aa2e7a563
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1d2953775a948aa20009cf419bd253cafc9a5e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372824"
---
# <a name="step-2-create-an-application-definition-file-for-the-sap-artifacts"></a>第 2 步：为 SAP 项目创建应用程序定义文件
![步骤 2，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **若要完成的时间：** 15 分钟  
  
 **目标：** Microsoft SharePoint Server 中的业务数据目录功能公开，并将业务线 (LOB) 应用程序中的数据合并到门户。 若要将此数据合并到您的门户网站，必须生成可以使用 Microsoft Office SharePoint Server 应用程序定义文件。  
  
 Microsoft Office SharePoint Server 2007 SDK 提供的 Business Data Catalog Definition Editor 工具，可为业务数据目录中创建应用程序定义文件。 此工具自动生成 XML 文件，以便定义文件中，因此不需要手动创建该文件在 XML 编辑器。  
  
 要创建的 Microsoft Office SharePoint Server 应用程序的目的是：  
  
- 基于客户名称上的 SAP 系统中搜索客户。  
  
- 从提取客户的列表中选择客户并检索客户的详细信息。  
  
- 从提取客户的列表中选择客户并检索客户的销售订单。  
  
  对于每个这些要求，必须完成一组 Business Data Catalog Definition Editor tool 中的任务。 本主题提供有关如何执行这些任务的说明。  
  
## <a name="prerequisites"></a>先决条件  
  
-   必须确保您具有 Microsoft Office SharePoint Server 2007 SDK 的一部分安装 Business Data Catalog Definition Editor。 你可以下载从 SDK [ http://go.microsoft.com/fwlink/?LinkId=104130 ](http://go.microsoft.com/fwlink/?LinkId=104130)。  
  
-   发布 WCF 服务，如中所述[步骤 1:将 SAP 项目作为 WCF 服务发布](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)。  
  
## <a name="creating-an-application-definition-file"></a>创建应用程序定义文件  
 本主题提供创建 WCF 服务应用程序定义文件的分步说明。  
  
### <a name="connect-to-the-wcf-lob-service-and-create-entities"></a>连接到 WCF LOB 服务，并创建实体  
 您必须连接到 WCF 服务以提取 Web 服务描述语言 (WSDL) 服务。 从 WSDL，Business Data Catalog Definition Editor 提取方法。 这些方法可以用于创建实体。 对于此示例中，两个实体创建，分别对应于客户和销售订单。  
  
##### <a name="to-connect-to-the-wcf-service-and-create-entities"></a>若要连接到 WCF 服务并创建实体  
  
1. 启动 Business Data Catalog Definition Editor。 上**启动**菜单上，单击**Microsoft Business Data Catalog Definition Editor**。  
  
2. 在工具栏上，单击**添加 LOB 系统**。  
  
3. 在添加 LOB 系统窗口中，单击**连接到 web 服务**。  
  
4. 在中**URL**框中，键入 WCF 服务的 URL。 该 URL 必须采用以下格式：  
  
   ```  
   https://<computer_name>/Customer_Order/Rfc.svc?wsdl  
   ```  
  
    其中 Rfc.svc 是 Rfc 协定创建的文件。  
  
    测试是否成功，如本主题中所述发布 WCF 服务时，URL 是可用[步骤 1:将 SAP 项目作为 WCF 服务发布](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)。  
  
5. 单击 **“连接”**。  
  
6. 若要查看你在 WCF 适配器服务开发向导中选择的操作，请单击**添加 Web 方法**选项卡。你将看到以下方法：  
  
   - SD_RFC_CUSTOMER_GET  
  
   - BAPI_SALESORDER_GETLIST  
  
      ![将 web 方法添加到 BDC 应用程序](../../adapters-and-accelerators/adapter-sap/media/ea411db2-5cf4-4486-83da-57d3fc332448.gif "ea411db2-5cf4-4486-83da-57d3fc332448")  
  
     将方法拖到设计图面。 请确保将这两种操作拖动到不同的实体。  
  
     ![为 web 方法创建实体](../../adapters-and-accelerators/adapter-sap/media/ce4e9bc3-1eae-43ae-8375-e44cf19aaffc.gif "ce4e9bc3-1eae-43ae-8375-e44cf19aaffc")  
  
7. 单击“确定” 。  
  
8. 在中**输入 LOB 系统的名称**对话框中键入名称**LOB 系统名称**框。 此示例中，称之为**Customer_Order**，然后单击**确定**。  
  
9. 在 Business Data Catalog Definition Editor，两个实体被列为**Entity0**并**Entity1**。 为这些实体指定友好名称。 为到 SD_RFC_CUSTOMER_GET 重命名实体**客户**，并为到 BAPI_SALESORDER_GETLIST 重命名实体**SalesOrder**。 执行以下步骤以重命名实体：  
  
    1.  展开**Customer_Order**节点，然后展开**实体**节点。  
  
    2.  选择**Entity0**节点。  
  
    3.  在属性窗格中，键入**客户**中**名称**框。  
  
         ![重命名实体](../../adapters-and-accelerators/adapter-sap/media/4e83a036-3ab7-4f74-9f67-420574219d3d.gif "4e83a036-3ab7-4f74-9f67-420574219d3d")  
  
    4.  选择**Entity1**节点。  
  
    5.  在属性窗格中，键入**SalesOrder**中**名称**框。  
  
### <a name="specify-user-name-and-password-headers-for-the-methods"></a>为方法中指定用户名和密码标头  
 在 SAP 系统中创建所选 Rfc 的 WCF 服务，指定用户名称和密码标头为终结点行为配置的一部分。 请参阅[步骤 1:将 SAP 项目作为 WCF 服务发布](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)。 必须指定方法属性相同的值。  
  
##### <a name="to-specify-user-name-and-password-headers"></a>若要指定用户名称和密码标头  
  
1.  添加 SD_RFC_CUSTOMER_GET 方法的用户名称和密码标头。  
  
    1.  在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。  
  
    2.  单击 SD_RFC_CUSTOMER_GET 节点，然后在属性窗格中单击省略号 （...） 按钮根据**属性**框。  
  
    3.  在 PropertyView 集合编辑器窗口中，单击**外**，然后在属性窗格中，键入**HttpHeaderUserName**有关**名称**框。 同样，键入**MyUserHeader**有关**PropertyValue**框。 选择**System.String**有关**类型**框。  
  
         ![将属性添加](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")  
  
    4.  在 PropertyView 集合编辑器窗口中，单击**外**，然后在属性窗格中，键入**HttpHeaderPassword**有关**名称**框。 同样，键入**MyPassHeader**有关**PropertyValue**框。 选择**System.String**有关**类型**框。  
  
    5.  单击“确定” 。  
  
2.  添加 BAPI_SALESORDER_GETLIST 方法的用户名称和密码标头。  
  
    1.  在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。  
  
    2.  单击 BAPI_SALESORDER_GETLIST 节点，然后在属性窗格中单击省略号 （...） 按钮根据**属性**框。  
  
    3.  在 PropertyView 集合编辑器窗口中，单击**外**，然后在属性窗格中，键入**HttpHeaderUserName**有关**名称**框。 同样，键入**MyUserHeader**有关**PropertyValue**框。 选择**System.String**有关**类型**框。  
  
    4.  在 PropertyView 集合编辑器窗口中，单击**外**，然后在属性窗格中，键入**HttpHeaderPassword**有关**名称**框。 同样，键入**MyPassHeader**有关**PropertyValue**框。 选择**System.String**有关**类型**框。  
  
    5.  单击“确定” 。  
  
### <a name="set-up-single-sign-on-for-connecting-to-the-sap-system"></a>为连接到 SAP 系统设置了单一登录  
 执行本主题中的所有过程完成后，您将创建可导入 SharePoint 应用程序的应用程序定义文件。 从应用程序，您调用以检索相关数据从 SAP 系统的 SAP 方法。 若要启用此功能，必须在 SharePoint 应用程序中创建 SAP 系统中的用户和用户之间的映射。 在导入应用程序定义文件后，可以在 SharePoint 中心管理控制台中创建此映射。  
  
 但是，若要创建该映射必须设置属性**SecondarySsoApplicationId**中 Business Data Catalog Definition Editor。  
  
##### <a name="to-set-the-secondaryssoapplicationid-property"></a>若要设置 SecondarySsoApplicationId 属性  
  
1.  在元数据对象窗格中，展开**Customer_Order**节点，然后展开**实例**节点。  
  
2.  单击**Customer_Order_Instance**，并在属性窗格中，单击省略号 （...） 按钮针对**属性**框。  
  
3.  在 PropertyView 集合编辑器窗口中，单击**外**，然后在属性窗格中，键入**SecondarySsoApplicationId**有关**名称**框。 同样，键入**SAPSSO**有关**PropertyValue**框。 选择**System.String**有关**类型**框。  
  
     ![添加 SSO 属性](../../adapters-and-accelerators/adapter-sap/media/1eb813e4-fed2-45c2-8902-9af5dd3369bf.gif "1eb813e4-fed2-45c2-8902-9af5dd3369bf")  
  
4.  单击“确定” 。  
  
### <a name="requirement-1-search-for-customers-based-on-customer-name"></a>要求 1:客户基于客户名称搜索  
 若要创建可用于搜索客户基于客户名称的应用程序定义文件，必须执行以下一组任务。  
  
-   在 SD_RFC_CUSTOMER_GET 方法中，创建一个筛选器，并将其映射到存储的客户名称的参数。  
  
-   创建**Finder** SD_RFC_CUSTOMER_GET 方法的方法实例。 一个**Finder**方法检索基于筛选器记录的列表。  
  
##### <a name="to-create-a-filter-and-map-it-to-the-customer-name-parameter"></a>若要创建筛选器，并将其映射到的客户名称参数  
  
1.  创建一个筛选器。  
  
    1.  在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。  
  
    2.  展开 SD_RFC_CUSTOMER_GET 方法中，右键单击**筛选器**，然后单击**添加筛选器**。  
  
         ![向方法中添加筛选器](../../adapters-and-accelerators/adapter-sap/media/23eaab24-66e4-486f-8f99-02a5e0fef984.gif "23eaab24-66e4-486f-8f99-02a5e0fef984")  
  
    3.  在属性窗格中，键入**CustomerName**中**名称**框。  
  
         ![指定筛选器的名称](../../adapters-and-accelerators/adapter-sap/media/0a0d0f85-a16a-4969-a122-097355141c27.gif "0a0d0f85-a16a-4969-a122-097355141c27")  
  
    4.  有关**FilterType**属性中，选择**WildcardFilter**。  
  
2.  筛选器映射到**NAME1** SD_RFC_CUSTOMER_GET 方法中的参数。  
  
    1.  在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。  
  
    2.  展开 SD_RFC_CUSTOMER_GET 方法，然后展开**参数**节点。  
  
    3.  展开**NAME1**节点，然后单击第二个**NAME1**节点。 **NAME1**参数包含客户的名称。  
  
    4.  在属性窗格中选择**CustomerName**从**FilterDescriptor**列表。  
  
         ![将筛选器映射到方法参数](../../adapters-and-accelerators/adapter-sap/media/6cc4ef85-503c-4847-95cb-633b902a715d.gif "6cc4ef85-503c-4847-95cb-633b902a715d")  
  
##### <a name="to-create-a-finder-method-instance-for-the-sdrfccustomerget-method"></a>若要创建 Finder 方法实例 SD_RFC_CUSTOMER_GET 方法  
  
1.  在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。  
  
2.  展开**SD_RFC_CUSTOMER_GET**节点，右键单击**实例**，然后单击**添加方法实例**以打开创建方法实例窗口。  
  
     ![添加方法实例](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")  
  
3.  在创建方法实例窗口中，单击**Finder**有关**方法实例类型**。 选择**CUSTOMER_T**有关**的返回 TypeDescriptor**。  
  
     ![添加 Finder 方法实例](../../adapters-and-accelerators/adapter-sap/media/e9ae47f2-32f5-4586-8467-94e3713d2a06.gif "e9ae47f2-32f5-4586-8467-94e3713d2a06")  
  
4.  单击“确定” 。  
  
5.  在属性窗格中，键入**GetCustomerByName_Instance**中**名称**框。  
  
     ![指定方法实例的名称](../../adapters-and-accelerators/adapter-sap/media/e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5.gif "e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5")  
  
### <a name="requirement-2-retrieve-details-for-a-specific-customer-from-the-list-of-customers"></a>要求 2:检索客户列表从特定客户的详细信息  
 若要创建可用于搜索客户基于客户名称的应用程序定义文件，必须执行以下一组任务。  
  
-   在 SD_RFC_CUSTOMER_GET 方法中，创建一个标识符，并将其映射到参数，用于存储的客户编号。  
  
-   创建**特定的 Finder** SD_RFC_CUSTOMER_GET 方法的方法实例。 一个**特定的 Finder**方法查找基于标识符的特定记录。  
  
##### <a name="to-create-an-identifier-and-map-it-to-the-customer-number-parameter"></a>若要创建一个标识符，并将其映射到客户数字参数  
  
1.  创建标识符**客户**实体。  
  
    1.  在元数据对象窗格中，展开**客户**节点。  
  
    2.  右键单击**标识符**节点，并选择**添加标识符**。  
  
         ![将标识符添加到方法](../../adapters-and-accelerators/adapter-sap/media/3adeeda3-426c-41fe-8d5c-5ca5863fb430.gif "3adeeda3-426c-41fe-8d5c-5ca5863fb430")  
  
    3.  在属性窗格中，键入**CustomerID**中**名称**框。  
  
    4.  选择**System.String**有关**类型**框。  
  
         ![指定的名称标识符](../../adapters-and-accelerators/adapter-sap/media/a2304bca-9a54-4d2b-ba9f-461cfaafccb0.gif "a2304bca-9a54-4d2b-ba9f-461cfaafccb0")  
  
2.  将标识符映射到 SD_RFC_CUSTOMER_GET 方法的关键参数。  
  
    1.  在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。  
  
    2.  展开 SD_RFC_CUSTOMER_GET 方法，然后展开**参数**节点。  
  
    3.  展开**应**参数，然后单击第二个**应**节点。  
  
    4.  在属性窗格中选择**CustomerID [Customer]** 从**标识符**列表。  
  
         ![将标识符映射到参数](../../adapters-and-accelerators/adapter-sap/media/04ff6496-34a7-421b-ae9e-f9263895c153.gif "04ff6496-34a7-421b-ae9e-f9263895c153")  
  
3.  设置输入和返回参数之间的关联。  
  
    1.  在元数据对象窗格中，展开**客户**节点，然后展开**方法**节点。  
  
    2.  展开 SD_RFC_CUSTOMER_GET 方法，然后展开**参数**节点。  
  
    3.  展开**CUSTOMER_T**节点，然后第二个**CUSTOMER_T**节点，然后**项**节点，并单击**应**节点。  
  
    4.  在属性窗格中选择**CustomerID [Customer]** 从**标识符**列表。  
  
##### <a name="to-create-a-specific-finder-method-instance-for-the-sdrfccustomerget-method"></a>若要创建 SD_RFC_CUSTOMER_GET 方法的特定的 Finder 方法实例  
  
1.  在元数据对象窗格中，展开**客户**节点，然后**方法**节点。  
  
2.  展开**SD_RFC_CUSTOMER_GET**节点，右键单击**实例**，然后选择**添加方法实例**以打开创建方法实例窗口。  
  
     ![添加方法实例](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")  
  
3.  在创建方法实例窗口中，选择**特定的 Finder**有关**方法实例类型**。 同样，选择**CUSTOMER_T**有关**返回 TypeDescriptor**。  
  
     ![添加特定的 Finder 方法实例](../../adapters-and-accelerators/adapter-sap/media/838eb512-b967-46e7-a865-0bf3651b02a1.gif "838eb512-b967-46e7-a865-0bf3651b02a1")  
  
4.  单击“确定” 。  
  
5.  在属性窗格中，键入**GetCustomerByNumber_Instance**有关**名称**框。  
  
     ![指定方法实例的名称](../../adapters-and-accelerators/adapter-sap/media/970f543c-cd06-4921-86c9-c110abdc7994.gif "970f543c-cd06-4921-86c9-c110abdc7994")  
  
### <a name="requirement-3-retrieve-sales-order-details-for-a-specific-customer-from-the-list-of-customers"></a>要求 3:检索客户列表从特定客户的销售订单详细信息  
 若要创建可用于检索特定客户的销售订单详细信息的应用程序定义文件，必须执行以下一组任务。  
  
-   设置之间的关联**客户**并**SalesOrder**实体。  
  
-   创建**关联**BAPI_SALESORDER_GETLIST 方法方法。  
  
##### <a name="to-create-an-association-between-the-customer-and-salesorder-entities"></a>若要创建客户和 SalesOrder 实体之间的关联  
  
1.  在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。  
  
2.  展开 BAPI_SALESORDER_GETLIST 方法，然后展开**参数**节点。  
  
3.  展开**CUSTOMER_NUMBER**节点，然后单击第二个**CUSTOMER_NUMBER**节点。  
  
4.  在属性窗格中选择**CustomerID [Customer]** 从**标识符**列表。  
  
     ![创建两个实体之间的关联](../../adapters-and-accelerators/adapter-sap/media/ae7e1e7a-a12b-4905-b002-2a04c7050848.gif "ae7e1e7a-a12b-4905-b002-2a04c7050848")  
  
##### <a name="to-create-an-association-method-instance-for-the-bapisalesordergetlist-method"></a>若要创建关联方法实例 BAPI_SALESORDER_GETLIST 方法  
  
1.  在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。  
  
2.  展开**BAPI_SALESORDER_GETLIST**节点，右键单击**实例**，然后选择**添加方法实例**以打开创建方法实例窗口。  
  
     ![添加关联方法实例](../../adapters-and-accelerators/adapter-sap/media/c62a0d01-d4f3-470e-92f1-8a5cf666f8da.gif "c62a0d01-d4f3-470e-92f1-8a5cf666f8da")  
  
3.  在创建方法实例窗口中，选择**关联**有关**方法实例类型**。  
  
4.  在中**源实体**列表中，选择**客户**。  
  
5.  在中**返回 TypeDescriptor**列表中，选择**SALES_ORDERS**...  
  
     ![创建关联方法实例](../../adapters-and-accelerators/adapter-sap/media/15975b78-8932-41ce-8c10-41891fc1fb22.gif "15975b78-8932-41ce-8c10-41891fc1fb22")  
  
6.  单击“确定” 。  
  
7.  在属性窗格中，键入**SalesOrderForCustomer_Instance**有关**名称**框。  
  
     ![指定关联方法的名称](../../adapters-and-accelerators/adapter-sap/media/0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0.gif "0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0")  
  
### <a name="remove-parameters-of-systemnullable-type"></a>删除 System.Nullable 类型的参数  
 创建时**关联**方法实例作为 SALES_ORDERS BAPI_SALESORDER_GETLIST 方法中，选择返回的类型。 如果展开 SALES_ORDER 参数，你会注意到某些参数的 System.Nullable 类型。 您可以看到通过选择该参数在 Business Data Catalog Definition Editor，并查看的值类型的参数**TypeName**属性。  
  
 对于此类参数，Business Data Catalog Definition Editor 创建另一个参数具有相同名称但具有"Specified"后缀。 例如，看一下参数*ITM_NUMBER*并*ITM_NUMBERSpecified*。 Microsoft Office SharePoint Server 不支持 System.Nullable 参数。 因此，当您尝试记录，其中包含 System.Nullable 参数类型，则会引发异常。 因此，必须删除从 Business Data Catalog Definition Editor 这两个参数 （使用或不包含"Specified"后缀和具有相同名称）  
  
##### <a name="to-remove-the-parameters-of-systemnullable-type"></a>若要删除 System.Nullable 类型的参数  
  
1.  在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。  
  
2.  展开**BAPI_SALESORDER_GETLIST**节点，然后展开**参数**节点。  
  
3.  展开**SALES_ORDERS**，展开第二个**SALES_ORDERS**，然后展开**项**。  
  
4.  右键单击包含在名称的"Specified"后缀的参数，然后选择**删除**。  
  
5.  右键单击已删除，而不使用后缀，该参数与同名的参数，然后选择**删除**。 通常情况下，此参数是前面有"Specified"后缀的参数正确。  
  
### <a name="set-default-parameters"></a>设置默认参数  
 BAPI_SALESORDER_GETLIST 采用两个参数。 其中一个参数，TRANSACTION_GROUP，是默认参数。 因此，必须设置此参数的默认值。  
  
##### <a name="to-set-the-default-value-for-transactiongroup"></a>若要为 TRANSACTION_GROUP 设置默认值  
  
1.  在元数据对象窗格中，展开**SalesOrder**节点，然后展开**方法**节点。  
  
2.  展开**BAPI_SALESORDER_GETLIST**节点，然后展开**实例**节点。  
  
3.  选择**SalesOrderForCustomer_Instance**方法实例，并在属性窗格中，单击省略号按钮 （...） 针对**DefaultValues**框。  
  
4.  在编辑窗口中，展开**TRANSACTION_GROUP**节点，并为**TRANSACTION_GROUP**框中，指定默认值 0。  
  
     ![指定方法实例的默认值](../../adapters-and-accelerators/adapter-sap/media/86e0a42d-61c0-4d5d-ba3f-55b328f79576.gif "86e0a42d-61c0-4d5d-ba3f-55b328f79576")  
  
5.  单击 **“关闭”**。  
  
### <a name="export-the-application-definition-to-a-file"></a>应用程序定义导出到文件  
 现在已创建包含 SAP 系统实例元数据的应用程序定义。 必须将此定义导出到 XML 文件，可以导入到 Microsoft Office SharePoint Server。  
  
##### <a name="to-export-the-application-definition-to-a-file"></a>若要将应用程序定义导出到文件  
  
1.  在元数据对象窗格中，右键单击**Customer_Order**节点，并单击**导出**。  
  
2.  将文件另存 Customer_Order.xml。  
  
## <a name="next-steps"></a>后续步骤  
 现在必须创建 SharePoint 应用程序以从 SAP 系统中检索数据。 请参阅[步骤 3:创建 SharePoint 应用程序检索的数据从 SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)有关的说明。  
  
## <a name="see-also"></a>请参阅  
 [教程 1:在 SharePoint 站点上提供来自 SAP 系统的数据](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)